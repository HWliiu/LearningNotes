### 鸟哥的 Linux 私房菜

- [鸟哥的 Linux 私房菜](#鸟哥的-linux-私房菜)
  - [Linux 的文件权限与目录配置](#linux-的文件权限与目录配置)
  - [Linux 文件与目录管理](#linux-文件与目录管理)
    - [重点回顾](#重点回顾)
  - [认识和学习 bash](#认识和学习-bash)
  - [学习 shell scripts](#学习-shell-scripts)
  - [Linux 账号管理与 ACL 权限设定](#linux-账号管理与-acl-权限设定)
    - [重点回顾](#重点回顾-1)
  - [磁盘配额(Quota)与进阶文件系统管理](#磁盘配额quota与进阶文件系统管理)
  - [例行性工作排程(crontab)](#例行性工作排程crontab)
  - [进程管理与 SELinux 初探](#进程管理与-selinux-初探)
    - [SELinux 初探](#selinux-初探)
  - [认识系统服务(daemons)](#认识系统服务daemons)
    - [systemd 使用的 unit 分类](#systemd-使用的-unit-分类)
    - [systemd 的配置文件放置目录](#systemd-的配置文件放置目录)
    - [systemd 的 unit 类型分类说明](#systemd-的-unit-类型分类说明)
    - [透过 systemctl 管理服务](#透过-systemctl-管理服务)
    - [systemctl 针对 service 类型的配置文件](#systemctl-针对-service-类型的配置文件)
    - [systemctl 配置文件的设定项目简介](#systemctl-配置文件的设定项目简介)
  - [认识与分析登录档](#认识与分析登录档)

---

#### Linux 的文件权限与目录配置

- 对文件来讲，权限的效能为:

  - r: 可读取此文件的实际内容，如读取文本文件的文字内容等;
  - w:可以编辑、新增或者是修改该文件的内容(但不含删除该文件);
  - x:该文件具有可以被系统执行的权限。

- 对目录来说，权限的效能为:
  - r: (read contents in directory)
  - w: (modify contents
    of directory)
  - x: (access directory)

要开放目录给任何人浏览时，应该至少也要给予 r 及 x 的权限，但 w 权限不可随便给;

在预设的条件中，cp 的来源档与目的档的权限是不同的，目的档的拥有者通常会是指令操作者本身。

---

#### Linux 文件与目录管理

**Set UID**

- SUID 权限仅对二进制程序(binary program)有效;
- 执行者对于该程序需要具有 x 的可执行权限;
  本权限仅在执行该程序的过程中有效(run-time);
- 执行者将具有该程序拥有者(owner) 的权限。

**Set GID**

- 对文件来说

  - SGID 对二进制程序有用;
  - 程序执行者对于该程序来说，需具备 x 的权限;
  - 执行者在执行的过程中将会获得该程序群组的支持!

- 对目录来说
  - 用户若对于此目录具有 r 与 x 的权限时，该用户能够进入此目录;
  - 用户在此目录下的有效群组(effective group)将会变成该目录的群组;
  - 用途:若用户在此目录下具有 w 的权限(可以新建文件)，则使用者所建立的新文件，该新文件的群组与此目录的群组相同。

**Sticky Bit**

只对目录有效

- 当用户对于此目录具有 w,x 权限，亦即具有写入的权限时;
- 当用户在该目录下建立文件或目录时，仅有自己与 root 才有权力删除该文件

**find**

![image-20210628145035367](Linux%E7%AC%94%E8%AE%B0.assets/image-20210628145035367.png)

- {}代表的是「由 find 找到的内容」，如上图所示，find 的结果会被放置到{}位置中;
- -exec
  一直到\; 是关键词，代表 find 额外动作的开始(-exec) 到结束(;)，在这中间的就是 find 指令内
  的额外动作。在本例中就是 「ls-l {}」
- 因为「;」在 bash 环境下是有特殊意义的，因此利用反斜杠来跳脱

##### 重点回顾

- 除了传统的 rwx 权限之外，在 Ext2/Ext3/Ext4/xfs 文件系统中，还可以使用 chattr 与 lsattr 设定及观察隐藏属性。常见的包括只能新增数据的+a 与完全不能更动文件的+i 属性。
- 新建文件/目录时，新文件的预设权限使用 umask 来规范。默认目录完全权限为 drwxrwxrwx，文件则为
  -rw-rw-rw-。
- 文件具有 SUID 的特殊权限时，代表当用户执行此 binary 程序时，在执行过程中用户会暂时具有程序拥有者的权限
- 目录具有 SGID 的特殊权限时，代表用户在这个目录底下新建的文件的群组都会与该目录的组名相同。
- 目录具有 SBIT 的特殊权限时，代表在该目录下用户建立的文件只有自己与 root 能够删除

---

#### 认识和学习 bash

**查询指令是否为 Bash shell 的内建命令: type**

推荐用 type -a 替代 which

**在变量的设定当中，单引号与双引号的用途有何不同?**

单引号与双引号的最大不同在于双引号仍然可以保有变量的内容，但单引号内仅能是一般字符，而不会有特殊符号。

**在指令下达的过程中，反单引号(`)这个符号代表的意义为何?**

在一串指令中，在`之内的指令将会被先执行，而其执行出来的结果将做为外部的输入信息

**export: 自定义变量转成环境变量**

环境变量会被子程序所继续引用，子程序仅会继承父程序的环境变量，子程序不会继承父程序的自定义变量

**路径与指令搜寻顺序**

1. 以相对/绝对路径执行指令，例如「/bin/ls」 或「./Is 」;
2. 由 alias 找到该指令来执行;
3. 由 bash 内建的(builtin) 指令来执行;
4. 透过$PATH 这个变量的顺序搜寻到的第一个指令来执行。

**bash 的环境配置文件**

**login 与 non-login shell**

- login shell：取得 bash 时需要完整的登入流程的，就称为 login shell。举例来说，你要由 tty1~tty6 登入，需要输入用户的账号与密码，此时取得的 bash 就称为「login shell」;
- non-login shell：取得 bash 接口的方法不需要重复登入的举动，举例来说, (1)你以 X window 登入 Linux 后，再以 X 的图形化接口启动终端机，此时那个终端接口并没有需要再次的输入账号与密码，那个 bash 的环
  境就称为 non-login shell 了。(2)你在原本的 bash 环境下再次下达 bash 这个指令，同样的也没有输入账号
  密码，那第二个 bash (子程序)也是 non-login shell。
- bash 的配置文件主要分为 login shell 与 non-login shell。login shell 主要读取/etc/profile 与~/.bash\_ profile,
  non-login shell 则仅读取~/.bashrc

**/etc/profile（login shell 才会读）**

每个使用者登入取得 bash 时一定会读取的配置文件

**~/.bashrc (non-login shell 会读)**

当取得 non-login shell 时，该 bash 配置文件仅会读取~/.bashrc

**终端机的环境设定: stty, set**

- Ctrl+ C
  终止目前的命令
- Ctrl+ D
  输入结束(EOF)， 例如邮件结束的时候;
- CtrI+ M
  就是 Enter 啦!
- Ctrl+ S
  暂停屏幕的输出
- Ctrl+ Q
  恢复屏幕的输出
- Ctrl+ U
  在提示字符下，将整列命令删除
- Ctrl+ Z
  「暂停」目前的命令
- ‘ ’ 单引号 不具有变量置换的功能(\$变为纯文本)
- “ ”
  具有变量置换的功能! (\$ 可保留相关功能)
- `` 中间为可以先执行的指令，亦可使用\$()
- ( )
  在中间为子 shell 的起始与结束
- { }
  在中间为命令区块的组合!

**数据流重导向**

1. 标准输入
   (stdin) :代码为 0，使用\<或\<\<;
2. 标准输出
   (stdout):代码为 1，使用>或>>;
3. 标准错误输出(stderr):代码为 2，使用 2>或 2>>
   ;

**将正确与错误数据通通写入同一个文件**

2>&1 或 &>

**管线命令(pipe)**

- 管线命令仅会处理 standard output,对于 standard error output
  会予以忽略
- 管线命令必须要能够接受来自前一个指令的数据成为 standard input 继续处理才行

**双向重导向**

tee [-a] file 加-a 相当于>>，不加相当于>

---

#### 学习 shell scripts

bash shell.sh 或 sh shell.sh 只要 shell.sh 有 r 的权限即可被执行

`!#/bin/bash`宣告这个文件内的语法使用 bash 的语法!
当这个程序被执行时，他就能够加载 bash 的相关环境配置文件(一般来说就是 non-login shell 的
~/.bashrc)，并且执行 bash 来使我们底下的指令能够执行!

**script 的执行方式差异(source, sh script, ./script)**

- 利用直接执行的方式来执行 script：在子程序中执行

  不论是绝对路径/相对路径还是${PATH}内，或者是利用
  bash (或 sh) 来下达脚本时，该 script 都会使用一个新的 bash 环境来执行脚本内的指令!也就是说，使用这种执行方式时，其实 script 是在子程序的 bash 内执行的！重点在于: 「 当子程序完成后,
  在子程序内的各项变量或动作将会结束而不会传回到父程序中」!

- 利用 source 或 . 来执行脚本：在父程序中执行

  shell.sh 会在父程序中执行的，因此各项动作都会在原本的 bash 内生效!这也是为啥你不注销系统而要让
  些写入~/.bashrc 的设定生效时，需要使用「source ~/.bashrc」而不能使用「bash ~/.bashrc」是一样的啊!

---

#### Linux 账号管理与 ACL 权限设定

id 命令查看用户 id 属性

**关于群组:有效与初始群组、groups, newgrp**

每个使用者可以拥有多个支持的群组

**有效群组(effective group)与初始群组(initial group)**

/etc/passwd 中的 gid 为 initial group，也就是说，当用户一-發入系统，立刻就拥有这个群组的相关权限的意思。

groups 命令查看用户 group 信息，第一个输出的群组即为有效群组(effective group)了。也就是说，我的有效群组为 dmtsai 啦~
此时，如果我以 touch 去建立一个新档，例如:「 touch test 」 ,那么这个文件的拥有者为 dmtsai ,
而且群组也是 dmtsai 的啦。通常有效群组的作用是在新建文件啦!

newgrp 命令可以切换有效群组，而且是另外以一个 shell 来提供这个功能的喔

**账号管理**

使用 useradd 这支程序在建立 Linux 上的账号时，至少会参考:

- /etc/default/useradd
- /etc/login.defs
- /etc/skel/\*

SKEL=/etc/skel:用户家目录参考基准目录

chage 命令也可以设置密码，比 passwd 更优雅，chage 有一个功能很不错喔!如果你想要让「使用者在第一次登入时，强制她们一 定要更改密码后才能够使用系统资源」，可以用 chage -d 0 username

usermod 可以在账户创建后修改用户信息

如果想要完整的将某个账号完整的移除，最好可以在下达 userdel -r username 之前，先以「find/
-user username」查出整个系统内属于 username 的文件，然后再加以删除吧!

id 这个指令则可以查询某人或自己的相关 UID/GID 等等的信息

groupadd:曾经有某些版本的教育训练手册谈到，为了让使用者的 UID/GID 成对，她们建议新建的与使用者私有群组无关的其他群组时，使用小于 1000 以下的 GID 为宜。也就是说， 如果要建立群组的话,
最好能够使用「groupadd-r 群组名」的方式来建立啦!不过，这见仁见智啦!看你自己的抉择!

**ACL 可以单纯的针对某一个使用者或某一个群组来设定特定的权限需求**

man getfacl;man setfacl

**su 与 su - 的区别**

单纯使用「su」切换成为 root 的身份，读取的变量设定方式为 non-login shell 的方式，这种方式很多原本的变量不会被改变，尤其是我们之前谈过很多次的 PATH 这个变量

若要完整的切换到新使用者的环境，必须要使用「su - username」或「su -l username」，才会连同
PATH/USER/MAIL 等变量都转成新用户的环境

**sudo**

sudo -u username 以 username 的身份执行，尤其在 username 为 nologin 时特别好用

**sudo 执行流程**

1. 当用户执行 sudo 时，系统于/etc/sudoers 文件中搜寻该使用者是否有执行 sudo 的权限;
2. 若使用者具有可执行 sudo 的权限后，便让使用者「输入用户自己的密码」来确认;
3. 若密码输入成功，便开始进行 sudo 后续接的指令(但 root 执行 sudo 时，不需要输入密码);
4. 若欲切换的身份与执行者身份相同，那也不需要输入密码。

_sudo passwd 是去改 root 的密码，要特别注意_

\#Forbid other users to modify the root password

myuser ALL=(root) !/usr/bin/passwd,/usr/bin/passwd [A-Za-z]\*, !/usr/bin/passwd root

**PAM 模块**

PAM 藉由一个与程序相同文件名的配置文件来进行一连串的认证分析需求。我们同样以 passwd 这个指令的呼叫 PAM 来说明好了。当你执行 passwd 后，这支程序呼叫 PAM 的流程是:

1. 用户开始执行/usr/bin/passwd 这支程序，并输入密码;
2. passwd 呼叫 PAM 模块进行验证;

3. PAM 模块会到/etc/pam.d/ 找寻与程序(passwd)同名的配置文件;
4. 依据/etc/pam.d/passwd 内的设定，引用相关的 PAM 模块逐步进行验证分析;
5. 将验证结果(成功、失败以及其他讯息)回传给 passwd 这支程序;
6. passwd 这支程序会根据 PAM 回传的结果决定下一个动作(重新输入新密码或者通过验证! )

![image-20210628214514620](Linux%E7%AC%94%E8%AE%B0.assets/image-20210628214514620.png)

limits.conf 可以限制用户使用资源的大小

w 可以显示比 who 更详细的信息，lastlog 可以查看用户上一次登录的时间(/var/log/lastlog)

**使用者对谈:
write, mesg, wall**

**一些账号相关的检查工具**

pwck

chpasswd: chpasswd 是个挺有趣的指令，他可以「读入未加密前的密码，并且经过加密后，将加密后的密码写入/etc/shadow 当中。」这个指令很常被使用在大量建置账号的情况中喔! passwd 已经默认加入了--stdin 的选项，因此这个 chpasswd 就变得英雄无用武之地了

##### 重点回顾

- Linux 操作系统上面，关于账号与群组，其实记录的是 UID/GID 的数字而已;
  使用者的账号/群组与 UID/GID 的对应，参考/etc/passwd 及/etc/group 两个文件
- /etc/passwd 文件结构以冒号隔开，共分为七个字段，分别是「账号名称、密码、UID、GID、全名、家目录、
  shell
- UID 只有 0 与非为 0 两种，非为 0 则为一般账号。一般账号又分为系统账号(1~999) 及可登入者账号
  (大于 1000)
  账号的密码已经移动到/etc/shadow 文件中，该文件权限为仅有 root 可以更动。该文件分为九个字段，内容为「账号名称、加密密码、密码更动日期、密码最小可变动日期、密码最大需变动日期、密码过期前警告日数、密码失效天数、账号失效日、 保留未使用
- 使用者可以支持多个群组，其中在新建文件时会影响新文件群组者，为有效群组。而写入/etc/passwd 的第四个字段者，称为初始群组。
- 与使用者建立、更改参数、删除有关的指令为: useradd, usermod, userdel 等，密码建立则为 passwd;
- 与群组建立、修改、删除有关的指令为: groupadd, groupmod, groupdel 等;
- 群组的观察与有效群组的切换分别为: groups 及 newgrp 指令;
- useradd 指令作用参考的文件有: /etc/default/useradd, /etc/login.defs, /etc/skel/等等
- 观察用户详细的密码参数，可以使用「chage -l 账号」来处理;
- 用户自行修改参数的指令有: chsh, chfn 等，观察指令则有: id, finger 等
- ACL 的功能需要文件系统有支持，CentOS 7 预设的 XFS 确实有支持 ACL 功能!
- ACL 可进行单一个人或群组的权限管理，但 ACL 的启动需要有文件系统的支持;
- ACL 的设定可使用 setfacl ，查阅则使用 getfacl;
- 身份切换可使用 su，亦可使用 sudo ，但使用 sudo 者，必须先以 visudo 设定可使用的指令;
- PAM 模块可进行某些程序的验证程序!与 PAM 模块有关的配置文件位于/etc/pam.d/_ 及/etc/security/_
- 系统上面账号登入情况的查询，可使用 w, who, last, lastlog 等;
- 在线与使用者交谈可使用 write, wall， 脱机状态下可使用 mail 传送邮件!

---

#### 磁盘配额(Quota)与进阶文件系统管理

ext 不支持文件夹 quota

---

#### 例行性工作排程(crontab)

**at 的运作方式**

我们使用 at 这个指令来产生所要运作的工作，并将这个工作以文本文件的方式写入/var/spool/at/目录内，该工作便能等待 atd 这个服务的取用与执行了。

**crontab 的运作方式**

当用户使用 crontab 这个指令来建立工作排程之后，该项工作就会被纪录到/var/spool/cron/ 里面去了，而且是以账号来作为判别的喔! 另外，cron 执行的每一项工作都会被纪录到/var/log/cron 这个登录档中，所以，如果你的 Linux 不知道有否被植入木马时，也可以搜寻一下/var/log/cron 这个登录档呢!

这个「crontab-e 」是针对使用者的 cron 来设计的，如果是「 系统的例行性任务」时，只要编辑/etc/crontab 这个文件就可以啦!有一点需要特别注意喔!那就是 crontab-e 这个 crontab 其实是
/usr/bin/crontab 这个执行档，但是/etc/crontab 可是一个「纯文本档」喔!你可以 root 的身份编辑一下这个文件哩!

基本上，cron 这个服务的最低侦测限制是「分钟」，所以「cron 会每分钟去读取一次/etc/crontab 与
/var/spool/cron 里面的数据内容」，因此，只要你编辑完/etc/crontab 这个文件,并且将他储存之后,
那么 cron 的设定就自动的会来执行了!

一般来说，crond 预设有三个地方会有执行脚本配置文件，他们分别是:

●
/etc/crontab
●
/etc/cron.d/_
● /var/spool/cron/_

run-parts 是 shell script,
run-parts 脚本会在大约 5 分钟内随机选一个时间来执行

**anacron：可唤醒停机期间的工作任务**

其实 anacron 也是每个小时被 crond 执行一次，然后 anacron 再去检测相关的排程任务有没有被执行，如果有超过期限的工作在，就执行该排程任务， 执行完毕或无须执行任何排程时，anacron 就停止了。

anacron
会去分析现在的时间与时间记录文件所记载的上次执行 anacron 的时间，
两者比较后若发现有差异，那就是在某些时刻没有进行 crontab!此时 anacron 就会开始执行未进行的 crontab 任务了!

anacron 其实是一支程序并非一个服务!这支程序在 CentOS 当中已经进入 crontab 的排程喔!同时 anacron 会每个小时被主动执行一次喔!

**anacron
的执行流程(以 cron.daily 为例):**

1. 由/etc/anacrontab 分析到 cron.daily 这项工作名称的天数为 1 天;
2. 由 /var/spool/anacron/cron.daily 取出最近一次执行 anacron 的时间戳;
3. 由上个步骤与目前的时间比较，若差异天数为 1 天以上(含 1 天)，就准备进行指令;
4. 若准备进行指令，根据/etc/anacrontab 的设定，将延迟 5 分钟;
5. 延迟时间过后，开始执行后续指令，亦即「run-parts /etc/cron.daily」这串指令;
6. 执行完毕后，anacron 程序结束。

**总结**

1. crond 会主动去读取/etc/crontab, /var/spool/cron/*, /etc/cron.d/*等配置文件,并依据[分、时、日、月、周」
   的时间设定去各项工作排程;
2. 因为/etc/cron.hourly/0anacron 这个脚本文件的缘故，主动的每小时执行 anacron，并呼叫/etc/anacrontab 的配置文件;
3. 根据/etc/anacrontab 的设定,依据每天、每周、每月去分析/etc/cron.daily/, /etc/cron.weekly/, /etc/cron.monthly/内的执行文件，以进行固定周期需要执行的指令。

---

#### 进程管理与 SELinux 初探

在 Linux 系统当中:「 触发任何一个事件时，系统都会将他定义成为一个进程，并且给予这个进程一个 ID，称为 PID，同时依据启发这个进程的用户与相关属性关系，给予这个 PID 一组有效的权限设定。」从此以后，这个 PID 能够在系统上面进行的动作，就与这个 PID 的权限有关了!

**job control**

进行工作管理的行为中，其实每个工作都是目前 bash 的子进程，亦即彼此之间是有相关性的。我们无法以 job control 的方式由 tty1 的环境去管理 tty2 的
bash!（工作号码(job number) 只与你这个 bash 环境有关）

killall -i commandname

**进程执行顺序**

PRI 值越低代表越优先。不过这个 PRI 值是由核心动态调整的，用户无法直接调整 PRI
值的。

PRI(
new
)= PRI(old) + nice

不过你要特别留意到,如果原本的 PRI 是 50, 并不是我们给予一个 nice=5 , 就会让 PRI 变成 55 喔!因为 PRI 是系统「动态」决定的，所以，虽然 nice 值是可以影响 PRI，不过，最终的 PRI 仍是要经过系统分析后才会决定的。另外，nice 值是有正负的喔，而既然 PRI 越小越早被执行，所以，当 nice 值为负值时，那么该进程就会降低 PRI 值，亦即会变的较优先被处理。此外，你必须
要留意到:

- nice 值可调整的范围为-20~19 ;
- root
  可随意调整自己或他人进程的 Nice 值，且范围为-20~19 ;
- 一般使用者仅可调整自己进程的 Nice 值，且范围仅为 0~ 19 (避免一般用户抢占系统资源);
- 一般使用者仅可将 nice 值越调越高，例如本来 nice 为 5，则未来仅能调整到大于 5;

_调整 nice 的指令：nice renice_

_nice 值可以在父进程到子进程之间传递_

**查询已开启文件或已执行进程开启之文件**

**fuser:藉由文件(或文件系统)找出正在使用该文件的进程**

fuser 可以让我们了解到某个文件(或文件系统)目前正在被哪些进程所利用

**lsof :列出被进程所开启的文件档名**

相对于 fuser 是由文件或者装置去找出使用该文件或装置的进程,反过来说，如何查出某个进程开启
或者使用的文件与装置呢?呼呼!那就是使用 lsof 哕~

**pidof :找出某支正在执行的程序的 PID**

##### SELinux 初探

SELinux 是在进行进程、文件等细部权限设定依据的一个核心模块!由于启动网络服务的也是进程，因此刚好也能够控制网络服务能否存取系统资源的一道关卡!

**SELinux 的运作模式**

- 主体(Subject):
  SELinux 主要想要管理的就是进程，因此你可以将「主体」跟本章谈到的 process 划上等号;
- 目标(Object);
  主体进程能否存取的目标资源一般就是文件系统。因此这个目标项目可以等文件系统划上等号;
- 政策(Policy):
  由于进程与文件数量庞大，因此 SELinux 会依据某些服务来制订基本的存取安全性政策。这些政策内还会有详细的规则(rule)来指定不同的服务开放某些资源的存取与否。在目前的 CentOS7.x 里面仅有提供三个主要的政策，分别是:
  - targeted:针对网络服务限制较多，针对本机限制较少，是预设的政策;
  - minimum:由 target 修订而来，仅针对选择的进程来保护!
  - mls:完整的 SELinux 限制，限制方面较为严格。
- 安全性本文(security context):
  我们刚刚谈到了主体、目标与政策面，但是主体能不能存取目标除了政策指定之外，主体与目标的安全性本文必须一致才能够顺利存取。这个安全性本文(security context)有点类似文件系统的 rwx 啦!安全性本文的内容与设定是非常重要的!如果设定错误， 你的某些服务(主体进程)就无法存取文件系统(目标资源)，
  当然就会一直出现「权限不符」的错误讯息了!

---

#### 认识系统服务(daemons)

##### systemd 使用的 unit 分类

- **平行处理所有服务，加速开机流程:**

  旧的 init 启动脚本是「一 项一项任务依序启动」的模式，因此不相依的服务也是得要一个一个的等待。systemd 就是可以让不相依的所有服务同时启动。

- **一经要求就响应的 on-demand 启动方式:**

  systemd 全部就是仅有一只 systemd 服务搭配 systemctl 指令来处理，无须其他额外的指令来支持。此外，systemd 由于常驻内存，因此任何要求
  (on-demand)都可以立即处理后续的 daemon 启动的任务。

- **服务相依性的自我检查:**

  由于 systemd 可以自定义服务相依性的检查，因此如果 B 服务是架构在 A 服务上面启动的，那当你在没有启动 A 服务的情况下仅手动启动 B 服务时，systemd 会自动帮你启动 A 服务喔!

- **依 daemon 功能分类:**

  systemd 先定义所有的服务为一个服务单位(unit)， 并将该 unit 归类到不同的服务类型(type) 去。systemd 将服务单位(unit) 区分为 service, socket, target, path, snapshot,
  timer 等多种不同的类型(type)，方便管理员的分类与记忆。

- **将多个 daemons 集合成为一个群组:**

  如同 systemV 的 init 里头有个 runlevel 的特色，systemd 亦将许多的功能集合成为一个所谓的 target 项目，这个项目主要在设计操作环境的建置， 所以是集合了许多的 daemons, 亦即是执行某个 target 就是执行好多个 daemon 的意思!

- **向下兼容旧有的 init 服务脚本:**

  基本上，systemd 是可以兼容于 init 的启动脚本的，因此，旧的 init 启动脚本也能够透过 systemd 来管理，只是更进阶的 systemd 功能就没有办法支持就是了。

虽然如此，不过 systemd 也是有些地方无法完全取代 init 的!包括:

- 在 runlevel 的对应上，大概仅有 runlevel 1,3,5 有对应到 systemd 的某些 target 类型而已,没有全部对应;
- 全部的 systemd 都用 systemctl 这个管理程序管理，而 systemctl 支持的语法有限制，不像/etc/init.d/daemon 就是纯脚本可以自定义参数，systemctl 不可自定义参数。
- 如果某个服务启动是管理员自己手动执行启动，而不是使用 systemctl 去启动的(例如你自己手动输入 crond
  以启动 crond 服务)，那么 systemd 将无法侦测到该服务，而无法进一步管理。
- systemd 启动过程中,无法与管理员透过 standard input 传入讯息!因此,自行撰写 systemd 的启动设定时,
  务必要取消互动机制~(连透过启动时传进的标准输入讯息也要避免!)

##### systemd 的配置文件放置目录

- /usr/lib/systemd/system/:每个服务最主要的启动脚本设定，有点类似以前的/etc/init.d 底下的文件;
- /run/systemd/system/:系统执行过程中所产生的服务脚本,这些脚本的优先序要比/usr/ib/systemd/system/ 高!
- /etc/systemd/system/:管理员依据主机系统的需求所建立的执行脚本，其实这个目录有点像以前
  /etc/rc.d/rc5.d/Sxx 之类的功能!执行优先序又比/run/systemd/system/ 高喔!

##### systemd 的 unit 类型分类说明

看书

##### 透过 systemctl 管理服务

**status**

- active (running):正有一只或多只程序正在系统中执行的意思。
- active (exited):仅执行一次就正常结束的服务，目前并没有任何程序在系统中执行。
- active (waiting):正在执行当中，不过还再等待其他的事件才能继续处理。
- static:这个 daemon 不可以自己启动(enable 不可)，不过可能会被其他的 enabled 的服务来唤醒(相依属性的服务)
- mask:这个 daemon 无论如何都无法被启动!因为已经被强制注销(非删除)。可透过 systemctl unmask 方式改回原本状态

很多服务彼此之间是有相依性的!cups 是一种打印服务，这个打印服务会启用 port 631 来提供网络打印机的打印功能。但是其实我们无须一直启动 631 埠口吧?因此，多了一个名为
cups.socket 的服务，这个服务可以在用户有需要打印时，才会主动唤醒
cups.service」的意思!因此，如果你仅是 disable/stop cups.service 而忘记了其他两个服务的话，那么当有用户向其他两个 cups.path, cups.socket 提出要求时，cups.service 就会被唤醒!所以，你关掉也没用!

在 service 部份用 start/stop/restart ，在 target
项目则请使用 isolate (隔离不同的操作模式)!

/etc/services 记录了端口对应的服务名称

##### systemctl 针对 service 类型的配置文件

现在我们知道服务的管理是透过 systemd，而 systemd 的配置文件大部分放置于/usr/lib/systemd/system/目录内。但是 RedHat 官方文件指出，该目录的文件主要是原本软件所提供的设定，建议不要修改!而要修改的位置应该放置于/etc/systemd/system/目录内。举例来说，如果你想要额外修改 vsftpd.service 的话，他们建议要放置到哪些地方呢?

- /usr/ib/systemd/system/vsftpd.service:官方释出的预设配置文件;
- /etc/systemd/system/vsftpd.service.d/custom.conf: 在/etc/systemd/system 底下建立与配置文件相同文件名的目录,但是要加上.d 的扩展名。然后在该目录下建立配置文件即可。另外,配置文件最好附档名取名为.conf
  较佳!在这个目录下的文件会「 累加其他设定」进入/usr/lib/systemd/system/vftpd.service 内喔!
- /etc/systemd/system/vsftpd.service.wants/\*:此目录内的文件为链接档，设定相依服务的连结。意思是启动了 vsftpd.service 之后，最好再加上这目录底下建议的服务。
- /etc/systemd/system/vsftpd.service.requires/\*: 此目录内的文件为链接档，设定相依服务的连结。意思是在启动 vsftpd.service 之前，需要事先启动哪些服务的意思。

##### systemctl 配置文件的设定项目简介

看书（重要）

getty@.service @后面是输入的参数，在getty@.service文件中通过%i 取出

**systemctl 针对 timer 的配置文件**

**优势**

- 由于所有的 systemd 的服务产生的信息都会被纪录(log)， 因此比 crond 在 debug. 上面要更清楚方便的多;

- 各项 timer 的工作可以跟 systemd 的服务相结合;

- 各项 timer 的工作可以跟 control group (cgroup,用来取代/etc/secure/limit.conf 的功能)结合，来限制该工作的资源利用

弱点：例如 systemd 的 timer 并没有 email 通知的功能(除非自己写一个),也没有类似 anacron 的一段时间内的随机取样功能(random delay)，不过，总体来说，还是挺不错的!此外，相对于 crond 最小的单位到分，systemd 是可以到秒甚至是毫秒的单位哩!相当有趣!

基本上，想要使用 systemd 的 timer 功能，你必须要有几个要件:

- 系统的 timer.target 一 定要启动
- 要有个 sname.service 的服务存在(sname 是你自己指定的名称)
- 要有个 sname.timer 的时间启动服务存在

#### 认识与分析登录档

**登录档所需相关服务与程序**

- systemd-journald.service:最主要的讯息收受者，由 systemd 提供的;
- rsyslog.service:
  主要登录系统与网络等服务的讯息;
- logrotate:主要在进行登录文件的轮替功能。

所有经由 systemd 启动的服务，如果再启动或结束的过程中发生一些问题或者是正常的讯息，就会将该讯息由 systemd-journald.service 以二进制的方式记录下来，之后再将这个讯息发送给 rsyslog.service 作进一步的记载。systemd-journald.service 的记录主要都放置于内存中，因此在存取方面效能比较好。

dpkg -L package 查看 package 的安装位置
