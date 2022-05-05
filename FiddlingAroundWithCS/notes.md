## Essence of c#
- syntactically approachable to cpp and java programmers
  - semicolons as newline terminators
  - curly braces to group blocks of code that r in the same scope
  - supporting oop
  - 0 based indexing
- strongly typed
- multi paradigm programming
- resilient and safe
  - native performance (optimal perf on any given device)
  - doesn&#39;t have memory corruption
- pen source and cross-platform (using .net 5)
- has undergone constant evolution

## code execution models:
- complied languages (native):
  - ex: c
  - tend to be strongly typed
  - type safety enforced at compile-time (can&#39;t compile code if there r any type issues)
  - manual memory management (malloc and dealloc)
  - text files (source code) in ide converted into binary language/machine code at compile time (native/platform dependant)
    - if there&#39;s a func that&#39;s called 1000 times, it only needs to be translated into machine code once
  - I AM SPEED
  - lack of portability
  - need to build code
- interpreted (dynamic)
  - ex: python
  - loosely typed
  - permissive runtime type conversion
  - automatic memory management
  - performance tradeoff (slow performance profile)
  - hard to find errors
  - starts off same (source code in ide, edit-time)
  - then everything else happens within interpreter (program that runs on target machine, generally converts high level source code into machine code on a line by line basis)
    - so if there&#39;s a func that&#39;s called 1000 times, interpreter has to translate it 1000 times
  - designs of syntax tends to limit efficiency gains that can be achieved
  - this design allows python REPL, juypter notebooks, etc
- hybrid model &quot;managed&quot; (execution engine)
  - ex: c#
  - strong typing
  - checks for type when running
    - runtime type safety
    - so u can still compile code bc it&#39;s less strict than compiled languages
    - robust safety checks
  - more automated memory management via automatic garbage collection
  - can still achieve fast performance profiles (native code performance)
  - source code is still run thru compiler, however, the output is an intermediate representation of the high level source code (ex: intermediate language/IL/assembly .dll/.exe in c#, byte code in java)
  - cannot be directly executed on compt, so u need an execution engine on target machine that then converts IL into CPU understandable machine code in JIT basis
  - machine code generation is only done the first time a given method is invoked, generated code is then cached and used for subsequent invocations
  - all steps designed for max efifciency (so machine code is generated if and only if it&#39;s needed, hence just in time)
    - in other words, if a func is never called, no time or resources r spent generating the machine code equivalent of its intermediate language representation
    - if a func is called, machine code is generated and removes itself from call chain (so for subsequent invocations of the func, it won&#39;t have to retranslate the IL into machine code again)
  - JIT compiler also assists w runtime type safety (ie. verifying types, encoding other safety checks like out of bounds array, etc)
  - allows for both efficiency and convenience

## execution engine
- .net execu engine is called common language runtime (CLR)
- ILE is the common language all .net compilers emit
- .net 5
  - cross-platform
- .net framework
  - specific to windows operating system

## .net base class libraries
- CLR provides runtime critical services (ex: JIT compilation, garbage collection)
- base class libraries (BCL) includes other utilitarian libraries that devs can use when needed
  - has clases that work with text, performs file AO, collection classes like queues, hash tables, etc
- all managed .net code shares IL so side effect of learning c# is u learn broader .net platform

## TLDR
- c# fairly approachable, strongly typed, resilient to change, has runtime type safety, is oop but also has functional features, open-source and cross platform, is general purpose
- c# code is compiled into IL assemblies
- IL is JIT compiled at runtime if/when used
- JITed code exhibits native performance
- CLR ensures runtime type safety
- BCL includes general purpose libraries and app framework functionality
