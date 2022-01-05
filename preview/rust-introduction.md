# what is Rust?

Rust is a multi-paradigm(多范式), general-purpose programming language（通用编程语言）designed for performance and safety（性能和安全）, especially safe concurrency.[12][13] Rust is syntactically similar to C++（语句构成上与 c++ 相似）,[14] but can guarantee memory safety（保证内存安全） by using a #borrow checker# to validate references.[15] Rust achieves memory safety without garbage collection（无垃圾回收机制）, and reference counting is optional（引用计数可选）.[16][17] Rust has been called a systems programming language and in addition to high-level features such as functional programming(函数式编程) it also offers mechanism（机制） for low-level memory management（底层内存管理）.

Rust was originally designed by Graydon Hoare at Mozilla Research,[18] with contributions from Dave Herman, Brendan Eich, and others.[19][20] The designers refined the language while writing the Servo experimental browser engine[21] and the Rust compiler. Rust's major influences include C++, OCaml, Haskell, and Erlang.[5] It has gained increasing use and investment in industry, by companies including Amazon, Microsoft, Facebook, Discord, and Dropbox.

Rust has been voted the "most loved programming language" in the Stack Overflow Developer Survey every year since 2016, though only used by 7% of the respondents in 2021.

# history
The language grew out of a personal project begun in 2006 by Mozilla employee Graydon Hoare.[13] Hoare has stated that the project was possibly named after rust fungi and that the name is also a substring of "robust".[23] Mozilla began sponsoring the project in 2009[13] and announced it in 2010.[24][25] The same year, work shifted from the initial compiler (written in OCaml) to an LLVM-based self-hosting compiler written in Rust（基于 LLVM 的 自主编译器，是rust 编写的，命名为 rustc）.[26] Named rustc, it successfully compiled itself in 2011.[27]

The first numbered pre-alpha release of the Rust compiler occurred in January 2012.[28] Rust 1.0, the first stable release, was released on May 15, 2015.[29][30] Following 1.0, stable point releases are delivered every six weeks, while features are developed in nightly Rust with daily releases, then tested with beta releases that last six weeks.[31][32] Every 2 to 3 years, a new Rust "Edition" is produced. This is to provide an easy reference point for changes due to the frequent nature of Rust's Train release schedule, as well as to provide a window to make breaking changes. Editions are largely compatible.[33]

Rust 编译器的第一个编号 pre-alpha 版本发生在 2012 年 1 月。 [28] Rust 1.0 是第一个稳定版本，于 2015 年 5 月 15 日发布。[29][30]在 1.0 之后，每六周发布一次稳定点版本，而功能则在每晚 Rust 中开发，每日发布，然后使用持续六周的 beta 版本进行测试。[31][32]每 2 到 3 年，就会产生一个新的 Rust “版本”。由于 Rust 的 Train 发布时间表的频繁性质，这是为了为更改提供一个简单的参考点，并提供一个窗口来进行重大更改。版本在很大程度上兼容

Along with conventional static typing, before version 0.4, Rust also supported typestates. The typestate system modeled assertions before and after program statements, through use of a special check statement. Discrepancies could be discovered at compile time, rather than at runtime, as might be the case with assertions in C or C++ code. The typestate concept was not unique to Rust, as it was first introduced in the language NIL.[34] Typestates were removed because in practice they were little used,[35] though the same functionality can be achieved by leveraging Rust's move semantics.[36]


除了传统的静态类型，在 0.4 版本之前，Rust 还支持类型状态。类型状态系统通过使用特殊的检查语句对程序语句前后的断言进行建模。可以在编译时发现差异，而不是在运行时发现，就像 C 或 C++ 代码中的断言一样。 typestate 概念并不是 Rust 独有的，因为它首先在 NIL 语言中引入。 [34]类型状态被删除是因为在实践中它们很少被使用，[35] 尽管可以通过利用 Rust 的移动语义来实现相同的功能。 [36]

The object system style changed considerably within versions 0.2, 0.3, and 0.4 of Rust. Version 0.2 introduced classes for the first time, and version 0.3 added several features, including destructors and polymorphism through the use of interfaces. In Rust 0.4, traits were added as a means to provide inheritance; interfaces were unified with traits and removed as a separate feature. Classes were also removed and replaced by a combination of implementations and structured types.[37]

在 Rust 的 0.2、0.3 和 0.4 版本中，对象系统风格发生了很大变化。 0.2 版首次引入了类，0.3 版通过使用接口添加了一些特性，包括析构函数和多态性。在 Rust 0.4 中，添加了 trait 作为提供继承的手段；接口与特征统一并作为一个单独的特性被删除。类也被删除并替换为实现和结构化类型的组合

Starting in Rust 0.9 and ending in Rust 0.11, Rust had two built-in pointer types: ~ and @, simplifying the core memory model. It reimplemented those pointer types in the standard library as Box and (the now removed) Gc.

从 Rust 0.9 开始到 Rust 0.11 结束，Rust 有两个内置的指针类型：~ 和 @，简化了核心内存模型。它将标准库中的那些指针类型重新实现为 Box 和（现已删除的）Gc。

In January 2014, before the first stable release, Rust 1.0, the editor-in-chief of Dr. Dobb's, Andrew Binstock, commented on Rust's chances of becoming a competitor to C++ and to the other up-and-coming languages D, Go, and Nim (then Nimrod). According to Binstock, while Rust was "widely viewed as a remarkably elegant language", adoption slowed because it repeatedly changed between versions.[38]

2014 年 1 月，在第一个稳定版本发布之前，Rust 1.0，Dr. Dobb's 的主编 Andrew Binstock 评论了 Rust 有可能成为 C++ 和其他新兴语言 D、Go 的竞争对手，和 Nim（然后是 Nimrod）。根据 Binstock 的说法，虽然 Rust “被广泛认为是一种非常优雅的语言”，但由于它在版本之间反复更改，所以采用速度很慢。

In August 2020, Mozilla laid off 250 of its 1,000 employees worldwide as part of a corporate restructuring caused by the long-term impact of the COVID-19 pandemic.[39][40] Among those laid off were most of the Rust team,[41][better source needed] while the Servo team was completely disbanded.[42][better source needed] The event raised concerns about the future of Rust.[43]

2020 年 8 月，作为因 COVID-19 大流行的长期影响而导致的企业重组的一部分，Mozilla 在全球范围内解雇了 1,000 名员工中的 250 名。[39][40]其中大部分被解雇的是 Rust 团队，[41][需要更好的消息来源]而 Servo 团队完全解散。[42][需要更好的消息来源] 该事件引发了对 Rust 未来的担忧。[43]

In the following week, the Rust Core Team acknowledged the severe impact of the layoffs and announced that plans for a Rust foundation were underway. The first goal of the foundation would be taking ownership of all trademarks and domain names, and also take financial responsibility for their costs.[44]

在接下来的一周，Rust 核心团队承认裁员的严重影响，并宣布 Rust 基金会的计划正在进行中。该基金会的首要目标是获得所有商标和域名的所有权，并对其成本承担财务责任。 [44]

On February 8, 2021 the formation of the Rust Foundation was officially announced by its five founding companies (AWS, Huawei, Google, Microsoft,[45][46] and Mozilla).[47][48]

2021 年 2 月 8 日，其五家创始公司（AWS、华为、谷歌、微软、[45][46] 和 Mozilla）正式宣布成立 Rust 基金会。[47][48]

On April 6, 2021, Google announced support for Rust within Android Open Source Project as an alternative to C/C++.[49]

2021 年 4 月 6 日，Google 宣布在 Android 开源项目中支持 Rust 作为 C/C++ 的替代方案。

# Features
Rust is intended to be a language for highly concurrent and highly safe systems,[51] and programming in the large, that is, creating and maintaining boundaries that preserve large-system integrity.[52] This has led to a feature set with an emphasis on safety, control of memory layout, and concurrency.

Rust 旨在成为一种用于高度并发和高度安全的系统 [51] 和大型编程的语言，即创建和维护保持大型系统完整性的边界。 [52]这导致了一个强调安全性、内存布局控制和并发性的功能集。

## Memory safety
Rust is designed to be memory safe. It does not permit null pointers, dangling pointers, or data races.[53][54][55] Data values can be initialized only through a fixed set of forms, all of which require their inputs to be already initialized.[56] To replicate pointers being either valid or NULL, such as in linked list or binary tree data structures, the Rust core library provides an option type, which can be used to test whether a pointer has Some value or None.[54] Rust has added syntax to manage lifetimes, which are checked at compile time by the borrow checker. Unsafe code can subvert some of these restrictions using the unsafe keyword.[15]

Rust 被设计为内存安全。它不允许空指针、悬空指针或数据竞争。 [53][54][55]数据值只能通过一组固定的形式进行初始化，所有这些都要求它们的输入已经被初始化。 [56]为了复制有效或 NULL 的指针，例如在链表或二叉树数据结构中，Rust 核心库提供了一个选项类型，可用于测试指针是否具有 Some 值或 None 值。 [54] Rust 添加了管理生命周期的语法，在编译时由借用检查器进行检查。不安全的代码可以使用 unsafe 关键字破坏其中的一些限制。 [15

## Memory management
Rust does not use automated garbage collection. Memory and other resources are managed through the resource acquisition is initialization convention,[57] with optional reference counting. Rust provides deterministic management of resources, with very low overhead.[58] Rust favors stack allocation of values and does not perform implicit boxing.

Rust 不使用自动垃圾收集。内存和其他资源通过资源获取进行管理是初始化约定，[57] 带有可选的引用计数。 Rust 提供资源的确定性管理，开销非常低。 [58] Rust 支持值的堆栈分配并且不执行隐式装箱。

There is the concept of references (using the & symbol), which does not involve run-time reference counting. The safety of such pointers is verified at compile time, preventing dangling pointers and other forms of undefined behavior. Rust's type system separates shared, immutable pointers of the form &T from unique, mutable pointers of the form &mut T. A mutable pointer can be coerced to an immutable pointer, but not vice versa.

有引用的概念（使用 & 符号），它不涉及运行时引用计数。在编译时验证此类指针的安全性，防止悬空指针和其他形式的未定义行为。 Rust 的类型系统将 &T 形式的共享、不可变指针与 &mut T 形式的唯一可变指针分开。可变指针可以强制转换为不可变指针，反之则不行。

## Ownership
Rust has an ownership system where all values have a unique owner, and the scope of the value is the same as the scope of the owner.[59][60] Values can be passed by immutable reference, using &T, by mutable reference, using &mut T, or by value, using T. At all times, there can either be multiple immutable references or one mutable reference (an implicit readers–writer lock). The Rust compiler enforces these rules at compile time and also checks that all references are valid.

Rust 有一个所有权系统，其中所有值都有唯一的所有者，值的范围与所有者的范围相同。 [59] [60]值可以通过不可变引用（使用 &T）、可变引用（使用 &mut T）或值（使用 T）传递。在任何时候，都可以有多个不可变引用或一个可变引用（隐式读者-写者锁）。 Rust 编译器在编译时强制执行这些规则，并检查所有引用是否有效。

## Types and polymorphism(多态性)
Rust's type system supports a mechanism called traits, inspired by type classes in the Haskell language. Traits annotate types and are used to define shared behavior between different types. For example, floats and integers both implement the Add trait because they can both be added; and any type that can be printed out as a string implements the Display or Debug traits. This facility is known as ad hoc polymorphism.

Rust 的类型系统支持一种称为特征的机制，其灵感来自 Haskell 语言中的类型类。 Traits 注释类型并用于定义不同类型之间的共享行为。例如，浮点数和整数都实现了 Add trait，因为它们都可以相加；任何可以作为字符串打印出来的类型都实现了 Display 或 Debug 特性。此功能称为临时多态性。

Rust uses type inference for variables declared with the keyword let. Such variables do not require a value to be initially assigned to determine their type. A compile time error results if any branch of code leaves the variable without an assignment.[61] Variables assigned multiple times must be marked with the keyword mut (short for mutable).

Rust 对使用关键字 let 声明的变量使用类型推断。此类变量不需要初始分配值来确定其类型。如果任何代码分支在没有赋值的情况下离开变量，则会导致编译时错误。 [61]多次分配的变量必须用关键字 mut（可变的缩写）标记。

A function can be given generic parameters, which allows the same function to be applied to different types. Generic functions can constrain the generic type to implement a particular trait or traits; for example, an "add one" function might require the type to implement "Add". This means that a generic function can be type-checked as soon as it is defined.

一个函数可以被赋予泛型参数，这允许将相同的函数应用于不同的类型。泛型函数可以约束泛型类型以实现特定的一个或多个特征；例如，“添加一个”函数可能需要类型来实现“添加”。这意味着泛型函数可以在定义后立即进行类型检查。

The implementation of Rust generics is similar to the typical implementation of C++ templates: a separate copy of the code is generated for each instantiation. This is called monomorphization and contrasts with the type erasure scheme typically used in Java and Haskell. Rust's type erasure is also available by using the keyword dyn. The benefit of monomorphization is optimized code for each specific use case; the drawback is increased compile time and size of the resulting binaries.

Rust 泛型的实现类似于 C++ 模板的典型实现：为每个实例化生成一个单独的代码副本。这称为单态化，与 Java 和 Haskell 中通常使用的类型擦除方案形成对比。 Rust 的类型擦除也可以通过使用关键字 dyn 来实现。单态化的好处是针对每个特定用例优化代码；缺点是增加了编译时间和生成的二进制文件的大小。

In Rust, user-defined types are created with the struct keyword. These types usually contains fields of data like objects or classes in other languages. The impl keyword can define methods for the struct (data and function are defined separately in a struct) or implement a trait for the structure. A trait is a contract that a structure has certain required methods implemented. Traits are used to restrict generic parameters and because traits can provide a struct with more methods than the user defined. For example, the trait Iterator requires that the next method be defined for the type. Once the next method is defined the trait provides common functional helper methods over the iterator like map or filter.

在 Rust 中，用户定义的类型是使用 struct 关键字创建的。这些类型通常包含数据字段，如其他语言中的对象或类。 impl 关键字可以为结构定义方法（数据和函数在结构中分别定义）或为结构实现特征。 trait 是一个契约，一个结构已经实现了某些必需的方法。特征用于限制泛型参数，因为特征可以为结构提供比用户定义的方法更多的方法。例如，trait Iterator 要求为该类型定义 next 方法。一旦定义了下一个方法，特征就会通过迭代器（如 map 或 filter）提供通用的功能辅助方法。

The object system within Rust is based around implementations, traits and structured types. Implementations fulfill a role similar to that of classes within other languages and are defined with the keyword impl. Traits provide inheritance and polymorphism; they allow methods to be defined and mixed in to implementations. Structured types are used to define fields. Implementations and traits cannot define fields themselves, and only traits can provide inheritance. Among other benefits, this prevents the diamond problem of multiple inheritance, as in C++. In other words, Rust supports interface inheritance but replaces implementation inheritance with composition; see composition over inheritance.

Rust 中的对象系统基于实现、特征和结构化类型。实现的作用类似于其他语言中的类，并使用关键字 impl 定义。 Traits 提供继承和多态性；它们允许定义方法并将其混合到实现中。结构化类型用于定义字段。实现和特征本身不能定义字段，只有特征可以提供继承。除了其他好处外，这还可以防止多重继承的菱形问题，就像在 C++ 中一样。换句话说，Rust 支持接口继承，但是用组合代替了实现继承；请参阅组合而不是继承。

Macros for language extension（语言扩展宏）
It is possible to extend the Rust language using the procedural macro mechanism.[62]

Procedural macros use Rust functions that run at compile time to modify the compiler's token stream. This complements the declarative macro mechanism (also known as macros by example), which uses pattern matching to achieve similar goals.

可以使用过程宏机制来扩展 Rust 语言。 [62]

程序宏使用在编译时运行的 Rust 函数来修改编译器的令牌流。这补充了声明性宏机制（也称为示例宏），它使用模式匹配来实现类似的目标。

Procedural macros come in three flavors:

Function-like macros custom!(...)
Derive macros #[derive(CustomDerive)]
Attribute macros #[custom_attribute]
The println! macro is an example of a function-like macro and serde_derive[63] is a commonly used library for generating code for reading and writing data in many formats such as JSON. Attribute macros are commonly used for language bindings such as the extendr library for Rust bindings to R.[64]

The following code shows the use of the Serialize, Deserialize and Debug derive procedural macros to implement JSON reading and writing as well as the ability to format a structure for debugging.


Interface with C and C++
Rust has a foreign function interface (FFI) that can be used both to call code written in languages such as C from Rust and to call Rust code from those languages. While calling C++ has historically been challenging (from any language), Rust has a library, CXX, to allow calling to or from C++, and "CXX has zero or negligible overhead."[65]

# Components
Besides the compiler and standard library, the Rust ecosystem includes additional components for software development. Component installation is typically managed by rustup, a Rust toolchain installer developed by the Rust project.[66]

## Cargo
Cargo is Rust's build system and package manager. Cargo handles downloading and building dependencies. Cargo also acts as a wrapper for Clippy and other Rust components. It requires projects to follow a certain directory structure.[67]

The dependencies for a Rust package are specified in a Cargo.toml file along with version requirements, telling Cargo which versions of the dependency are compatible with the package. By default, Cargo sources its dependencies from the user-contributed registry crates.io, but Git repositories and packages in the local filesystem can be specified as dependencies, too.[68]

## Rustfmt
Rustfmt is a code formatter for Rust. It takes Rust source code as input and changes the whitespace and indentation to produce code formatted in accordance to the Rust style guide or rules specified in a rustfmt.toml file. Rustfmt can be invoked as a standalone program or on a Rust project through Cargo.[69][70]

## Clippy
Clippy is Rust's built-in linting tool to improve the correctness, performance, and readability of Rust code. It was created in 2014[71] and named after the eponymous Microsoft Office feature.[72] As of 2021, Clippy has more than 450 rules,[73] which can be browsed online and filtered by category.[74] Some rules are disabled by default.

Clippy 是 Rust 的内置 linting 工具，用于提高 Rust 代码的正确性、性能和可读性。它创建于 2014 年 [71] 并以同名的 Microsoft Office 功能命名。 [72]截至 2021 年，Clippy 有超过 450 条规则，[73] 可以在线浏览并按类别过滤。[74]默认情况下禁用某些规则。

## IDE support
The most popular language servers for Rust are rust-analyzer[75] and RLS.[76] These projects provide IDEs and text editors with more information about a Rust project. Basic features include linting checks via Clippy and formatting via Rustfmt, among other functions. RLS also provides automatic code completion via Racer, though development of Racer was slowed down in favor of rust-analyzer.[77]

Rust 最流行的语言服务器是 rust-analyzer[75] 和 RLS。[76]这些项目为 IDE 和文本编辑器提供了有关 Rust 项目的更多信息。基本功能包括通过 Clippy 进行的 linting 检查和通过 Rustfmt 进行格式化，以及其他功能。 RLS 还通过 Racer 提供自动代码完成功能，尽管 Racer 的开发速度被减慢以支持 rust-analyzer。 [77]