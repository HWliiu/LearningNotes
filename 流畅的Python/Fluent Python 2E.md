## Fluent Python 2E
- [Fluent Python 2E](#fluent-python-2e)
	- [CHAPTER 1 The Python Data Model](#chapter-1-the-python-data-model)
		- [Overview of Special Methods](#overview-of-special-methods)
		- [Collection API](#collection-api)
	- [CHAPTER 2 An Array of Sequences](#chapter-2-an-array-of-sequences)
		- [tuples more efficient than lists](#tuples-more-efficient-than-lists)
		- [Unpacking with * in Function Calls and Sequence Literals](#unpacking-with--in-function-calls-and-sequence-literals)
		- [Pattern Matching](#pattern-matching)
	- [CHAPTER 3 Dictionaries and Sets](#chapter-3-dictionaries-and-sets)
		- [Modern dict Syntax](#modern-dict-syntax)
		- [Pattern Matching with Mappings](#pattern-matching-with-mappings)
		- [Inconsistent Usage of \_\_missing__ in the Standard Library](#inconsistent-usage-of-__missing__-in-the-standard-library)
		- [collections.OrderedDict](#collectionsordereddict)
		- [Practical Consequences of How dict Works](#practical-consequences-of-how-dict-works)
		- [Set Operations](#set-operations)
	- [CHAPTER 4 Unicode Text Versus Bytes](#chapter-4-unicode-text-versus-bytes)
	- [CHAPTER 5 Data Class Builders](#chapter-5-data-class-builders)
		- [Main Features](#main-features)
		- [Classic Named Tuples](#classic-named-tuples)
		- [Typed Named Tuples](#typed-named-tuples)
		- [Field Options](#field-options)
		- [Post-init Processing](#post-init-processing)
		- [Typed Class Attributes](#typed-class-attributes)
		- [Initialization Variables That Are Not Fields](#initialization-variables-that-are-not-fields)
		- [Pattern Matching Class Instances](#pattern-matching-class-instances)
		- [Soapbox](#soapbox)
	- [CHAPTER 6 Object References, Mutability, and Recycling](#chapter-6-object-references-mutability-and-recycling)
	- [CHAPTER 7 Functions as First-Class Objects](#chapter-7-functions-as-first-class-objects)
		- [The Nine Flavors of Callable Objects](#the-nine-flavors-of-callable-objects)
		- [Positional-Only Parameters](#positional-only-parameters)
	- [CHAPTER 8 Type Hints in Functions](#chapter-8-type-hints-in-functions)
		- [Using None as a Default](#using-none-as-a-default)
		- [Types Are Defined by Supported Operations](#types-are-defined-by-supported-operations)
		- [Types Usable in Annotations](#types-usable-in-annotations)
		- [The Any Type](#the-any-type)
		- [Subtype-of versus consistent-with](#subtype-of-versus-consistent-with)
		- [Simple Types and Classes](#simple-types-and-classes)
		- [Optional and Union Types](#optional-and-union-types)
		- [Generic Collections](#generic-collections)
		- [Tuple Types](#tuple-types)
		- [Generic Mappings](#generic-mappings)
		- [Abstract Base Classes](#abstract-base-classes)
		- [The fall of the numeric tower](#the-fall-of-the-numeric-tower)
		- [Iterable](#iterable)
		- [Parameterized Generics and TypeVar](#parameterized-generics-and-typevar)
		- [Static Protocols](#static-protocols)
		- [Callable](#callable)
		- [NoReturn](#noreturn)
		- [Annotating Positional Only and Variadic Parameters](#annotating-positional-only-and-variadic-parameters)
		- [Imperfect Typing and Strong Testing](#imperfect-typing-and-strong-testing)
	- [CHAPTER 9 Decorators and Closures](#chapter-9-decorators-and-closures)
		- [Memoization with functools.cache](#memoization-with-functoolscache)
		- [Using lru_cache](#using-lru_cache)
		- [Function singledispatch](#function-singledispatch)
		- [A Class-Based Clock Decorator](#a-class-based-clock-decorator)
	- [CHAPTER 10 Design Patterns with First-Class Functions](#chapter-10-design-patterns-with-first-class-functions)
	- [CHAPTER 11 A Pythonic Object](#chapter-11-a-pythonic-object)
	- [CHAPTER 12 Special Methods for Sequences](#chapter-12-special-methods-for-sequences)
		- [A Slice-Aware \_\_getitem__](#a-slice-aware-__getitem__)
	- [CHAPTER 13 Interfaces, Protocols, and ABCs](#chapter-13-interfaces-protocols-and-abcs)
		- [The Typing Map](#the-typing-map)
		- [Two Kinds of Protocols](#two-kinds-of-protocols)
		- [Python Digs Sequences](#python-digs-sequences)
		- [Goose Typing](#goose-typing)
		- [ABCs in the Standard Library](#abcs-in-the-standard-library)
		- [Structural Typing with ABCs](#structural-typing-with-abcs)
		- [Static Protocols](#static-protocols-1)
		- [Runtime Checkable Static Protocols](#runtime-checkable-static-protocols)
		- [Limitations of Runtime Protocol Checks](#limitations-of-runtime-protocol-checks)
		- [Best Practices for Protocol Design](#best-practices-for-protocol-design)
		- [Extending a Protocol](#extending-a-protocol)
		- [The numbers ABCs and Numeric Protocols](#the-numbers-abcs-and-numeric-protocols)
		- [Typing Approaches in Popular Languages](#typing-approaches-in-popular-languages)
	- [CHAPTER 14 Inheritance: For Better or for Worse](#chapter-14-inheritance-for-better-or-for-worse)
		- [The super() Function](#the-super-function)
		- [Mixin Classes](#mixin-classes)
	- [CHAPTER 15 More About Type Hints](#chapter-15-more-about-type-hints)
		- [Overloaded Signatures](#overloaded-signatures)
		- [TypedDict](#typeddict)
		- [Type Casting](#type-casting)
		- [Reading Type Hints at Runtime](#reading-type-hints-at-runtime)
		- [Problems with Annotations at Runtime](#problems-with-annotations-at-runtime)
		- [Implementing a Generic Class](#implementing-a-generic-class)
		- [Basic Jargon for Generic Types](#basic-jargon-for-generic-types)
		- [Variance](#variance)
		- [Variance Review](#variance-review)
		- [Implementing a Generic Static Protocol](#implementing-a-generic-static-protocol)
	- [CHAPTER 16 Operator Overloading](#chapter-16-operator-overloading)
		- [Overloading + for Vector Addition](#overloading--for-vector-addition)
		- [Overloading * for Scalar Multiplication](#overloading--for-scalar-multiplication)
		- [Using @ as an Infix Operator](#using--as-an-infix-operator)
	- [CHAPTER 17 Iterators, Generators, and Classic Coroutines](#chapter-17-iterators-generators-and-classic-coroutines)
		- [Subgenerators with yield from](#subgenerators-with-yield-from)
		- [Generic Iterable Types](#generic-iterable-types)
		- [Classic Coroutines](#classic-coroutines)
		- [Generic Type Hints for Classic Coroutines](#generic-type-hints-for-classic-coroutines)
	- [CHAPTER 18 with, match, and else Blocks](#chapter-18-with-match-and-else-blocks)
		- [Context Managers and with Blocks](#context-managers-and-with-blocks)
		- [The contextlib Utilities](#the-contextlib-utilities)
		- [Using @contextmanager](#using-contextmanager)
	- [CHAPTER 19 Concurrency Models in Python](#chapter-19-concurrency-models-in-python)
		- [A Bit of Jargon](#a-bit-of-jargon)
		- [Processes, Threads, and Python’s Infamous GIL](#processes-threads-and-pythons-infamous-gil)
		- [A Concurrent Hello World](#a-concurrent-hello-world)
		- [Supervisors Side-by-Side](#supervisors-side-by-side)
		- [The Real Impact of the GIL](#the-real-impact-of-the-gil)
		- [A Homegrown Process Pool](#a-homegrown-process-pool)
	- [CHAPTER 20 Concurrent Executors](#chapter-20-concurrent-executors)
		- [Downloading with concurrent.futures](#downloading-with-concurrentfutures)
		- [Where Are the Futures?](#where-are-the-futures)
		- [Multicore Prime Checker Redux](#multicore-prime-checker-redux)
	- [CHAPTER 21 Asynchronous Programming](#chapter-21-asynchronous-programming)
		- [A Few Definitions](#a-few-definitions)
		- [An asyncio Example: Probing Domains](#an-asyncio-example-probing-domains)
		- [Guido’s Trick to Read Asynchronous Code](#guidos-trick-to-read-asynchronous-code)
		- [New Concept: Awaitable](#new-concept-awaitable)
		- [Downloading with asyncio and HTTPX](#downloading-with-asyncio-and-httpx)
		- [The Secret of Native Coroutines: Humble Generators](#the-secret-of-native-coroutines-humble-generators)
		- [Asynchronous Context Managers](#asynchronous-context-managers)
		- [Using asyncio.as_completed and a Thread](#using-asyncioas_completed-and-a-thread)
		- [Throttling Requests with a Semaphore](#throttling-requests-with-a-semaphore)
		- [Making Multiple Requests for Each Download](#making-multiple-requests-for-each-download)
		- [Delegating Tasks to Executors](#delegating-tasks-to-executors)
		- [Asynchronous Iteration and Asynchronous Iterables](#asynchronous-iteration-and-asynchronous-iterables)
		- [Asynchronous Generator Functions](#asynchronous-generator-functions)
		- [Experimenting with Python’s async console](#experimenting-with-pythons-async-console)
		- [Asynchronous generators as context managers](#asynchronous-generators-as-context-managers)
		- [Asynchronous generators versus native coroutines](#asynchronous-generators-versus-native-coroutines)
		- [Async Comprehensions and Async Generator Expressions](#async-comprehensions-and-async-generator-expressions)
		- [Asynchronous comprehensions](#asynchronous-comprehensions)
		- [async Beyond asyncio: Curio](#async-beyond-asyncio-curio)
		- [Type Hinting Asynchronous Objects](#type-hinting-asynchronous-objects)
	- [CHAPTER 22 Dynamic Attributes and Properties](#chapter-22-dynamic-attributes-and-properties)
		- [Caching Properties with functools](#caching-properties-with-functools)
	- [CHAPTER 23 Attribute Descriptors](#chapter-23-attribute-descriptors)
		- [Automatic Naming of Storage Attributes](#automatic-naming-of-storage-attributes)
	- [CHAPTER 24 Class Metaprogramming](#chapter-24-class-metaprogramming)
		- [type: The Built-In Class Factory](#type-the-built-in-class-factory)
		- [Introducing \_\_init_subclass__](#introducing-__init_subclass__)
		- [Why \_\_init_subclass__ Cannot Configure \_\_slots__](#why-__init_subclass__-cannot-configure-__slots__)
		- [Enhancing Classes with a Class Decorator](#enhancing-classes-with-a-class-decorator)
		- [What Happens When: Import Time Versus Runtime](#what-happens-when-import-time-versus-runtime)
		- [How a Metaclass Customizes a Class](#how-a-metaclass-customizes-a-class)
		- [Modern Features Simplify or Replace Metaclasses](#modern-features-simplify-or-replace-metaclasses)
		- [A Metaclass Hack with \_\_prepare__](#a-metaclass-hack-with-__prepare__)
		- [Wrapping Up](#wrapping-up)
### CHAPTER 1 The Python Data Model
![](assets/Pasted%20image%2020220807233618.png)

#### Overview of Special Methods
- Most of these methods will be covered throughout the book, including the most recent additions: asynchronous special methods such as \_\_anext__ (added in Python 3.5), and the class customization hook, \_\_init_subclass__ (from Python 3.6).
- ![](assets/Pasted%20image%2020220807233640.png)
- ![](assets/Pasted%20image%2020220807233658.png)
- ![](assets/Pasted%20image%2020220807233719.png)

#### Collection API
![](assets/Pasted%20image%2020220807234259.png)

---
### CHAPTER 2 An Array of Sequences
![](assets/Pasted%20image%2020220807235858.png)

- ![](assets/Pasted%20image%2020220808000529.png)
#### tuples more efficient than lists
![](assets/Pasted%20image%2020220808001254.png)
#### Unpacking with * in Function Calls and Sequence Literals
![](assets/Pasted%20image%2020220808001600.png)
#### Pattern Matching
![](assets/Pasted%20image%2020220808002512.png)
- **Sequence** 
	- ![](assets/Pasted%20image%2020220808074759.png)
	- Sequence patterns may be written as tuples or lists or any combination of nested tuples and lists, but it makes no difference which syntax you use: in a sequence pat‐ tern, square brackets and parentheses mean the same thing.
	- A sequence pattern can match instances of most actual or virtual subclasses of collec tions.abc.Sequence, with the exception of str, bytes, and bytearray.
	- ![](assets/Pasted%20image%2020220808082807.png)
	- In the standard library, these types are compatible with sequence patterns:
		![](assets/Pasted%20image%2020220808082838.png)
	- Unlike unpacking, patterns don’t destructure iterables that are not sequences (such as iterators).
	- The _ symbol is special in patterns: it matches any single item in that position, but it is never bound to the value of the matched item. Also, the _ is the only variable that can appear more than once in a pattern.
	- ![](assets/Pasted%20image%2020220808083341.png]]![[Pasted%20image%2020220808083404.png)
	- ![](assets/Pasted%20image%2020220808084319.png)
	- ![](assets/Pasted%20image%2020220808084537.png)
	- ![](assets/Pasted%20image%2020220808084659.png)

- **Mapping** 
	- ![](assets/Pasted%20image%2020220808075448.png)
	- In contrast with sequence patterns, mapping patterns succeed on partial matches.
	- There is no need to use \*\*extra to match extra key-value pairs, but if you want to capture them as a dict, you can prefix one variable with \*\*. It must be the last in the pattern, and \*\*_ is forbidden because it would be redundant. A simple example:
	- ![](assets/Pasted%20image%2020220808080015.png)
	- ![](assets/Pasted%20image%2020220808080207.png)
- **Pattern Matching Class Instances**
	- *Simple Class Patterns*
		- ![](assets/Pasted%20image%2020220808090705.png)
	- *Keyword Class Patterns*
		- ![](assets/Pasted%20image%2020220808092934.png]] ![[Pasted%20image%2020220808093042.png)
	- *Positional Class Patterns*
		- ![](assets/Pasted%20image%2020220808093911.png]]![[Pasted%20image%2020220808093954.png]]![[Pasted%20image%2020220808094011.png)

---
### CHAPTER 3 Dictionaries and Sets
![](assets/Pasted%20image%2020220808100257.png)

#### Modern dict Syntax
- **Unpacking Mappings**
![](assets/Pasted%20image%2020220808100815.png)
- **Merging Mappings with |**
![](assets/Pasted%20image%2020220808101045.png)

#### Pattern Matching with Mappings
[[#Pattern Matching]]

#### Inconsistent Usage of \_\_missing__ in the Standard Library
![](assets/Pasted%20image%2020220808102445.png)

#### collections.OrderedDict
![](assets/Pasted%20image%2020220808102725.png)

#### Practical Consequences of How dict Works
- Key ordering is preserved as a side effect of a more compact memory layout for dict in CPython 3.6, which became an official language feature in 3.7.
- To save memory, avoid creating instance attributes outside of the \_\_init__ method.
![](assets/Pasted%20image%2020220808105521.png)
- ![](assets/Pasted%20image%2020220808105631.png)

#### Set Operations
![](assets/Pasted%20image%2020220808110343.png)

---
### CHAPTER 4 Unicode Text Versus Bytes
**None**

---
### CHAPTER 5 Data Class Builders
![](assets/Pasted%20image%2020220808112756.png)

- Python offers a few ways to build a simple class that is just a collection of fields, with little or no extra functionality. That pattern is known as a “data class”.
- This chapter covers three different class builders that you may use as shortcuts to write data classes:
![](assets/Pasted%20image%2020220808112941.png)
- ![](assets/Pasted%20image%2020220808113344.png)
- The data class builders covered in this chapter provide the necessary \_\_init__, \_\_repr__, and \_\_eq__ methods automatically, as well as other useful features.
- ![](assets/Pasted%20image%2020220808113742.png)
- Here is a Coordinate class built with namedtuple:![](assets/Pasted%20image%2020220808113901.png)
- The newer typing.NamedTuple provides the same functionality, adding a type anno‐ tation to each field:![](assets/Pasted%20image%2020220808113934.png)
- ![](assets/Pasted%20image%2020220808114103.png)
- Since Python 3.6, typing.NamedTuple can also be used in a class statement, This is much more readable, and makes it easy to override methods or add new ones.![](assets/Pasted%20image%2020220808114600.png)
- ![](assets/Pasted%20image%2020220808114725.png)
- In the \_\_init__ method generated by `typing.NamedTuple`, the fields appear as parameters in the same order they appear in the class statement.
- The `dataclass` decorator reads the variable annotations and auto‐ matically generates methods for your class.![](assets/Pasted%20image%2020220808115131.png)

#### Main Features 
- ![](assets/Pasted%20image%2020220808115554.png)
- ![](assets/Pasted%20image%2020220808115706.png)

#### Classic Named Tuples 
- A named tuple offers a few attributes and methods in addition to those inherited from the tuple![](assets/Pasted%20image%2020220808120807.png)
- Since Python 3.7, namedtuple accepts the defaults keyword-only argument provid‐ ing an iterable of N default values for each of the N rightmost fields of the class.![](assets/Pasted%20image%2020220808121258.png)

#### Typed Named Tuples 
- Classes built by typing.NamedTuple don’t have any methods beyond those that col lections.namedtuple also generates—and those that are inherited from tuple.
- The only difference is the presence of the \_\_annotations__ class attribute.![](assets/Pasted%20image%2020220808142508.png)
- In the context of type hints, None is not the NoneType singleton, but an alias for NoneType itself.
- *The Meaning of Variable Annotations*
	- The `a` survives only as an annotation. It doesn’t become a class attribute because no value is bound to it. The b and c are stored as class attributes because they are bound to values.![](assets/Pasted%20image%2020220808145617.png]]![[Pasted%20image%2020220808145631.png)
	- The a and b class attributes are descriptors. The c attribute is just a plain class attribute with the value 'spam'. The nt object has the a and b attributes as expected; it doesn’t have a c attribute, but Python retrieves it from the class, as usual.![](assets/Pasted%20image%2020220808145703.png]]![[Pasted%20image%2020220808145722.png]]![[Pasted%20image%2020220808150041.png)
	- There is no attribute named a in DemoDataClass, because the a attribute will only exist in instances of DemoDataClass. It will be a public attribute that we can get and set, unless the class is frozen. But b and c exist as class attributes, with b holding the default value for the b instance attribute, while c is just a class attribute that will not be bound to the instances.![](assets/Pasted%20image%2020220808150312.png)
- #### More About @dataclass
 ![](assets/Pasted%20image%2020220808151538.png)
 
 #### Field Options
 - The instance fields you declare will become parameters in the generated \_\_init__.
 - Python does not allow parameters without defaults after parameters with defaults, therefore after you declare a field with a default value, all remaining fields must also have default values.
 - Mutable default values are a common source of bugs for beginning Python developers.
 - To prevent bugs, @data class rejects the class definition in Example 5-13.![](assets/Pasted%20image%2020220808162934.png)
 - instead of a literal list, the default value is set by calling the dataclasses.field function with default_factory=list.![](assets/Pasted%20image%2020220808163302.png)
 - The default_factory parameter lets you provide a function, class, or any other call‐ able, which will be invoked with zero arguments to build a default value each time an instance of the data class is created.
 - This way, each instance of ClubMember will have its own list—instead of all instances sharing the same list from the class, which is rarely what we want and is often a bug.
 - ![](assets/Pasted%20image%2020220808163441.png)
 - The default_factory is likely to be the most common option of the field function, but there are several others, listed in Table 5-3.![](assets/Pasted%20image%2020220808163728.png]]![[Pasted%20image%2020220808163741.png)

#### Post-init Processing
- When \_\_post_init__ method exists, @dataclass will add code to the generated \_\_init__ to call \_\_post_init__ as the last step.
- Common use cases for \_\_post_init__ are validation and computing field values based on other fields.
*TODO*

#### Typed Class Attributes
- To code a class variable with a type hint, we need to use a pseudotype named typ ing.ClassVar, which leverages the generics [] notation to set the type of the variable and also declare it a class attribute.
```python
all_handles: ClassVar[set[str]] = set()
```
That type hint is saying: all_handles is a class attribute of type set-of-str, with an empty set as its default value.
- The @dataclass decorator doesn’t care about the types in the annotations, except in two cases, and this is one of them: if the type is ClassVar, an instance field will not be generated for that attribute.
- The other case where the type of the field is relevant to @dataclass is when declaring init-only variables, our next topic.

#### Initialization Variables That Are Not Fields 
- Sometimes you may need to pass arguments to \_\_init__ that are not instance fields.
- To declare an argument like that, the dataclasses module provides the pseudotype Init Var, which uses the same syntax of typing.ClassVar.
- ![](assets/Pasted%20image%2020220808164737.png)
*TODO*

*TODO remain*

#### Pattern Matching Class Instances 
[[#Pattern Matching]]

#### Soapbox
![](assets/Pasted%20image%2020220808170704.png]]![[Pasted%20image%2020220808170743.png)

---
### CHAPTER 6 Object References, Mutability, and Recycling
![](assets/Pasted%20image%2020220808171343.png)

---
### CHAPTER 7 Functions as First-Class Objects
![](assets/Pasted%20image%2020220808182017.png)

#### The Nine Flavors of Callable Objects 
![](assets/Pasted%20image%2020220808183440.png)

#### Positional-Only Parameters
- To define a function requiring positional-only parameters, use / in the parameter list.![](assets/Pasted%20image%2020220808184029.png)


---
### CHAPTER 8 Type Hints in Functions 
![](assets/Pasted%20image%2020220808185246.png)

#### Using None as a Default
![](assets/Pasted%20image%2020220808193902.png)
![](assets/Pasted%20image%2020220808193825.png)

#### Types Are Defined by Supported Operations
- There are many definitions of the concept of type in the literature. Here we assume that type is a set of values and a set of functions that one can apply to these values.
- In practice, it’s more useful to consider the set of supported operations as the defin‐ ing characteristic of a type.
- For example, from the point of view of applicable operations, what are the valid types for x in the following function?![](assets/Pasted%20image%2020220808194808.png)
- Duck typing: Objects have types, but variables (including parameters) are untyped. In practice, it doesn’t matter what the declared type of the object is, only what operations it actually supports.
- Nominal typing: the type checker only cares about the source code where variables (including parameters) are annotated with type hints.

#### Types Usable in Annotations 
![](assets/Pasted%20image%2020220808200639.png)

#### The Any Type
- Any accepts values of every type—and the most specialized type, supporting every possible operation.

#### Subtype-of versus consistent-with
- subtype-of: Given a class T1 and a subclass T2, then T2 is subtype-of T1.(the Liskov Substitution Principle—LSP)
- consistent-with: In a gradual type system, there is another relationship: consistent-with, which applies wherever subtype-of applies, with special provisions for type Any. ![](assets/Pasted%20image%2020220808202028.png)

#### Simple Types and Classes 
- Simple types like int, float, str, and bytes may be used directly in type hints. Con‐ crete classes from the standard library, external packages, or user defined—French Deck, Vector2d, and Duck—may also be used in type hints.
- Abstract base classes are also useful in type hints. We’ll get back to them as we study collection types.
- ![](assets/Pasted%20image%2020220808202731.png)

#### Optional and Union Types 
- The construct Optional[str] is actually a shortcut for Union[str, None]
- ![](assets/Pasted%20image%2020220808203138.png)
- If possible, avoid creating functions that return Union types, as they put an extra bur‐ den on the user—forcing them to check the type of the returned value at runtime to know what to do with it.
- ![](assets/Pasted%20image%2020220808203626.png)
- Union[] requires at least two types. Nested Union types have the same effect as a flattened Union. So this type hint: Union[A, B, Union[C, D, E]] is the same as: Union[A, B, C, D, E]
- Union is more useful with types that are not consistent among themselves. For exam‐ ple: Union[int, float] is redundant because int is consistent-with float. If you just use float to annotate the parameter, it will accept int values as well.

#### Generic Collections 
- Generic types can be declared with type parameters to specify the type of the items they can handle.
- The annotations stuff: list and stuff: list[Any] mean the same thing: stuff is a list of objects of any type.
- ![](assets/Pasted%20image%2020220808204050.png)
- ![](assets/Pasted%20image%2020220808204303.png)
- ![](assets/Pasted%20image%2020220808204637.png]]![[Pasted%20image%2020220808204954.png)

#### Tuple Types 
- There are three ways to annotate tuple types:
- `# type: ignore` stops Mypy from reporting that the package doesn’t have type hints.  
- **Tuples as records**
	 - If you’re using a tuple as a record, use the tuple built-in and declare the types of the fields within []. For example, the type hint would be `tuple[str, float, str]` to accept a tuple ('Shanghai', 24.28, 'China').
- **Tuples as records with named fields**
	- To annotate a tuple with many fields, or specific types of tuple your code uses in many places, I highly recommend using typing.NamedTuple, as seen in Chapter 5. Example 8-12 shows a variation of Example 8-11 with NamedTuple.
	- ![](assets/Pasted%20image%2020220808210204.png)
- **Tuples as immutable sequences**
	- To annotate tuples of unspecified length that are used as immutable lists, you must specify a single type, followed by a comma and ...
	- For example, tuple[int, ...] is a tuple with int items.
	- The ellipsis indicates that any number of elements >= 1 is acceptable. There is no way to specify fields of different types for tuples of arbitrary length.
	- The annotations stuff: tuple[Any, ...] and stuff: tuple mean the same thing: stuff is a tuple of unspecified length with objects of any type.

#### Generic Mappings
![](assets/Pasted%20image%2020220808212122.png)
- Generic mapping types are annotated as MappingType[KeyType, ValueType].
- ![](assets/Pasted%20image%2020220808211225.png)
-  ==TODO== walrus operator :=

#### Abstract Base Classes
- Using abc.Mapping allows the caller to provide an instance of dict, defaultdict, ChainMap, a UserDict subclass, or any other type that is a subtype-of Mapping.
- Mypy would reject a UserDict or an instance of a class derived from it, because UserDict is not a subclass of dict; they are siblings. Both are subclasses of abc.MutableMapping.
- The return value of a function is always a concrete object, so the return type hint should be a concrete type.

#### The fall of the numeric tower
- ![](assets/Pasted%20image%2020220808212519.png)
- Those ABCs work perfectly well for runtime type checking, but they are not sup‐ ported for static type checking.
- The “Numeric Tower” section of PEP 484 rejects the numbers ABCs and dictates that the built-in types complex, float, and int should be treated as special cases, as explained in “int Is Consistent-With complex” on page 269.
- ![](assets/Pasted%20image%2020220808212756.png)

#### Iterable
- ![](assets/Pasted%20image%2020220808213237.png)
- ![](assets/Pasted%20image%2020220808213435.png)
- *abc.Iterable versus abc.Sequence*
	- Like Sequence, Iterable is best used as a parameter type. It’s too vague as a return type. A function should be more precise about the concrete type it returns.

#### Parameterized Generics and TypeVar
- A parameterized generic is a generic type, written as list[T], where T is a type vari‐ able that will be bound to a specific type with each usage. This allows a parameter type to be reflected on the result type.
- ![](assets/Pasted%20image%2020220808214253.png)
- ![](assets/Pasted%20image%2020220808214840.png)
- When it first appears in the signature, the type parameter T can be any type. The sec‐ ond time it appears, it will mean the same type as the first.
- *Restricted TypeVar:* TypeVar accepts extra positional arguments to restrict the type parameter.![](assets/Pasted%20image%2020220808215310.png)
- *Bounded TypeVar:* In Example 8-18, we have `bound=Hashable`, which means the type parameter may be Hashable or any subtype of it.![](assets/Pasted%20image%2020220808215719.png)
- To summarize:
	- A restricted type variable will be set to one of the types named in the TypeVar declaration.
	- A bounded type variable will be set to the inferred type of the expression—as long as the inferred type is consistent-with the boundary declared in the bound= keyword argument of TypeVar.
- The typing.TypeVar constructor has other optional parameters—covariant and con travariant—that we’ll cover in Chapter 15, “Variance” on page 544.
- The AnyStr predefined type variable: The typing module includes a predefined TypeVar named AnyStr. It’s defined like this: `AnyStr = TypeVar('AnyStr', bytes, str)`

#### Static Protocols
- a protocol is a typing.Protocol subclass defining an interface that a type checker can verify. Both kinds of protocols are covered in Chapter 13.
- a protocol type is defined by specifying one or more methods, and the type checker verifies that those methods are imple‐ mented where that protocol type is required.
- In Python, a protocol definition is written as a typing.Protocol subclass. However, classes that implement a protocol don’t need to inherit, register, or declare any rela‐ tionship with the class that defines the protocol. It’s up to the type checker to find the available protocol types and enforce their usage.
- ![](assets/Pasted%20image%2020220808221615.png)
- *TODO*

#### Callable 
- the collections.abc module provides the Callable type, available in the typ ing module for those not yet using Python 3.9. A Callable type is parameterized like this:
```python
Callable[[ParamType1, ParamType2], ReturnType]
```
- There is no syntax to annotate optional or keyword argument types. The documentation of typing.Callable says “such function types are rarely used as callback types.” If you need a type hint to match a function with a flexible signature, replace the whole parameter list with ...—like this: `Callable[..., ReturnType]`.
- Variance in Callable types(协变、逆变)
	- covariant: `Callable[[], int]` is subtype-of `Callable[[], float]`—as int is subtype-of float. This means that Callable is covariant on the return type because the subtype-of relationship of the types `int` and `float` is in the same direction as the relationship of the Callable types that use them as return types.
	- contravariant: In the parameterized Callable type the relationship is reversed: Callable[[float], None] is subtype-of Callable[[int], None]. (本来是需要一个可以处理int类型参数的函数的，现在给了一个可以处理float类型参数的函数，那么这个函数也可以胜任原来的工作)

#### NoReturn
- This is a special type used only to annotate the return type of functions that never return.
- ![](assets/Pasted%20image%2020220808232848.png)

#### Annotating Positional Only and Variadic Parameters
![](assets/Pasted%20image%2020220808233447.png)
- Note the type hint \*content: str for the arbitrary positional parameters; this means all those arguments must be of type str. The type of the content local variable in the function body will be tuple[str, ...].
- Arbitrary keyword arguments is \*\*attrs: str in this example, therefore the type of attrs inside the function will be dict[str, str]. For a type hint like \*\*attrs: float, the type of attrs in the function would be dict[str, float].
- If the attrs parameter must accept values of different types, you’ll need to use a Union[] or Any: \*\*attrs: Any.
- The PEP 484 convention is to prefix each positional-only parameter name with two underscores.![](assets/Pasted%20image%2020220808234411.png)

#### Imperfect Typing and Strong Testing
![](assets/Pasted%20image%2020220808234619.png)

---
### CHAPTER 9 Decorators and Closures
![](assets/Pasted%20image%2020220809232710.png)

#### Memoization with functools.cache
![](assets/Pasted%20image%2020220809233636.png]]![[Pasted%20image%2020220809233741.png]]![[Pasted%20image%2020220809233949.png]]![[Pasted%20image%2020220809234239.png)

#### Using lru_cache
- The functools.cache decorator is actually a simple wrapper around the older func tools.lru_cache function, which is more flexible and compatible with Python 3.8 and earlier versions.
- ![](assets/Pasted%20image%2020220809234400.png)

#### Function singledispatch
![](assets/Pasted%20image%2020220809234935.png]]![[Pasted%20image%2020220809234958.png]]![[Pasted%20image%2020220809235746.png]]![[Pasted%20image%2020220809235856.png)

#### A Class-Based Clock Decorator
![](assets/Pasted%20image%2020220810000625.png)


---
### CHAPTER 10 Design Patterns with First-Class Functions
![](assets/Pasted%20image%2020220810000913.png)
![](assets/Pasted%20image%2020220810002021.png)

---
### CHAPTER 11 A Pythonic Object
![](assets/Pasted%20image%2020220810002903.png)


---
### CHAPTER 12 Special Methods for Sequences
![](assets/Pasted%20image%2020220810075131.png)

![](assets/Pasted%20image%2020220810082014.png)

#### A Slice-Aware \_\_getitem__
![](assets/Pasted%20image%2020220810082259.png)
The operator.index() function calls the \_\_index__ special method. The function and the special method were defined in PEP 357—Allowing Any Object to be Used for Slicing, proposed by Travis Oliphant to allow any of the numerous types of inte‐ gers in NumPy to be used as indexes and slice arguments. The key difference between operator.index() and int() is that the former is intended for this specific purpose. For example, int(3.14) returns 3, but operator.index(3.14) raises TypeError because a float should not be used as an index.

---
![](assets/Pasted%20image%2020220810084653.png)


---
### CHAPTER 13 Interfaces, Protocols, and ABCs
![](assets/Pasted%20image%2020220810085948.png)

#### The Typing Map
![](assets/Pasted%20image%2020220810091306.png)

#### Two Kinds of Protocols
- Dynamic protocol: The informal protocols Python always had. Dynamic protocols are implicit, defined by convention, and described in the documentation.
- Static protocol: A protocol as defined by PEP 544—Protocols: Structural subtyping (static duck typing), since Python 3.8. A static protocol has an explicit definition: a typing.Protocol subclass.
- There are two key differences between them:
	- An object may implement only part of a dynamic protocol and still be useful; but to fulfill a static protocol, the object must provide every method declared in the protocol class, even if your program doesn’t need them all.
	- Static protocols can be verified by static type checkers, but dynamic protocols can’t.
- Both kinds of protocols share the essential characteristic that a class never needs to declare that it supports a protocol by name, i.e., by inheritance.

#### Python Digs Sequences
![](assets/Pasted%20image%2020220810093001.png)

#### Goose Typing 
- Subclassing from ABCs to make it explict that you are implementing a previously defined interface.
- Runtime type checking using ABCs instead of concrete classes as the second argument for isinstance and issubclass.

#### ABCs in the Standard Library 
- For callable detection, the `callable(obj)` built-in function is more convenient than `insinstance(obj, Callable)`.
- If insinstance(obj, Hashable) returns False, you can be certain that obj is not hashable. But if the return is True, it may be a false positive.![](assets/Pasted%20image%2020220810102653.png)

#### Structural Typing with ABCs
- \_\_subclasshook__ allows ABCs to support structural typing.
- For ABCs that you and I may write, a \_\_subclasshook__ would be even less depend‐ able. I am not ready to believe that any class named Spam that implements or inherits load, pick, inspect, and loaded is guaranteed to behave as a Tombola. It’s better to let the programmer affirm it by subclassing Spam from Tombola, or registering it with Tombola.register(Spam).

#### Static Protocols
- ![](assets/Pasted%20image%2020220810110717.png)

#### Runtime Checkable Static Protocols
- When defining a typing.Protocol subclass, you can use the @runtime_checkable decorator to make that protocol sup‐ port isinstance/issubclass checks at runtime.
- This works because typing.Proto col is an ABC, therefore it supports the \_\_subclasshook__.
- ![](assets/Pasted%20image%2020220810124235.png)
- ![](assets/Pasted%20image%2020220810143320.png)

#### Limitations of Runtime Protocol Checks 
![](assets/Pasted%20image%2020220810144421.png]]Type hinting complex.\_\_float__ on typeshed would not solve this problem because Python’s runtime generally ignores type hints—and can’t access the typeshed stub files anyway.![[Pasted%20image%2020220810144525.png)
![](assets/Pasted%20image%2020220810144744.png)

#### Best Practices for Protocol Design
- Use plain names for protocols that represent a clear concept (e.g., Iterator, Container). 
- Use SupportsX for protocols that provide callable methods (e.g., SupportsInt, SupportsRead, SupportsReadSeek).
- Use HasX for protocols that have readable and/or writable attributes or getter/ setter methods (e.g., HasItems, HasFileno).

#### Extending a Protocol
![](assets/Pasted%20image%2020220810153019.png)

#### The numbers ABCs and Numeric Protocols 
![](assets/Pasted%20image%2020220810153213.png)
- Sadly, the numeric tower was not designed for static type checking. The root ABC— numbers.Number—has no methods, so if you declare x: Number, Mypy will not let you do arithmetic or call any methods on x.
- A good place to look for typing solutions is the typeshed project. As part of the Python standard library, the statistics module has a corresponding statistics.pyi stub file with type hints for on typeshed. There you’ll find the following definitions, which are used to annotate several functions:![](assets/Pasted%20image%2020220810154108.png)That approach is correct, but limited. It does not support numeric types outside of the standard library, which the numbers ABCs do support at runtime—when the numeric types are registered as virtual subclasses.
- The main takeaways for this section are:
	- The numbers ABCs are fine for runtime type checking, but unsuitable for static typing.
	- The numeric static protocols SupportsComplex, SupportsFloat, etc. work well for static typing, but are unreliable for runtime type checking when complex numbers are involved.

#### Typing Approaches in Popular Languages
![](assets/Pasted%20image%2020220810155313.png)


---
### CHAPTER 14 Inheritance: For Better or for Worse
![](assets/Pasted%20image%2020220810160027.png)

#### The super() Function
- Recommended way:![](assets/Pasted%20image%2020220810160755.png)
- You may have seen code that doesn’t use super(), but instead calls the method directly on the superclass, like this:![](assets/Pasted%20image%2020220810160835.png)
- It is useful to review how we had to call it in Python 2, because the old signature with two argu‐ ments is revealing:![](assets/Pasted%20image%2020220810161045.png) Both arguments of super are now optional. The Python 3 bytecode compiler auto‐ matically provides them by inspecting the surrounding context when super() is invoked in a method.
- Whether you or the compiler provides those arguments, the super() call returns a dynamic proxy object that finds a method (such as \_\_setitem__ in the example) in a superclass of the type parameter, and binds it to the object_or_type, so that we don’t need to pass the receiver (self) explicitly when invoking the method.
- In Python 3, you can still explicitly provide the first and second arguments to super(). 3 But they are needed only in special cases, such as skipping over part of the MRO for testing or debugging, or for working around undesired behavior in a superclass.

#### Mixin Classes 
- ![](assets/Pasted%20image%2020220810162225.png)
- Since every method ot UpperCaseMixin calls super(), this mixin depends on a sibling class that implements or inherits methods with the same signature.
- In practice, that means mixins must appear first in the tuple of base classes in a class declaration.
- ![](assets/Pasted%20image%2020220810162655.png)



---
### CHAPTER 15 More About Type Hints 
![](assets/Pasted%20image%2020220809000100.png)

#### Overloaded Signatures
![](assets/Pasted%20image%2020220809074049.png)

#### TypedDict
![](assets/Pasted%20image%2020220809085355.png)

![](assets/Pasted%20image%2020220809083624.png)
- At first glance, typing.TypedDict may seem like a data class builder, similar to typing.NamedTuple.
- The syntactic similarity is misleading. TypedDict is very different. It exists only for the benefit of type checkers, and has no runtime effect.
- TypedDict provides two things: 
• Class-like syntax to annotate a dict with type hints for the value of each “field.” 
• A constructor that tells the type checker to expect a dict with the keys and values as specified.
- At runtime, a TypedDict constructor such as BookDict is a placebo: it has the same effect as calling the dict constructor with the same arguments.
- The fact that BookDict creates a plain dict also means that: 
• The “fields” in the pseudoclass definition don’t create instance attributes. 
• You can’t write initializers with default values for the “fields.” 
• Method definitions are not allowed.

- ![](assets/Pasted%20image%2020220809084124.png]]![[Pasted%20image%2020220809084138.png)

- ![](assets/Pasted%20image%2020220809085845.png]]![[Pasted%20image%2020220809085927.png)

#### Type Casting
![](assets/Pasted%20image%2020220809091131.png)

#### Reading Type Hints at Runtime
- Note that the annotations are evaluated by the interpreter at import time, just as parameter default values are also evaluated.
- That’s why the values in the annotations are the Python classes str and int, and not the strings 'str' and 'int'.

#### Problems with Annotations at Runtime
- The increased use of type hints raised two problems: 
• Importing modules uses more CPU and memory when many type hints are used. 
• Referring to types not yet defined requires using strings instead of actual types.
- ![](assets/Pasted%20image%2020220809092751.png)
- Writing forward referencing type hints as strings is the standard and required practice as of Python 3.10. Static type checkers were designed to deal with that issue from the beginning.
- The typing module includes three functions and a class categorized as Introspection helpers, the most important being typing.get_type_hints.
- get_type_hints(obj, globals=None, locals=None, include_extras=False) […] : This is often the same as obj.\_\_annotations__. In addition, forward references encoded as string literals are handled by evaluating them in globals and locals namespaces. […]![](assets/Pasted%20image%2020220809093024.png)
- PEP 563—Postponed Evaluation of Annotations was approved to make it unneces‐ sary to write annotations as strings, and to reduce the runtime costs of type hints. This PEP proposes changing function annotations and variable annotations so that they are no longer evaluated at function definition time. Instead, they are preserved in annotations in string form. ![](assets/Pasted%20image%2020220809114933.png]]![[Pasted%20image%2020220809114906.png]]![[Pasted%20image%2020220809093304.png]]The typing.get_type_hints function is able to resolve many type hints![[Pasted%20image%2020220809093326.png)That’s the recommended way to read type hints at runtime.

#### Implementing a Generic Class
![](assets/Pasted%20image%2020220809102008.png)
![](assets/Pasted%20image%2020220809102026.png)

![](assets/Pasted%20image%2020220809102540.png)

#### Basic Jargon for Generic Types
![](assets/Pasted%20image%2020220809102454.png)

#### Variance 
- Invariant: Python mutable collection types—such as list and set—are invariant.
- Covariance: the subtype relationship of the parameterized dispensers varies in the same direction as the subtype relationship of the type parameters.![](assets/Pasted%20image%2020220809104604.png)
- ![](assets/Pasted%20image%2020220809105029.png]]![[Pasted%20image%2020220809105045.png)

#### Variance Review
- **Invariant types**
	- A generic type L is invariant when there is no supertype or subtype relationship between two parameterized types, regardless of the relationship that may exist between the actual parameters.
	- In other words, if L is invariant, then L[A] is not a supertype or a subtype of L[B]. They are inconsistent in both ways.
	- As mentioned, Python’s mutable collections are invariant by default. The list type is a good example: list[int] is not consistent-with list[float] and vice versa.
	- In general, if a formal type parameter appears in type hints of method arguments, and the same parameter appears in method return types, that parameter must be invariant to ensure type safety when updating and reading from the collection.
- **Covariant types**
	- Covariant generic types follow the subtype relationship of the actual type parameters.
	- Immutable containers can be covariant. For example, this is how the typing.Frozen Set class is documented as a covariant with a type variable using the conventional name T_co: class `FrozenSet(frozenset, AbstractSet[T_co])`
	- Iterators are another example of covariant generics: they are not read-only collections like a frozenset, but they only produce output.
	- Callable types are covariant on the return type for a similar reason.
- **Contravariant types**
	- Contravariant generic types reverse the subtype relationship of the actual type parameters.
	- A contravariant container is usually a write-only data structure, also known as a “sink.” There are no examples of such collections in the standard library, but there are a few types with contravariant type parameters.
	- Callable[[ParamType, …], ReturnType] is contravariant on the parameter types, but covariant on the ReturnType.
	- In addition, Generator, Coroutine, and AsyncGenerator have one contravariant type parameter.
	- For the present discussion about variance, the main point is that the contravariant formal parameter defines the type of the arguments used to invoke or send data to the object, while different covariant formal parameters define the types of outputs produced by the object—the yield type or the return type, depending on the object.

#### Implementing a Generic Static Protocol
- The Python 3.10 standard library provides a few generic static protocols. One of them is SupportsAbs![](assets/Pasted%20image%2020220809111905.png)


---
### CHAPTER 16 Operator Overloading
![](assets/Pasted%20image%2020220810170740.png)

#### Overloading + for Vector Addition 
![](assets/Pasted%20image%2020220810171144.png)
![](assets/Pasted%20image%2020220810172518.png)

#### Overloading * for Scalar Multiplication
![](assets/Pasted%20image%2020220810172546.png)

#### Using @ as an Infix Operator
![](assets/Pasted%20image%2020220810173356.png)
![](assets/Pasted%20image%2020220810172928.png)



---
### CHAPTER 17 Iterators, Generators, and Classic Coroutines
![](assets/Pasted%20image%2020220810182030.png)

#### Subgenerators with yield from
![](assets/Pasted%20image%2020220810193444.png)

#### Generic Iterable Types
- Iterator types don’t appear as often as Iterable types, but they are also simple to write.![](assets/Pasted%20image%2020220810193859.png)
- Note that the type Iterator is used for generators coded as functions with yield, as well as iterators written “by hand” as classes with \_\_next__.
- There is also a collec tions.abc.Generator type that we can use to annotate generator objects, but it is needlessly verbose for generators used as iterators.
- When checked with Mypy, reveals that the Iterator type is really a simplified special case of the Generator type.![[

![](assets/Pasted%20image%2020220810194658.png)abc.Iterator[str] is consistent-with abc.Generator[str, None, None]. Iterator[T] is a shortcut for Generator[T, None, None]. Both annotations mean “a generator that yields items of type T, but that does not consume or return values.”

#### Classic Coroutines
![](assets/Pasted%20image%2020220810194950.png)
- There are two different ways to annotate tuples with type hints:![](assets/Pasted%20image%2020220810195202.png)Something similar happens with generators. They are commonly used as iterators, but they can also be used as coroutines.
- A coroutine is really a generator function, created with the yield keyword in its body. And a coroutine object is physically a generator object. Despite sharing the same underlying implementation in C, the use cases of generators and coroutines in Python are so different that there are two ways to type hint them:![](assets/Pasted%20image%2020220810195351.png)
- The Generator type has the same type parameters as typing.Coroutine: `Coroutine[YieldType, SendType, ReturnType]`.
- `collections.abc.Coroutine` (generic since Python 3.9) are intended to anno‐ tate only native coroutines, not classic coroutines.
- In practice, productive work with coroutines requires the support of a specialized framework. That is what asyncio provided for classic coroutines way back in Python 3.3. With the advent of native coroutines in Python 3.5, the Python core developers are gradually phasing out support for classic coroutines in asyncio. But the underly‐ ing mechanisms are very similar. The async def syntax makes native coroutines eas‐ ier to spot in code, which is a great benefit. Inside, native coroutines use await instead of yield from to delegate to other coroutines. Chapter 21 is all about that.

#### Generic Type Hints for Classic Coroutines
- Here is how typing.Generator was declared in the typing.py module of Python 3.6:![](assets/Pasted%20image%2020220810201710.png)From the type variables in the formal parameters, we see that YieldType and Return Type are covariant, but SendType is contravariant.


---
### CHAPTER 18 with, match, and else Blocks
![](assets/Pasted%20image%2020220810202950.png)

#### Context Managers and with Blocks
![](assets/Pasted%20image%2020220810203829.png)

#### The contextlib Utilities
- nullcontext: A context manager that does nothing, to simplify conditional logic around objects that may not implement a suitable context manager. It serves as a standin when conditional code before the with block may or may not provide a con‐ text manager for the with statement—added in Python 3.7.
- AbstractContextManager: An ABC that formalizes the context manager interface, and makes it a bit easier to create context manager classes by subclassing—added in Python 3.6.
- With Python 3.7, contextlib added AbstractAsyncContextManager, @asynccontext manager, and AsyncExitStack. They are similar to the equivalent utilities without the async part of the name, but designed for use with the new async with statement, covered in Chapter 21.

#### Using @contextmanager
![](assets/Pasted%20image%2020220810205010.png]]![[Pasted%20image%2020220810205026.png)
A little-known feature of @contextmanager is that the generators decorated with it can also be used as decorators themselves.5 That happens because @contextmanager is implemented with the contextlib.ContextDecorator class.![](assets/Pasted%20image%2020220810205105.png)


---
### CHAPTER 19 Concurrency Models in Python
![](assets/Pasted%20image%2020220810213637.png)

#### A Bit of Jargon
![](assets/Pasted%20image%2020220810215602.png]]![[Pasted%20image%2020220810221154.png]]![[Pasted%20image%2020220810221210.png)

#### Processes, Threads, and Python’s Infamous GIL
![](assets/Pasted%20image%2020220810221635.png]]![[Pasted%20image%2020220810222301.png)
![](assets/Pasted%20image%2020220810222917.png)

#### A Concurrent Hello World
- **Spinner with Threads** ![](assets/Pasted%20image%2020220811152421.png]]![[Pasted%20image%2020220811152448.png]]![[Pasted%20image%2020220811152504.png)(线程同步对象的相关概念看threading.py源码，Lock-->RLock-->Condition-->Semaphore, Event, Barrier-->Timer)
- **Spinner with Processes**![](assets/Pasted%20image%2020220811152650.png]]one challenge when converting from threads to processes is how to communicate between processes that are isolated by the operating system and can’t share Python objects. This means that objects crossing process boundaries have to be serialized and deserialized, which cre‐ ates overhead. In Example 19-3, the only data that crosses the process boundary is the Event state, which is implemented with a low-level OS semaphore in the C code underlying the multiprocessing module.![[Pasted%20image%2020220811152832.png)
- **Spinner with Coroutines**
	- It is the job of OS schedulers to allocate CPU time to drive threads and processes. In contrast, coroutines are driven by an application-level event loop that manages a queue of pending coroutines, drives them one by one, monitors events triggered by I/O operations initiated by coroutines, and passes control back to the corresponding coroutine when each event happens.
	- The event loop and the library coroutines and the user coroutines all execute in a single thread. Therefore, any time spent in a coroutine slows down the event loop—and all other coroutines.
	- ![](assets/Pasted%20image%2020220811162224.png]]![[Pasted%20image%2020220811162309.png]]![[Pasted%20image%2020220811162325.png)
	- Python code using asyncio has only one flow of execution, unless you’ve explicitly started additional threads or processes. That means only one coroutine executes at any point in time. Concurrency is achieved by control passing from one coroutine to another.
	- ![](assets/Pasted%20image%2020220811162954.png)

#### Supervisors Side-by-Side
![](assets/Pasted%20image%2020220811163822.png]]![[Pasted%20image%2020220811163843.png)

#### The Real Impact of the GIL
- Answer for threading: The spinner is controlled by a secondary thread, so it continues spinning while the primality test is computed by the main thread. Because Python suspends the running thread every 5ms (by default), making the GIL available to other pending threads. Therefore, the main thread running is_prime is interrupted every 5ms, allowing the secondary thread to wake up and iterate once through the for loop, until it calls the wait method of the done event, at which time it will release the GIL. The main thread will then grab the GIL, and the is_prime computation will proceed for another 5ms.
- Answer for asyncio:![](assets/Pasted%20image%2020220811170733.png]]![[Pasted%20image%2020220811170753.png)

#### A Homegrown Process Pool
![](assets/Pasted%20image%2020220811181521.png)
![](assets/Pasted%20image%2020220811190131.png]]![[Pasted%20image%2020220811190210.png]]![[Pasted%20image%2020220811190417.png]]![[Pasted%20image%2020220811190436.png)


---
### CHAPTER 20 Concurrent Executors
![](assets/Pasted%20image%2020220811210208.png]]![[Pasted%20image%2020220811210225.png)

![](assets/Pasted%20image%2020220811211520.png)

#### Downloading with concurrent.futures
![](assets/Pasted%20image%2020220811212816.png]]![[Pasted%20image%2020220811220608.png]]![[Pasted%20image%2020220811220712.png)

#### Where Are the Futures?
![](assets/Pasted%20image%2020220811223053.png)
![](assets/Pasted%20image%2020220811223113.png)

#### Multicore Prime Checker Redux
![](assets/Pasted%20image%2020220811225114.png]]![[Pasted%20image%2020220811225127.png)
![](assets/Pasted%20image%2020220811225623.png)


---
### CHAPTER 21 Asynchronous Programming
![](assets/Pasted%20image%2020220811232544.png)

![](assets/Pasted%20image%2020220811232604.png)

#### A Few Definitions
![](assets/Pasted%20image%2020220811233046.png)

#### An asyncio Example: Probing Domains
![](assets/Pasted%20image%2020220811235944.png]]![[Pasted%20image%2020220812000005.png]]![[Pasted%20image%2020220812000022.png)
![](assets/Pasted%20image%2020220812000038.png)

#### Guido’s Trick to Read Asynchronous Code
![](assets/Pasted%20image%2020220812000852.png]]![[Pasted%20image%2020220812002436.png)

#### New Concept: Awaitable
- The `for` keyword works with iterables. The `await` keyword works with awaitables.
- As an end user of asyncio, these are the awaitables you will see on a daily basis:
	- A ==native coroutine object==, which you get by calling a native coroutine function 
	- An ==asyncio.Task==, which you usually get by passing a coroutine object to asyn cio.create_task()
- When implementing asynchronous libraries or contributing to asyncio itself, you may also deal with these lower-level awaitables:
	- An object with an \_\_await__ method that returns an iterator; for example, an asyncio.Future instance (asyncio.Task is a subclass of asyncio.Future)
	- Objects written in other languages using the Python/C API with a tp_as_async.am_await function, returning an iterator (similar to \_\_await__ method)

#### Downloading with asyncio and HTTPX
![](assets/Pasted%20image%2020220812084725.png]]![[Pasted%20image%2020220812084746.png]]![[Pasted%20image%2020220812084806.png]]![[Pasted%20image%2020220812084824.png)

#### The Secret of Native Coroutines: Humble Generators
![](assets/Pasted%20image%2020220812091125.png)
- Under the hood, the asyncio event loop makes the .send calls that drive your coroutines, and your coroutines await on other coroutines, including library coroutines. As mentioned, `await` borrows most of its implementation from `yield from`, which also makes .send calls to drive coroutines.
- The await chain eventually reaches a low-level awaitable, which returns a generator that the event loop can drive in response to events such as timers or network I/O. The low-level awaitables and generators at the end of these await chains are implemented deep into the libraries, are not part of their APIs, and may be Python/C extensions.
- Using functions like asyncio.gather and asyncio.create_task, you can start mul‐ tiple concurrent await channels, enabling concurrent execution of multiple I/O oper‐ ations driven by a single event loop, in a single thread.

#### Asynchronous Context Managers
PEP 492—Coroutines with async and await syntax introduced the async with statement, which works with asynchronous context managers: objects implementing the \_\_aenter__ and \_\_aexit__ methods as coroutines. The \_\_aenter__ and \_\_aexit__ methods returning await‐ ables—usually in the form of coroutine objects.
![](assets/Pasted%20image%2020220812095444.png)
![](assets/Pasted%20image%2020220812095558.png)

#### Using asyncio.as_completed and a Thread
![](assets/Pasted%20image%2020220812125456.png]]![[Pasted%20image%2020220812125512.png)Since Python 3.9, the asyncio.to_thread coroutine makes it easy to delegate file I/O to a thread pool provided by asyncio. If you need to support Python 3.7 or 3.8, “Dele‐ gating Tasks to Executors” on page 797 shows how to add a couple of lines to do it.
![](assets/Pasted%20image%2020220812145740.png]]![[Pasted%20image%2020220812145800.png]]![[Pasted%20image%2020220812145951.png)
(asyncio.as_completed 会立刻返回不会等待，迭代其返回的迭代器时可能会等待，且其返回的顺序是按完成的时间而不是原来的列表顺序)
![](assets/Pasted%20image%2020220812151201.png)

#### Throttling Requests with a Semaphore
![](assets/Pasted%20image%2020220812144040.png)

#### Making Multiple Requests for Each Download
![](assets/Pasted%20image%2020220812152219.png)

![](assets/Pasted%20image%2020220812152634.png]]![[Pasted%20image%2020220812152647.png)
Much better than nested callbacks!

#### Delegating Tasks to Executors
- In Python, if you’re not careful, file I/O can seriously degrade the perfor‐ mance of asynchronous applications, because reading and writing to storage in the main thread blocks the event loop.
- As mentioned before, the asyncio.to_thread was added in Python 3.9. If you need to support 3.7 or 3.8, then replace that single line with the lines in Example 21-10.
- ![](assets/Pasted%20image%2020220812154959.png)
- The newer asyncio.to_thread function is easier to use and more flexible, as it also accepts keyword arguments.
- A common pattern in asynchronous APIs is to wrap blocking calls that are imple‐ mentation details in coroutines using run_in_executor internally. That way, you provide a consistent interface of coroutines to be driven with await, and hide the threads you need to use for pragmatic reasons.
- The main reason to pass an explict Executor to loop.run_in_executor is to employ a ProcessPoolExecutor if the function to execute is CPU intensive, so that it runs in a different Python process, avoiding contention for the GIL.
- ![](assets/Pasted%20image%2020220812160011.png)

#### Asynchronous Iteration and Asynchronous Iterables
- `async with` works with objects implementing the \_\_aenter__ and \_\_aexit__ methods returning awaitables—usually in the form of coroutine objects.
- Similarly, `async for` works with `asynchronous iterables`: objects that implement \_\_aiter__. However, \_\_aiter__ must be a regular method—not a coroutine method —and it must return an `asynchronous iterator`.
- An `asynchronous iterator` provides an \_\_anext__ coroutine method that returns an awaitable—often a coroutine object. They are also expected to implement \_\_aiter__, which usually returns self.
(eg: range(10)是Iterable对象，iter(range(10))是Iterator对象，Genertor是Iterator的子类;
for in后接的如果是Iterable对象，则迭代iter函数返回的新Iterator对象，如果接的是Iterator对象，则迭代iter函数返回的self)

#### Asynchronous Generator Functions
- You can implement an asynchronous iterator by writing a class with \_\_anext__ and \_\_aiter__, but there is a simpler way: write a function declared with async def and use yield in its body.
- ![](assets/Pasted%20image%2020220812194952.png]]![[Pasted%20image%2020220812195305.png)
- ![](assets/Pasted%20image%2020220812195321.png)

#### Experimenting with Python’s async console
- Since Python 3.8, you can run the interpreter with the -m asyncio command-line option to get an “async REPL”: a Python console that imports asyncio, provides a running event loop, and accepts await, async for, and async with at the top-level prompt—which otherwise are syntax errors when used outside of native coroutines.
- ![](assets/Pasted%20image%2020220812200549.png]]![[Pasted%20image%2020220812200602.png)

#### Asynchronous generators as context managers
![](assets/Pasted%20image%2020220812202101.png]]![[Pasted%20image%2020220812202115.png)

#### Asynchronous generators versus native coroutines
![](assets/Pasted%20image%2020220812202715.png)

#### Async Comprehensions and Async Generator Expressions
- The only construct defined by PEP 530 that can appear outside an async def body is an asynchronous generator expression.
- ![](assets/Pasted%20image%2020220812203413.png)
- To summarize: an asynchronous generator expression can be defined anywhere in your program, but it can only be consumed inside a native coroutine or asynchro‐ nous generator function.

#### Asynchronous comprehensions
![](assets/Pasted%20image%2020220812232733.png]]![[Pasted%20image%2020220812232952.png)
![](assets/Pasted%20image%2020220812233608.png)

#### async Beyond asyncio: Curio
- Python’s async/await language constructs are not tied to any specific event loop or library.
- ![](assets/Pasted%20image%2020220812234155.png)
- *TODO*

#### Type Hinting Asynchronous Objects
- The return type of a native coroutine describes what you get when you await on that coroutine, which is the type of the object that appears in the return statements in the body of the native coroutine function.![](assets/Pasted%20image%2020220812235048.png)
- ![](assets/Pasted%20image%2020220812235211.png]]![[Pasted%20image%2020220812235225.png)
- I want to highlight three aspects of those generic types.
	- First: they are all covariant on the first type parameter, which is the type of the items yielded from these objects.
	- Second: AsyncGenerator and Coroutine are contravariant on the second to last parameter. That’s the type of the argument of the low-level .send() method that the event loop calls to drive asynchronous generators and coroutines. As such, it is an “input” type.
	- Third: AsyncGenerator has no return type, in contrast with typing.Generator


---
### CHAPTER 22 Dynamic Attributes and Properties
![](assets/Pasted%20image%2020220813074250.png)

#### Caching Properties with functools
- Python 3.8 introduced the @functools.cached_property decorator, which is thread safe.
- The functools.cached_property decorator caches the result of the method in an instance attribute with the same name.
- The @cached_property decorator does not create a full-fledged property, it creates a nonoverriding descriptor.
- ![](assets/Pasted%20image%2020220813091951.png)
- The @cached_property documentation recommends an alternative solution that we can use: stacking @property and @cache decorators. (The order is important: @property goes on top)


---
### CHAPTER 23 Attribute Descriptors
![](assets/Pasted%20image%2020220813093255.png)

#### Automatic Naming of Storage Attributes
- ![](assets/Pasted%20image%2020220813104254.png)
- To avoid retyping the attribute name in the descriptor instances, we’ll implement \_\_set_name__ to set the storage_name of each Quantity instance. The \_\_set_name__ special method was added to the descriptor protocol in Python 3.6. The interpreter calls \_\_set_name__ on each descriptor it finds in a class body—if the descriptor implements it.
- More precisely, \_\_set_name__ is called by type.\_\_new__—the constructor of objects representing classes.
- ![](assets/Pasted%20image%2020220813104743.png]]![[Pasted%20image%2020220813104850.png)


---
### CHAPTER 24 Class Metaprogramming
![](assets/Pasted%20image%2020220813115401.png)

#### type: The Built-In Class Factory
![](assets/Pasted%20image%2020220813120601.png)
![](assets/Pasted%20image%2020220813120614.png)

#### Introducing \_\_init_subclass__
- Both \_\_init_subclass__ and \_\_set_name__ were proposed in PEP 487—Simpler customization of class creation.
- In Chapter 5, we saw that `typing.NamedTuple` and `@dataclass` let programmers use the class statement to specify attributes for a new class, which is then enhanced by the class builder with the automatic addition of essential methods like \_\_init__, \_\_repr__, \_\_eq__, etc.
- Both of these class builders read type hints in the user’s class statement to enhance the class. Those type hints also allow static type checkers to validate code that sets or gets those attributes. However, NamedTuple and @dataclass do not take advantage of the type hints for attribute validation at runtime. The Checked class in the next example does.
- ![](assets/Pasted%20image%2020220813155709.png)

![](assets/Pasted%20image%2020220813184137.png)
![](assets/Pasted%20image%2020220813185115.png]]![[Pasted%20image%2020220813185200.png)
![](assets/Pasted%20image%2020220813185524.png]]![[Pasted%20image%2020220813185934.png]]![[Pasted%20image%2020220813190113.png]]![[Pasted%20image%2020220813190134.png)

![](assets/Pasted%20image%2020220813185057.png)
![](assets/Pasted%20image%2020220813185459.png)
![](assets/Pasted%20image%2020220813190000.png)

#### Why \_\_init_subclass__ Cannot Configure \_\_slots__
The \_\_slots__ attribute is only effective if it is one of the entries in the class name‐ space passed to type.\_\_new__. Adding \_\_slots__ to an existing class has no effect. Python invokes \_\_init_subclass__ only after the class is built—by then it’s too late to configure \_\_slots__. A class decorator can’t configure \_\_slots__ either, because it is applied even later than \_\_init_subclass__.

#### Enhancing Classes with a Class Decorator
![](assets/Pasted%20image%2020220813191536.png]]![[Pasted%20image%2020220813191557.png)

#### What Happens When: Import Time Versus Runtime
- At import time, the interpreter:
	- Parses the source code of a .py module in one pass from top to bottom. This is when a SyntaxError may occur.
	- Compiles the bytecode to be executed.
	- Executes the top-level code of the compiled module.
- If there is an up-to-date .pyc file available in the local \_\_pycache__, parsing and compiling are skipped because the bytecode is ready to run.
- The import statement can trigger all sorts of “runtime” behavior.
- “Import time” can also happen deep inside runtime, because the import statement and the \_\_import__() built-in can be used inside any regular function.
- ![](assets/Pasted%20image%2020220813192715.png)
- The implementation of type.\_\_new__ is written in C.
- Python’s built-in type.\_\_new__ has created the Klass object and calls \_\_set_name__ on each descriptor instance of descriptor classes that provide that method.
- type.\_\_new__ then calls \_\_init_subclass__ on the superclass of Klass, passing Klass as the single argument.
- When type.\_\_new__ returns the class object, Python applies the decorator.
- A base class with \_\_init_subclass__ and a class decorator are powerful tools, but they are limited to working with a class already built by type.\_\_new__ under the covers.
- (具体单步调试24-class-metaprog/evaltime/evaldemo_meta.py)

#### How a Metaclass Customizes a Class
- When you implement MetaKlass.\_\_new__, you can inspect and change those argu‐ ments before passing them to super().\_\_new__, which will eventually call type.\_\_new__ to create the new class object.
- After super().\_\_new__ returns, you can also apply further processing to the newly created class before returning it to Python. Python then calls Super Klass.\_\_init_subclass__, passing the class you created, and then applies a class decorator to it, if one is present. Finally, Python binds the class object to its name in the surrounding namespace—usually the global namespace of a module, if the class statement was a top-level statement.
- The most common processing made in a metaclass \_\_new__ is to add or replace items in the cls_dict—the mapping that represents the namespace of the class under con‐ struction. For instance, before calling super().\_\_new__, you can inject methods in the class under construction by adding functions to cls_dict. However, note that adding methods can also be done after the class is built, which is why we were able to do it using \_\_init_subclass__ or a class decorator.
- One attribute that you must add to the cls_dict before type.\_\_new__ runs is \_\_slots__, as discussed in “Why \_\_init_subclass__ Cannot Configure \_\_slots__” on page 921. The \_\_new__ method of a metaclass is the ideal place to configure \_\_slots__.
- ![](assets/Pasted%20image%2020220814080501.png)
- The main use case for \_\_prepare__ before Python 3.6 was to provide an OrderedDict to hold the attributes of the class under construction, so that the metaclass \_\_new__ could process those attributes in the order in which they appear in the source code of the user’s class definition. Now that dict preserves the insertion order, \_\_prepare__ is rarely needed.

#### Modern Features Simplify or Replace Metaclasses
- Class decorators: Simpler to understand than metaclasses, and less likely to cause conflicts with base classes and metaclasses.
- \_\_set_name__: Avoids the need for custom metaclass logic to automatically set the name of a descriptor.
- \_\_init_subclass__: Provides a way to customize class creation that is transparent to the end user and even simpler than a decorator—but may introduce conflicts in a complex class hierarchy.
- Built-in dict preserving key insertion order: Eliminated the #1 reason to use \_\_prepare__: to provide an OrderedDict to store the namespace of the class under construction. Python only calls \_\_prepare__ on metaclasses, so if you needed to process the class namespace in the order it appears in the source code, you had to use a metaclass before Python 3.6.
- A Class Can Only Have One Metaclass.

#### A Metaclass Hack with \_\_prepare__
- see 24-class-metaprog/autoconst/autoconst_demo.py
![](assets/Pasted%20image%2020220814085909.png)

#### Wrapping Up
Metaclasses, as well as class decorators and \_\_init_subclass__ are useful for:
• Subclass registration 
• Subclass structural validation 
• Applying decorators to many methods at once 
• Object serialization 
• Object-relational mapping 
• Object-based persistence 
• Implementing special methods at the class level 
• Implementing class features found in other languages, such as traits and aspectoriented programmin