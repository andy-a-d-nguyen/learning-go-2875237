# Go

- [Go](#go)
  - [Compiled or Interpreted?](#compiled-or-interpreted)
  - [Is Go Object Oriented?](#is-go-object-oriented)
  - [What Go Doesn't Support](#what-go-doesnt-support)
  - [Essential Syntax Rules](#essential-syntax-rules)
    - [Semicolons Usually Not Needed](#semicolons-usually-not-needed)
    - [Code Blocks with Braces](#code-blocks-with-braces)
    - [Built-In Functions](#built-in-functions)
  - [Storing Data in Variables](#storing-data-in-variables)
    - [Boolean and String Types](#boolean-and-string-types)
    - [Integer Types](#integer-types)
    - [Other Numeric Types](#other-numeric-types)
    - [Complex Types](#complex-types)
    - [Math Requires Identical Types](#math-requires-identical-types)
  - [Memory Management](#memory-management)
    - [Memory Allocation](#memory-allocation)
    - [Memory Deallocation](#memory-deallocation)

## Compiled or Interpreted?

- Go is a compiled, statically typed language
- The Go tool can run a file without precompiling
- Compiled executables are OS specific
- Compiled apps contain a statically linked runtime
- No external VM needed

## Is Go Object Oriented?

- Everything is a type in Go
- Go has some object-oriented features
  - You can define custom interfaces
  - Custom types can implement one or more interfaces
  - Custom types can have function methods
  - Custom structs (data structures) can have member fields and member methods

## What Go Doesn't Support

- Type inheritance (no classes)
- Method or operator overloading
- Structured exception handling
  - No try catch keywords
  - Error objects are returned by functions that generate those errors which conditional logic can be used to examine
- Implicit numeric conversions

## Essential Syntax Rules

- Go is case sensitive
- Variable and package names are lowercase and mixed case
- Names of public fields have initial uppercase characters
- Initial uppercase character means the symbol is exported (equivalent to public in Java or C#)
- Initial lower case character means the symbol is not exported (private in Java or C#)

### Semicolons Usually Not Needed

- Line feed ends a statement; no semicolon required
- Semicolons are part of the formal language spec
- The lexer adds them as needed

### Code Blocks with Braces

- Code blocks are wrapped in braces

### Built-In Functions

- Members of builtin package
  - len(string) - returns the length of a string
  - panic(error) - stops execution; displays error message

## Storing Data in Variables

- Go is a statically typed language
- All variables have assigned types
- You can set types explicitly or implicitly

### Boolean and String Types

- Boolean values
  - bool
- String type
  - string

### Integer Types

- Fixed integer types
  - uint8
  - uint16
  - uint32
  - uint64
  - int8
  - int16
  - int32
  - int64
- Aliases can be used instead of full type names
  - byte
  - uint
  - int
  - uintptr

### Other Numeric Types

- Floating values
  - float32
  - float64
- Complex numbers
  - complex64
  - complex128

### Complex Types

- Data collections
  - Arrays
  - Slices
  - Maps
  - Structs
- Language organization
  - Funtions
  - Interfaces
  - Channels
- Data management
  - Pointers

### Math Requires Identical Types

- Numeric types don't implicitly convert
- Convert types before using
  - Wrap value in target type as function call
- FOr other operations, use math package

## Memory Management

- Memory is managed by the runtime
- The Go runtime is statically linked into the application
- Memory is allocated and deallocated automatically
- Use make() or new() to initialize maps, slices. and channels

### Memory Allocation

- The new() function
  - Allocates, but does not initialize memory
  - Results in zeroed storage, but returns a memory address
- The make() function
  - Allocates and initializes memory
  - Allocates non-zeroed storage and returns a memory address

### Memory Deallocation

- Memory is deallocated by garbage collector (GC)
- Objects out of scope or set to nil are eligible
- GC was rebuilt in Go 1.5 for very low latency