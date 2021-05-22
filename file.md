## 引言

此 Ecma Standard 定义了 ECMAScript 2015 Language。它是 ECMAScript 语言规范的第六版。自 1997 年初版以来，ECMAScript 已经成为世界上用途最广的通用编程语言之一。最广为人知的是它作为网页浏览器的嵌入语言，同事它也被服务器和嵌入式应用广泛采用。自从 1997 年初版以来，第六版是对 ECMAScript 的最广泛的更新。

ECMAScript 2015 的目标包括为大型应用程序、库创建以及将 ECMAScript 用作其他语言的编译目标提供更好的支持。它的一些主要增强功能包括模块，类声明，词法块级作用域、迭代器和生成器，对异步编程的 promise，解构模式以及适当的尾部调用。ECMAScript 内置库已扩展至支持其他数据抽象，包括映射、集合、二进制数值数组、对字符串中 Unicode 补充字符的附加支持以及正则表达式。现在可以通过子类扩展内置函数。

ECMAScript 基于多种原始技术，最著名的是 JavaScript（Netscape）和JScript（Microsoft）。该语言是 Netscape 的 Brendan Eich 发明的，最早出现在该公司的 Navigator 2.0 浏览器中。从 Internet Explorer 3.0 开始，它出现在 Netscape 的所有后续浏览器以及 Microsoft 的所有浏览器中。

ECMAScript 语言规范的开发始于 1996 年 11 月。该 Ecma 标准的第一版在 1997 年 6 月的Ecma 大会上获得通过。

该 Ecma 标准已提交给 ISO / IEC JTC 1 以在快速程序下通过，并于 1998 年 4 月被批准为国际标准 ISO / IEC 16262。1998 年 6 月的 Ecma 大会批准了 ECMA-262 的第二版，以使其完全与 ISO / IEC 16262 保持一致。第一版和第二版之间的更改本质上是社论。

第三版标准引入了强大的正则表达式、更好的字符串处理、新的控制声明、tra/catch 异常处理、更严格的错误定义、用于数字输出的格式设置以及预期的将来语言增长的细微变化。ECMAScript 标准的第三版于 1999 年 12 月由 Ecma 大会采用，并于2002年6月作为 ISO / IEC 16262:2002 发布。

在发布第三版之后，ECMAScript 与万维网一起获得了广泛的采用，在万维网中，ECMAScript 已经成为基本上所有网络浏览器都支持的编程语言。为开发 ECMAScript 第四版，有大量工作被展开。但是，那些工作尚未完成，也没有作为 ECMAScript 的第四版发布，但其中一些已合并到第六版的开发中。ECMAScript 的第五版（作为 ECMA-262 第 5 版发布）对已在浏览器实现中已变得很普遍，并增加了对自第三版发布以来出现的新功能的支持的语言规范的实际解释进行了整理。这些功能包括访问者属性、反射性创建和检查对象、属性特性的程序控制、其他数组操作功能、对 JSON 对象编码格式的支持以及提供增强的错误检查和程序安全性的严格模式。第五版于2009 年 12 月由 Ecma 大会通过。

第五版已提交给 ISO / IEC JTC 1 以在快速程序下通过，并被批准为国际标准 ISO / IEC 16262:2011。ECMAScript 标准的 5.1 版包含一些小的更正，并且与 ISO / IEC 16262:2011相同。5.1 版由 2011 年 6 月的 Ecma 大会通过。

第六版的重点开发工作始于 2009 年，当时正准备出版第五版。但是，在此之前需要进行大量的实验和语言增强设计工作，这些工作要追溯到 1999 年。实际上，第六版的完成是十五年努力的结晶。

在 Ecma TC39 中，代表许多组织的数十个人为该版本和以前版本的开发做出了非常重要的贡献。此外，已经形成了一个支持 TC39 的 ECMAScript 工作的充满活力的非正式社区。该社区审查了许多草案，提交了数千个错误报告，执行了实施实验，提供了测试套件，并对全球开发人员社区进行了 ECMAScript 的指导。不幸的是，无法一一确认以及感谢对这一努力做出贡献的每个人和组织。

ECMAScript 的新用途和需求不断涌现。第六版为常规、增量语言和库增强功能提供了基础。

# ECMAScript 2015 语言规范

## 1 范围

本标准定义了ECMAScript 2015通用编程语言。

## 2 一致性

符合 ECMAScript 的实现必须提供并支持本规范中描述的所有类型、值、对象、属性、函数以及程序语法和语义。

符合 ECMAScript 的实现必须解释符合 Unicode 标准 5.1.0 版或更高版本以及 ISO / IEC 10646 的源文本输入。如果未另外指定所采用的 ISO / IEC 10646-1 子集，则假定它是Unicode 集，集合10646。

符合 ECMAScript 的实现，提供了一个应用程序编程接口，该接口支持需要适应不同人类语言所使用的语言和文化惯例的程序，并且国家/地区必须实现与此版本兼容的最新版本ECMA-402 定义的接口 规范。

符合 ECMAScript 的实现可能会提供本规范中所描述之外的其他类型、值、对象、属性和函数。特别地，符合 ECMAScript 的实现可以为本规范中描述的对象提供本规范中未描述的属性以及这些属性的值。

符合 ECMAScript 的实现可以支持本规范中未描述的程序和正则表达式语法。特别地，符合ECMAScript 的实现可以支持程序语法，该程序语法使用了本规范 [11.6.2.2](http://www.ecma-international.org/ecma-262/6.0/#sec-future-reserved-words) 节中列出的「未来保留字」。

符合 ECMAScript 的实现不得实现第 [ 16.1](http://www.ecma-international.org/ecma-262/6.0/#sec-forbidden-extensions) 节中列为禁止扩展的任何扩展。

## 3 规范性引用

以下参考文件对于本文件的应用是必不可少的。凡是注日期的引用文件，仅所引用的版本适用。凡是不注日期的引用文件，其最新版本（包括所有的修改单）适用于本标准。

ISO/IEC 10646:2003: *Information Technology – Universal Multiple-Octet Coded Character Set (UCS) plus Amendment 1:2005, Amendment 2:2006, Amendment 3:2008, and Amendment 4:2008*, plus additional amendments and corrigenda, or successor

ECMA-402, *ECMAScript 2015 Internationalization API Specification*.
http://www.ecma-international.org/publications/standards/Ecma-402.htm

ECMA-404, *The JSON Data Interchange Format*.
http://www.ecma-international.org/publications/standards/Ecma-404.htm

## 4 总览

本节包含ECMAScript语言的非规范性概述。

ECMAScript 是一种面向对象的编程语言，用于在主机环境中执行计算和操作计算对象，此处定义的 ECMAScript 并非旨在实现计算自给自足；实际上，此规范中没有规定要输入外部数据或输出。相反，期望 ECMAScript 程序的计算环境将不仅提供本规范中描述的对象和其他设施，而且还提供某些特定于环境的对象，这些对象的描述和行为超出了本规范的范围，除了表明它们可以提供某些可以访问的属性以及可以从 ECMAScript 程序调用的某些功能之外。

ECMAScript 最初仅被设计为一个脚本语言，但如今已广泛用作通用语言。**脚本语言**是用于操纵、定制和自动化现有系统设施的语言。在这样的系统中，有用的功能已经可以通过用户界面获得，脚本语言是一种将该功能暴露给程序控制的机制。如此一来，现有系统可以提供对象和设施的宿主环境，从而完善了脚本语言的功能。脚本语言旨在供专业和非专业程序员使用。

ECMAScript 最初被设计为一种 Web 脚本语言，它提供了一种机制来激活浏览器中的网页并执行服务器计算，并将其作为基于 Web 的客户端-服务器体系结构的一部分。ECMAScript 现在用于为各种主机环境提供核心脚本功能。因此，除任何特定主机环境外，本文档中还指定了核心语言。

ECMAScript 的使用已经超越了简单的脚本编写，现在已用于许多不同环境和规模的各种编程任务。随着ECMAScript用途的扩展，它提供的功能和设施也随之增加。ECMAScript现在是功能齐全的通用编程语言。

ECMAScrip t的某些功能类似于其他编程语言中使用的功能；特别是 C，Java™，Self 和 Scheme，如以下所述：

ISO/IEC 9899:1996, *Programming Languages – C*.

Gosling, James, Bill Joy and Guy Steele. *The Java™ Language Specification*. Addison Wesley Publishing Co., 1996.

Ungar, David, and Smith, Randall B. Self: The Power of Simplicity. *OOPSLA '87 Conference Proceedings*, pp. 227–241, Orlando, FL, October 1987.

*IEEE Standard for the Scheme Programming Language*. IEEE Std 1178-1990.

### 4.1 Web 脚本

Web 浏览器为客户端计算提供 ECMAScript 主机环境，例如，代表窗口，菜单，弹出窗口，对话框，文本区域，锚点，框架，历史记录，Cookie 和输入/输出的对象。此外，宿主环境提供了一种将脚本代码附加到事件（例如更改焦点，页面和图像加载，卸载，错误和中止，选择，表单提交和鼠标操作）的方法。脚本代码出现在 HTML 中，显示的页面是用户界面元素以及固定的和计算的文本和图像的组合。脚本代码对用户交互具有反应性，因此不需要主程序。

Web 服务器为服务器端计算提供了不同的主机环境，包括代表请求，客户端和文件的对象；以及锁定和共享数据的机制。通过一起使用浏览器端脚本和服务器端脚本，可以在客户端和服务器之间分配计算，同时为基于 Web 的应用程序提供自定义的用户界面。

每个支持 ECMAScript 的 Web 浏览器和服务器都提供自己的宿主环境，从而完善了 ECMAScript 执行环境。

### 4.2 ECMAScript 总览

以下是ECMAScript的非正式概述-并未描述该语言的所有部分。此概述不是标准的一部分。

ECMAScript 是基于对象的：基本语言和宿主功能由对象提供，而 ECMAScript 程序是通信对象的群集。在 ECMAScript 中，一个对象是零个或多个属性的集合，每个属性具有确定如何使用每个属性的特性——例如，当某个属性的 `Writable` 特性设置为 `false` 时，执行的 ECMAScript 代码中任何欲修改这个属性值的尝试都会失败。属性是保存其他对象，*基本值*或*函数*的容器。基本值是以下内置类型之一的成员：**Undefined**，**Null**，**Boolean**，**Number**，**String** 和 **Symbol**；对象是内置类型 **Object** 的成员；函数是可调用的对象。通过属性与对象关联的函数称为方法。

ECMAScript 定义了一组*内置对象*，这些对象对 ECMAScript 实体的定义进行了完善。这些内置对象包括全局对象；语言运行时语义的基础的对象，包括 **Object**，**Function**，**Boolean**，**Symbol** 和各种 **Error**；代表和操纵数值的对象，包括**Math**，**Number** 和 **Date**；文本处理对象 **String** 和 **RegExp**; 被索引的值集合的对象，包括 **Array** 和九种不同类型的类型化数组，它们的元素都具有特定的数值数据表示形式；键控集合，包括 **Map** 和 **Set** 对象；支持结构化数据的对象，包括 **JSON** 对象，**ArrayBuffer** 和 **DataView**；支持控件抽象的对象，包括 **Generator** 和 **Promise** 对象；以及映射对象，包括 **Proxy** 和 **Reflect**。

ECMAScript 还定义了一组内置运算符。ECMAScript 运算符包括各种一元运算符，乘法运算符，加法运算符，按位移位运算符，关系运算符，相等运算符，二进制按位运算符，二进制逻辑运算符，赋值运算符和逗号运算符。

大型 ECMAScript 程序受*模块*支持，这些模块允许将程序分为多个语句和声明序列。每个模块都明确标识其使用的声明，这些声明需要由其他模块提供，以及哪些声明可供其他模块使用。

ECMAScript 语法故意类似于 Java 语法。宽松的 ECMAScript 语法使其能够用作易于使用的脚本语言。例如，变量不需要声明其类型，也不要求类型与属性相关联，并且不需要定义的函数在调用它们之前以文本形式显示其声明。

#### 4.2.1 Objects

即使 ECMAScript 包含用于类定义的语法，但 ECMAScript 对象从根本上来说并不是基于类的，例如 C ++，Smalltalk 或 Java 中的对象。相反，可以通过各种方式创建对象，包括通过文字符号或通过创建对象的**构造函数**，然后执行通过将初始值分配给它们的属性来初始化全部或部分对象的代码。每个构造函数都是一个函数，该函数具有名为“ prototype”的属性，该属性用于实现基于原型的继承和共享属性。通过在 **new** 表达式中使用构造函数来创建对象。例如，`new Date(2009,11)` 创建一个新的 Date 对象。在不使用 new 的情况下调用构造函数的后果取决于构造函数。例如，`Date()` 生成当前日期和时间的字符串表示形式，而不是对象。

构造函数创建的每个对象都有对其构造函数的“ prototype”属性值的隐式引用（称为对象的原型）。此外，原型可能对其原型具有非 `null` 的隐式引用，依此类推；这称为原型链。当引用对象中的属性时，该引用就是包含该名称的属性的原型链中第一个对象中该名称的属性。换句话说，首先检查直接提到的对象是否具有这种属性；如果该对象包含命名属性，那么该引用就是该属性；如果该对象不包含命名属性，则接下来检查该对象的原型；依此类推。

通常，在基于类的面向对象语言中，状态由实例承载，方法由类承载，并且继承仅是结构和行为。在 ECMAScript 中，状态和方法由对象承载，而结构，行为和状态都被继承。

所有不直接包含其原型包含的特定属性的对象都共享该属性及其值。图 1 说明了这一点：

CF 是一个构造函数（也是一个对象）。通过使用新表达式创建了五个对象：cf1，cf2，cf3，cf4 和 cf5。这些对象中的每一个都包含名为 q1 和 q2 的属性。虚线表示隐式原型关系。因此，例如，cf3 的原型是 CFp。构造函数 CF 本身具有两个属性，分别称为 P1 和 P2，CFp，cf1，cf2，cf3，cf4 或 cf5不可见。CFp 中名为 CFP1 的属性由 cf1，cf2，cf3，cf4 和 cf5（但不是由 CF）共享，以及在 CFp 的隐式原型链中找到的所有未命名为 q1，q2 或 CFP1 的属性。注意，CF 和 CFp 之间没有隐式原型链接。

与大多数基于类的对象语言不同，可以通过为对象分配值来将属性动态添加到对象。也就是说，构造函数不需要为所有或任何构造对象的属性命名或分配值。在上图中，可以通过为 CFp 中的属性分配新值来为 cf1，cf2，cf3，cf4 和 cf5 添加新的共享属性。

尽管 ECMAScript 对象并不是天生就基于类的，但通常可以根据构造函数，原型对象和方法的通用模式来定义类抽象。ECMAScript 内置对象本身遵循这样的类模式。从 ECMAScript 2015 开始，ECMAScript 语言包括语法类定义，这些语法定义使程序员可以简洁地定义与内置对象所使用的类类抽象模式相同的对象。

#### 4.2.2 ECMAScript 的严格变体

ECMAScript 语言认识到该语言的某些用户可能希望限制其使用该语言可用的某些功能的可能性。他们这样做可能是出于安全性的考虑，以避免他们认为容易出错的功能，进行增强的错误检查或出于其他选择的原因。为了支持这种可能性，ECMAScrip t定义了该语言的严格变体。该语言的严格变体排除了常规 ECMAScript 语言的某些特定语法和语义特征，并修改了某些特征的详细语义。严格变体还指定了其他错误条件，在语言的非严格形式未将其指定为错误的情况下，必须通过抛出错误异常来报告这些错误条件。

ECMAScript 的严格变体通常称为语言的*严格模式*。在单个 ECMAScript 源文本单元级别上明确进行了严格的模式选择以及 ECMAScript 的严格模式语法和语义的使用。因为在语法源文本单元级别选择了严格模式，所以严格模式仅在这种源文本单元内施加了具有局部效果的限制。严格模式不会限制或修改必须在多个源文本单元中一致运行的 ECMAScript 语义的任何方面。完整的 ECMAScript 程序可能由严格模式和非严格模式 ECMAScript 源文本单元组成。在这种情况下，严格模式仅在实际执行在严格模式源文本单元中定义的代码时适用。

为了符合此规范，ECMAScript 实现必须同时实现完全无限制的 ECMAScript 语言和该规范定义的 ECMAScript 语言的严格变体。另外，实现必须支持将无限制和严格模式的源文本单元组合到单个复合程序中。

### 4.3 术语和定义

就本文档而言，以下术语和定义适用。

#### 4.3.1 type

本规范第 6 节中定义的一组数据值

#### 4.3.2 primitive value

第 6 节中定义的类型 Undefined，Null，Boolean，Number，Symbol 或 String 之一的成员

注：原始值是直接在语言实现的最低级别上表示的数据

#### 4.3.3 object

Object 类型的成员

注：对象是属性的集合，并且具有单个原型对象。原型可以为空值。

#### 4.3.4 constructor

创建和初始化对象的函数对象

注：构造函数的 prototype 属性的值是一个原型对象，用于实现继承和共享属性。

#### 4.3.5 prototype

提供其他对象共享属性的对象

注：构造函数创建对象时，该对象隐式引用构造函数的 prototype 属性，以解决属性引用的问题。构造表达式的原型属性可以由程序表达式的 *constructor***.prototype** 引用，添加到对象原型的属性可以通过继承由共享原型的所有对象共享。或者，可以使用 `Object.create` 内置函数使用明确指定的原型创建新对象。

#### 4.3.6 ordinary object

每个对象都必须支持一组基本内部方法，如果一个对象对这些内部基本方法中的每一个都有默认行为，那么这个对象是一个 ordinary object，否则是一个 exotic object

这些所有对象都必须支持的基本内部方法是都有啥？举个例子？比如哪些是 ordinary object 哪些不是？

#### 4.3.7 exotic object

对所有对象都必须支持的一种或多种基本内部方法没有默认行为的对象

注：任何对象不是 ordinary object 就是 exotic object

#### 4.3.8 standard object

该规范定义了其语义的对象

#### 4.3.9 built-in object

由 ECMAScript 实现指定和提供的对象

注：此规范中定义的内置对象称为标准内置对象。ECMAScript 实现可以指定并提供其他种类的内置对象。内置构造函数是一个内置对象，它也是一个构造函数。

#### 4.3.10 undefined value

未给变量赋值时使用的原始值

#### 4.3.11 Undefined type

其唯一值是 undefined value 的类型

#### 4.3.12 null value

表示有意缺少任何对象值的原始值

#### 4.3.13 Null type

其唯一值为 null value 的类型

#### 4.3.14 Boolean value

布尔类型成员

注：只有两个布尔值，`true` 和 `false`

#### 4.3.15 Boolean type

由原始值 `true `和 `false` 组成的类型

#### 4.3.16 Boolean object

Object 类型的成员，它是标准内置构造函数 **Boolean** 的实例

注：通过在 **new** 表达式中使用布尔构造函数创建布尔对象，并提供布尔值作为参数。结果对象具有一个 internal slot，其值为布尔值。布尔对象可以强制为布尔值。

#### 4.3.17 String value

基本值，它是零个或多个 16 位无符号整数的有限有序序列

注：字符串值是字符串类型的成员。序列中的每个整数值通常代表 UTF-16 文本的单个 16位单元。但是，ECMAScript 对值没有任何限制或要求，只是它们必须是 16 位无符号整数。

#### 4.3.18 String type

所有可能的字符串值组成的类型

#### 4.3.19 String object

Object 类型的成员，它是标准内置构造函数 **String** 的实例

注：通过在 **new** 表达式中使用 **String** 构造函数创建 String 对象，并提供 String 值作为参数。生成的对象具有一个内部插槽，其值为 String 值。通过将 String 构造函数作为函数调用（21.1.1.1），可以将 String 对象强制为 String 值。

#### 4.3.20 Number value

对应于双精度 64 位二进制格式 IEEE 754-2008 值的原始值

注：Number 值是 Number 类型的成员，并且是数字的直接表示。

#### 4.3.21 Number type

所有可能的 Number 值的集合，包括特殊的“非数字”（NaN）值，正无穷大和负无穷大。

#### 4.3.22 Number object

Object 类型的成员，它是标准内置构造函数 **Number** 的实例

注：通过在 **new** 表达式中使用 **Number** 构造函数创建 Number 对象，并提供 Number 值作为参数。生成的对象具有一个内部插槽，其值为 Number 值。通过将 Number 构造函数作为函数调用（21.1.1.1），可以将 Number 对象强制为 Number 值。

#### 4.3.23 Infinity

是正无穷数值的数值

#### 4.3.24 NaN

是 IEEE 754-2008 “非数字”值的数字值 

#### 4.3.25 Symbol value

表示唯一的非 String Object 属性键的原始值

#### 4.3.26 Symbol type

所有可能的符号值的集合

#### 4.3.27 Symbol object

Object 类型的成员，它是标准内置构造函数 **Symbol** 的实例（realy？`Symbol('s') instanceof Object === false`）

#### 4.3.28 function

Object 类型的成员，可以作为子例程调用

注：除了其属性之外，函数还包含可执行代码和状态，这些代码和状态确定了调用时的行为。函数的代码可能会或可能不会用 ECMAScript 编写。

#### 4.3.29 built-in function

同时是 function 的内置对象

注：内置函数的示例包括 **parseInt** 和 **Math.exp**。一种实现可以提供在本说明书中未描述的与实现有关的内置功能。

#### 4.3.30 property

对象的一部分，关联 key（字符串值或符号值）和值（任意值）

注：根据属性的形式，值可以直接表示为数据值（原始值，对象或函数对象），也可以通过一对访问器函数间接表示。

#### 4.3.31 method

作为对象某个属性的值的函数

注：当将函数作为对象的方法调用时，该对象将作为其this值传递给函数。

#### 4.3.32 built-in method

作为方法的内置函数

注：在此规范中定义了标准的内置方法，并且 ECMAScript 实现可以指定并提供其他附加的内置方法。

#### 4.3.33 attribute

定义属性某些特征的内部值

#### 4.3.34 own property

由其对象直接包含的属性

#### 4.3.34 inherited property

不是 own property，而是属于（拥有或继承）对象原型的属性

### 4.4 本规范的组织

本规范的其余部分安排如下：

第 5 章定义了整个说明书中使用的符号约定。

第 6-9 章定义了 ECMAScript 程序在其中运行的执行环境。

第 10-16 章定义了实际的 ECMAScript 编程语言，包括其语法编码和所有语言功能的执行语义。

第 17-26章定义了 ECMAScript 标准库。它包括 ECMAScript 程序执行时可以使用的所有标准对象的定义。

## 5 符号约定

### 5.1 Syntactic and Lexical Grammars

#### 5.1.1 Context-Free Grammars

A *context-free grammar* 由许多 *productions* 组成。每个 production 的左手边都有一个称为非终结符的抽象符号，其右手边为一个由零个或多个非终结符和终结符的序列。对于每个语法，终结符号都是从指定的字母中绘制的。

A *chain production* 是在其右侧恰好有一个非终结符号以及零个或多个终结符号的 production。

（何为 production——译为产生式，见 https://www.zhihu.com/question/21833944）

给定的上下文无关语法从一个由单独的非终结符组成的句子（称为 *goal symbol*）开始，指定一种语言，即，（可能是无限的）可能的终结符序列集，这些序列可能是由于反复替换词中的任何非终结符而导致的。序列具有生产的右侧的序列，其非末端为左侧。

#### 5.1.2 The Lexical and RegExp Grammars

第 11 节给出了 ECMAScript 的 *lexical grammar*。该语法的终结符号为 Unicode 码点，它们符合 10.1 中定义的 *SourceCharacter* 规则。它定义了一组产生式，从 goal symbol（注：后面统一翻译成目标符号）*InputElementDiv*，*InputElementTemplateTail* 或 *InputElementRegExp* 或 *InputElementRegExpOrTemplateTail* 开始，描述了如何将这些码点的序列转换为输入元素的序列。

除空格和注释以外的其他输入元素构成 ECMAScript syntactic grammar 的终结符号，称为ECMAScript *token*。这些 token 是 ECMAScript 语言的保留字，标识符，文字和标点符号。此外，行终止符尽管不被视为 token，但也成为输入元素流的一部分，并指导自动分号插入的过程（11.9）。简单的空格和单行注释将被丢弃，并且不会出现在 syntactic grammar 的输入元素流中。如果 *MultiLineComment* 不包含任何行结束符，则它会被简单地丢弃（即，注释形式为/ *…* /，而不管它是否跨越多行）；但是，如果 MultiLineComment 包含一个或多个行终止符，则将其替换为一个行终止符，该行终结符成为 syntactic grammar 输入元素流的一部分。

21.2.1 中给出了 ECMAScript 的 *RegExp grammar*  语法。该语法还具有 *SourceCharacter* 定义的码点作为其终结符。它定义了一组从目标符号“模式”开始的产生式，这些产生式描述了如何将码点的序列转换为正则表达式模式。

lexical grammars 和 RegExp grammars 的产生式以两个冒号 "::" 作为分隔标点符号来加以区分。lexical grammars 和 RegExp grammars 共享一些产生式。

#### 5.1.3 The Numeric String Grammar

另一种语法用于将字符串转换为数值。该语法类似于lexical grammar 中与数字字面量有关的部分，并且其末尾符号为 *SourceCharacter*。该语法出现在7.1.3.1中。

数字字符串语法的产生式以标点符号为三个冒号 ":::" 来区分。

#### 5.1.4 The Syntactic Grammar（注：后面统一翻译成「句法语法」）

第 11、12、13、14 和 15 节中给出了ECMAScript 的 *syntactic grammar*。此语法具有由 *lexical grammar* （后面统一翻译成「词法语法」）定义的 ECMAScript token 作为其终结符（5.1.2）。它从两个替代的目标符号 *Script* 和 *Module* （后面统一翻译成「脚本」和「模块」）开始定义了一组产生式，这些产生式描述了 token（注：后面统一翻译成「标记」） 序列如何形成语法正确的 ECMAScript 程序独立组件。

当将码点流解析为 ECMAScript 脚本或模块时，首先通过重复应用词法语法将其转换为输入元素流。然后，通过语法的单个应用程序来解析此输入元素流。如果无法将输入元素流中的标记解析为目标非终结（脚本或模块）的单个实例，而没有标记剩下，则输入流在语法上是错误的。

句法语法的产生式以标点符号为一个冒号 ":" 区分。

第 12、13、14 和 15 节中提出的句法语法不能完全说明哪些标记序列被接受为正确的ECMAScript 脚本或模块。某些其他标记序列也被接受，即如果在某些位置仅将分号添加到序列中（例如在行终止符之前），则语法将描述的那些标记序列。此外，如果在某些“尴尬”的地方出现了行终止符，则语法描述的某些标记序列将不被接受。

在某些情况下，为了避免歧义，句法语法使用通用的产生式，从而使标记序列不会形成有效的 ECMAScript 脚本或模块。例如，此技术用于对象字面量和对象解构模式。在这种情况下，提供了更具限制性的补充语法，该语法进一步限制了可接受的标记序列。在某些情况下，当明确指定时，将使用补充语法的目标符号再次解析与此类产生式相对应的输入元素。如果通过一个 cover grammer 分析的输入元素流中的标记不能被解析为相应补充目标符号的单个实例，而没有任何标记剩下，则输入流在语法上是错误的。

#### 5.1.5 Grammer Notation（语法符号）

词法，RegExp 和数字字符串语法的终结符以 `固定宽度`（注：此文档中以代码体表示）的字体显示，无论是在语法的产生式中还是在整个规范中，只要文本直接涉及到这种终结符。这些将完全按照书面形式出现在脚本中。以此方式指定的所有终结符码点都应理解为基本拉丁语范围中的适当 Unicode 码点，而不是其他 Unicode 范围中任何外观相似的码点。

非终结符号以*斜体*显示。非终结符（也称为产生式）的定义由定义的非终结符的名称后跟一个或多个冒号引入。（冒号的数量表示该产生式所属的语法。）非终结符的一个或多个可选右手边，然后在后续行中跟随。例如，句法定义（注：下面那个例子整体就是一个 production，冒号左边是 nonterminal 右边是零个或多个终结符和终结符）：

---

*WhileStatement* **:**

​		`while` `(` *Expression* `)` *Statement*ssion

---

声明非终结符 *WhileStatement* 表示标记 `while`，其后是左括号标记，然后是 *Expression*，再是右括号标记，然后是 *Statement*。*Expression* 和 *Statement* 的出现本身是非终结符（它们又可以替换成它们自身定义中的分隔符右边的那部分内容）。再举一个例子，句法定义：

---

*ArgumentList* **:**

​		*AssignmentExpression*

​		*ArgumentList* `,` *AssignmentExpression*

---

声明 *ArgumentList* 可以表示单个 *AssignmentExpression* 或 *ArgumentList* 后跟逗号，然后是 *AssignmentExpression*。*ArgumentList* 的此定义是递归的，也就是说，它是根据自身定义的。结果是 *ArgumentList* 可以包含任意正数的参数，并用逗号分隔，其中每个参数表达式都是一个 *AssignmentExpression*。非终结符的这种递归定义很常见。

下标 "<sub>opt</sub>"（可能出现在终结或非终结之后）表示可选符号。包含可选符号的替代实际上指定了两个右侧，一个省略了可选元素，而一个包含了可选元素。这意味着：

------

*VariableDeclaration* **:**

​		*BindingIdentifier* *Initializer*<sub>opt</sub>

------

是下面格式的一个方便缩写：

------

*VariableDeclaration* **:**

​		*BindingIdentifier*

​		*BindingIdentifier* *Initializer*

------

而

------

*IterationStatement* **:**

​		`for` `(` *LexicalDeclaration* *Expression*<sub>opt</sub> `;` *Expression*<sub>opt</sub> `)` *Statement*

------

则下面格式的一个方便缩写：

------

*IterationStatement* **:**

​		`for` `(` *LexicalDeclaration* `;` *Expression*<sub>opt</sub> `)` *Statement*

​		`for` `(` *LexicalDeclaration* *Expression* `;` *Expression*<sub>opt</sub> `)` *Statement*

------

而这又是下面的缩写：

------

*IterationStatement* **:**

​		`for` `(` *LexicalDeclaration* `;` `)` *Statement*

​		`for` `(` *LexicalDeclaration* `;` *Expression* `)` *Statement*

​		`for` `(` *LexicalDeclaration* *Expression* `;` `)` *Statement*

​		`for` `(` *LexicalDeclaration* *Expression* `;` *Expression* `)` *Statement*

------

因此，在此示例中，非终结 *IterationStatement* 实际上具有四个备选右侧。

可以通过形式为 "<sub>[parameters]</sub>" 的下标注释对产生式进行参数化，该注释可以作为产生式所定义的非终结符号的后缀。"<sub>[parameters]</sub>" 可以是单个名称，也可以是逗号分隔的名称列表。参数化产生式是一组产生式的简写，这些产生式定义了参数名称的所有组合，后跟一个下划线，并附加到参数化的非终结符上。这意味着：

------

*StatementList*<sub>[Return]</sub> **:**

​		*ReturnStatement*

​		*ExpressionStatement*

------

是下面的缩写：

------

*StatementList* **:**

​		*ReturnStatement*

​		*ExpressionStatemen

*StatementList_Return* **:**

​		*ReturnStatement*

​		*ExpressionStatemen*

------

而

------

*StatementList*<sub>[Return, In]</sub> **:**

​		*ReturnStatement*

​		*ExpressionStatement*

------

是下面的缩写：

------

*StatementList* **:**

​		*ReturnStatement*

​		*ExpressionStatemen*

*StatementList_Return* **:**

​		*ReturnStatement*

​		*ExpressionStatemen*

*StatementList_In* **:**

​		*ReturnStatement*

​		*ExpressionStatemen*

*StatementList_Return_In* **:**

​		*ReturnStatement*

​		*ExpressionStatemen*

------

多个参数可产生组合数量的产生式，但并非所有的产生式都必须在完整的语法中引用。

也可以对产生式右侧的非终结符引用进行参数化。例如：

------

*StatementList* **:**

​		*ReturnStatement*

​		*ExpressionStatement*<sub>[In]</sub>

------

等价于

------

*StatementList* **:**

​		*ReturnStatement*

​		*ExpressionStatement_In*

------

非终结符引用可以同时具有参数列表和 "<sub>opt</sub>" 后缀。例如：

------

*VariableDeclaration* **:**

​		*BindingIdentifier* *Initializer<sub>[In]opt</sub>*

------

是下面的简写：

------

*VariableDeclaration* **:**

​		*BindingIdentifier*

​		*BindingIdentifier* *Initializer_In*

------

在右侧非终结符引用的参数名称前加上 "<sub>?</sub>"  使该参数值取决于当前产生式左侧符号引用上的参数名称的出现。例如：

------

*VariableDeclaration*<sub>[In]</sub> **:**

​		*BindingIdentifier* *Initializer*<sub>[?In]</sub>

------

是下面的简写：

------

*VariableDeclaration***:**

​		*BindingIdentifier* *Initializer*

*VariableDeclaration_In* **:**

​		*BindingIdentifier* *Initializer_In*

------

如果右侧的替代项以 "<sub>[+parameter]</sub>" 为前缀，则只有在使用命名参数引用产生式的非终结符号时，该替代项才可用。如果右侧的替代项以 "<sub>[~parameter]</sub>" 为前缀，则该替代项仅在未使用命名参数引用产生的非终结符号时才可用。这意味着：

------

*StatementList*<sub>[Return]</sub> **:**

​		[+Return] *ReturnStatement*

​		*ExpressionStatement*

------

是下面的简写：

------

*StatementList_return* **:**

​		*ReturnStatement*

​		*ExpressionStatement*

*StatementList* **:**

​		*ExpressionStatement*

------

而

------

*StatementList*<sub>[Return]</sub> **:**

​		[-Return] *ReturnStatement*

​		*ExpressionStatement*

------

是下面的简写：

------

*StatementList* **:**

​		*ReturnStatement*

​		*ExpressionStatement*

*StatementList_return* **:**

​		*ExpressionStatement*

------

当语法定义中的冒号之后的单词 "**one of**" 时，它们表示以下一行或每行上的每个结束符号都是替代定义。例如，ECMAScript 的词法语法包含产生式：

------

*NonZeroDigit* **::** **one of**

​		`1` `2` `3` `4` `5` `6` `7` `8` `9`

------

仅仅是下面的一个方便的简写：

------

*NonZeroDigit* **::**

​		`1`

​		`2`

​		`3`

​		`4`

​		`5`

​		`6`

​		`7`

​		`8`

​		`9`

------

 如果短语 "[empty]" 出现在产生式的右侧，则表示该产生式的右侧不包含终结符或非终结符。

如果短语 "[lookahead∉set]"  出现在产生式的右侧，则表示如果紧随其后的输入标记序列是给定集的成员，则可能不能使用该产生式。该集合可以写成用逗号分隔的列表，其中用大括号括起来的一个或两个元素终结符序列。为了方便起见，该集合也可以写为非终结符，在这种情况下，它表示该非终结符可以扩展到的所有终结符的集合。如果集合由单个终结符组成，则可以使用短语 "[lookahead≠terminal]"。

例如，给定的定义

------

*DecimalDigit* **::** **one of**

​		`0` `1` `2` `3` `4` `5` `6` `7` `8` `9`

*DecimalDigits* **::**

​		*DecimalDigit*

​		*DecimalDigits* *DecimalDigit*

------

定义

------

*LookaheadExample* **::**

​		`n` [lookahead ∉ {`1`, `3`, `5`, `7`, `9`}] *DecimalDigits*

​		*DecimalDigit* [lookahead ∉ *DecimalDigit*]

------

匹配字母 n，后跟一个或多个十进制数字（第一个为偶数），或者匹配一个十进制数字，其后不跟另一个十进制数字。

如果在句法语法的产生式的右边出现短语 "[no *LineTerminator* here]"，则表示该产生式是受限产生式：如果 *LineTerminator* 出现在指定位置的输入流中出现，则可能不能使用它。例如，产生式：

------

*ThrowStatement* **:**

​		`throw` [no *LineTerminator* here] *Expression* ;

------

表示如果在脚本中在 **throw** 标记和 *Expression* 之间出现 *LineTerminator*，则可能不能使用产生式。

除非有限制的生产禁止 *LineTerminator* 的存在，否则在输入元素流中的任何两个连续标记之间可能出现 *LineTerminator* 的任何次数，而不会影响脚本的语法可接受性。

当词法语法或数字字符串语法的产生式中的替代方法看起来是多码点标记时，它表示组成此类标记的码点的序列。

产生式的右侧可以通过使用短语 "but not" 来指定不允许某些扩展，然后指示要排除的扩展。例如，产生式：

------

*Identifier* **::**

​		*IdentifierName* **but not** *ReservedWord*

------

表示非终结符 *Identifier* 可以由可以替换 *IdentifierName* 但不能替换 *ReservedWord* 的任何码点序列替换。

最后，在无法列出所有替代方案的情况下，用无衬线类型的描述性短语描述了一些非终结符：

------

*SourceCharacter* **::**

​		any Unicode code point

------

### 5.2 Algorithm Conventions（算法约定）

该规范通常使用编号列表来指定算法中的步骤。这些算法用于精确指定 ECMAScript 语言构造所需的语义。该算法无意暗示使用任何特定的实现技术。实际上，可能有更有效的算法可用于实现给定的功能。

可以对算法进行显式参数化，在这种情况下，必须提供参数的名称和用法作为算法定义的一部分。为了便于在本规范的多个部分中使用它们，某些算法（称为抽象操作）以参数化功能形式进行命名和编写，以便可以从其他算法中按名称进行引用。通常使用功能性应用程序样式（例如 `operationName(arg1, arg2)`）来引用抽象操作。一些抽象操作被视为类规范说明抽象的多态调度方法。通常使用诸如 `someValue.operationName(arg1, arg2)` 之类的方法应用程序样式来引用此类类似于方法的抽象操作。

算法可以与 ECMAScript 语法之一的产生式相关联。具有多个备选定义的产生式通常会为每个备选方案使用不同的算法。当算法与语法产生式相关联时，它可以引用产生式替代项的结束符和非结束符，就像它们是算法的参数一样。当以这种方式使用时，非结束符指的是在解析源文本时匹配的实际替代定义。

当算法与产生式备选项相关联时，通常会在没有任何“ []”语法注释的情况下显示该备选项。这样的注释应该只影响替代的句法识别，而对替代的关联语义没有影响。

除非另有明确说明，否则所有链式产生式对可能应用于该产生式的左侧非终结符的每种算法都有一个隐式定义。隐式定义只是将具有相同参数（如果有）的相同算法名称重新应用于链式产生式的唯一右侧非终结符，然后返回结果。比如，假设这样一个产生式：

------

*Block* **:**

​		`{` *StatementList* `}`

------

但没有为该产生式明确指定相应的求值算法。如果在某种算法中存在以下形式的陈述：“Return the result of evaluating *Block*”，则隐含存在以下形式的求值算法：

**Runtime Semantics: Evaluation**（运行时语义：求值）

------

*Block* **:** `{` *StatementList* `}`

1. Return the result of evaluating *StatementList*.

------

为了表达清楚，算法步骤可以细分为连续的子步骤。子步骤是缩进的，它们本身可以进一步分为缩进的子步骤。大纲编号约定用于标识子步骤，其中第一级子步骤标记为小写字母字符，第二级子步骤标记为小写罗马数字。如果需要三个以上的级别，这些规则将使用数字标签重复到第四个级别。例如：

------

1. Top-level step

   ​	a. Substep.

   ​	b. Substep.

   ​			i. Subsubstep.

   ​					1. Subsubsubstep

   ​							a. Subsubsubsubstep

   ​										i. Subsubsubsubsubstep

------

步骤或子步骤可以写为条件子步骤的“ if”谓词。在这种情况下，仅当谓词为 true 时才应用子步骤。如果某个步骤或子步骤以单词“ else”开头，则该谓词是先前的“ if”谓词步骤在相同级别上的取反。

步骤可以指定其子步骤的迭代应用程序。

以 "Assert:" 开始的步骤断言了其算法的不变条件。此类断言用于产生显式的算法不变量，否则它们将是隐式的。这样的断言不增加任何附加的语义要求，因此不需要由实现来检查。它们仅用于阐明算法。

本章后面定义的数学运算（如加，减，否定，乘法，除法和数学函数）应始终理解为在数学实数上计算精确的数学结果，除非另有说明，否则不包括无穷大且不包包括区别于正零的负零。该标准中对浮点算术建模的算法在必要时包括显式步骤，以处理无限性和带符号的零并执行舍入。如果将数学运算或函数应用于浮点数，则应将其理解为应用于该浮点数表示的确切数学值；这样的浮点数必须是有限的，如果它是 +0 或 −0，则相应的数学值就是 0。

数学函数 `abs(x)` 产生 x 的绝对值，如果 x 为负（小于零），则为 -x，否则为 x 本身。

如果x为正数，则数学函数 `sign(x)` 生成 1，如果 x 为负数，则生成 -1。对于 x 为零的情况，在本标准中不使用符号功能。

数学函数 `min(x1，x2，...，xn)` 产生数学上最小的 x1 到 xn。数学函数 `max(x1，x2，...，xn)` 产生数学上最大的 x1 到 xn。这些数学函数的作用域和取值范围包括 +∞ 和 -∞。

符号“x modulo y”（y 必须是有限且非零）可计算出与 y（或零）具有相同符号的值 k，使得`abs(k)<abs(y)` 且有某个整数 q 满足 x−k = q×y。

数学函数 `floor(x)` 返回不大于 x 的最大整数（最接近正无穷大）。

注：`floor(x) = x - (x modulo 1)`

### 5.3 Static Semantic Rules（静态语义规则）

上下文无关的语法功能没有强大到能表达可以定义一个输入元素流是否能形成一个有效的可求值的 ECMAScript 脚本或模块的所有规则。在某些情况下，可能需要使用 ECMAScript 算法约定或散文要求表达的其他规则。这样的规则总是与语法的产生式相关联，并被称为产生式的静态语义。

静态语义规则具有名称，通常使用算法进行定义。 命名静态语义规则与语法产生式相关联，并且具有多个替代定义的产生式通常会为每个替代具有针对每个适用的命名静态语义规则的不同算法。

除非另有说明，否则本规范中的所有语法产生式替代方案均隐含一个名为 *Contains* 的静态语义规则的定义，该规则采用名为 *symbol* 的参数，其值是包含相关产生式的语法的终结符或非终结符。Contains 的默认定义是：

------

1. 在此产生式的定义中，对于每个终结符和非终结符语法符号 *sym*

   1. 若 *sym* 是与 *symbol* 相同的语法符号，返回 **true**.

   2. 若 *sym* 是非终结符，则

      ​	i. 使 *contained* 为 *sym* Contains *symbol* 的结果

      ​	ii. 若 *contained* 为 **true**，返回 **true**.

2. 返回 **false**.

------

*译者注*：什么意思？*symbol* 是代表 production 多个可选方案中某个组成部分，*sym* 是 production 的某个具体方案的各个组成部分？

比如 *VariableDeclaration* 的定义：

------

*VariableDeclaration* **:**

​		*BindingIdentifier*

​		*BindingIdentifier* *Initializer*

*BindingIdentifier* *Initializer* *Contain* *Initializer*？ // **true**

*BindingIdentifier*  *Contain* *Initializer*？ // **true**

------

对于特定的产生式，以上定义已被明确覆盖。

一种特殊的静态语义规则是「早期错误规则」。早期错误规则定义与特定语法产生式关联的早期错误条件（请参阅第 16节 ）。在本规范的算法中，未明确调用大多数早期错误规则的求值。 符合标准的实现必须在对脚本或模块进行首次求值之前，验证用于解析该脚本或模块的产生式的所有早期错误规则。如果违反了任何早期错误规则，则脚本或模块无效，无法求值。

## 6 ECMAScript 数据类型和值

本规范中的算法处理每个值都具有关联类型的值。 可能的值类型正是本节中定义的值类型。 类型进一步细分为 **ECMAScript 语言类型**和**规范类型**。

在本规范中，符号 "Type(x)" 用作 "the type of x" 的简写，其中「类型」是指本节中定义的 ECMAScript 语言和规范类型。 当使用 "empty" 一词来命名值时，等同于说「没有任何类型的值」。

### 6.1 ECMAScript 语言类型

ECMAScript 语言类型对应那些可以由 ECMAScript 程序员使用 ECMAScript 语言直接操纵的值。ECMAScript 语言类型指的是 Undefined、Null、Boolean、String、Symbol、Number 和 Object。ECMAScript 值是以 ECMAScript 语言类型为特征的值。

#### 6.1.1 Undefined 类型

Undefined 类型只有一个值，称为 **undefined**，任何未被赋值的变量的值均为 **undefined**。

#### 6.1.2 Null 类型

Null 类型只有一个值，称为 **null**

#### 6.1.3 Boolean 类型

Boolean 类型表示一个拥有两个值的逻辑实体，两个值称为 **true** 和 **false**。

#### 6.1.4 String 类型

String 类型是一个由零个或多个 16 位无符号整数值（称为一个「元素」）的序列组成的集合，序列最多包含 2<sup>53</sup>-1 个16 元素。String 类型在一个运行的 ECMAScript 程序中通常被用于表示文本数据，这种情况下字符串中的每一个元素被当做 UTF-16 的码元值。每个元素被视作在序列中占据一个位置。这些位置用非负整数索引。第一个元素为索引 0，下一个为索引 1，依次类推。字符串的长度是其包含的元素（即 16 位值）的个数。空字符串长度为零，因此不包含任何元素。

在 ECMAScript 操作解释字符串值的情况下，每个元素都解释为单个 UTF-16 码元。但是，ECMAScript 对 String 值中的代码单元序列没有任何限制或要求，因此当将它们解释为 UTF-16 码元序列时，它们可能格式不正确。不解释字符串内容的操作将它们视为未区分的 16 位无符号整数的序列。`String.prototype.normlize`（见 21.1.3.12）可以用来显式标准化 String 值。`String.prototype.localeCompare`（见21.1.3.10）在内部对 String 值进行规范化，但是没有其他操作隐式对其进行操作的字符串进行规范化。只有明确指定为对语言或地区敏感的操作才能产生对语言敏感的结果。

注：这种设计的基本原理是使 Strings 的实现尽可能简单和高性能。如果 ECMAScript 源文本为规范化格式 C，则字符串文字也可以进行规范化，只要它们不包含任何 Unicode 转义序列即可。

某些操作将 String 内容解释为 UTF-16 编码的 Unicode 代码点。在这种情况下，解释是：

- 0 到 0xD7FF 范围内或 0xE000 到 0xFFFF 范围内的码元被解释为具有相同值的码点。
- 一个由两个码元组成，其第一个码元 *c1* 的范围在 0xD800 到 0xDBFF 之间，第二个码元 *c2* 在 0xDC00 到 0xDFFF 之间的序列是一个代理对，会被解释成值 `(c1 - 0xD800) * 0x400 + (c2 - 0xDC00) + 0x10000` 对应的码点
- 范围在 0xD800 到 0xDFFF 之间但不属于代理对的代码单元被解释为具有相同值的代码点。（译者注：比如由 oxDC00 和 oxD800 两个 16 bit 无符号整数按顺序组成的 String，因为这两个码元并不能组成一个代理对，所以这个 String 的两个码元会被解释为两个各自的值对应的 Unicode 码点。而由 oxD800 和 oxDC00 两个 16 bit 无符号整数按顺序组成的 String 则是一个代理对，会按上面第二种方式解释为字符 *𐀀*。）

#### 6.1.5 Symbol 类型

Symbol 类型是所有可以用作对象属性的 key 的非 String 值的集合。

每个可能的 Symbol 值都是独一无二且不可变的。

每个 Symbol 值不变地包含一个称为 [[Description]] 的关联值，该关联值为 **undefined** 或为 String 值。

##### 6.1.5.1 Well-known Symbols

Well-known symbols 是被此规范的算法明确引用的内置 Symbol 值。它们通常用作属性的键，其值用作规范算法的扩展点。除非另有说明，否则所有的 well-known symbols 值为所有 Code Realm（8.2）共享。

在此规范中，一个 well-known symbol 值通过 *@@name* 形式来引用，其中 "name" 是表格 1 中列出的值之一：

##### 表 1 ——Well-known Symbols

|       规范名称       |         [[Description]]         | 值和目的                                                     |
| :------------------: | :-----------------------------: | :----------------------------------------------------------- |
|    @@hasInstance     |    **"Symbol.hasInstance"**     | 一种确定构造函数对象是否将一个对象识别为构造函数实例之一的方法。由 **instanceof** 运算符的语义调用。 |
| @@isConcatSpreadable | **"Symbol.isConcatSpreadable"** | 一个 Boolean 值，如果为 true 则指示对象应通过[Array.prototype.concat](https://262.ecma-international.org/6.0/#sec-array.prototype.concat) 方式展开为其数组元 |
|      @@iterator      |      **"Symbol.iterator"**      | 一个为对象返回默认 Iterator 的方法。由 for-of 语句的语义调用。 |
|       @@match        |       **"Symbol.match"**        | 将正则表达式与字符串匹配的正则表达式方法。由 [String.prototype.match](https://262.ecma-international.org/6.0/#sec-string.prototype.match) 调用 |
|      @@replace       |      **"Symbol.replace"**       | 一个正则表达式方法，用于替换字符串的匹配子字符串。由 [String.prototype.replace](https://262.ecma-international.org/6.0/#sec-string.prototype.replace) 方法调用。 |
|       @@search       |       **"Symbol.search"**       | 返回与正则表达式匹配的字符串中的索引的正则表达式方法。由 [String.prototype.search](https://262.ecma-international.org/6.0/#sec-string.prototype.search) 方法调用 |
|      @@species       |      **"Symbol.species"**       | 一个函数值属性，它是用于创建派生对象的构造函数。             |
|    @@toPrimitive     |       "**Symbol.split**"        | 一个正则表达式方法，该方法在与正则表达式匹配的索引处拆分字符串。由 [String.prototype.split](https://262.ecma-international.org/6.0/#sec-string.prototype.split) 方法调用。 |
|    @@toStringTag     |    **"Symbol.toPrimitive"**     | 一种将对象转换为响应原始值的方法，由抽象操作 [ToPrimitive](https://262.ecma-international.org/6.0/#sec-toprimitive) 调用。 |
|    @@toStringTag     |    "**Symbol.toStringTag**"     | 一个 String 值属性，用于创建对象的默认字符串描述。被内置方法 [Object.prototype.toString](https://262.ecma-international.org/6.0/#sec-object.prototype.tostring) 访问。 |
|    @@unscopables     |    **"Symbol.unscopables"**     | 对象值属性，其自身的属性名称将会从从关联对象的 **with** 环境绑定中的属性名称里排除。 |

#### 6.1.6 Number 类型

Number 类型刚好有 18437736874454810627（即 2<sup>64</sup>-2<sup>53</sup>+3）个值，表示 IEEE 二进制浮点算术标准中指定的双精度 64 位格式 IEEE 754-2008 值，但 9007199254740990（ 即 2<sup>53</sup>-2）IEEE 标准的不同 "Not-a-Number" 值在 ECMAScript 中表示为单个特殊的 **NaN** 值。（请注意，**NaN** 值由程序表达式 **NaN** 产生。）在某些实现中，外部代码可能能够检测各种 Not-a-Number 值之间的差异，但是这种行为取决于实现。在 ECMAScript 代码中，所有 NaN 值彼此之间是无法区分的。

注：将 Number 值存储到其中后，在 ArrayBuffer（请参阅 [24.1](https://262.ecma-international.org/6.0/#sec-arraybuffer-objects)）中可能会观察到的位模式不一定与 ECMAScript 实现使用的 Number 值的内部表示相同。

还有两个其他的特殊值，称为正无穷大和负无穷大，简记 **+∞** 和 **−∞**。（注：两个值由程序表达式 **Infinity** 和 **-Infinity** 产生。）

另外 18437736874454810624 （即 2<sup>64</sup>-2<sup>53</sup>）个值被称为有限数。一半是整数一半是负数；每个有限负数都对应一个负值，大小相同。

需要注意的是有正 0 和负 0，简记 **+0** 和 **-0**。（注：两个值由程序表达式 **0** 和 **-0** 产生。）

18428729675200069632（即 2<sup>64</sup>-2<sup>53</sup>-2）个有限非零值为以下两类：

其中的 18428729675200069632 （即2<sup>64</sup>-2<sup>54</sup>-2）个被规范化，其形式为：$s×m×2^e$，其中 $s$ 为 +1 或 -1，$m$ 是一个小于 2<sup>53</sup> 的但不小于 2<sup>52</sup> 的正整数，$e$ 是一个取值范围为从 -1074 到 971 （包括端点）的正数。

剩下的 9007199254740990（即 2<sup>53</sup>-2）个非规范化值，其形式为：$s×m×2^e$，其中 $s$ 为 +1 或 -1，$m$ 是一个小于 2<sup>52</sup> 的正整数，$e$ 是一个取值范围为从 -1074。

请注意，所有大小不大于 2<sup>53</sup> 的正整数和负整数都可以在 Number 类型中表示（实际上，整数 0 具有 **+0** 和 **-0** 两种表示形式）。

如果有限数非零且用于表示它的整数 $m$（以上述两种形式之一表示）为奇数，则它具有奇数意义。 否则，它甚至具有偶数意义。

在本说明书中，短语「$x$ 的数值」，其中 x 表示确切的非零实数（甚至可能是无理数，例如 π）表示按以下方式选择的数值。考虑 Number 类型的所有有限值的集合，删除了 −0 并添加了两个其他在 Number 类型中无法表示的值，即 2<sup>1024</sup>（$+1×2^{53}×2^{971}$）和 −2<sup>1024</sup>（$-1×2^{53}×2^{971}$）。选择该集合中值最接近 $x$ 的成员。如果该集合的两个值相等接近，则选择一个具有偶数意义的值。为此，两个额外的值 2<sup>1024</sup> 和 -2<sup>1024</sup> 被认为具有偶数意义。最后，如果选择 2<sup>1024</sup>，则将其替换为 +∞；如果选择了-2<sup>1024</sup>，则将其替换为 -∞；如果选择了 +0，则当且仅当 $x$ 小于零时，才将其替换为 -0；其他任何选择的值均保持不变。 结果是 $x$ 的Number 值。（此过程完全符合 IEEE 754-2008 「四舍五入，并保持偶数」模式的行为。）

某些 ECMAScript 运算符仅处理特定范围内的整数，例如 -2<sup>31</sup> 至 2<sup>31</sup>-1（包括端点）或 0 至2<sup>16</sup>-1（包括端点）的范围。 这些运算符接受 Number 类型的任何值，但首先将每个此类值转换为期望范围内的整数值。 请参阅 [7.1](https://262.ecma-international.org/6.0/#sec-type-conversion). 中数字转换操作的说明。

#### 6.1.7 Object 类型

一个 Object 逻辑上是属性的集合。每个属性要么是一个数据属性，要么是一个访问器属性。

- *数据属性*将一个键值与一个 ECMAScript 值和一组 Boolean 特性关联。
- *访问器属性*将一个键值与一个或两个访问器函数和一组 Boolean 特性关联。访问器函数用于存储和获取与该属性相关的 ECMAScript 值。

属性通过键值来区分。一个属性的键值要么是一个 ECMAScript String 值，要么是一个 ECMAScript Symbol 值。所有的 String 值和 Symbol 值包括空字符串都可以用作属性键。*属性名*称是作为 String 值的属性键。

*整数索引*是一个 String 值的属性键，它是规范的数字字符串（见 [7.1.16](https://262.ecma-international.org/6.0/#sec-canonicalnumericindexstring)），其数值为 +0 到 2<sup>53</sup>-1 （包扩端点）之间的正整数。 *数组索引*是一个整数索引，其数值 $i$ 处于 $+0≤i <2^{32}-1$ 的范围内。

属性键用于访问属性及其值。属性有两种访问方式：*get* 和 *set*，分别对应取值和赋值。通过 get 和 set 访问可访问的属性包括作为对象直接一部分的*自身属性*和由另一个关联对象通过属性继承关系提供的*继承属性*。 继承的属性可以是关联对象的自己的属性或继承的属性。一个对象的每个自己的属性必须各自具有与该对象的其他自己的属性的键值不同的键值。

从逻辑上讲，所有对象都是属性的集合，但是有多种形式的对象在其访问和操作其属性时具有不同的语义。*普通对象*是最常见的对象形式，并具有默认的对象语义。*奇异对象*是其属性语义与默认语义有任何不同的任何形式的对象。

##### 6.1.7.1 属性特性

本规范中的特性用于定义和解释对象属性的状态。一个数据属性将一个键值与表 2 中列出的特性关联。

##### 表2 —— 数据属性的特性

| 特性名称         |        值域        | 描述                                                         |
| :--------------- | :----------------: | :----------------------------------------------------------- |
| [[Value]]        | 任何 ECMAScript 值 | 通过属性的 get 访问的值                                      |
| [[Writable]]     |      Boolean       | 如果为 false，通过 ECMAScript 代码使用 [[Set]] 去修改属性的 [[Value]] 特性的尝试不会成功 |
| [[Enumerable]]   |      Boolean       | 如果为 true，属性将可以通过 for-in 枚举（见 [13.7.5](https://262.ecma-international.org/6.0/#sec-for-in-and-for-of-statements)），否则被认为不可枚举。 |
| [[Configurable]] |      Boolean       | 如果为 false，删除该属性、修改该属性为一个访问器属性、修改除了 [[Value]] 的特性或者将 [[Writable]] 特性修改为 false 的尝试将会失败 |

访问器属性将一个键值与表 3 列出的特性关联。

##### 表3 —— 访问器属性的特性

| 特性名称         | 值域                | 描述                                                         |
| :--------------- | ------------------- | ------------------------------------------------------------ |
| [[Get]]          | Object \| Undefined | 如果值是一个 Object，则必须是一个函数对象。每次 get 访问该属性时，用一个空参数列表调用函数的内部方法（见 [Table 6](https://262.ecma-international.org/6.0/#table-6)） [[Call]]来获取属性值。 |
| [[Set]]          | Object \| Undefined | 如果是值一个 Object，则必须是一个函数对象。每次 set 访问该属性时，用一个包含分配值为其唯一参数的参数列表调用函数内部方法（见 [Table 6](https://262.ecma-international.org/6.0/#table-6)）[[Call]] 。属性的内部方法 [[Set]] 的效果可能（但并不是必须）会对属性的内部方法 [[Get]] 的后续调用的返回值产生影响。 |
| [[Enumerable]]   | Boolean             | 如果为 true，属性将可以通过 for-in 枚举（见 [13.7.5](https://262.ecma-international.org/6.0/#sec-for-in-and-for-of-statements)），否则被认为不可枚举。 |
| [[Configurable]] | Boolean             | 如果为 false，删除属性、修改属性为一个数据属性或者修改属性的特性尝试将会失败 |

如果此规范未明确指定属性的特性的初始值，则使用表 4 中定义的默认值。

##### 表 4 —— 默认特性值

| 特性名           | 默认值    |
| ---------------- | --------- |
| [[Value]]        | undefined |
| [[Get]]          | undefined |
| [[Set]]          | undefined |
| [[Writable]]     | false     |
| [[Enumerable]]   | false     |
| [[Configurable]] | false     |

##### 6.1.7.2 对象的内部方法和内部插槽

ECMAScript 中对象的实际语义是通过称为*内部方法*的算法指定的。ECMAScript 引擎中的每个对象都与一组内部方法相关联，这些内部方法定义了其运行时行为。这些内部方法并不是 ECMAScript 语言的一部分。本规范定义他们仅仅出于说明的目的。但是，ECMAScript 实现中的每个对象都必须按照与其关联的内部方法指定的方式运行。实现的确切方式由实现方式决定。

内部方法名称是多态的。这意味着，当一个通用的内部方法名称被调用时，不同的对象值可能执行不同的算法。调用内部方法的实际对象是调用的「目标」。 如果在运行时算法的实现尝试使用该对象不支持的对象的内部方法，则将引发 **TypeError** 异常。

内部插槽对应于与对象关联并由各种 ECMAScript 规范算法使用的内部状态。内部插槽不是对象属性，也不是继承的。根据特定的内部插槽规范，这种状态可以由任何 ECMAScript 语言类型的值或特定的 ECMAScript 规范类型的值组成。除非另有明确指定，内部插槽是在创建对象的过程中分配的，并且可能不会动态添加到对象中。除非另有明确规定，内部插槽的初始值为 **undefined**。本规范中的各种逻辑都会创建有内部插槽的对象。但是，ECMAScript 语言没有提供直接的方式来关联内部插槽和对象。

在本规范中，内部方法和内部插槽通过由双方括号 "[[]]" 包围的名称来区分。

表 5 总结了本规范使用的用于所有通过 ECMAScript 代码创建或操纵的对象的「基本内部方法」。每个对象都必须有所有基本内部方法的算法。但是，所有对象并不一定要为那些方法使用相同的的算法。

表 5 和其他相似表的「签名」那一列描述了内部方法的调用模式。调用模式始终包括带括号的描述性参数名称列表。如果参数名称与 ECMAScript 类型名称相同，则参数值必须是参数名描述的那个类型。如果一个内部方法显式返回一个值，那么它的参数列表后面会紧跟一个 "→" 符号以及返回值的类型名。签名中使用的类型名称是指第 6 章中定义的类型，并由以下附加名称扩展。"any" 表示该值可以是任何 ECMAScript 语言类型。一个内部方法隐式返回一个 [6.2.2](https://262.ecma-international.org/6.0/#sec-completion-record-specification-type) 中描述的 [Completion Record](https://262.ecma-international.org/6.0/#sec-completion-record-specification-type)。除了其参数外，内部方法始终可以访问作为方法调用目标的对象。

##### 表 5 —— 基本内部方法

|       内部方法        |                             签名                             | 描述                                                         |
| :-------------------: | :----------------------------------------------------------: | ------------------------------------------------------------ |
|  [[GetPrototypeOf]]   |                   () **→** Object \| Null                    | 确定为该对象提供继承属性的对象。如果为 **null** 说明该对象没有继承属性。 |
|  [[SetPrototypeOf]]   |               (*Object* \| Null) **→** Boolean               | 将此对象与另一个提供继承属性的对象关联。传 **null** 时说明没有继承属性。返回 **true** 时表明操作成功，否则说明操作失败。 |
|   [[IsExtensible]]    |                      ( ) **→** Boolean                       | 确定是否允许为该对象添加额外属性。                           |
| [[PreventExtensions]] |                      ( ) **→** Boolean                       | 控制是否可以将新属性添加到该对象。 如果操作成功，则返回 **true**；否则返回 **false**。 |
|  [[GetOwnProperty]]   | (*propertyKey*) **→** Undefined \| [Property Descriptor](https://262.ecma-international.org/6.0/#sec-property-descriptor-specification-type) | 为该对象其 key 为 *propertyKey* 的自有属性返回一个 Property Descriptor，如果没有这样的属性，则返回 **undefined**。 |
|    [[HasProperty]]    |                (*propertyKey*) **→** Boolean                 | 返回一个 Boolean 值表示该对象是否有一个其 key 为 *propertyKey* 的属性，不管是自有还是继承。 |
|        [[Get]]        |           (*propertyKey*, *Receiver*) **→** *any*            | 返回该对象中其 key 为 *propertyKey* 的属性的值。如果必须执行任何 ECMAScript 代码以检索属性值，那么在对代码求值的时候 *Receiver* 则被用作 **this** 值。 |
|        [[Set]]        |     (*propertyKey*,*value*, *Receiver*) **→** *Boolean*      | 设置该对象中其 key 为 *propertyKey* 的属性的值为 *value*。如果必须执行任何 ECMAScript 代码以检索属性值，那么在对代码求值的时候 *Receiver* 则被用作 **this** 值。如果设置成功则返回 **true**，否则返回 **false**。 |
|      [[Delete]]       |                (*propertyKey*) **→** Boolean                 | 删除该对象中其 key 为 *propertyKey* 的属性。如果该对象上不再存在删除的属性则返回 **true**，否则返回 **false**。 |
| [[DefineOwnProperty]] |     (*propertyKey*, *PropertyDescriptor*) **→** Boolean      | 创建或改变该对象中其 key 为 *propertyKey* 的自有属性，使其具有 *PropertyDescriptor* 所描述的状态。如果属性被成功创建或更新则返回 **true**，否则返回 **false**。 |
|     [[Enumerate]]     |                        () *→* Object                         | 返回一个迭代器对象，该对象生成对象的字符串键可枚举属性的 key。 |
|  [[OwnPropertyKeys]]  | ()**→**[List](https://262.ecma-international.org/6.0/#sec-list-and-record-specification-type) of propertyKey | 返回一个其元素为该对象所有自有属性的 key 的 [List](https://262.ecma-international.org/6.0/#sec-list-and-record-specification-type) |

表 6 总结了那些可以作为函数调用的对象所支持其他基本内部方法。「函数对象」是指支持 [[Call]] 内部方法的对象。「构造器」（也称为构造器函数）是指支持 [[Constructor]] 内部方法的对象。

##### 表 6 —— 函数对象的其他基本内部方法

|    内部方法     |                             签名                             | 描述                                                         |
| :-------------: | :----------------------------------------------------------: | ------------------------------------------------------------ |
|    [[Call]]     | (*any*, a [List](https://262.ecma-international.org/6.0/#sec-list-and-record-specification-type) of *any*) **→** *any* | 执行与该对象相关的代码。通过函数调用表达式触发。内部方法的参数值是 **this** 值和一个通过调用表达式传递给该函数的参数列表。实现此内部方法的对象是「可调用的」。 |
| [[Constructor]] | (a [List](https://262.ecma-international.org/6.0/#sec-list-and-record-specification-type) of *any*, Object) **→** Object | 创建一个对象。通过 **new** 或 **super** 操作符触发。内部方法的第一个参数是一个包含操作符传递的参数的列表。第二个参数是一个 **new** 操作符初始应用的对象。实现此内部方法的对象被称为「构造器」。函数对象不一定是构造函数，此类非构造函数函数的对象没有 [[Construct]] 内部方法。 |

第 9 章规定了普通对象和标准奇异对象的基本内部方法的语义。如果一个奇异对象的内部方法的任何一个指定用法不被某个实现支持，那么尝试这个用法就必须抛出一个 **TypeError**。

##### 6.1.7.3 基本内部方法的不变量

ECMAScript 引擎的对象内部方法必须符合以下指定的不变量列表。 普通 ECMAScript 对象以及本规范中的所有标准奇异对象都维护了这些不变量。 ECMAScript Proxy 对象通过对 [[ProxyHandler]] 对象上调用的陷阱的结果进行运行时检查来维护这些不变量。

任何提供奇异对象的实现都必须为对象维护那些不变量。违反这些不变式可能会导致 ECMAScript 代码具有不可预测的行为并引发安全问题。但是，违反这些不变量绝不能损害实现的内存安全性。

一个实现禁止以任何方式规避这些不变量，例如通过提供实现基本内部方法功能而不使用其不变量的替代接口。

定义：

- 内部方法的 *target* 是内部方法被调用的对象
- 当一个 target 的 [[IsExtensible]] 内部方法返回 false 或 [[PreventExtensions]] 返回 true 时，那么它是不可扩展的
- 不存在的属性是指不可扩展的 target 的自有属性里不存在的属性
- 对 *SameValue* 的所有引用均根据 [7.2.9](https://262.ecma-international.org/6.0/#sec-samevalue) 中指定的 [SameValue](https://262.ecma-international.org/6.0/#sec-samevalue) 算法的定义。

**[[GetPrototypeOf]] ( )**

- 返回值的类型必须为 Object 或者 Null。
- 如果 target 是不可扩展的，而且 [[GetPrototypeOf]] 的返回值是 v，那么未来任何对 [[GetPrototypeOf]] 的调用得到的返回值与 v 是 sameValue。

注 1：一个对象的原型链应该是有限的长度（也就是说，从任何对象开始，对 [[GetPrototypeOf]] 的结果递归调用内部方法 [[GetPrototypeOf]] 最终都值指向 null 值）。但是，如果原型链中包括任何不使用 [[GetPrototypeOf]] 普通对象定义的奇异对象，则此要求不能作为对象级别不变而强制执行。当访问对象属性时，这样的环形原型链可能会导致无限循环。

**[[SetPrototypeOf]] (V)**

- 返回值的类型必须是 Boolean。
- 如果 target  是不可扩展的，[[SetPrototypeOf]] 必须返回 false，除非 V 与 target 观察到的 [[GetPrototypeOf]] 值是 SameValue。

**[[PreventExtensions]] ( )**

- 返回值的类型必须是 Boolean。
- 如果 [[PreventExtensions]] 返回 true，那么后续所有在 target 上对 [[IsExtensible]] 的调用必须返回 false，而且 target 被认为是不可扩展的。

**[[GetOwnProperty]] (P)**

- 返回值得类型必须要么是 Undefined 或者是 [Property Descriptor](https://262.ecma-international.org/6.0/#sec-property-descriptor-specification-type)。
- 如果返回值的类型是 [Property Descriptor](https://262.ecma-international.org/6.0/#sec-property-descriptor-specification-type)，那么其值必须是一个完整的属性描述（见 [6.2.4.6](https://262.ecma-international.org/6.0/#sec-completepropertydescriptor)）。
- 如果属性 P 是一个其 [[Value]] 特性值为 v、[[Writable]] 和 [[Configurable]] 特性值均为 false，那么后续调用 [[GetOwnProperty]] (P) 得到的返回值里的 [[Value]] 特性值必须与 v 是 SameValue。
- 如果 P 除了 [[Writable]] 以外的特性会随着时间发生变化或是消失，那么 P 的 [[Configurable]] 特性值必须为 true。
- 如果 [[Writable]] 特性值会从 false 变为 true，那么 [[Configurable]] 特性值必须为 true。
- 如果 target 不可扩展而且 P 又不存在，那么后续任何对 target 的 [[GetOwnProperty]] (P) 的调用都必须将 P 描述为不存在（即 [[GetOwnProperty]] (P) 必须返回 undefined）。

注 2：由于第三个不变式，如果将属性描述为数据属性，并且随着时间的推移它可能返回不同的值，则 Desc.[[Writable]] 和 Desc.[[Configurable]] 属性中的一个或两个必须为 true 即使没有其他内部方法公开更改值的机制。

**[[DefineOwnProperty]] (P, Desc)**

- 返回值的类型必须是 Boolean。
- 当 P 先前已经被视为是 target 的不可配置的自有属性时，[[DefineOwnProperty]] 必须返回 false，除非出现以下任何一种情况：
  1. P 是一个不可配置但可写的自有数据属性。一个不可配置但可写的自有数据属性可以变成不可配置、不可写的数据属性。
  2. 所有 Desc 里的特性与 P 对应的特性均是 SameValue。
- 如果 target 是不可扩展的而且 P 是不存在的。那么 [[DefineOwnProperty]] (P, Desc) 必须返回 false。即一个不可扩展的 target 对象不能添加新的属性。

**[[HasProperty]] ( P )**

- 返回值类型必须是 Boolean
- 如果 P 先前已经被视为是 target 的不可配置的自有数据属性或自有访问器属性，那么 [[HasProperty]]  必须返回 true。

**[[Get]] (P, Receiver)**

- 如果 P 先前被视为 target 的不可扩展、不可写且其值为 v 的自有数据属性，那么 [[Get]] 的返回值必须与 v 是 SameValue。
- 如果 P 先前被视为 target 的不可扩展的自有访问器属性，且其 [[Get]] 特性值为 undefined，那么 [[Get]] 操作必须返回 undefined。

**[[Set]] ( P, V, Receiver)**

- 返回值的类型必须是 Boolean。
- 如果 P 被视为是不可配置、不可写的自有数据属性，那么 [[Set]] 必须返回 false，除非 V 与 P 的 [[Value]] 是 SameValue。
- 如果 P 被视为不可配置的自有访问器属性而且其 [[Set]] 特性为 undefined，那么 [[Set]] 操作必须返回 false。

**[[Delete]] ( P )**

- 返回值类型必须为 Boolean。
- 如果 P 被视为是不可配置的自有数据属性或自有访问器属性，那么 [[Delete]] 必须返回 false。

**[[Enumerate]] ( )**

- 返回值类型必须是 Object。

**[[OwnPropertyKeys]] ( )**

- 返回值类型必须是 [List](https://262.ecma-international.org/6.0/#sec-list-and-record-specification-type)。
- 返回的 [List](https://262.ecma-international.org/6.0/#sec-list-and-record-specification-type) 里的元素类型是 String 或者 Symbol。
- 返回的 [List](https://262.ecma-international.org/6.0/#sec-list-and-record-specification-type) 必须至少包含先前被观察的所有不可配置的自有属性的 key。
- 如果对象时不可扩展的，那返回的 [List](https://262.ecma-international.org/6.0/#sec-list-and-record-specification-type) 必须仅包含能通过 [[GetOwnProperty]] 观察到的属性的 key。

**[[Construct]] ( )**

●  返回值的类型必须是 Object。

##### 6.1.7.4 熟知的固有对象

熟知的固有函数是由本规范的算法明确引用并且通常具有特定于 [Realm](https://262.ecma-international.org/6.0/#sec-code-realms) 标识的内置对象。（译者注：固有对象是内置对象的子集？）除非另有说明，否则每个内部对象实际上对应于一组相似对象，每个 Realm 一个。

在本规范中，诸如 ％name％ 之类的引用表示与该名称对应的与 [the current Realm](https://262.ecma-international.org/6.0/#sec-execution-contexts) 相关联的固有对象。 [the current Realm](https://262.ecma-international.org/6.0/#sec-execution-contexts) 及其内在函数的确定在 [8.3](https://262.ecma-international.org/6.0/#sec-execution-contexts) 中描述。 表 7 列出了熟知的固有对象。

##### 表 7 —— 熟知的固有对象

| 固有名称                                                     |                           全局名称                           | ECMAScript 语言关联                                          |
| ------------------------------------------------------------ | :----------------------------------------------------------: | ------------------------------------------------------------ |
| %Array%                                                      |                          **Array**                           | `Array` 构造器 ([22.1.1](https://262.ecma-international.org/6.0/#sec-array-constructor)) |
| %ArrayBuffer%                                                |                       **ArrayBuffer**                        | `ArrayBuffer` 构造器 ([24.1.2](https://262.ecma-international.org/6.0/#sec-arraybuffer-constructor)) |
| %ArrayBufferPrototype%                                       | [ArrayBuffer.prototype](https://262.ecma-international.org/6.0/#sec-arraybuffer.prototype) | ％ArrayBuffer％数据属性 `prototype` 的初始值。               |
| %ArrayIteratorPrototype%                                     |                                                              | 数组迭代器对象的原型  ([22.1.5](https://262.ecma-international.org/6.0/#sec-array-iterator-objects)) |
| %ArrayPrototype%                                             |                     **Array.prototype**                      | ％Array％数据属性 `prototype` 的初始值 ([22.1.3](https://262.ecma-international.org/6.0/#sec-properties-of-the-array-prototype-object)) |
| %ArrayProto_values%                                          | [Array.prototype.values](https://262.ecma-international.org/6.0/#sec-array.prototype.values) | ％ArrayPrototype％的values 数据属性的初始值 ([22.1.3.29](https://262.ecma-international.org/6.0/#sec-array.prototype.values)) |
| %Boolean%                                                    |                         **Boolean**                          | `Boolean` 构造器 ([19.3.1](https://262.ecma-international.org/6.0/#sec-boolean-constructor)) |
| %BooleanPrototype%                                           |                    **Boolean.prototype**                     | ％Boolean％数据属性 `prototype` 的初始值  ([19.3.3](https://262.ecma-international.org/6.0/#sec-properties-of-the-boolean-prototype-object)) |
| %DataView%                                                   |                         **DataView**                         | `DataView` 构造器 ([24.2.2](https://262.ecma-international.org/6.0/#sec-dataview-constructor)) |
| %DataViewPrototype%                                          | [DataView.prototype](https://262.ecma-international.org/6.0/#sec-dataview.prototype) | ％DataView％数据属性 `prototype` 的初始值                    |
| %Date%                                                       |                           **Date**                           | `Date` 构造器                                                |
| %DatePrototype%                                              |                      **Date.prototype**                      | %Date% 数据属性 `prototype` 的初始值                         |
| %decodeURI%                                                  |                        **decodeURI**                         | `decodeURI` 函数                                             |
| %decodeURIComponent%                                         |                    **decodeURIComponent**                    | `decodeURIComponent` 函数                                    |
| %encodeURI%                                                  |                        **encodeURI**                         | `encodeURI` 函数                                             |
| %encodeURIComponent%                                         |                    **encodeURIComponent**                    | `encodeURIComponent` 函数                                    |
| %Error%                                                      |                          **Error**                           | `Error` 构造器                                               |
| %ErrorPrototype%                                             |                     **Error.prototype**                      | %Error% 数据属性 `prototype` 的初始值                        |
| %eval%                                                       |                           **eval**                           | `eval` 函数                                                  |
| %EvalError%                                                  |                        **EvalError**                         | `EvalError` 构造器                                           |
| %EvalErrorPrototype%                                         |                     EvalError.prototype                      | %EvalError% 数据属性 `prototype` 的初始值                    |
| %Float32Array%                                               | [Float32Array](https://262.ecma-international.org/6.0/#sec-float32array) | `Float32Array` 构造器                                        |
| %Float32ArrayPrototype%                                      |                  **Float32Array.prototype**                  | %Float32Array% 数据属性 `prototype` 的初始值                 |
| %Float64Array%                                               | [Float64Array](https://262.ecma-international.org/6.0/#sec-float64array) | `Float64Array` 构造器                                        |
| %Float64ArrayPrototype%                                      |                  **Float64Array.prototype**                  | %Float64Array% 数据属性 `prototype` 的初始值                 |
| %Function%                                                   |                         **Function**                         | `Function` 构造器                                            |
| %FunctionPrototype%                                          |                    **Function.prototype**                    | %Function% 数据属性 `prototype` 的初始值                     |
| %Generator%                                                  |                                                              | %GeneratorFunction% 数据属性 `prototype` 的初始值            |
| %GeneratorFunction%                                          |                                                              | generator 对象的构造器 ([25.2.1](https://262.ecma-international.org/6.0/#sec-generatorfunction-constructor)) |
| %GeneratorPrototype%                                         |                                                              | %Generator% 数据属性 `prototype` 的初始值                    |
| %Int8Array%                                                  | [Int8Array](https://262.ecma-international.org/6.0/#sec-int8array) | `Int8Array` 构造器                                           |
| %Int8ArrayPrototype%                                         |                   **Int8Array.prototype**                    | %Int8Array% 数据属性 `prototype` 的初始值                    |
| %Int16Array%                                                 | [Int16Array](https://262.ecma-international.org/6.0/#sec-int16array) | `Int16Array` 构造器                                          |
| %Int16ArrayPrototype%                                        |                   **Int16Array.prototype**                   | %Int16Array% 数据属性 `prototype` 的初始值                   |
| %Int32Array%                                                 | [Int32Array](https://262.ecma-international.org/6.0/#sec-int32array) | `Int32Array` 构造器                                          |
| %Int32ArrayPrototype%                                        |                   **Int32Array.prototype**                   | %Int32Array% 数据属性 `prototype` 的初始值                   |
| %isFinite%                                                   |                           isFinite                           | `isFinite` 函数                                              |
| %isNaN%                                                      |                            isNaN                             | `isNaN` 函数                                                 |
| %IteratorPrototype%                                          |                                                              | 所有标准内置迭代器对象间接继承的对象                         |
| %JSON%                                                       |                           **JSON**                           | `JSON` 对象 ([24.3](https://262.ecma-international.org/6.0/#sec-json-object)) |
| %Map%                                                        |                           **Map**                            | `Map` 构造器                                                 |
| %MapIteratorPrototype%                                       |                                                              | Map 迭代器对象的原型 ([23.1.5](https://262.ecma-international.org/6.0/#sec-map-iterator-objects)) |
| %MapPrototype%                                               |                      **Map.prototype**                       | %Map% 数据属性 `prototype` 的初始值                          |
| %Math%                                                       |                           **Math**                           | `Math` 对象([20.2](https://262.ecma-international.org/6.0/#sec-math-object)) |
| %Number%                                                     |                          **Number**                          | `Number` 构造器 ([20.1.1](https://262.ecma-international.org/6.0/#sec-number-constructor)) |
| %NumberPrototype%                                            |                     **Number.prototype**                     | %Number% 数据属性 `prototype` 的初始值                       |
| %Object%                                                     |                          **Object**                          | **Object** 构造器 ([19.1.1](https://262.ecma-international.org/6.0/#sec-object-constructor)) |
| %ObjectPrototype%                                            |                       Object.prototype                       | **Object** 数据属性 `prototype` 的初始值                     |
| %ObjProto_toString%                                          |            **Object.prototype.**<br/>**toString**            | **ObjectPrototype** 数据属性 **toString** 的初始值 ([19.1.3.6](https://262.ecma-international.org/6.0/#sec-object.prototype.tostring)) |
| %parseFloat%                                                 |                        **parseFloat**                        | **parseFloat** 函数 ([18.2.4](https://262.ecma-international.org/6.0/#sec-parsefloat-string)) |
| %parseInt%                                                   |                         **parseInt**                         | **parseInt** 函数 ([18.2.5](https://262.ecma-international.org/6.0/#sec-parseint-string-radix)) |
| %Promise%                                                    |                         **Promise**                          | **Promise** 构造器 ([25.4.3](https://262.ecma-international.org/6.0/#sec-promise-constructor)) |
| %PromisePrototype%                                           |                    **Promise.prototype**                     | %Promise% 数据属性 `prototype` 的初始值                      |
| %Proxy%                                                      |                          **Proxy**                           | **Proxy** 构造器 ([26.2.1](https://262.ecma-international.org/6.0/#sec-proxy-constructor)) |
| %RangeError%                                                 |                        **RangeError**                        | **RangeError** 构造器 ([19.5.5.2](https://262.ecma-international.org/6.0/#sec-native-error-types-used-in-this-standard-rangeerror)) |
| %RangeErrorPrototype%                                        |                   **RangeError.prototype**                   | The initial value of the `prototype` property of %RangeError% |
| %ReferenceError%                                             |                      **ReferenceError**                      | The `ReferenceError` constructor ([19.5.5.3](https://262.ecma-international.org/6.0/#sec-native-error-types-used-in-this-standard-referenceerror)) |
| %ReferenceErrorPrototype%                                    |                 **ReferenceError.prototype**                 | The initial value of the `prototype` property of %ReferenceError% |
| %Reflect%                                                    |                         **Reflect**                          | The `Reflect` object ([26.1](https://262.ecma-international.org/6.0/#sec-reflect-object)) |
| %RegExp%                                                     |                          **RegExp**                          | The `RegExp` constructor ([21.2.3](https://262.ecma-international.org/6.0/#sec-regexp-constructor)) |
| %RegExpPrototype%                                            |                       RegExp.prototype                       | The initial value of the `prototype` data property of %RegExp% |
| %Set%                                                        |                           **Set**                            | `Set` 构造器                                                 |
| %SetIteratorPrototype%                                       |                                                              | The prototype of Set iterator objects ([23.2.5](https://262.ecma-international.org/6.0/#sec-set-iterator-objects)) |
| %SetPrototype%                                               |                      **Set.prototype**                       | `Date` 数据属性The initial value of the `prototype` data property of %Set% |
| %String%                                                     |                          **String**                          | The `String` constructor ([21.1.1](https://262.ecma-international.org/6.0/#sec-string-constructor)) |
| %StringIteratorPrototype%                                    |                                                              | The prototype of String iterator objects ([21.1.5](https://262.ecma-international.org/6.0/#sec-string-iterator-objects)) |
| %StringPrototype%                                            |                     **String.prototype**                     | The initial value of the `prototype` data property of %String% |
| %Symbol%                                                     |                          **Symbol**                          | The `Symbol` constructor ([19.4.1](https://262.ecma-international.org/6.0/#sec-symbol-constructor)) |
| %SymbolPrototype%                                            |                     **Symbol.prototype**                     | The initial value of the `prototype` data property of %Symbol%. ([19.4.3](https://262.ecma-international.org/6.0/#sec-properties-of-the-symbol-prototype-object)) |
| %SyntaxError%                                                |                       **SyntaxError**                        | The `SyntaxError` constructor ([19.5.5.4](https://262.ecma-international.org/6.0/#sec-native-error-types-used-in-this-standard-syntaxerror)) |
| %SyntaxErrorPrototype%                                       |                  **SyntaxError.prototype**                   | The initial value of the `prototype` property of %SyntaxError% |
| [%ThrowTypeError%](https://262.ecma-international.org/6.0/#sec-%throwtypeerror%) |                                                              | A function object that unconditionally throws a new instance of %TypeError% |
| %TypedArray%                                                 |                                                              | The super class of all typed Array constructors ([22.2.1](https://262.ecma-international.org/6.0/#sec-%typedarray%-intrinsic-object)) |
| %TypedArrayPrototype%                                        |                                                              | The initial value of the `prototype` property of %TypedArray% |
| %TypeError%                                                  |                        **TypeError**                         | **TypeError** 构造器 ([19.5.5.5](https://262.ecma-international.org/6.0/#sec-native-error-types-used-in-this-standard-typeerror)) |
| %TypeErrorPrototype%                                         |                   **TypeError.prototype**                    | %TypeError% 数据属性 `prototype` 的初始值                    |
| %Uint8Array%                                                 | [Uint8Array](https://262.ecma-international.org/6.0/#sec-uint8array) | [Uint8Array](https://262.ecma-international.org/6.0/#sec-uint8array) 构造器 ([22.2](https://262.ecma-international.org/6.0/#sec-typedarray-objects)) |
| %Uint8ArrayPrototype%                                        |                   **Uint8Array.prototype**                   | %Uint8Array% 数据属性 `prototype` 的初始值                   |
| %Uint8ClampedArray%                                          | [Uint8ClampedArray](https://262.ecma-international.org/6.0/#sec-uint8clampedarray) | [Uint8ClampedArray](https://262.ecma-international.org/6.0/#sec-uint8clampedarray) 构造器 ([22.2](https://262.ecma-international.org/6.0/#sec-typedarray-objects)) |
| %Uint8ClampedArrayPrototype%                                 | [Uint8ClampedArray](https://262.ecma-international.org/6.0/#sec-uint8clampedarray)**.**prototype | %Uint8ClampedArray% 数据属性 `prototype` 的初始值            |
| %Uint16Array%                                                | [Uint16Array](https://262.ecma-international.org/6.0/#sec-uint16array) | [Uint16Array](https://262.ecma-international.org/6.0/#sec-uint16array) 构造器 ([22.2](https://262.ecma-international.org/6.0/#sec-typedarray-objects)) |
| %Uint16ArrayPrototype%                                       |                  **Uint16Array.prototype**                   | %Uint16Array% 数据属性 `prototype` 的初始值                  |
| %Uint32Array%                                                | [Uint32Array](https://262.ecma-international.org/6.0/#sec-uint32array) | [Uint32Array](https://262.ecma-international.org/6.0/#sec-uint32array) 构造器 ([22.2](https://262.ecma-international.org/6.0/#sec-typedarray-objects)) |
| %Uint32ArrayPrototype%                                       |                  **Uint32Array.prototype**                   | %Uint32Array% 数据属性 `prototype` 的初始值                  |
| %URIError%                                                   | [URIError](https://262.ecma-international.org/6.0/#sec-constructor-properties-of-the-global-object-urierror) | [URIError](https://262.ecma-international.org/6.0/#sec-constructor-properties-of-the-global-object-urierror) 构造器 ([19.5.5.6](https://262.ecma-international.org/6.0/#sec-native-error-types-used-in-this-standard-urierror)) |
| %URIErrorPrototype%                                          |                    **URIError.prototype**                    | %URIError% 数据属性 `prototype` 的初始值                     |
| %WeakMap%                                                    |                         **WeakMap**                          | **WeakMap** 构造器([23.3.1](https://262.ecma-international.org/6.0/#sec-weakmap-constructor)) |
| %WeakMapPrototype%                                           | [WeakMap.prototype](https://262.ecma-international.org/6.0/#sec-weakmap.prototype) | %WeakMap% 数据属性 `prototype` 的初始值                      |
| %WeakSet%                                                    |                         **WeakSet**                          | **WeakSet** 构造器 ([23.4.1](https://262.ecma-international.org/6.0/#sec-weakset-constructor)) |
| %WeakSetPrototype%                                           | [WeakSet.prototype](https://262.ecma-international.org/6.0/#sec-weakset.prototype) | %WeakSet% 数据属性 `prototype` 的初始值                      |

### 6.2 ECMAScript 规范类型

规范类型对应于算法中用于描述 ECMAScript 语言构造和 ECMAScript 语言类型的语义的元值。规范类型为：[Reference](https://262.ecma-international.org/6.0/#sec-reference-specification-type), [List](https://262.ecma-international.org/6.0/#sec-list-and-record-specification-type), [Completion](https://262.ecma-international.org/6.0/#sec-completion-record-specification-type), [Property Descriptor](https://262.ecma-international.org/6.0/#sec-property-descriptor-specification-type), [Lexical Environment](https://262.ecma-international.org/6.0/#sec-lexical-environments), [Environment Record](https://262.ecma-international.org/6.0/#sec-environment-records), and [Data Block](https://262.ecma-international.org/6.0/#sec-data-blocks)。规范类型值是不一定对应于 ECMAScript 实现中的任何特定实体的规范制品。规范类型值可用于描述 ECMAScript 表达式求值的中间结果，但是此类值不能存储为对象的属性或 ECMAScript 语言变量的值。

#### 6.2.1 List 规范类型 和 Record 规范类型

List 类型用于解释变量列表在 **new** 表达式、函数调用的以及其它需要简单的值的有序列表的算法中对参数列表（见 [12.3.6](https://262.ecma-international.org/6.0/#sec-argument-lists)）的求值。List 类型的值是包含各个值的列表元素的简单排序序列。这些序列可以是任何长度。 列表的元素可以使用 0 起点索引随机访问。为了符号上的方便，可以使用类似数组的语法来访问 List 元素。例如，*arguments*[2] 是表示 List 参数的第 3 个元素的简写。

为方便起见，在本规范中，可以使用文字语法来表示新的 List 值。例如，«1、2» 定义具有两个元素的 List 值，每个元素都被初始化为特定值。 一个新的空列表可以表示为 «»。

Record 类型用于描述本规范算法内的数据聚合。Record 类型值包含一个或多个命名字段。 每个字段的值可以是 ECMAScript 值，也可以是由与 Record 类型关联的名称表示的抽象值。 字段名称始终用双括号括起来，例如 [[value]]。

为方便起见，在本规范中，可以使用类似于对象字面量的语法来表示 Record 值。 例如，`{[[field1]]：42，[[field2]]：false，[[field3]]：empty}` 定义了一个 Record 值，该值具有三个字段，每个字段都被初始化为特定值。 字段名称顺序不重要。 任何未明确列出的字段均视为不存在。

在规范文本和算法中，点符号可用于指代 Record 值的特定字段。例如，如果 R 是上一段中显示的记录，则 R.[[field2]] 是“R 的名为 [[field2]] 的字段”的简写。

可以命名常用 Record 字段组合的模式，并且该名称可以用作字面 Record 值的前缀，以标识所描述的特定类型的聚合。 例如：PropertyDescriptor {[[Value]]：42，[[Writable]]：false，[[Configurable]]：true}。

#### 6.2.2 Completion Record 规范类型

Completion 类型是一个 Record，用于解释值和控制流的运行时传播，例如执行非本地控制转移的语句（**break**，**continue**，**return** 和 **throw**）的行为。

Completion 类型的值是其字段在表 8 中定义的 Record 值

##### 表 8 —— Completion Record 字段

| 字段       |                              值                              | 意义                     |
| ---------- | :----------------------------------------------------------: | :----------------------- |
| [[type]]   | **normal**、**break**、**continue**、**return**、**throw** 之一 | 发生的完成类型。         |
| [[value]]  |                任意 ECMAScript 语言值或者为空                | 生成的值                 |
| [[target]] |                 任意 ECMAScript 字符串或为空                 | 定向控制转移的目标标签。 |

术语  "abrupt completion" 指的是任何其 [[type]] 值不是 **normal** 的 completion。

##### 6.2.2.1 NormalCompletion

有一个参数的抽象操作 NormalCompletion 比如：

1. Return NomralCompletion(*argument*)

是下面定义的简写：

1. Return Completion{[[type]]: nomral, [[value]]: *argument*, [[target]]: empty}

##### 6.2.2.2 隐式 Completion Values

本规范的算法经常隐式地返回 [[type]] 字段值为 **normal** 的 Completion Record。除非从上下文中可以明显看出，否则算法语句将返回一个非 "Completion Record" 的值，比如：

1. Return **"Infinity"**

与下面同义：

1. Return NormalCompletion(**"Infinity"**)

但是，如果一个 "return" 语句的值表达式是一个 Completion Record 的构造字面量，则返回结果 Completion Record。如果值表达式是对抽象操作的调用，则返回抽象操作生成的 Completion Record。

抽象操作 Completion(*completionRecord*) 用于强调将返回之前计算的 Completion Record。抽象操作 Completion 采用单个参数 *completionRecord* 则执行一下步骤：

1. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): *completionRecord* 是一个 Completion Record
2. 返回 *completionRecord* 作为抽象操作的 Completion Record

在算法步骤中一个没有值的 "return" 语句等同于：

1. Return NormalCompetion(**undefined**)

在上下文中明确地不需要完整的 Completion Record 值的任何对 Completion Record 值的引用都等同于对 Completion Record 值的 [[value]] 字段的明确引用，除非 Completion Record 是一个 abrupt completion。

##### 6.2..2.3  Throw an Exception

算法步骤中说抛出一个异常，比如：

1. Throw a **TypeError** exception

等同于：

1. Return Completion{[[type]]: throw, [[value]]: 一个新建的 **TypeError** 对象, [[target]]: empty}

##### 6.2..2.4  ReturnIfAbrupt

算法步骤里说：

1. ReturnIfAbrupt(*argument*)

等同于：

1. 如果 *argument* 是一个 abrupt completion，返回 *argument*
2. 否则，如果 *argument* 是一个 Completion Record，将 *argument* 赋值为 *argument*.[[value]]

##### 6.2.2.5 UpdateEmpty ( completionRecord, value)

抽象操作 UpdateEmpty 采用 *completionRecord* 和 *value* 两个参数，执行以下步骤：

1. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): 如果 *completionRecord*.[[type]] 是 throw，则 *completionRecord*.[[value]] 不为空
2. 如果 *completionRecord*.[[type]] 是 throw，返回 Completion(*completionRecord*)
3. 如果 *completionRecord*.[[value]] 不为空，返回 Completion(*completionRecord*)
4. 返回 Completion{[[type]]: *completionRecord*.[[type]], [[value]]: *value*, [[target]]: *completionRecord*.[[target]]}

#### 6.2.3 Reference 规范类型

注：Reference 类型用于解释诸如 **delete**、**typeof**、赋值操作、**super** 关键字以及其他的一些语言特性的操作的行为。比如，一个赋值的左操作数应该产生一个 reference。

一个 Reference 是一个解析的名称或属性绑定。它包含三个部分，*base* 值、*reference name* 和一个值类型为 Boolean 的 *strict reference* 的标记。*base* 值的类型为 Undefined、Object、Boolean、Symbol、Number 和 [Environment Record](https://262.ecma-international.org/6.0/#sec-environment-records) ([8.1.1](https://262.ecma-international.org/6.0/#sec-environment-records)) 之一。值为 undefined 的 *bbase value* 表示无法将这个 Reference 解析为绑定。*reference name* 则是一个 String 或者 Symbol 类型的值。

Super Reference 是用于表示使用 super 关键字表示的名称绑定的 Reference。其拥有一个额外的组成部分——*thisValue*，而且其 *base* 值永远不可能是 [Environment Record](https://262.ecma-international.org/6.0/#sec-environment-records)。

本规范中的以下抽象操作用于访问 reference 的组成部分

- GetBase(V)：返回 reference V 的 *base* 值
- GetReferencedName(V)：返回 reference V 的 *reference name*
- IsStrictReference(V)：返回 reference V 的 *strict reference* 标记
- HasPrimitiveBase(V)：如果 Type(*base*) 是 Boolean、String、Symbol、Number 之一则返回 true
- IsPropertyReference(V)：如果 HasPrimitiveBase(V) 返回 true 或者 *base* 值是一个对象则返回 true，否则返回 false
- IsUnresolvableReference(V)：如果 *base* 值是 **undefined** 则返回 true，否则返回 false
- IsSuperReference(V)：如果 V 拥有 *thisValue* 则返回 true

本规范中的以下的抽象操作用于操纵 references：

##### 6.2.3.1 GetValue(V)

1. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*V*)

2. 如果 Type(V) 不是 Reference，返回 V

3. 让 *base* 为 GetBase(V)

4. 如果  [IsUnresolvableReference](https://262.ecma-international.org/6.0/#sec-reference-specification-type)(*V*)，引发一个 **ReferenceError** 异常

5. 如果 [IsPropertyReference](https://262.ecma-international.org/6.0/#sec-reference-specification-type)(*V*)，则

   ​	a. 如果 If [HasPrimitiveBase](https://262.ecma-international.org/6.0/#sec-reference-specification-type)(*V*) 为 **true**

   ​			i. Assert：此时，*base* 永远不会是 null 或 undefined

   ​			ii. 让 *base* 为 [ToObject](https://262.ecma-international.org/6.0/#sec-toobject)(*base*)

   ​	b. 返回 *base.*\[[Get]\](GetReferencedName(V), [GetThisValue](https://262.ecma-international.org/6.0/#sec-getthisvalue)(*V*))

6. 否则 *base* 必须是一个 [Environment Record](https://262.ecma-international.org/6.0/#sec-environment-records),

   ​	a. 返回 *base.*GetBindingValue([GetReferencedName](https://262.ecma-international.org/6.0/#sec-reference-specification-type)(*V*), [IsStrictReference](https://262.ecma-international.org/6.0/#sec-reference-specification-type)(*V*)) ([see 8.1.1](https://262.ecma-international.org/6.0/#sec-environment-records))

注：在上述抽象操作和普通对象 [[Get]] 内部方法之外，无法访问可能在步骤 5.a.ii 中创建的对象。一个实现应该选择避免实际创建这个对象。

##### 6.2.3.2 PutValue (V, W)

1. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*V*)

2. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*W*)

3. 如果 Type(V) 不是 **Reference**，引发一个 **ReferenceError** 异常

4. 让 *base* 为 GetBase(*V*)

5. 如果 [IsUnresolvableReference](https://262.ecma-international.org/6.0/#sec-reference-specification-type)(*V*)，则

   ​	a. 如果 [IsStrictReference](https://262.ecma-international.org/6.0/#sec-reference-specification-type)(*V*) 为 true 则

   ​			i. 引发一个 **ReferenceError** 异常

   ​	b. 让 *globalObj* 为 [GetGlobalObject](https://262.ecma-international.org/6.0/#sec-getglobalobject)()

   ​	c. 返回 [Set](https://262.ecma-international.org/6.0/#sec-set-o-p-v-throw)(*globalObj*,[GetReferencedName](https://262.ecma-international.org/6.0/#sec-reference-specification-type)(*V*), *W*, **false**)

6. 否则，如果 [IsPropertyReference](https://262.ecma-international.org/6.0/#sec-reference-specification-type)(*V*)，则

   ​	a. 如果 [HasPrimitiveBase](https://262.ecma-international.org/6.0/#sec-reference-specification-type)(*V*) ，则

   ​			i. Assert：此时，*base* 永远不会是 null 或 undefined

   ​			ii. 让 *base* 为 [ToObject](https://262.ecma-international.org/6.0/#sec-toobject)(*base*)

   ​	b. 让 *succeeded* 为 *base*.\[[Set]\]([GetReferencedName](https://262.ecma-international.org/6.0/#sec-reference-specification-type)(*V*), *W*, [GetThisValue](https://262.ecma-international.org/6.0/#sec-getthisvalue)(*V*))

   ​	c.  [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*succeeded*)

   ​	d. 如果 *succeeded* 为 false 而且 [IsStrictReference](https://262.ecma-international.org/6.0/#sec-reference-specification-type)(*V*) 为 true，引发一个 **TypeError** 异常

   ​	e. Return

7. 否则 *base* 必是一个 [Environment Record](https://262.ecma-international.org/6.0/#sec-environment-records)

   ​	a. 返回 *base.*GetBindingValue([GetReferencedName](https://262.ecma-international.org/6.0/#sec-reference-specification-type)(*V*), [IsStrictReference](https://262.ecma-international.org/6.0/#sec-reference-specification-type)(*V*)) ([see 8.1.1](https://262.ecma-international.org/6.0/#sec-environment-records))

注：在上述抽象操作和普通对象 [[Set]] 内部方法之外，无法访问可能在步骤 6.a.ii 中创建的对象。一个实现应该选择避免实际创建这个对象。

##### 6.2.3.3 GetThisValue(V)

1. Assert：IsPropertyReference(V) 为 true

2. 如果 [IsSuperReference](https://262.ecma-international.org/6.0/#sec-reference-specification-type)(*V*)，则

   ​		a. 返回 V 的 *thisArg* 值

3. 返回 GetBase(V)

##### 6.2.3.4 InitializeReferencedBinding (V, W)

1. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*V*)
2. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*W*)
3. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*V*) 是 [Reference](https://262.ecma-international.org/6.0/#sec-reference-specification-type).
4. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [IsUnresolvableReference](https://262.ecma-international.org/6.0/#sec-reference-specification-type)(*V*)  为 false
5. 让 *base* 为 GetBase(*V*)
6. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): *base* 是 [Environment Record](https://262.ecma-international.org/6.0/#sec-environment-records)
7. 返回 *base.*InitializeBinding([GetReferencedName](https://262.ecma-international.org/6.0/#sec-reference-specification-type)(*V*), *W*)

#### 6.2.4 Property Descriptor 规范类型

Property Descriptor 类型用于解释对象属性特性的操纵和确定。Property Descriptor（译者注：后续统一翻译为「属性描述」） 类型的值是 Records。每个字段的名称是一个特性名称，其值是一个在 6.1.7.1 中指定的相应属性值。另外，任何字段都可以存在或不存在。在本规范中用于标记属性描述记录的字面量描述的架构名称为 "PropertyDescriptor"。

基于某些字段的存在或使用，属性描述值可以进一步分类为数据属性描述和访问器属性描述。数据属性描述是一个包含任何名为 [[Value]] 或 [[Writable]] 的字段的属性。访问器属性描述是一个包含名为 [[Get]] 或 [[Set]] 的任何字段的属性描述。任何属性描述都可以具有名为 [[Enumerable]] 和 [[Configurable]] 的字段。属性描述值不能同时是数据属性描述和访问器属性描述。但是，可能两者都不是。通用属性描述是既不是数据属性描述也不是访问器属性描述的属性描述符。完全填充的属性描述是访问器属性描述或数据属性描述，并且具有与表 2 或表 3 中定义的属性特性相对应的所有字段。

在本规范中，以下抽象操作用于对属性描述值进行操作：

##### 6.2.4.1 IsAccessorDescriptor ( Desc )

当抽象操作 IsAccessorDescriptor 以属性描述 *Desc* 为参数被调用时，执行以下步骤：

1. 如果 *Desc* 为 **undefined** 返回 false
2. 如果 *Desc*.[[Get]] 和 *Desc*.[[Set]] 均不存在，返回 false
3. 返回 true

##### 6.2.4.2 IsDataDescriptor ( Desc )

当抽象操作 IsDataDescriptor 以属性描述 *Desc* 为参数被调用时，执行以下步骤：

1. 如果 *Desc* 为 **undefined** 返回 false
2. 如果 *Desc*.[[Value]] 和 *Desc*.[[Writable]] 均不存在，返回 false
3. 返回 true

##### 6.2.4.3 IsGenericDescriptor ( Desc )

当抽象操作 IsGenericDescriptor 以属性描述 *Desc* 为参数被调用时，执行以下步骤：

1. 如果 *Desc* 为 **undefined** 返回 false
2. 如果 IsDataDescriptor(*Desc*) 和 IsAccessorDescriptor(*Desc*) 均返回 false，返回 true
3. 返回 false

##### 6.2.4.4 FromPropertyDescriptor ( Desc )

抽象操作 FromPropertyDescriptor 以属性描述 *Desc* 为参数被调用时，执行以下步骤：

1. 如果 *Desc* 是 undefined，返回 undefined
2. 让 *obj* 为 [ObjectCreate](https://262.ecma-international.org/6.0/#sec-objectcreate)(%ObjectPrototype%)
3. Assert：*obj* 是没有自有属性的可扩展普通对象
4. 如果 *Desc* 有 [[Value]] 字段，则执行 [CreateDataProperty](https://262.ecma-international.org/6.0/#sec-createdataproperty)(*obj*, `"value"`, *Desc*.[[Value]])
5. 如果 *Desc* 有 [[Wriable]] 字段，则执行 [CreateDataProperty](https://262.ecma-international.org/6.0/#sec-createdataproperty)(*obj*, `"writable"`, *Desc*.[[Writable]])
6. 如果 *Desc* 有 [[Get]] 字段，则执行 [CreateDataProperty](https://262.ecma-international.org/6.0/#sec-createdataproperty)(*obj*, `"get"`, *Desc*.[[Get]])
7. 如果 *Desc* 有 [[Set]] 字段，则执行 [CreateDataProperty](https://262.ecma-international.org/6.0/#sec-createdataproperty)(*obj*, `"get"`, *Desc*.[[Set]])
8. 如果 *Desc* 有 [[Enumerable]] 字段，则执行 [CreateDataProperty](https://262.ecma-international.org/6.0/#sec-createdataproperty)(*obj*, `"enumerable"`, *Desc*.[[Enumerable]])
9. 如果 *Desc* 有 [[Configurable]] 字段，则执行 [CreateDataProperty](https://262.ecma-international.org/6.0/#sec-createdataproperty)(*obj*, `"configurable"`, *Desc*.[[Configurable]])
10. Assert：上述所有 [CreateDataProperty] 操作都返回 true
11. 返回 *obj*

##### 6.2.4.5 ToPropertyDescriptor ( Obj )

抽象操作 ToPropertyDescriptor 以对象 *Obj* 为参数被调用时，执行以下步骤：

1. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*Obj*)

2. 如果 Type(*Obj*) 不是 Object，引发一个 **TypeError** 异常

3. 让 *desc* 为一个新的属性描述，初始没有任何字段

4. 让 *hasEnumerable* 为 [HasProperty](https://262.ecma-international.org/6.0/#sec-hasproperty)(*Obj*, `"enumerable"`)

5. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*hasEnumerable*)

6. 如果 *hasEnumerable* 为 true，则

   ​	a. 让 *enum* 为 [ToBoolean](https://262.ecma-international.org/6.0/#sec-toboolean)([Get](https://262.ecma-international.org/6.0/#sec-get-o-p)(*Obj*, `"enumerable"`))

   ​	b. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*enum*)

   ​	c. 设置 *desc* 的[[Enumerable]] 为 *enum*

7. 让 *hasConfigurable* 为 [HasProperty](https://262.ecma-international.org/6.0/#sec-hasproperty)(*Obj*, `"configurable"`)

8. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*hasConfigurable*)

9. 如果 *hasConfigurable* 为 true，则

   ​	a. 让 *conf* 为 [ToBoolean](https://262.ecma-international.org/6.0/#sec-toboolean)([Get](https://262.ecma-international.org/6.0/#sec-get-o-p)(*Obj*, `"configurable"`))

   ​	b. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*conf*)

   ​	c. 设置 *desc* 的[[Configurable]] 为 *conf*

10. 让 *hasValue* 为 [HasProperty](https://262.ecma-international.org/6.0/#sec-hasproperty)(*Obj*, `"value"`)

11. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*hasValue*)

12. 如果 *hasValue 为 true*, 则：

    ​	a. Let *value* be [Get](https://262.ecma-international.org/6.0/#sec-get-o-p)(*Obj*, `"value"`)

    ​	b. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*value*)

    ​	c. 设置 *desc* 的 [[Value]] 字段为 *value*

13. 让 *hasWritable* 为 [HasProperty](https://262.ecma-international.org/6.0/#sec-hasproperty)(*Obj*, `"writable"`)

14. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*hasWritable*)

15. 如果 *hasWritable* 为 true 则：

    ​	a. 让 *writable* 为 [ToBoolean](https://262.ecma-international.org/6.0/#sec-toboolean)([Get](https://262.ecma-international.org/6.0/#sec-get-o-p)(*Obj*, `"writable"`))

    ​	b. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*writable*)

    ​	c. 设置 *desc* 的 [[Writable]] 字段为 *writable*

16. 让 *hasGet* 为 [HasProperty](https://262.ecma-international.org/6.0/#sec-hasproperty)(*Obj*, `"get"`)

17. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*hasGet*).

18. 如果 *hasGet* 为 true，则：

    ​	a. 让 *getter* 为 [Get](https://262.ecma-international.org/6.0/#sec-get-o-p)(*Obj*, `"get"`)

    ​	b. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*getter*)

    ​	c. 如果 [IsCallable](https://262.ecma-international.org/6.0/#sec-iscallable)(*getter*) 为 **false** 而且 *getter* 非 undefined, 引发一个 **TypeError** 异常

    ​	d. 设置 *desc* [[Get]] 字段为 *getter*

19. 让 *hasSet* 为 [HasProperty](https://262.ecma-international.org/6.0/#sec-hasproperty)(*Obj*, `"set"`)

20. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*hasSet*)

21. 如果 *hasSet* 为 true，则：

    ​	a. 让 *setter* 为 [Get](https://262.ecma-international.org/6.0/#sec-get-o-p)(*Obj*, `"set"`)

    ​	b. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*setter*)

    ​	c. 如果 [IsCallable](https://262.ecma-international.org/6.0/#sec-iscallable)(*setter*) 为 **false** 而且 *setter* 非 **undefined**, 引发一个 **TypeError** 异常

    ​	d. 设置 *desc* [[Set]] 字段为 *setter*

22. 如果 *desc*.[[Get]] 和 *desc*.[[Set]] 之一存在，则：

    ​	a. 如果 *desc*.[[Value]] 和 *desc*.[[Writable]] 之一存在, 引发一个 **TypeError** 异常

23. 返回 *desc*

##### 6.2.4.6 CompletePropertyDescriptor ( Desc )

抽象操作 CompletePropertyDescriptor 以属性描述 *Desc* 为参数被调用时，执行以下步骤：

1. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*Desc*)

2. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): *Desc* 是属性描述

3. 让 *like* 为 Record{[[Value]]: **undefined**, [[Writable]]: **false**, [[Get]]: **undefined**, [[Set]]: **undefined**, [[Enumerable]]: **false**, [[Configurable]]: **false**}

4. 如果 [IsGenericDescriptor](https://262.ecma-international.org/6.0/#sec-isgenericdescriptor)(*Desc*) 和 [IsDataDescriptor](https://262.ecma-international.org/6.0/#sec-isdatadescriptor)(*Desc*) 之一为 true，则：

   ​	a. 如果 *Desc* 没有 [[Value]] 字段, 设置 *Desc*.[[Value]] 为 *like*.[[Value]]

   ​	b. 如果 *Desc* 没有 a [[Writable]] 字段, 设置 *Desc*.[[Writable]] to *like*.[[Writable]]

5. 否则：

   ​	a. 如果 *Desc* 没有 [[Get]] 字段, 设置 *Desc*.[[Get]] 为 *like*.[[Get]]

   ​	b. 如果 *Desc* 没有 [[Set]] 字段, 设置 *Desc*.[[Set]] 为 *like*.[[Set]]

6. 如果 *Desc* 没有 [[Enumerable]] 字段, 设置 *Desc*.[[Enumerable]] 为 *like*.[[Enumerable]]

7. 如果 *Desc* 没有 [[Configurable]] 字段, 设置 *Desc*.[[Configurable]] 为 *like*.[[Configurable]].

8. 返回 *Desc*

#### 6.2.5 Lexical Environment 规范类型 和 Environment Record 规范类型

Lexical Environment 规范类型 和 Environment Record 规范类型用于解释嵌套函数和块中名称解析行为。这些类型和对它们的操作在  [8.1](https://262.ecma-international.org/6.0/#sec-lexical-environments) 定义。

#### 6.2.6 Data Blocks

Data Block 规范类型用于描述字节大小（8 位）数字值的不同且可变的序列。使用固定数量的字节创建的 Data Block（译者注：后续统一翻译为数据块），每个字节的初始值均为 0。

为方便起见，在本规范中，可以使用类似数组的语法来访问数据块值的各个字节。该表示法将数据块值表示为从 0 开始的整数索引的字节序列。例如，如果 db 是 5 字节的数据块值，则db [2]可用于访问其第 3 个字节。

在本规范中，以下抽象操作用于对数据块值进行操作：

##### 6.2.6.1 CreateByteDataBlock(size)

当使用整数参数大小调用抽象操作 CreateByteDataBlock 时，将执行以下步骤：

1. Assert: *size*≥0
2. 让 *db* 为一个新的包含 *size* 字节的数据块。如果不可能创建这样的数据块，引发一个 **RangeError** 异常
3. 设置 *db* 的每一字节为 0
4. 返回 *db*

##### 6.2.6.2 CopyDataBlockBytes(toBlock, toIndex, fromBlock, fromIndex, count)

调用抽象操作 CopyDataBlockBytes 时，将执行以下步骤：

1. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions)：fromBlock 和 toBlock 是不同的数据块值

2. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions)：fromIndex，toIndex 和 count 都是正整数

3. 令 fromSize 为 fromBlock 中的字节数

4. Assert：*fromIndex*+*count* ≤ *fromSize*

5. 令 toSize 为 toBlock 中的字节数

6. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): *toIndex*+*count* ≤ *toSize*

7. 重复，当 count> 0 时：

   ​		a. 将 toBlock [toIndex] 设置为 fromBlock [fromIndex] 的值

   ​		b. 将 toIndex 和 fromIndex 分别增加 1

   ​		c. *count* 减 1

8. 返回 [NormalCompletion](https://262.ecma-international.org/6.0/#sec-normalcompletion)(empty)

## 7 抽象操作

这些操作并非 ECMAScript 语言的一部分，它们被定义完全是为了规范 ECMAScript 语言的语义。在本说明书中，还定义了其他更专门的抽象操作。

### 7.1 Type Convertion

ECMAScript 语言在必要时会隐式执行自动的类型转换。为了阐明某些构造的语义，定义一组转换抽象操作很有用。转换抽象操作是多态的。它们可以接受任何 ECMAScript 语言类型的值或 Compeletion Record 值。除此之外这些操作没有使用其他的规范类型。

#### 7.1.1 ToPrimitive(input, [, PreferredType])

抽象操作 ToPrimitive 以一个 *input* 和一个可选的 *PreferredType* 为参数。它将 *input* 参数转化为一个非 对象类型。如果一个对象可能转换成不止一个原始类型，可以使用可选的提示 *PreferredType* 来转换成偏好的类型。转换根据表 9 进行：

##### 表 9 —— ToPrimitive 转换

| 输入类型          | 结果                                                         |
| ----------------- | ------------------------------------------------------------ |
| Completion Record | 如果 *input* 是一个 abrupt completion，返回 input。否则返回 ToPrimitive(*input*.[[value]], *PreferredType*) |
| Undefined         | 返回 *input*                                                 |
| Null              | 返回 *input*                                                 |
| Boolean           | 返回 *input*                                                 |
| Number            | 返回 *input*                                                 |
| String            | 返回 *input*                                                 |
| Symbol            | 返回 *input*                                                 |
| Object            | 执行下面步骤                                                 |

当 Type(*input*) 是 Object 时，执行以下步骤：

1. 如果没传 *PreferredType*，让 *hint* 为 **default**

2. 否则如果 *PreferredType* 提示 String，让 *hint* 为 **string**

3. 否则如果 *PreferredType* 提示 Number，让 *hint* 为 **number**

4. 让 *exoticToPrim* 为 GetMethod(*input*, @@toPrimitive)

5. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*exoticToPrim*)

6. 如果 *exoticToPrim* 不为 undefined，那么：

   ​		a. 让 *result* 为 [Call](https://262.ecma-international.org/6.0/#sec-call)(*exoticToPrim*, *input,* «*hint*»)

   ​		b. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*result*)

   ​		c. 如果 Type(*result*) 不是 Object，返回 result

   ​		d. 引发一个 **TypeError** 异常

7. 如果 *hint* 是 **default**，让 *hint* 为 "**number**"

8. 返回 OrdinaryToPrimitive(*input*, *hint*)

当抽象操作传入参数 *O* 和 *hint* 调用时，执行以下步骤：

1. Assert: Type(O) 是 Object

2. Assert：Type(*hint*) 是 String 且其值是 "**string**" 和 "**number**" 之一

3. 如果 *hint* 是  "**string**"，则让 *methodNames* 为 «`"toString"`, `"valueOf"`»

4. 否则，让 *methodNames* 为 «`"valueOf"`, `"toString"`»

5. 依次对 *methodName* 中的每个 *name* 进行：

   ​		a. 让 *method* 为 [Get](https://262.ecma-international.org/6.0/#sec-get-o-p)(*O*, *name*).

   ​		b. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*method*)

   ​		c. 如果 [IsCallable](https://262.ecma-international.org/6.0/#sec-iscallable)(*method*)，则：

   ​				i. 让 *result* 为 [Call](https://262.ecma-international.org/6.0/#sec-call)(*method*, *O*)

   ​				ii. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*result*)

   ​				iii. 如果 Type(*result*) 非 Object，返回 *result*

6. 引发一个 *TypeError* 异常

注：如果在没有提示的情况下调用 ToPrimitive，则其行为通常就像提示是 Number 一样。但是，对象可以通过定义 @@toPrimitive 方法来替代此行为。在本规范中定义的对象中，只有 Date 对象（请参见 [20.3.4.45](https://262.ecma-international.org/6.0/#sec-date.prototype-@@toprimitive)）和 Symbol 对象（请参见 [19.4.3.4](https://262.ecma-international.org/6.0/#sec-symbol.prototype-@@toprimitive)）会覆盖默认的 ToPrimitive 行为。 Date 对象将没有提示视为提示是 String。

#### 7.1.2 ToBoolean(argument)

抽象操作 ToBoolean 依照表 10 将 *argument* 转换为 Boolean 类型的值：

##### 表 10 —— ToBoolean 转换

| 参数类型                                                     | 结果                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [Completion Record](https://262.ecma-international.org/6.0/#sec-completion-record-specification-type) | 如果 *input* 是一个 abrupt completion，返回 input。否则返回 ToBoolean(*input*.[[value]]) |
| Undefined                                                    | 返回 false                                                   |
| Null                                                         | 返回 false                                                   |
| Boolean                                                      | 返回 *argument*                                              |
| Number                                                       | 如果 *argument* 是 +0、-0 或者 NaN，返回 false，否则返回 true |
| String                                                       | 如果 *argument* 是空 String（长度为 0）则返回 false，否则返回 true |
| Symbol                                                       | 返回 true                                                    |
| Object                                                       | 返回 true                                                    |

#### 7.1.3 ToNumber(argument)

抽象操作 ToNumber 根据表 11 将 *argument* 转换为 Number 类型的值：

##### 表 11 —— ToNumber 转换

| 参数类型          | 结果                                                         |
| ----------------- | ------------------------------------------------------------ |
| Completion Record | 如果 *input* 是一个 abrupt completion，返回 input。否则返回 ToNumber(*input*.[[value]]) |
| Undefined         | 返回 NaN                                                     |
| Null              | 返回 +0                                                      |
| Boolean           | 如果为 true 返回 1，否则返回 +0                              |
| Number            | 返回 *argument*                                              |
| String            | 见下面的语法和转换算法                                       |
| Symbol            | 引发 **TypeError** 异常                                      |
| Object            | 执行以下步骤：1. 让 *primValue* 为 [ToPrimitive](https://262.ecma-international.org/6.0/#sec-toprimitive)(*argument*, hint Number)；2. 返回 Return ToNumber(*primValue*) |

##### 7.1.3.1 ToNumber 应用于 String 类型

应用于字符串的 ToNumber 将以下语法应用于被解释为 UTF-16 编码码点序列的输入字符串。如果语法无法将 String 解释为 StringNumericLiteral 的扩展，则 ToNumber 的结果为 NaN。

注 1：该语法的终结符号全部由 Unicode BMP 码点组成，因此，如果字符串包含任何补充平面的码点或任何未配对的代理码点的 UTF-16 编码，则结果为 NaN。

**Syntax**

------

*StringNumericLiteral* **:::**

​		*StrWhiteSpace*<sub>opt</sub>

​		*StrWhiteSpace*<sub>opt</sub> *StrNumericLiteral* *StrWhiteSpace*<sub>opt</sub>

*StrWhiteSpace* **:::**

​		*StrWhiteSpaceChar* *StrWhiteSpace*<sub>opt</sub>

*StrWhiteSpaceChar* **:::**

​		*WhiteSpace*

​		*LineTerminator*

*StrNumericLiteral* **:::**

​		*StrDecimalLiteral*

​		*BinaryIntegerLiteral*

​		*OctalIntegerLiteral*

​		*HexIntegerLiteral*

*StrDecimalLiteral* **:::**

​		*StrUnsignedDecimalLiteral*

​		`+` *StrUnsignedDecimalLiteral*

​		`-` *StrUnsignedDecimalLiteral*

*StrUnsignedDecimalLiteral* **:::**

​		*Infinity*

​		*DecimalDigits* `.` *DecimalDigits*<sub>opt</sub> *ExponentPart*<sub>opt</sub>

​		`.` *DecimalDigits* *ExponentPart*<sub>opt</sub>

​		*DecimalDigits* *ExponentPart*<sub>opt</sub>

*DecimalDigits* **:::**

​		*DecimalDigit*

​		*DecimalDigits* *DecimalDigit*

*DecimalDigit* **:::** **one of**

​		`0` `1` `2` `3` `4` `5` `6` `7` `8` `9`

*ExponentPart* **:::**

​		*ExponentIndicator* *SignedInteger*

*ExponentIndicator* **:::** **one of**

​		`e` `E`

*SignedInteger* **:::**

​		*DecimalDigits*

​		`+` *DecimalDigits*

​		`-` *DecimalDigits*

------

上面未明确定义的所有语法符号都具有词法语法中用于数字字面量([11.8.3](https://262.ecma-international.org/6.0/#sec-literals-numeric-literals))的定义。

注 2：*StringNumericLiteral* 语法和  *NumericLiteral* ([see 11.8.3](https://262.ecma-international.org/6.0/#sec-literals-numeric-literals)) 语法中的一些区别需要指出：

- *StringNumericLiteral* 可以包括前导和/或后尾空白和/或行终止符。
- 十进制的 *StringNumericLiteral* 可以有任意数量的前导 0 数字
- 十进制的 *StringNumericLiteral* 可能包括 + 或 - 以表明其符号
- *StringNumericLiteral* 为空或者只包含空白符时被转换为 +0
- **Infinity** 和 **-Infinity** 被认为是一个 *StringNumericLiteral* 但不是 *NumericLiteral*

###### 7.1.3.1.1 运行时语义：MV's

将 String 值转换为 Number 值总体上与从一个数字字面量中确定一个 Number 值相同，只是一些细节的地方有些差异，所以在这里给出将 String 值转换为 Number 值的处理过程。这个值分两步来确定：1. 一个数学值 (MV) 被从字符串数字字面量中分离；2. 这个数学值按如下所述四舍五入。下文未提供的任何语法符号上的 MV 是 [11.8.3.1](https://262.ecma-international.org/6.0/#sec-static-semantics-mv) 中定义的符号的 MV。

- *StringNumericLiteral* **:::** [empty] 的 MV 是 0
- *StringNumericLiteral* **:::** *StrWhiteSpace* 的 MV 是 0
- *StringNumericLiteral* **:::** *StrWhiteSpace*<sub>opt</sub> *StrNumericLiteral* *StrWhiteSpace*<sub>opt</sub> 的 MV 即 *StringNumericLiteral* **:::** *StrNumericLitera* 的 MV，不管有无空白符
- *StrNumericLiteral* **:::** *StrDecimalLiteral* 的 MV 即 *StrDecimalLiteral* 的 MV
- *StrNumericLiteral* **:::** *BinaryIntegerLiteral* 的 MV 即 *BinaryIntegerLiteral* 的 MV
- *StrNumericLiteral* **:::** *OctalIntegerLiteral* 的 MV 即 of *OctalIntegerLiteral* 的 MV
- *StrNumericLiteral* **:::** *HexIntegerLiteral* 的 MV 即 *HexIntegerLiteral* 的 MV
- *StrDecimalLiteral* **:::** *StrUnsignedDecimalLiteral* 的 MV 即  *StrUnsignedDecimalLiteral* 的 MV
- *StrDecimalLiteral* **:::** **+** *StrUnsignedDecimalLiteral* 的 MV 即  *StrUnsignedDecimalLiteral* 的 MV
- *StrDecimalLiteral* **:::** **-** *StrUnsignedDecimalLiteral* 的 MV 即  *StrUnsignedDecimalLiteral* 的 MV 的相反数。（注：如果后者是 0，那前者依然是 0。如下所述的舍入规则处理此无符号的数学零到适当的浮点+0或-0的转换。）
- *StrUnsignedDecimalLiteral* **:::** *Infinity* 的 MV 是 10<sup>10000</sup>（一个大到会被四舍五入成 +∞的值）
- *StrUnsignedDecimalLiteral* **:::** *DecimalDigits* 的 MV 即 *DecimalDigits* 的 MV
- *StrUnsignedDecimalLiteral* **:::** *DecimalDigits* `.` *DecimalDigits* 的 MV 即第一个 *DecimalDigits* 的 MV 加上第二个 *DecimalDigits* 的 MV 乘以 10<sup>-*n*</sup>，其中 *n* 为第二个 DecimalDigits 中的码点的个数
- *StrUnsignedDecimalLiteral* **:::** *DecimalDigits* `.` *ExponentPart* 的 MV 即 *DecimalDigits* 的 MV 乘以 10<sup>*e*</sup> ，其中 *e* 为 *ExponentPart* 的 MV
- *StrUnsignedDecimalLiteral* **:::** *DecimalDigits* `.` *DecimalDigits* *ExponentPart* 的 MV 即第一个 *DecimalDigits* 的 MV 加上第二个 *DecimalDigits* 的 MV 乘以 10<sup>*e*-*n*</sup>，其中 *n* 为第二个 DecimalDigits 中的码点的个数，*e* 为 *ExponentPart* 的 MV
- *StrUnsignedDecimalLiteral* **:::** `.` *DecimalDigits* 的 MV 即 *DecimalDigits* 的 MV 乘以 10<sup>-*n*</sup>，其中 *n* 为 DecimalDigits 中的码点的个数
- *StrUnsignedDecimalLiteral* **:::** `.` *DecimalDigits* *ExponentPart* 的 MV 即 *DecimalDigits* 的 MV 乘以 10<sup>*e*-*n*</sup>，其中 *n* 为 DecimalDigits 中的码点的个数，*e* 为 *ExponentPart* 的 MV
- *StrUnsignedDecimalLiteral* **:::** *DecimalDigits* 的 MV 即 *DecimalDigits* 的 MV
- *StrUnsignedDecimalLiteral* **:::** *DecimalDigits* *ExponentPart* 的 MV 即 *DecimalDigits* 的 MV 乘以 10<sup>*e*</sup>，其中 *e* 为 *ExponentPart* 的 MV

确定了字符串数字字面量的确切 MV 之后，将其四舍五入为 Number 类型的值。如果 MV 为 0，那么四舍五入的值是 +0，除非该字符串数字字面量的第一个非空白符的码点对应的字符是 '**-**'，在这种情况下四舍五入的值为 -0。否则，舍入后的值必须是 MV 的Number值（在6.1.6中定义），除非文字包括 StrUnsignedDecimalLiteral 且字面量具有 20 个以上的有效数字，在这种情况下 Number 值可以是通过将 20 位之后的每个有效数字都替换为 0 而产生的字面量 MV 的 Number 值或通过将 20 位之后的每个有效数字都替换为 0 然后在 20 号处增加字面量而产生的字面量的 MV 的 Number 值。一个数字是有效，如果它不是 ExpnentPart 的一部分并且满足：

- 它不是 0，或者
- 它左边有一个非零数字，右边有一个非零数字（不在 ExponentPart 中）

#### 7.1.4 ToInteger(argument)

抽象操作 ToInteger 将 *argument* 转换为一个字面量数字值。其操作步骤如下：

1. 让 *number* 为 [ToNumber](https://262.ecma-international.org/6.0/#sec-tonumber)(*argument*)
2. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*number*)
3. 如果 *number* 是 NaN，返回 +0
4. 如果 *number* 是  **+0**、**−0**、**+∞、** 或 **−∞**，返回 *number*
5. 返回与 *number* 相同正负且大小为 [floor](https://262.ecma-international.org/6.0/#sec-algorithm-conventions)([abs](https://262.ecma-international.org/6.0/#sec-algorithm-conventions)(*number*)) 的数字值

#### 7.1.5 ToInt32(argument)

抽象操作 ToInt32 将 *argument* 转换为取值范围为 -2<sup>31</sup> 到 2<sup>31</sup>-1 之间（包含端点）总共 2<sup>32</sup> 个值之一。其操作如下：

1. 让 *number* 为 ToNumber(*argument*)
2. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*number*)
3. 如果 *number* 是 **NaN**、 **+0**、**−0**、**+∞、** 或 **−∞**，返回 +0
4. 让 *int* 为与 *number* 相同正负且大小为 [floor](https://262.ecma-international.org/6.0/#sec-algorithm-conventions)([abs](https://262.ecma-international.org/6.0/#sec-algorithm-conventions)(*number*)) 的数字值
5. 让 *int32bit* 为 *int* [modulo](https://262.ecma-international.org/6.0/#sec-algorithm-conventions) 2<sup>32</sup>
6. 如果 *int32bit* ≥ 2<sup>31</sup>，返回 *int32bit* − 2<sup>32</sup>，否则返回 *int32bit*

注：鉴于以上 ToInt32 的定义：

- ToInt32 抽象操作是幂等的：如果将其应用于所产生的结果，则第二个应用程序将使该值保持不变
- 对于所有 *x* 值，*ToInt32(*[ToUint32](https://262.ecma-international.org/6.0/#sec-touint32)*(x))* 与 ToInt32(*x*) 等价。（要保留后一个属性，将 +∞ 和 -∞ 映射到 +0）
- ToInt32 将−0 映射到 +0

#### 7.1.6 ToUint32 ( argument )

抽象操作 ToUint32 将 *argument* 转换为取值范围为 0 到 2<sup>32</sup>-1 之间（包含端点）总共 2<sup>32</sup> 个值之一。其操作如下：

1. 让 *number* 为 ToNumber(*argument*)
2. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*number*)
3. 如果 *number* 是 **NaN**、 **+0**、**−0**、**+∞、** 或 **−∞**，返回 +0
4. 让 *int* 为与 *number* 相同正负且大小为 [floor](https://262.ecma-international.org/6.0/#sec-algorithm-conventions)([abs](https://262.ecma-international.org/6.0/#sec-algorithm-conventions)(*number*)) 的数字值
5. 让 *int32bit* 为 *int* [modulo](https://262.ecma-international.org/6.0/#sec-algorithm-conventions) 2<sup>32</sup>
6. 返回 *int32bit*

注：鉴于以上 ToUint32 的定义：

- 第 6 步是与 [ToInt32](https://262.ecma-international.org/6.0/#sec-toint32) 的唯一区别

- ToUint32 抽象操作是幂等的：如果将其应用于所产生的结果，则第二个应用程序将使该值保持不变
- 对于所有 *x* 值，ToUint32([ToInt32](https://262.ecma-international.org/6.0/#sec-toint32)(*x*)) 与 ToUint32(*x*) 等价。（要保留后一个属性，将 +∞ 和 -∞ 映射到 +0）
- ToUint32 将−0 映射到 +0

#### 7.1.7 ToInt16(argument)

抽象操作 ToInt16 将 *argument* 转换为取值范围为 -32768 到 32767 之间（包含端点）总共 65536 个值之一。其操作如下：

1. 让 *number* 为 ToNumber(*argument*)
2. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*number*)
3. 如果 *number* 是 **NaN**、 **+0**、**−0**、**+∞、** 或 **−∞**，返回 +0
4. 让 *int* 为与 *number* 相同正负且大小为 [floor](https://262.ecma-international.org/6.0/#sec-algorithm-conventions)([abs](https://262.ecma-international.org/6.0/#sec-algorithm-conventions)(*number*)) 的数字值
5. 让 *int16bit* 为 *int* [modulo](https://262.ecma-international.org/6.0/#sec-algorithm-conventions) 2<sup>16</sup>
6. 如果 *int16bit* ≥ 2<sup>15</sup>，返回 *int16bit* − 2<sup>16</sup>，否则返回 *int16bit*

#### 7.1.8 ToUint16 ( argument )

抽象操作 ToUint16 将 *argument* 转换为取值范围为 0 到 65535 之间（包含端点）总共 65536 个值之一。其操作如下：

1. 让 *number* 为 ToNumber(*argument*)
2. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*number*)
3. 如果 *number* 是 **NaN**、**+0**、**−0**、**+∞、** 或 **−∞**，返回 +0
4. 让 *int* 为与 *number* 相同正负且大小为 [floor](https://262.ecma-international.org/6.0/#sec-algorithm-conventions)([abs](https://262.ecma-international.org/6.0/#sec-algorithm-conventions)(*number*)) 的数字值
5. 让 *int16bit* 为 *int* [modulo](https://262.ecma-international.org/6.0/#sec-algorithm-conventions) 2<sup>16</sup>
6. 返回 *int16bit*

注：鉴于以上 ToUint16 的定义：

- 第 5 步中 将 2<sup>16</sup> 替换成 2<sup>32</sup> 是与 [ToInt32](https://262.ecma-international.org/6.0/#sec-toint32) 的唯一区别

- ToUint16 将−0 映射到 +0

#### 7.1.9 ToInt8(argument)

抽象操作 ToInt8 将 *argument* 转换为取值范围为 -128 到 127 之间（包含端点）总共 256 个值之一。其操作如下：

1. 让 *number* 为 ToNumber(*argument*)
2. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*number*)
3. 如果 *number* 是 **NaN**、 **+0**、**−0**、**+∞、** 或 **−∞**，返回 +0
4. 让 *int* 为与 *number* 相同正负且大小为 [floor](https://262.ecma-international.org/6.0/#sec-algorithm-conventions)([abs](https://262.ecma-international.org/6.0/#sec-algorithm-conventions)(*number*)) 的数字值
5. 让 *int8bit* 为 *int* [modulo](https://262.ecma-international.org/6.0/#sec-algorithm-conventions) 2<sup>8</sup>
6. 如果 *int8bit* ≥ 2<sup>7</sup>，返回 *int16bit* − 2<sup>8</sup>，否则返回 int8bit

#### 7.1.10 ToInt8(argument)

抽象操作 ToInt8 将 *argument* 转换为取值范围为 0 到 255 之间（包含端点）总共 256 个值之一。其操作如下：

1. 让 *number* 为 ToNumber(*argument*)
2. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*number*)
3. 如果 *number* 是  **NaN**、**+0**、**−0**、**+∞、** 或 **−∞**，返回 +0
4. 让 *int* 为与 *number* 相同正负且大小为 [floor](https://262.ecma-international.org/6.0/#sec-algorithm-conventions)([abs](https://262.ecma-international.org/6.0/#sec-algorithm-conventions)(*number*)) 的数字值
5. 让 *int8bit* 为 *int* [modulo](https://262.ecma-international.org/6.0/#sec-algorithm-conventions) 2<sup>8</sup>
6. 返回 *int8bit*

#### 7.1.11 ToUint8Clamp ( argument )

抽象操作 ToUint8Clamp 将 *argument* 转换为取值范围为 0 到 255 之间（包含端点）总共 256 个值之一。其操作如下：

1. 让 *number* 为 ToNumber(*argument*)
2. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*number*)
3. 如果 *number* 是 NaN，返回 +0
4. 如果 *number* ≤ 0，返回 +0
5. 如果 *number* ≥ 255，返回 255
6. 让 *f*  为 [floor](https://262.ecma-international.org/6.0/#sec-algorithm-conventions)(*number*)
7. 如果 *f +* 0.5 < *number*，返回 *f* + 1
8. 如果 *number* < *f +* 0.5，返回 *f*
9. 如果 *f* 是奇数，返回 *f* + 1
10. 返回 *f*

注：与其他 ECMAScript 整数转换抽象运算不同，ToUint8Clamp 舍入而不是截断非整数值，并且不将 +∞ 转换为 0。ToUint8Clamp 进行「将一半舍入为偶数」平局决胜。 这与 Math.round 不同。（译者注：比如 124.5 和 125.5，前者返回 124，后者返回 126）

#### 7.1.12 ToString(argument)

抽象操作 ToString 将 *argument* 按表 12 转成 String 类型的值

##### 表 12 —— ToString 转换

| 参数类型                                                     | 结果                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [Completion Record](https://262.ecma-international.org/6.0/#sec-completion-record-specification-type) | 如果 *input* 是一个 abrupt completion，返回 input。否则返回 ToString(*input*.[[value]]) |
| Undefined                                                    | 返回 "undefined"                                             |
| Null                                                         | 返回 "null"                                                  |
| Boolean                                                      | 如果 *argument* 为 true 返回 "true"，否则返回 "false"        |
| Number                                                       | 参见 [7.1.12.1](https://262.ecma-international.org/6.0/#sec-tostring-applied-to-the-number-type) |
| String                                                       | 返回 argument                                                |
| Symbol                                                       | 引发一个 **TypeError** 的异常                                |
| Object                                                       | 应用下面步骤：1. 让 *primValue* 为 [ToPrimitive](https://262.ecma-international.org/6.0/#sec-toprimitive)(*argument*, hint String)；2. 返回 ToString(*primValue*) |

##### 7.1.12.1 ToString 应用于数字类型

抽象操作 [ToString](https://262.ecma-international.org/6.0/#sec-tostring) 按如下操作将Number *m* 转换为 String 格式：

1. 如果 *m* 是 NaN，返回 String **"NaN"**
2. 如果 *m* 是 +0 或者 -0，返回 String **"0"**
3. 如果 *m* 小于 0，返回由 String **"-"** 和 String ToString(-*m*) 的连接的 String
4. 如果 *m* 是 +∞，返回 **"Infinity"**
5. 否则，让 *n*，*k* 和 *s* 为满足 *k* ≥ 1, 10<sup>*k*−1</sup> ≤ *s* < 10<sup>*k*</sup> 的整数，其中 *s* × 10<sup>*n−k*</sup> 的值即为 *m*，而且 *k* 尽可能的小。需要注意的是，*k* 是 *s* 十进制形式表示中的位数，*s* 不能被 10 整除，而且 *s* 的最低有效位不一定由这些条件唯一确定
6. 如果 *k* ≤ *n* ≤ 21，返回由 *s* 的十进制表示形式的 *k* 位代码单元组成的 String（按顺序，没有前导零），后面跟 *n-k* 个0x0030（数字 0） 码元
7. 如果 0 < *n* ≤ 21，返回由以下组成的字符串：*s* 的十进制表示形式的最高 *n* 位数字的码元，后跟码元 0x002E（FULL STOP），后跟 *s* 的十进制表示形式的其余 *k-n* 位的码元
8. 如果 −6 < *n* ≤ 0，返回由以下码元组成的字符串：码元 0x0030（DIGIT ZERO），后跟码元 0x002E（FULL STOP），后跟 *-n* 个码元 0x0030（DIGIT ZERO），然后是 *k* 个数字位的码元 *s* 的十进制表示
9. 否则，如果 *k=1*，返回字符串，该字符串由 *s*  的一位数字的码元组成，后跟码元 0x0065（拉丁文小写字母 E），然后是由 *n-1* 是正数还是负数决定的码元 0x002B（加号）或码元 0x002D（HYPHEN-MINUS），后跟整数 abs(*n-1*) 的十进制表示的码元（无前导零）
10. 返回由以下组成的字符串：*s* 的十进制表示形式的最高有效位的码元，然后是码元0x002E（FULL STOP），然后是 *s* 的十进制表示形式的其余 *k-1* 位的码元，然后是码元 0x0065（拉丁文小写字母 E），然后是由 *n-1* 是正数还是负数决定的码元 0x002B（加号）或码元 0x002D（HYPHEN-MINUS），后跟整数 abs(*n-1*) 的十进制表示的码元（无前导零）

注 1：下列意见可能对实现有帮助，但不是本标准规范要求的一部分：

- 如果 x 是除 -0 以外的任何 Number 值，则 ToNumber(ToString(x)) 与 x 完全相同
- s 的最低有效位数并非总是由步骤 5 中列出的要求唯一地确定

注 2：对于提供比上述规则所需的转换更准确的转换的实施，建议将以下步骤 5 的替代版本用作指导原则：

5. 否则，让 *n*，*k* 和 *s* 为满足 *k* ≥ 1, 10<sup>*k*−1</sup> ≤ *s* < 10<sup>*k*</sup> 的整数，其中 *s* × 10<sup>*n−k*</sup> 的值即为 *m*，而且 *k* 尽可能的小。如果 *s* 有多种可能，选择*s* × 10<sup>*n−k*</sup> 最接近 *m* 的 *s* 值。如果有两个这样的 *s* 值，选择偶数那个。请注意，*k* 是 *s* 的十进制表示形式中的位数，并且 *s* 不能被 *10* 整除。

注 3：David M. Gay 编写的有关浮点数从二进制到十进制转换的文章和代码可能会对 ECMAScript 的实现者很有用：

Gay, David M. Correctly Rounded Binary-Decimal and Decimal-Binary Conversions. Numerical Analysis, Manuscript 90-10. AT&T Bell Laboratories (Murray Hill, New Jersey). November 30, 1990. Available as
http://cm.bell-labs.com/cm/cs/doc/90/4-10.ps.gz. Associated code available as
http://netlib.sandia.gov/fp/dtoa.c and as
http://netlib.sandia.gov/fp/g_fmt.c and may also be found at the various `netlib` mirror sites.

#### 7.1.13 ToObject(argument)

抽象操作 ToObject 按表 13 将 *argument* 转换为 Object 类型：

##### 表 13 —— Object 转换

| 参数类型                                                     | 结果                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [Completion Record](https://262.ecma-international.org/6.0/#sec-completion-record-specification-type) | 如果 *input* 是一个 abrupt completion，返回 input。否则返回 ToObject(*input*.[[value]]) |
| Undefined                                                    | 引发一个 **TypeError** 异常                                  |
| Null                                                         | 引发一个 **TypeError** 异常                                  |
| Boolean                                                      | 返回一个 Boolean 对象，其内部插槽 [[BooleanData]] 的值为 *argument*。Boolean 对象的介绍参见 [19.3](https://262.ecma-international.org/6.0/#sec-boolean-objects) |
| Number                                                       | 返回一个 Number 对象，其内部插槽 [[NumberData]] 的值为 *argument*。Number 对象的介绍参见 [20.1](https://262.ecma-international.org/6.0/#sec-number-objects) |
| String                                                       | 返回一个 String 对象，其内部插槽 [[StringData]] 的值为 *argument*。String 对象的介绍参见 [21.1](https://262.ecma-international.org/6.0/#sec-string-objects) |
| Symbol                                                       | 返回一个 Symbol 对象，其内部插槽 [[SymbolData]] 的值为 *argument*。Symbol 对象的介绍参见 [19.4](https://262.ecma-international.org/6.0/#sec-symbol-objects) |
| Object                                                       | 返回 *argument*                                              |

#### 7.1.14 ToPropertyKey ( argument )

抽象操作 ToPropertyKey 将 *argument* 转换成一个可以作为属性键的值，转换步骤如下：

1. 让 *key* 为 ToPrimitive(*argument*, hint String)
2. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*key*)
3. 如果 Type(*key*) 是 Symbol，则返回 *key*
4. 返回 ToString(*key*)

#### 7.1.15 Tolength(argument)

抽象操作 ToLength 将 *argument* 转换为一个适合作为类数组对象的长度的整数值。转换步骤如下：

1. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*argument*)
2. 让 *len* 为 [ToInteger](https://262.ecma-international.org/6.0/#sec-tointeger)(*argument*)
3. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*len*)
4. 如果 *len* ≤ +0，返回 *len*
5. 如果 *len* 为 **+∞**，返回 2<sup>53</sup>-1
6. 返回 min(*len*, 2<sup>53</sup>-1)

#### 7.1.16 CanonicalNumericIndexString ( argument )

如果 *argument* 是 ToString 产生的 Number 的 String 表示形式或者是 "-0"，那么抽象操作 CanonicalNumericIndexString 将 *argument* 转换对应的数字值。否则返回 undefined。操作步骤如下：

1. Assert：Type(*argument*) 是 String
2. 如果 *argument* 是 "-0"，返回 -0
3. 让 *n* 为 [ToNumber](https://262.ecma-international.org/6.0/#sec-tonumber)(*argument*)
4. 如果 [SameValue](https://262.ecma-international.org/6.0/#sec-samevalue)([ToString](https://262.ecma-international.org/6.0/#sec-tostring)(*n*), *argument*) 为 false，返回 undefined
5. 返回 *n*

### 7.2 检测和比较操作

#### 7.2.1 RequireObjectCoercible ( argument )

如果 *argument* 是一个不能通过 ToObject 转化为 Object 的值，抽象操作 RequireObjectCoercible 会引发一个异常。定义如表 14：

##### 表 14 —— **RequireObjectCoercible 结果**

| 参数类型                                                     | 结果                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [Completion Record](https://262.ecma-international.org/6.0/#sec-completion-record-specification-type) | 如果 *argument* 是一个 [abrupt completion](https://262.ecma-international.org/6.0/#sec-completion-record-specification-type)，返回 *argument*。否则返回 RequireObjectCoercible(argument.[[value]]) |
| Undefined                                                    | 引发一个 **TypeError** 异常                                  |
| Null                                                         | 引发一个 **TypeError** 异常                                  |
| Boolean                                                      | 返回 *argument*                                              |
| Number                                                       | 返回 *argument*                                              |
| String                                                       | 返回 *argument*                                              |
| Symbol                                                       | 返回 *argument*                                              |
| Object                                                       | 返回 *argument*                                              |

#### 7.2.2 IsArray(argument)

抽象操作接受一个参数 *argument*，执行如下步骤：

1. 如果 [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*argument*) 非 Object，返回 false

2. 如果 *argument* 是  [Array exotic object](https://262.ecma-international.org/6.0/#sec-array-exotic-objects)，返回 true

3. 如果 *argument* 是 Proxy exotic object，那么：

   ​		a. 如果 *argument* 的内部插槽 [[ProxyHandler]] 的值是 null，引发一个 **TypeError** 异常

   ​		b. 让 *target* 为 *argument* 的内部插槽 [[ProxyHandler]] 的值

   ​		c. 返回 IsArray(*target*)

4. 返回 false

#### 7.2.3 IsCallable(argument)

抽象操作 IsCallable 确定其值必须为 ECMAScript 语言类型值或者为 Completion Record 类型值的 *argument* 是否是一个有 [[Call]] 内部方法的可调用的函数。

1. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*argument*)
2. 如果 [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*argument*) 不是 Object，返回 false
3. 如果 *argument* 有 [[Call]] 内部方法，返回 true
4. 返回 false

#### 7.2.4 IsConstructor ( argument )

抽象操作 IsConstructor 确定其值必须为 ECMAScript 语言类型值或者为 Completion Record 类型值的 *argument* 是否是一个有 [[Construct]] 内部方法的可调用的函数。

1. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*argument*)
2. 如果 [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*argument*) 不是 Object，返回 false
3. 如果 *argument* 有 [[Construct]] 内部方法，返回 true
4. 返回 false

#### 7.2.5 IsExtensible (O)

抽象操作 IsExtensible 用于确定是否可以往对象 *O* 上添加新的属性。返回一个 Boolean 值。操作步骤如下：

1. Assert：Type(*O*) 为 Object
2. 返回 *O*.[[IsExtensible]]()

#### 7.2.6 IsInteger ( argument )

抽象操作 IsInteger 确定 *argument* 是否是一个有限的整数

1. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*argument*)
2. 如果 Type(*argument*) 非 Number，返回 false
3. 如果 *argument* 为 NaN、+**∞** 或 -**∞**，返回 false
4. 如果 [floor](https://262.ecma-international.org/6.0/#sec-algorithm-conventions)([abs](https://262.ecma-international.org/6.0/#sec-algorithm-conventions)(*argument*)) ≠ [abs](https://262.ecma-international.org/6.0/#sec-algorithm-conventions)(*argument*)，返回 false
5. 返回 true

#### 7.2.7 IsPropertyKey ( argument )

抽象操作 IsPropertyKey 确定其类型必须为 ECMAScript 语言类型或者为 Completion Record 类型的 *argument* 是否可作为 property key

1. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*argument*)
2. 如果 Type(*argument*) 为 String，返回 true
3. 如果 Type(*argument*) 为 Symbol，返回 true
4. 返回 false

#### 7.2.8 IsRegExp ( argument )

以 *argument* 为参数抽象操作 IsRegExp 执行以下步骤：

1. 如果 Type(*argument*) 非 Object，返回 false
2. 让 *isRegExp* 为 [Get](https://262.ecma-international.org/6.0/#sec-get-o-p)(*argument*, @@match)
3. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*isRegExp*)
4. 如果 *RegExp* 非 undefined，返回 ToBoolean(*RegExp*)
5. 如果 *argument* 有内部插槽 [[RegExpMatcher]]，返回 true
6. 返回 false

#### 7.2.9 SameValue(x, y)

内部比较抽象操作 SameValue(*x*, *y*)，其中 *x* 和 *y* 为 ECMAScript 语言类型值，返回 true 或 false，比较操作如下：

1. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*x*)

2. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*y*)

3. 如果 Type(*x*) 与 Type(*y*) 不同，返回 false

4. 如果 Type(*x*) 为 Undefined，返回 true

5. 如果 Type(*x*) 为 Null，返回 true

6. 如果 Type(*x*) 为 Number，则：

   ​		a. 如果 *x*、*y* 都为 NaN，返回 true

   ​		b. 如果 *x* 为 -0，*y* 为 +0，返回 false

   ​		c. 如果 *x* 为 +0，*y* 为 -0，返回 false

   ​		d. 如果 *x* 与 *y* 是同一个 Number 值，返回 true

   ​		e. 返回 false

7. 如果 Type(*x*) 为 String，则：

   ​		a. 如果 *x*、*y* 为完全一样的码元序列（在相同索引处有相同的长度和相同的码元），返回 true，否则，返回 false

8. 如果 Type(*x*) 为 Boolean，则：

   ​		a. 如果 *x*、*y* 同时为 true 或同时为 false，返回 true，否则返回 false

9. 如果 Type(*x*) 为 Symbol，则：

   ​		a. 如果 *x*、*y* 为相同的 Symbol 值，返回 true，否则返回 false

10. 如果 *x*、*y* 是同一个 Object 值，返回 true，否则返回 false

#### 7.2.10 SameValueZero(x, y)

内部比较抽象操作 SameValueZero(*x*, *y*)，其中 *x* 和 *y* 为 ECMAScript 语言类型值，返回 true 或 false，比较操作如下：

1. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*x*)

2. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*y*)

3. 如果 Type(*x*) 与 Type(*y*) 不同，返回 false

4. 如果 Type(*x*) 为 Undefined，返回 true

5. 如果 Type(*x*) 为 Null，返回 true

6. 如果 Type(*x*) 为 Number，则：

   ​		a. 如果 *x*、*y* 都为 NaN，返回 true

   ​		b. 如果 *x* 为 -0，*y* 为 +0，返回 false

   ​		c. 如果 *x* 为 +0，*y* 为 -0，返回 true

   ​		d. 如果 *x* 与 *y* 是同一个 Number 值，返回 true

   ​		e. 返回 false

7. 如果 Type(*x*) 为 String，则：

   ​		a. 如果 *x*、*y* 为完全一样的码元序列（在相同索引处有相同的长度和相同的码元），返回 true，否则，返回 false

8. 如果 Type(*x*) 为 Boolean，则：

   ​		a. 如果 *x*、*y* 同时为 true 或同时为 false，返回 true，否则返回 false

9. 如果 Type(*x*) 为 Symbol，则：

   ​		a. 如果 *x*、*y* 为相同的 Symbol 值，返回 true，否则返回 false

10. 如果 *x*、*y* 是同一个 Object 值，返回 true，否则返回 false

注：SameValueZero 只在对待 +0 和 -0 上与 SameValue 不同

#### 7.2.11 抽象关系比较

比较 *x* < *y*（其中 *x* 和 *y*是值）会产生 true、false 或 undefined（这表明至少一个操作数是 NaN）。除 *x* 和 *y* 外，该算法还使用名为 *LeftFirst* 的布尔标志作为参数。该标志用于控制对 *x* 和 *y* 执行具有潜在可见副作用的操作的顺序。这是必需的，因为 ECMAScript 指定了表达式的从左到右求值。*LeftFirst* 的默认值为 true，表示 *x* 参数对应于 *y* 参数对应表达式左侧出现的表达式。如果 *LeftFirst* 为 false，则情况相反，并且必须在 *x* 之前的 *y* 上执行操作。比较操作如下：

1. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*x*)

2. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*y*)

3. 如果 *LeftFirst* 为 true，则：

   ​		a. 让 *px* 为 [ToPrimitive](https://262.ecma-international.org/6.0/#sec-toprimitive)(*x*, hint Number)

   ​		b. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*px*)

   ​		c. 让 *py* 为 [ToPrimitive](https://262.ecma-international.org/6.0/#sec-toprimitive)(*y*, hint Number)

   ​		d. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*py*)

4. 否则，求值顺序需要颠倒以保留从左到右的求值：

   ​		a. 让 *py* 为 [ToPrimitive](https://262.ecma-international.org/6.0/#sec-toprimitive)(*y*, hint Number)

   ​		b. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*py*)

   ​		c. 让 *px* 为 [ToPrimitive](https://262.ecma-international.org/6.0/#sec-toprimitive)*x*, hint Number)

   ​		d. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*px*)

5. 如果 *px* 和 *py* 均为 String，那么：

   ​		a. 如果 *py* 是 *px* 的前缀，返回 false。（一个 String 值 *p* 是另一个 String 值 *q* 的前缀定义为如果 *p* 拼接某个其他 String 值 *r* 能得到 *q*。需要注意的是，任意 String 值是它自身的前缀，因为 *r* 可以为空字符串）

   ​		b. 如果 *px* 是 *py* 的前缀，那么返回 true

   ​		c. 让 *k* 为使得 *px* 和 *py* 在索引 *k* 处的码元不相同的最小的非负整数。（这样的 *k* 是必然存在的，否则两个 String 必有一种一个为另一个的前缀）

   ​		d. 让 *m* 为 *px* 在索引 *k* 处的码元对应的整数

   ​		e. 让 *n* 为 *py* 在索引 *k* 处的码元对应的整数

   ​		f. 如果 *m* < *n*，则返回 true，否则返回 false

6. 否则：

   ​		a. 让 *nx* 为 [ToNumber](https://262.ecma-international.org/6.0/#sec-tonumber)(*px*)。因为 *px* 和 *py* 均为原子类型的值，所以顺序无关紧要

   ​		b. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*nx*)

   ​		c. 让 *ny* 为 [ToNumber](https://262.ecma-international.org/6.0/#sec-tonumber)(*py*)

   ​		d. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*ny*)

   ​		e. 如果 *nx* 为 NaN，返回 undefined

   ​		f. 如果 *ny* 为 NaN，返回 undefined

   ​		g. 如果 *nx* 和 *ny* 为同一个 Number 值，返回 false

   ​		h. 如果 *nx* 为 +0，*ny* 为 -0，返回 false

   ​		i. 如果 *nx* 为 -0，*ny* 为 +0，返回 false

   ​		j. 如果 *nx* 为 **+∞**，返回 false

   ​		k. 如果 *ny* 为 **+∞**，返回 true

   ​		l.  如果 *ny* 为 **-∞**，返回 false

   ​		m. 如果 *nx* 为 **-∞**，返回 true

   ​		n. 如果 *nx* 的数学值小于 *ny* 的数学值（需要注意的是，这些数学值都是有限而且非零的），返回 true，否则返回 false

注 1：[12.7.3](https://262.ecma-international.org/6.0/#sec-addition-operator-plus) 的算法中的第 5 步和第 11 步的区别在于是用 「且」而不是「或」

注 2：字符串的比较对码元值的序列使用简单的字典顺序。没有尝试使用更复杂的，面向语义的字符或字符串相等性定义以及 Unicode 规范中定义的整理顺序。因此，根据 Unicode 标准规范相等的字符串值可以测试为不相等。实际上，该算法假定两个字符串都已经处于规范化形式。另外，请注意，对于包含补充字符的字符串，UTF-16 码元值序列的字典顺序与码点值序列的字典顺序不同。

#### 7.2.12 抽象相等比较

比较 *x* == *y*（其中 *x* 和 *y* 是值）会返回 true 或 false。这样的比较如下进行：

1. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*x*)

2. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*y*)

3. 如果 [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*x*) 和 [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*y*) 相同，那么：

   ​		a. 返回返回严格相等比较 *x* === *y* 的结果

4. 如果 *x* 为 null 且 *y* 为 undefined，返回 true

5. 如果 *y* 为 null 且 *x* 为 undefined，返回 true

6. 如果 [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*x*) 为 Number 且 [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*y*) 为 String，返回比较 *x* == ToNumber(*y*) 的结果

7. 如果 [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*x*) 为 String 且 [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*y*) 为 Number，返回比较 ToNumber(*x*) == *y* 的结果

8. 如果 [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*x*) 为 Boolean，返回比较 ToNumber(*x*)==*y* 的结果

9. 如果 [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*y*) 为 Boolean，返回比较 *x*==ToNumber(*y*) 的结果

10. 如果 [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*x*) 为 String、Number 或 Symbol 之一且 [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*y*) 为 Object，返回比较 *x*==ToPrimitive(*y*) 的结果

11. 如果 [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*x*) 为 Object 且 [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*y*) 为 String、Number 或 Symbol 之一，返回 ToPrimitive(*x*)==*y* 的结果

12. 返回 false

#### 7.2.13 严格相等比较

比较 *x* === *y*，其中 *x* 和 *y* 为值，返回 true 或 false，比较操作如下：

1. 如果 Type(*x*) 与 Type(*y*) 不同，返回 false

2. 如果 Type(*x*) 为 Undefined，返回 true

3. 如果 Type(*x*) 为 Null，返回 true

4. 如果 Type(*x*) 为 Number，则：

   ​		a. 如果 *x 为 NaN，返回 false

   ​		b. a. 如果 *y* 为 NaN，返回 false

   ​		c. 如果 *x* 与 *y* 是同一个 Number 值，返回 true

   ​		d. 如果 *x* 为 -0，*y* 为 +0，返回 true

   ​		e. 如果 *x* 为 +0，*y* 为 -0，返回 true

   ​		f. 返回 false

5. 如果 Type(*x*) 为 String，则：

   ​		a. 如果 *x*、*y* 为完全一样的码元序列（在相同索引处有相同的长度和相同的码元），返回 true

   ​		b. 否则，返回 false

6. 如果 Type(*x*) 为 Boolean，则：

   ​		a. 如果 *x*、*y* 同时为 true 或同时为 false，返回 true

   ​		b. 否则，返回 false

7. 如果 Type(*x*) 为 Symbol，则：

   ​		a. 如果 *x*、*y* 为相同的 Symbol 值，返回 true

8. 如果 *x*、*y* 是同一个 Object 值，返回 true

9. 返回 false

注：算法与 SameValue 算法（[7.2.9](https://262.ecma-international.org/6.0/#sec-samevalue)）的区别在于处理 0 和 NaN 上有所不同。

### 7.3 对象操作

#### 7.3.1 Get(O, P)

抽象操作 Get 用于获取对象指定属性的值。操作传入两个参数，*O* 为对象，*P* 为一个属性键。抽象操作执行以下步骤：

1. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*O*) 为 Object.
2. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [IsPropertyKey](https://262.ecma-international.org/6.0/#sec-ispropertykey)(*P*) 为 **true**.
3. 返回 *O*.\[[Get]\](*P*, *O*)

#### 7.3.2 GetV (V, P)

抽象操作 GetV 用于获取一个 ECMAScript 语言值的指定属性的值。如果值非对象，则使用适合该值类型的包装对象执行属性查找。此操作传入 *V* 和 *P* 两个参数调用，其中 *V* 为值 *P* 为属性键。执行步骤如下：

1. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [IsPropertyKey](https://262.ecma-international.org/6.0/#sec-ispropertykey)(*P*) 为 **true**
2. 让 *O* 为 [ToObject](https://262.ecma-international.org/6.0/#sec-toobject)(*V*)
3. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*O*)
4. 返回 *O*.\[[Get]\](*P*, *V*)

#### 7.3.3 Set (O, P, V, Throw)

抽象操作 SetV 用于设置一个 对象的指定属性的值。操作传入 *O*、*P*、*V*、*Throw* 四个参数。其中 *O* 为对象，*P* 为属性键，*V* 为待赋的新属性值，*Throw* 为 Boolean 标记。抽象操作执行步骤如下：

1. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*O*) 为 Object
2. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [IsPropertyKey](https://262.ecma-international.org/6.0/#sec-ispropertykey)(*P*) 为 **true**
3. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*Throw*) 为 Boolean
4. 让 *success* 为 *O*.\[[Set]\](*P*, *V*, *O*)
5. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*success*)
6. 如果 *success* 为 **false** 而且 *Throw* 为 **true**，则引发一个 **TypeError** 异常
7. 返回 *success*

#### 7.3.4 CreateDataProperty (O, P, V)

抽象操作 CreateDataProperty 用于为对象创建一个新的自有属性。操作以 *O*、*P*、*V* 为参数调用，其中 *O* 为对象，*P* 为属性键，*V* 为属性值。抽象操作执行步骤如下：

1. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*O*) 为 Object
2. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [IsPropertyKey](https://262.ecma-international.org/6.0/#sec-ispropertykey)(*P*) 为 **true**
3. 让 *newDesc* 为 PropertyDescriptor{[[Value]]: *V*, [[Writable]]: **true**, [[Enumerable]]: **false**, [[Configurable]]: **true**}
4. 返回 *O*.\[[DefineOwnProperty]\](*P*, *newDesc*)

#### 7.3.5 CreateMethodProperty (O, P, V)

抽象操作 CreateMethodProperty 用于为对象创建一个新的自有属性。操作以 *O*、*P*、*V* 为参数调用，其中 *O* 为对象，*P* 为属性键，*V* 为属性值。抽象操作执行步骤如下：

1. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*O*) 为 Object
2. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [IsPropertyKey](https://262.ecma-international.org/6.0/#sec-ispropertykey)(*P*) 为 **true**
3. 让 *newDesc* 为 PropertyDescriptor{[[Value]]: *V*, [[Writable]]: **true**, [[Enumerable]]: **false**, [[Configurable]]: **true**}
4. 返回 *O*.\[[DefineOwnProperty]\](*P*, *newDesc*)

#### 7.3.6 CreateDataPropertyOrThrow (O, P, V)

抽象操作 CreateDataPropertyOrThrow 用于为对象创建一个新的自有属性。如果不能创建则引发一个 **TypeError** 异常。操作以 *O*、*P*、*V* 为参数调用，其中 *O* 为对象，*P* 为属性键，*V* 为属性值。抽象操作执行步骤如下：

1. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*O*) 为 Object
2. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [IsPropertyKey](https://262.ecma-international.org/6.0/#sec-ispropertykey)(*P*) 为 **true**
3. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*Throw*) 为 Boolean
4. 让 *success* 为 [CreateDataProperty](https://262.ecma-international.org/6.0/#sec-createdataproperty)
5. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*success*)
6. 如果 *success* 为 **false** 而且 *Throw* 为 **true**，则引发一个 **TypeError** 异常
7. 返回 *success*

注：此抽象操作将创建一个属性，该属性的特性设置为与 ECMAScript 语言赋值运算符创建的属性所使用的默认值相同的默认值。通常，该属性不会已经存在。如果它确实存在并且不可配置，或者 *O* 不可扩展，则 [[DefineOwnProperty]] 将返回 false，导致此操作引发 **TypeError** 异常。

#### 7.3.7 DefinePropertyOrThrow (O, P, desc)

抽象操作 DefinePropertyOrThrow 用于调用一个对象的 [[DefineOwnProperty]] 内部方法，如果指定的属性不能更新，则引发一个 **TypeError** 异常。操作以 *O*、*P* 和 *desc* 为参数，其中 *O* 为对象，*P* 为属性键，*desc* 为属性描述。抽象操作执行以下步骤：

1. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*O*) 为 Object
2. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [IsPropertyKey](https://262.ecma-international.org/6.0/#sec-ispropertykey)(*P*) 为 **true**
3. 让 *success* 为 *O*.\[[DefineOwnProperty]\](*P*, *desc*)
4. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*success*)
5. 如果 *success* 为 **false**，引发一个 **TypeError** 异常
6. 返回 *success*

#### 7.3.8 DeletePropertyOrThrow (O, P)

抽象操作 DeletePropertyOrThrow 用于将一个对象的指定自有属性移除。当属性为不可配置时，引发一个异常。操作以 *O* 和 *P* 为参数，其中 *O* 为对象，*P* 为属性键。抽象操作执行以下步骤：

1. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*O*) 为 Object
2. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [IsPropertyKey](https://262.ecma-international.org/6.0/#sec-ispropertykey)(*P*) 为 **true**
3. Let *success* be *O*.\[[Delete]\](*P*)
4. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*success*)
5. 如果 *success* 为 **false**，引发一个 **TypeError** 异常
6. 返回 *success*

#### 7.3.9 GetMethod (O, P)

抽象操作 GetMethod 用于获取对象的指定属性，该属性的值为一个函数。操作以 *O* 和 *P* 为参数，其中 *O* 为对象，*P* 为属性键。抽象操作执行以下步骤：

1. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [IsPropertyKey](https://262.ecma-international.org/6.0/#sec-ispropertykey)(*P*) 为 **true**
2. 让 *func* 为 [GetV](https://262.ecma-international.org/6.0/#sec-getv)(*O*, *P*)
3. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*func*)
4. 如果 *func* 为 **undefined、****null** 之一、 返回 **undefined**
5. 如果 [IsCallable](https://262.ecma-international.org/6.0/#sec-iscallable)(*func*) 为 **false**，引发一个 **TypeError** 异常
6. 返回 *func*

#### 7.3.10 HasProperty (O, P)

抽象操作 HasProperty 用于确定一个对象是否有指定属性。属性可以是自有的也可以是继承的。返回一个 Boolean 值。操作以 *O* 和 *P* 为参数，其中 *O* 为对象，*P* 为属性键。抽象操作执行以下步骤：

1. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*O*) 为 Object
2. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [IsPropertyKey](https://262.ecma-international.org/6.0/#sec-ispropertykey)(*P*) 为 **true**
3. 返回 *O*.\[[HasProperty]\](*P*)

#### 7.3.11 HasOwnProperty (O, P)

抽象操作 HasOwnProperty 用于确定一个对象是否有指定的自有属性。返回一个 Boolean 值。操作以 *O* 和 *P* 为参数，其中 *O* 为对象，*P* 为属性键。抽象操作执行以下步骤：

1. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*O*) 为 Object
2. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [IsPropertyKey](https://262.ecma-international.org/6.0/#sec-ispropertykey)(*P*) 为 **true**
3. 让 *desc* 为 *O*.\[[GetOwnProperty]\](*P*)
4. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*desc*)
5. 如果 *desc* 为 **undefined**，返回 *false**.
6. 返回 **true**

#### 7.3.13 Call(F, V, [argumentsList])

抽象操作 Call 用于调用函数对象的内部方法 [[Call]]。操作以 *F*、*V* 和一个可选的 *argumentsList* 为参数调用，其中 *F* 为函数对象，*V* 是一个为 [[Call]] 的 *this* 值的 ECMAScript 语言值，以及 *argumentsList* 是传给对应内部方法的参数值。如果没传 *argumentsList*，则一个空 List 作为其值。抽象操作执行以下步骤：

1. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*F*)
2. 如果未传 *argumentsList，让 *argumentsList* 为一个新的空 [List](https://262.ecma-international.org/6.0/#sec-list-and-record-specification-type)
3. 如果 [IsCallable](https://262.ecma-international.org/6.0/#sec-iscallable)(*F*) 为 **false**，引发一个 **TypeError** 异常
4. 返回 *F*.\[[Call]\](*V*, *argumentsList*)

注：如果未传 *newTarget* ，操作等同于：**new F(...argumentsList)**

#### 7.3.14 SetIntegrityLevel (O, level)

抽象操作 SetIntegrityLevel 用于固定对象自身属性的集合，抽象操作执行以下步骤：

1. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*O*) 为 Object

2. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): *level* 为 `"sealed"` 或 `"frozen"`

3. 让 *status* 为 *O*.\[[PreventExtensions]\]()

4. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*status*)

5. 如果 *status* 为 **false**，返回 **false**.

6. 让 *keys* 为 *O*.\[[OwnPropertyKeys]\]()

7. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*keys*)

8. 如果 *level* 为 "sealed"，那么：

   ​		a. 为 *keys* 的每个元素 *k* 重复

   ​					i. 让 *status* 为 [DefinePropertyOrThrow](https://262.ecma-international.org/6.0/#sec-definepropertyorthrow)(*O*, *k*, PropertyDescriptor{ [[Configurable]]: **false**})

   ​					ii. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*status*)

9. 否则，*level* 为 "frozen"

   ​		a. 为 *keys* 的每个元素 *k* 重复

   ​					i. 让 *currentDesc* 为 *O*.\[[GetOwnProperty]\](*k*)

   ​					ii. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*currentDesc*)

   ​					iii. 如果 *currentDesc* 非 undefined，那么：

   ​								1. 如果 [IsAccessorDescriptor](https://262.ecma-international.org/6.0/#sec-isaccessordescriptor)(*currentDesc*) 为 **true，那么

   ​											a. 让 *desc* 为 PropertyDescriptor{[[Configurable]]: **false**}

   ​								 2. 否则

   ​											a. 让 *desc* 为 PropertyDescriptor { [[Configurable]]: **false**, [[Writable]]: **false** }

   ​								3. 让 *status* 为 [DefinePropertyOrThrow](https://262.ecma-international.org/6.0/#sec-definepropertyorthrow)(*O*, *k*, *desc*)

   ​								4. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*status*)

10. 返回 **true**

#### 7.13.5 TestIntegrityLevel (O, level)

抽象操作 TestIntegrityLevel 用于确定对象自身属性的集合是否固定。抽象操作执行以下步骤：

1. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*O*) 为 Object
2. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): *level* 为 `"sealed"` 或 `"frozen"`
3. 让 *status* 为 [IsExtensible](https://262.ecma-international.org/6.0/#sec-isextensible-o)(*O*)
4. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*status*)
5. 如果 *status* 为 **true**，返回 **false**
6. 注：如果对象是可扩展的，不检测其属性
7. 让 *keys* 为 *O*.\[[OwnPropertyKeys]\]()
8. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*keys*)
9. 为 *keys* 的每个元素 *k* 重复
   1. 让 *currentDesc* 为 *O*.\[[GetOwnProperty]\](*k*)
   2. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*currentDesc*)
   3. 如果 *currentDesc* 非 undefined，那么：
      1. 如果 *currentDesc*.[[Configurable]] 为 **true**，返回 **false**
      2. 如果 *level* 为 "frozen" 且 IsDataDescriptor(*currentDesc*) 为 true，那么：
         1. 如果 *currentDesc*.[[Writable]] 为 **true，**返回 **false**
10. 返回 **true**

#### 7.3.16 CreateArrayFromList (elements)

抽象操作 CreateArrayFromList 用于创建一个其元素由 List 提供的数组对象。抽象操作执行如下步骤：

1. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): *elements* 为一个其元素均为 ECMASCript 语言类型值的 [List](https://262.ecma-international.org/6.0/#sec-list-and-record-specification-type)
2. 让 *array* 为 [ArrayCreate](https://262.ecma-international.org/6.0/#sec-arraycreate)(0) ([见 9.4.2.2](https://262.ecma-international.org/6.0/#sec-arraycreate))
3. 让 *n* 为 0
4.  对 *elements* 的每个元素 *e*：
   1. 让 *status* 为 [CreateDataProperty](https://262.ecma-international.org/6.0/#sec-createdataproperty)(*array*, [ToString](https://262.ecma-international.org/6.0/#sec-tostring)(*n*), *e*)
   2. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): *status* 为 **true**
   3. *n* 加 1
5. 返回 *array*

#### 7.3.17 CreateListFromArrayLike (obj [, elementTypes] )

抽象操作 CreateListFromArrayLike 用于创建一个其元素由类数组对象 *obj* 的索引类属性提供的 List。可选参数 *elementTypes* 是一个 List，其中包含所创建 List 的元素值所允许的 ECMAScript 语言类型的名称。抽象操作执行如下步骤：

1. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*obj*)
2. 如果未传 *elementTypes*，让 *elementTypes* 为 (Undefined, Null, Boolean, String, Symbol, Number, Object)
3. 如果 [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*obj*) 非 Object，引发一个 **TypeError** 异常
4. 让 *len* 为 [ToLength](https://262.ecma-international.org/6.0/#sec-tolength)([Get](https://262.ecma-international.org/6.0/#sec-get-o-p)(*obj*, `"length"`))
5. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*len*)
6. 让 *list* 为一个空 [List](https://262.ecma-international.org/6.0/#sec-list-and-record-specification-type)
7. 让 *index* 为 0
8. 重复以下步骤直到 *index*<*len*：
   1. 让 *indexName* 为  [ToString](https://262.ecma-international.org/6.0/#sec-tostring)(*index*)
   2. 让 *next* 为 [Get](https://262.ecma-international.org/6.0/#sec-get-o-p)(*obj*, *indexName*)
   3. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*next*)
   4. 如果 [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*next*)  不包含在 *elementTypes* 里, 引发一个 **TypeError** 异常
   5. 将 *next* 作为最后一个元素添加到 *list* 里
   6. *index* 加 1
9. 返回 *list*

#### 7.3.18 Invoke(O,P, [argumentsList])

抽象操作 Invoke 用于调用对象的方法。操作以 *O*、*P* 和一个可选的 *argumentsList* 为参数，其中 *O* 既为属性的查找点，又作为调用的 *this* 值，*P* 是属性键，而 *argumentsList* 为传给方法的参数列表。如果没传 *argumentsList*，那么其值为一个空 List。抽象操作执行如下步骤：

1. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [IsPropertyKey](https://262.ecma-international.org/6.0/#sec-ispropertykey)(*P*) 为 **true**
2. 如果未传 *argumentsList，让 *argumentsList* 为一个新的空 [List](https://262.ecma-international.org/6.0/#sec-list-and-record-specification-type)
3. 让 *func* 为 [GetV](https://262.ecma-international.org/6.0/#sec-getv)(*O*, *P*)
4. 返回 [Call](https://262.ecma-international.org/6.0/#sec-call)(*func*, *O*, *argumentsList*)

#### 7.3.19 OrdinaryHasInstance (C, O)

抽象操作 OrdinaryHasInstance 实现确定一个对象 *O* 是否从构造函数 *C* 提供的实例对象继承路径继承的默认算法。抽象操作执行如下步骤

1. 如果 [IsCallable](https://262.ecma-international.org/6.0/#sec-iscallable)(*C*) 为 **false**，返回 **false**
2. 如果 *C* 有 [[BoundTargetFunction]] 内部插槽，则：
   1. 让 *BC*  为 *C* 的 [[[BoundTargetFunction\]]](https://262.ecma-international.org/6.0/#sec-bound-function-exotic-objects) 内部插槽的值
   2. 返回 [InstanceofOperator](https://262.ecma-international.org/6.0/#sec-instanceofoperator)(*O*,*BC*) ([见 12.9.4](https://262.ecma-international.org/6.0/#sec-instanceofoperator))
3. 如果 [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*O*) 非 Object，返回 false
4. 让 *P* 为 [Get](https://262.ecma-international.org/6.0/#sec-get-o-p)(*C*, `"prototype"`)
5. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*P*)
6. 如果 [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*P*) 非 Object，引发一个 **TypeError** 异常
7. 重复：
   1. 让 *O* 为 *O*.[[GetPrototypeOf]]()
   2. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*O*)
   3. 如果 *O* 为 `null，`return **false**
   4. 如果 [SameValue](https://262.ecma-international.org/6.0/#sec-samevalue)(*P*, *O*) 为 **true**，返回 **true**

#### 7.3.20 SpeciesConstructor ( O, defaultConstructor )

抽象操作 SpeciesConstructor 用于检索构造函数，该构造函数应用于创建从参数对象 *O* 派生的新对象。**defaultConstructor** 参数是在从 *O* 开始找不到构造器 @@species 属性时使用的构造器。抽象操作执行如下步骤：

1. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*O*) 为 Object
2. 让 *C* 为 [Get](https://262.ecma-international.org/6.0/#sec-get-o-p)(*O*, `"constructor"`)
3. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*C*)
4. 如果 *C* 为 **undefined，**返回 *defaultConstructor*
5. 如果 [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*C*) 非 Object，引发一个 **TypeError** 异常
6. 让 *S* 为 [Get](https://262.ecma-international.org/6.0/#sec-get-o-p)(*C*, @@species)
7. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*S*)
8. 如果 *S* 为 **undefined** 或 **null**，返回 *defaultConstructor*
9. 如果 [IsConstructor](https://262.ecma-international.org/6.0/#sec-isconstructor)(*S*) 为 **true**，返回 *S*
10. 引发一个 **TypeError** 异常

#### 7.3.21 EnumerableOwnNames (O)

抽象操作 EnumerableOwnNames 被调用时，执行如下步骤：

1. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*O*) 为 Object
2. 让 *ownKeys* 为 *O*.\[[OwnPropertyKeys]\]()
3. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*ownKeys*)
4. 让 *names* 为一个新的空 [List](https://262.ecma-international.org/6.0/#sec-list-and-record-specification-type)
5. 按 List 顺序为 *ownProperty* 的每个元素 *key* 重复：
   1. 如果 Type(*key*) 为 String，那么：
      1. 让 *desc* 为 *O*.\[[GetOwnProperty]\](*key*)
      2. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*desc*)
      3. 如果 *desc* 非 undefined，那么：
         1. 如果 *desc.*[[Enumerable]] 为 **true，将 *key* 添加到 *names*
6. 对名称元素进行排序，以使它们具有与 Iterator 生成的相对顺序相同的相对顺序，如果在 *O*上调用 [[Enumerate]] 内部方法，则该 Iterator 会返回该元素。
7. 返回 *names*

注：返回列表中元素的顺序与 for-in 语句使用的枚举顺序相同

#### 7.3.22 GetFunctionRealm ( obj )

抽象操作 GetFunctionRealm (*obj*) 执行如下步骤：

1. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): *obj* 为可调用对象
2. 如果 *obj* 有 [[Realm]] 内部插槽，那么：
   1. 返回 *obj 的 [[Realm]] 内部插槽
3. 如果 *obj* 为 [Bound Function](https://262.ecma-international.org/6.0/#sec-bound-function-exotic-objects) 奇异对象，那么：
   1. 让 *target* 为 *obj* 的 [[[BoundTargetFunction\]]](https://262.ecma-international.org/6.0/#sec-bound-function-exotic-objects) 内部插槽
   2. 返回 GetFunctionRealm(*target*)
4. 如果 *obj* 为 Proxy 奇异对象，那么：
   1. 如果 *obj* 的 [[ProxyHandler]] 内部插槽的值为 **null**, 引发一个 **TypeError** 异常
   2. 让 *proxyTarget* 为 *obj* 的 [[ProxyTarget]] 内部插槽的值
   3. 返回 GetFunctionRealm(*proxyTarget*)
5. 返回 [the running execution context](https://262.ecma-international.org/6.0/#sec-execution-contexts) 的 [Realm](https://262.ecma-international.org/6.0/#sec-code-realms)

注：仅当 *target* 是不具有 [[Realm]] 内部插槽的非标准奇异函数对象时，才可能执行到步骤 5。

### 7.4 对迭代器对象的操作

请参见常用迭代接口（[25.1](https://262.ecma-international.org/6.0/#sec-iteration)）

#### 7.4.1 GetIterator ( obj, method )

抽象操作 GetIterator 以参数 *obj* 和 *method* 调用时，执行以下步骤：

1. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*obj*)
2. 如果 *method* 未传，那么：
   1. 让 *method* 为 [GetMethod](https://262.ecma-international.org/6.0/#sec-getmethod)(*obj*, @@iterator)
   2. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*method*)
3. 让 *iterator* 为 [Call](https://262.ecma-international.org/6.0/#sec-call)(*method*,*obj*)
4. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*iterator*)
5. 如果 [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*iterator*) 为 Object，引发 **TypeError** 异常
6. 返回 *iterator*





#### 7.4.2 IteratorNext ( iterator, value )

抽象操作 IteratorNext 以参数 *iterator* 和 *value* 调用时，执行以下步骤：

1. 如果 *value* 未传，那么：
   1. 让 *result* 为 [Invoke](https://262.ecma-international.org/6.0/#sec-invoke)(*iterator*, `"next"`, «‍ »)
2. 否则：
   1. 让 *result* 为 [Invoke](https://262.ecma-international.org/6.0/#sec-invoke)(*iterator*, `"next"`, «‍*value*»)
3. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*result*)
4. 如果 [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*result*) 非 Object，引发 **TypeError** 异常
5. 返回 *result*

#### 7.4.3 IteratorComplete ( iterResult )

抽象操作 IteratorComplete 以参数 *iterResult* 调用时，执行以下步骤：

1. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*iterResult*) 为 Object.
2. 返回 [ToBoolean](https://262.ecma-international.org/6.0/#sec-toboolean)([Get](https://262.ecma-international.org/6.0/#sec-get-o-p)(*iterResult*, `"done"`))

#### 7.4.4 IteratorValue ( iterResult )

抽象操作 IteratorValue 以参数 *iterResult* 调用时，执行以下步骤：

1. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*iterResult*) 为 Object.
2. 返回 [Get](https://262.ecma-international.org/6.0/#sec-get-o-p)(*iterResult*, `"value"`)

#### 7.4.5 IteratorStep ( iterator )

带有参数迭代器的抽象操作 IteratorStep 会向迭代器请求下一个值，并返回 false（表明迭代器已到达末尾）或 IteratorResult 对象（如果有下一个值可用）。IteratorStep 执行如下步骤：

1. 让 *result* 为  [IteratorNext](https://262.ecma-international.org/6.0/#sec-iteratornext)(*iterator*)
2. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*result*)
3. 让 *done* 为 [IteratorComplete](https://262.ecma-international.org/6.0/#sec-iteratorcomplete)(*result*)
4. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*done*)
5. 如果 *done* 为 **true**，返回 **false**
6. 返回 *result*

 #### 7.4.6 IteratorClose( iterator, completion )

抽象操作 IteratorClose 以 *iterator* 和 *completion* 为参数，用于通知迭代器应该执行在达到其完成状态时通常应执行的任何操作：

1. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*iterator*) 为 Object
2. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): *completion* 为 [Completion Record](https://262.ecma-international.org/6.0/#sec-completion-record-specification-type)
3. 让 *return* 为 [GetMethod](https://262.ecma-international.org/6.0/#sec-getmethod)(*iterator*, `"return"`)
4. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*return*)
5. 如果 *return* 为 **undefined*，返回 [Completion](https://262.ecma-international.org/6.0/#sec-completion-record-specification-type)(*completion*)
6. 让 *innerResult* 为 [Call](https://262.ecma-international.org/6.0/#sec-call)(*return*, *iterator*, «‍ »)
7. 如果 *completion*.[[type]] 为  **throw**，返回 [Completion](https://262.ecma-international.org/6.0/#sec-completion-record-specification-type)(*completion*)
8. 如果 *innerResult*.[[type]] 为 **throw**，返回 [Completion](https://262.ecma-international.org/6.0/#sec-completion-record-specification-type)(*innerResult*)
9. 如果 [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*innerResult*.[[value]]) 非 Object，引发 **TypeError** 异常
10. 返回 [Completion](https://262.ecma-international.org/6.0/#sec-completion-record-specification-type)(*completion*)

#### 7.4.7 CreateIterResultObject ( value, done )

抽象操作 CreateIterResultObject 以 *value* 和 *done* 为参数，创建一个支持 IteratorResult 接口的对象，通过执行如下步骤：

1. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*done*) 为 Boolean
2. 让 *obj* 为 [ObjectCreate](https://262.ecma-international.org/6.0/#sec-objectcreate)(%ObjectPrototype%)
3. 执行 [CreateDataProperty](https://262.ecma-international.org/6.0/#sec-createdataproperty)(*obj*, `"value"`, *value*)
4. 执行 [CreateDataProperty](https://262.ecma-international.org/6.0/#sec-createdataproperty)(*obj*, `"done"`, *done*)
5. 返回 *obj*

#### 7.4.8 CreateListIterator ( list )

具有参数 *list* 的抽象操作 CreateListIterator 创建一个Iterator（[25.1.1.2](https://262.ecma-international.org/6.0/#sec-iterator-interface)）对象，该对象的下一个方法返回 *list* 的连续元素。它执行以下步骤：

1. 让 *iterator* 为 [ObjectCreate](https://262.ecma-international.org/6.0/#sec-objectcreate)(%IteratorPrototype%, «[[IteratorNext]], [[IteratedList]], [[ListIteratorNextIndex]]»)
2. 设置 *iterator* 的 [[IteratedList]] 内部插槽为 *list*
3. 设置 *iterator* 的 [[ListIteratorNextIndex]] 内部插槽为 0
4. 让 *next* 为 一个新的如 ListIterator `next` ([7.4.8.1](https://262.ecma-international.org/6.0/#sec-listiterator-next)) 所定义的内置函数对象
5. 设置 *iterator* 的  [[IteratorNext]] 内部插槽为 *next*
6. 执行 [CreateMethodProperty](https://262.ecma-international.org/6.0/#sec-createmethodproperty)(*iterator*, `"next"`, *next*)
7. 返回 *iterator*

##### 7.4.8.1 ListIterator next( )

ListIterator **next** 方法为一个标准的内置函数对象（[clause 17](https://262.ecma-international.org/6.0/#sec-ecmascript-standard-built-in-objects)），它执行如下步骤：

1. 让 *O* 为 **this** 值
2. 让 *f* 为活跃的函数对象
3. 如果 *O* 没有 [[IteratorNext]] 内置对象，引发 **TypeError** 异常
4. 让 *next* 为 *O* 的  [[IteratorNext]] 内部插槽的值
5. 如果 [SameValue](https://262.ecma-international.org/6.0/#sec-samevalue)(*f*, *next*) 为 **false**，引发 **TypeError** 异常
6. 如果 *O*  没有 [[IteratedList]] 内置插槽，引发 **TypeError** 异常
7. 让 *list* 为 *O* 的 [[IteratedList]] 内置插槽的值
8. 让 *index* 为 *O* 的 [[ListIteratorNextIndex]] 内置插槽的值
9. 让 *len* 为 *list* 的元素的个数
10. 如果 *index*≥*len*，那么：
    1. 返回 [CreateIterResultObject](https://262.ecma-international.org/6.0/#sec-createiterresultobject)(**undefined**, **true**)
11. 设置 *O* 的 [[ListIteratorNextIndex]] 的内部插槽的值为 *index*+1.
12. 返回 [CreateIterResultObject](https://262.ecma-international.org/6.0/#sec-createiterresultobject)(*list*[*index*], **false**)

注意：如果将 ListIterator **next** 方法应用于最初与其关联的对象以外的任何对象，则将引发异常。

## 8 可执行代码和执行上下文

### 8.1 Lexical Environments

一个 *Lexcical Environment*（译者注：后统一翻译为「词法环境」）是一个规范类型，用于根据 ECMAScript 代码的词法嵌套结构来定义标识符与特定变量和函数的关联。一个词法环境由一个 [Environment Record](https://262.ecma-international.org/6.0/#sec-environment-records) 和一个指向外部词法环境的可能为空的引用组成。通常，词法环境总是与某些 ECMAScript 代码的特定语法结构相关联，比如 *FunctionDeclaration*、*BlockStatement* 或者 *TryStatement* 的 *Catch* 子句，每次些代码被求值时就会创建一个新的词法环境。

一个 [Environment Record](https://262.ecma-international.org/6.0/#sec-environment-records) 记录了相关词法环境作用域内创建的标识符的绑定。它被称为词法环境的 EnvironmentRecord。

外部环境引用用于对逻辑嵌套的词法环境值进行建模。一个（内部）词法环境的引用指的是对一个逻辑上包围内部词法环境的的词法环境。一个外部词法环境当然也会有自己的外部词法环境。一个词法环境可以作为多个内部词法环境的外部环境。比如，如果 *FunctionDeclaration* 里包含两个嵌套的 *FunctionDeclarations*，那么两个嵌套函数的词法环境都以包围这两个嵌套函数的函数的词法环境为外部词法环境。

「全局环境」是一个没有外部环境的词法环境。全局环境的外部环境引用为空。全局环境的 EnvironmentRecord 可能预填充了一些标识符绑定，并且包括关联的「全局对象」，该对象的属性提供了某些全局环境的标识符绑定。全局对象是全局环境的 **this** 绑定的值。随着 ECMAScript 代码的执行，其他属性可以被添加到全局对象，初始属性也可以被修改。

「模块环境」是一个包含模块顶级声明的绑定的词法环境。它也包含一些显式从其他模块导入的绑定。模块环境的外部环境是全局环境。

函数环境是一个对应于 ECMAScript 函数对象调用的词法环境。一个函数环境可以创建一个新的 *this* 绑定。函数环境还捕获支持 *super* 方法调用所必需的状态。

词法环境和 [Environment Record](https://262.ecma-international.org/6.0/#sec-environment-records) （译者注：后续翻译为「环境记录」）值纯粹是规范的机制，不需要与 ECMAScript 实现的任何特定 artefact 相对应。一个 ECMAScript 程序不可能直接访问和操作这些值。

#### 8.1.1 环境记录

本规范中主要包括两种环境记录的值：「声明式环境记录」和「对象环境记录」。声明式环境记录用于定义如 *FunctionDeclarations*、*VariableDeclarations* 和 *Catch* 子句等这些直接将标识符与 ECMAScript 语言值关联的 ECMAScript 语言语法元素的效果。对象环境记录用于定义如 *WithStatement* 等这些直接将标识符与某个对象的属性关联的 ECMAScript 语言语法元素的效果。全局环境记录和函数环境记录则是专门用于脚本全局声明和函数内顶级声明。

出于规范目的，环境记录的值为 Record 规范类型的值，而且可以认为它存在于简单的面向对象的层次结构中，其中环境记录是一个抽象类，具有三个具体的子类，即**声明式环境记录**，**对象环境记录**和**全局环境记录**。**函数环境记录**和**模块环境记录**是声明式环境记录的子类。抽象类所包含的规范方法定义如表 15 所示，这些抽象方法对每个具体的子类都有不同的具体算法。

##### 表 15 —— 环境记录的抽象方法

| 方法                         | 目的                                                         |
| ---------------------------- | ------------------------------------------------------------ |
| HasBinding(N)                | 确定环境记录是否有字符串值为 *N* 的绑定。有则返回 true，否则返回 false。 |
| CreateMutableBinding(N, D)   | 在一个环境记录中创建一个新的但是未初始化的绑定。字符串值 *N* 为绑定的名称的文本。如果可选的 Boolean 型变量 *D* 的值为 true，绑定随后可能被删除。 |
| CreateImmutableBinding(N, S) | 在环境记录中创建一个新的但是未初始化的不可变绑定。字符串值 *N* 为绑定的名称的文本。如果 *S* 为 true，那么在绑定初始化前尝试访问绑定的值或者在它初始化后尝试将之设置成其他值都会引发异常，不管引用该绑定的操作的严格模式设置如何。*S* 可选，默认值值为 false。 |
| InitializeBinding(N,V)       | 为环境记录里已经存在但未初始化的绑定设置值。字符串值 *N* 为绑定的名称的文本。*V* 为待设置的值，可以是任何 ECMAScript 语言类型的值。 |
| SetMutableBinding(N,V, S)    | 为环境记录里已经存在的可变的绑定设置值。字符串值 *N* 为绑定的名称的文本。*V* 为待设置的值，可以是任何 ECMAScript 语言类型的值。*S* 为 Boolean 类型。如果为 tue 且绑定不可被设置，那么引发一个 **TypeError** 异常。 |
| GetBindingValue(N,S)         | 获取环境记录中一个以及存在的绑定的值。字符串值 *N* 为绑定的名称的文本。*S* 用于标识源自严格模式代码的引用，或者以其他方式需要严格模式引用语义的引用。如果 *S* 为 true 而且绑定不存在，引发一个 **ReferenceError** 异常。如果绑定存在但是未被初始化，引发一个 **ReferenceError** 不管 *S* 为何值。 |
| DeleteBinding(N)             | 从环境记录中删除一个绑定。字符串值 *N* 为绑定的名称的文本。如果 *N* 对应的绑定存在，那么移除绑定然后返回 true。如果绑定存在，但不能移除，返回 false。如果绑定不存在，返回 true。 |
| HasThisBinding()             | 确定环境记录是否创建 **this** 绑定。是则返回 true，否则返回 false。 |
| HasSuperBinding()            | 确定环境记录是否创建 **super** 方法绑定。是则返回 true，否则返回 false。 |
| WithBaseObject ()            | 如果环境记录与一个 **with** 语句关联则返回对应的对象，否则返回 false。 |

##### 8.1.1.1 声明式环境记录

每个声明式环境记录都与一个包含 variable、constant、 let、 class、module、import 和/或函数声明的 ECMAScript 程序作用域关联。声明式环境记录为其作用域中通过声明定义的标识符创建绑定。

声明式环境记录的具体规范方法的行为由如下算法定义。

###### 8.1.1.1.1 HasBinding(N)

用于声明式环境记录的具体环境记录方法 HasBinding 确定参数标识符是否为记录所绑定的标识符之一：

1. 让 *envRec* 为调用方法的声明性环境记录
2. 如果 *envRec* 有名为 *N* 的绑定，返回 true
3. 返回 false

###### 8.1.1.1.2 CreateMutableBinding (N, D)

用于声明式环境记录的具体环境记录方法 CreateMutableBinding 创建一个其名为 *N* 的新的、可变的、未初始化的绑定。环境记录中必须不能已经存在名为 *N* 的绑定。如果 Boolean 变量 *D* 值为 true，则新的绑定被标记为要删除。

1. 让 *envRec* 为调用方法的声明性环境记录
2. Assert：*envRec* 里不存在名为 *N* 的绑定
3. 在 *envRec*  中创建一个对应名称为 *N* 的可变绑定，记录其为未初始化。如果 *D* 为 true，新创建的绑定将会被随后 DeleteBinding 调用删除
4. 返回 [NormalCompletion](https://262.ecma-international.org/6.0/#sec-normalcompletion)(empty)

###### 8.1.1.1.3 CreateImmutableBinding (N, S)

用于声明式环境记录的具体环境记录方法 CreateImmutableBinding 创建一个其名为 *N* 的新的、不可变绑定的、未初始化的绑定。环境记录中必须不能已经存在名为 *N* 的绑定。如果 Boolean 变量 *S* 值为 true，则新的绑定被标记为要严格绑定。

1. 让 *envRec* 为调用方法的声明性环境记录
2. Assert：*envRec* 里不存在名为 *N* 的绑定
3. 在 *envRec*  中创建一个对应名称为 *N* 的不可变的绑定，记录其为未初始化。如果 *S* 为 true，记录新创建的绑定为严格绑定
4. 返回 [NormalCompletion](https://262.ecma-international.org/6.0/#sec-normalcompletion)(empty)

###### 8.1.1.1.4 InitializeBinding (N,V)

用于声明式环境记录的具体环境记录方法 InitializeBinding 用于为名为 *N* 的绑定初始化绑定值为 *V*。一个名为 *N* 的未被初始化的绑定必须已经存在。

1. 让 *envRec* 为调用方法的声明性环境记录
2. Assert：*envRec* 里已经存在名为 *N* 的未初始化绑定
3. 为 *envRec*  其名为 *N* 的绑定设置值为 *V*
4. 记录名称 *N* 对应的绑定为已经初始化
5. 返回 [NormalCompletion](https://262.ecma-international.org/6.0/#sec-normalcompletion)(empty)

###### 8.1.1.1.5 SetMutableBinding (N,V,S)

用于声明式环境记录的具体环境记录方法 SetMutableBinding (N,V,S) 用于修改其名为 *N* 的绑定的值为 *V*。正常情况下名为 *N* 的绑定是已经存在的，但极少情况它也可能不存在。如果对应的绑定是不可变的，那么当 *S* 为 true 时引发一个 **TypeError**。

1. 让 *envRec* 为调用方法的声明性环境记录
2. 如果 *envRec* 已经有名为 *N* 的绑定，那么：
   1. 如果 *S* 为 true，引发一个 **ReferenceError** 异常
   2. 执行 *envRec*.CreateMutableBinding(*N*, **true**)
   3. 返回 Return [NormalCompletion](https://262.ecma-international.org/6.0/#sec-normalcompletion)(empty)
3. 如果 *envRec* 中名为 *N* 的绑定为严格绑定，让 *S* 为 true
4. 如果 *envRec* 中名为 *N* 的绑定未初始化，引发一个 **ReferenceError** 异常
5. 否则如果 envRec* 中名为 *N* 的绑定为可变绑定，更改其值为 *V*
6. 否则，这肯定是更改不可变绑定的值的尝试，因此，如果 *S* 为 true，则引发 **TypeError** 异常

注：一个导致步骤 2 缺少绑定的 ECMAScript 代码示例为 `function f(){eval("var x; x = (delete x, 0);")}`

###### 8.1.1.1.6 GetBindingValue(N,S)

用于声明式环境记录的具体环境记录方法 GetBindingValue 仅仅返回名为 *N* 的绑定的值。如果绑定已经存在，而且还未初始化，引发 **ReferenceError** 异常，不管 *S* 为何值。

1. 让 *envRec* 为调用方法的声明性环境记录
2. Assert：*envRec* 里已经存在名为 *N* 的绑定
3. 如果名为 *N* 的绑定未初始化，引发 **ReferenceError** 异常
4. 返回名为 *N* 的绑定的值

###### 8.1.1.1.7 DeleteBinding (N)

用于声明式环境记录的具体环境记录方法 DeleteBinding 只能删除已经被显式指定为待删除的绑定。

1. 让 *envRec* 为调用方法的声明性环境记录
2. Assert：*envRec* 里已经存在名为 *N* 的绑定
3. 如果名为 *N* 的绑定不能被删除，返回 false
4. 删除名为 *N* 的绑定
5. 返回 true

###### 8.1.1.1.8 HasThisBinding ()

常规的声明性环境记录不提供 **this** 绑定。

1. 返回 false

###### 8.1.1.1.9 HasSuperBinding()

常规的声明性环境记录不提供 **super** 绑定。

1. 返回 false

###### 8.1.1.1.10 WithBaseObject()

声明式环境记录总是返回 **undefined** 作为其 WithBaseObject

1. 返回 WithBaseObject

##### 8.1.1.2 对象环境记录

每个对象环境记录关联一个称为「绑定对象」的对象。对象环境记录为其绑定对象的属性名对应的字符串标识符名的集合创建绑定。名为非字符串的属性不被包含。自有属性和继承属性都被包含，不管其 [[Enumerable]] 特性为何。因为可以动态地从对象中添加和删除属性，所以对象环境记录所绑定的标识符集可能会因添加或删除属性的任何操作的副作用而发生更改。由于这种副作用而创建的任何绑定都被视为可变绑定，即使相应属性的 Writable 特性的值为false。对象环境记录不存在不可变的绑定。

为 **with** 语句创建的对象环境记录可以提供它们的绑定对象作为隐式 *this* 值在函数调用中使用。该功能由与每个对象环境记录关联的 *withEnvironment* Boolean 值控制。 默认情况下，对于任何对象环境记录，*withEnvironment* 的值为 false。

对象环境记录的具体规范方法的行为由如下算法定义。

###### 8.1.1.2.1 HasBinding(N)

用于对象环境记录的具体环境记录方法 HasBinding 确定参数标识符是否为记录所绑定的标识符之一：

1. 让 *envRec* 为调用方法的对象环境记录
2. 让 *bindings* 为 *envRec* 的绑定对象
3. 让 *foundBinding* 为 [HasProperty](https://262.ecma-international.org/6.0/#sec-hasproperty)(*bindings*, *N*)
4. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*foundBinding*)
5. 如果 *foundBinding* 为 false，返回 false
6. 如果 *envRec* 的 *withEnvironment* 标记为 false，返回 true
7. 让 *unscopables* 为 [Get](https://262.ecma-international.org/6.0/#sec-get-o-p)(*bindings*, @@unscopables)
8. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*unscopables*)
9. 如果 [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*unscopables*) 是 Object，则：
   1. 让 *blocked* 为 [ToBoolean](https://262.ecma-international.org/6.0/#sec-toboolean)([Get](https://262.ecma-international.org/6.0/#sec-get-o-p)(*unscopables*, *N*))
   2. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*blocked*)
   3. 如果 *blocked* 为 true，返回 false
10. 返回 true

###### 8.1.1.2.2 CreateMutableBinding (N, D)

用于对象环境记录的具体环境记录方法  CreateMutableBinding 在环境记录的关联绑定对象中创建一个属性，该属性的名称为 String 值，并将其初始化为 undefined。如果 *D* 为 true，则新属性的 [[Configruable]] 设置为 true，否则设置为 false。

1. 让 *envRec* 为调用方法的对象环境记录
2. 让 *bindings* 为 *envRec* 的绑定对象
3. 如果 *D* 为 true，让 **configValue** 为 true，否则为 false
4. 返回 [DefinePropertyOrThrow](https://262.ecma-international.org/6.0/#sec-definepropertyorthrow)(*bindings*, *N*, PropertyDescriptor{[[Value]]:**undefined**, [[Writable]]: **true**, [[Enumerable]]: **true** , [[Configurable]]: *configValue*})

注：通常，*envRec* 没有 *N* 的绑定，但如果有，则 DefinePropertyOrThrow 的语义可能会导致现有绑定被替换或隐藏或导致返回一个 [abrupt completion](https://262.ecma-international.org/6.0/#sec-completion-record-specification-type)。

###### 8.1.1.2.3 CreateImmutableBinding (N, S)

在此规范中，具体环境记录方法 CreateImmutableBinding 在对象环境记录中永远也不会被使用。

###### 8.1.1.2.4 InitializeBinding (N,V)

用于对象环境记录的具体环境记录方法 InitializeBinding 用于为名为 *N* 的绑定初始化绑定值为 *V*。一个名为 *N* 的未被初始化的绑定必须已经存在。

1. 让 *envRec* 为调用方法的对象环境记录
2. Assert：*envRec* 必须有一个名为 *N* 的未初始化绑定
3. 记录 *N* 对应的绑定为已初始化
4. 返回 *envRec*.SetMutableBinding(*N*, *V*, **false**)

注：在此规范中，对对象环境记录的 CreateMutableBinding 的所有使用，紧随其后的都将是对具有相同名称的 InitializeBinding 的调用。因此，实现无需显式跟踪单个对象环境记录绑定的初始化状态。

###### 8.1.1.2.5 SetMutableBinding (N,V,S)

用于对象环境记录的具体环境记录方法 SetMutableBinding (N,V,S) 尝试设置对应绑定对象中其名为 *N* 的属性的对应的绑定的值为 *V*。通常名为 *N* 的属性已经存在，但是如果该属性不存在或当前不可写，则错误处理由 Boolean 参数*S* 的值确定。

1. 让 *envRec* 为调用方法的对象环境记录
2. 让 *bindings* 为 *envRec* 的绑定对象
3. 返回 [Set](https://262.ecma-international.org/6.0/#sec-set-o-p-v-throw)(*bindings*, *N*, *V*, *S*)

###### 8.1.1.2.6 GetBindingValue(N,S)

用于对象环境记录的具体环境记录方法 GetBindingValue(N,S) 返回对应绑定对象中其名为 *N* 的属性的对应的绑定的值。属性应该存在，但如果不存在，则结果取决于S参数的值：

1. 让 *envRec* 为调用方法的对象环境记录
2. 让 *bindings* 为 *envRec* 的绑定对象
3. 让 *value* 为 [HasProperty](https://262.ecma-international.org/6.0/#sec-hasproperty)(*bindings*, *N*)
4. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*value*)
5. 如果 *value* 为 false，那么：
   1. 如果 *S* 为 false，返回 undefined，否则引发 **ReferenceError** 异常
6. 返回 [Get](https://262.ecma-international.org/6.0/#sec-get-o-p)(*bindings*, *N*)

##### 8.1.1.2.7 DeleteBinding (N)

对象环境记录的具体环境记录方法 DeleteBinding 只能删除与 [[Configurable]] 属性值为 true 的环境记录的属性相对应的绑定。

1. 让 *envRec* 为调用方法的对象环境记录
2. 让 *bindings* 为 *envRec* 的绑定对象
3. 返回 *bindings*.[[Delete]](*N*)

###### 8.1.1.2.8 HasThisBinding ()

常规对象环境记录不提供 *this* 绑定。

1. 返回 false

###### 8.1.1.2.9 HasSuperBinding ()

常规对象环境记录不提供 *super* 绑定。

1. 返回 false

###### 8.1.1.2.10 WithBaseObject()

除非其 *withEnvironment* 标志为 true，否则对象环境记录将返回 undefined 作为其WithBaseObject。

1. 让 *envRec* 为调用方法的对象环境记录
2. 如果 *withEnvironment* 标志为 true，返回 *envRec* 的绑定对象
3. 否则，返回 false

##### 8.1.1.3 函数环境记录

函数环境记录是声明式环境记录，用于表示函数的顶级范围，如果函数不是 *ArrowFunction*，则提供 **this** 绑定。如果一个函数不是 *ArrowFunction* 函数并且引用了 **super**，则其函数环境记录也包含用于从函数内部执行 **super** 方法调用的状态。

功能环境记录具有表 16 中列出的其他状态字段。

##### 表 16 —— 函数环境记录的其他字段

| 字段名                | 值                                            | 意义                                                         |
| --------------------- | --------------------------------------------- | ------------------------------------------------------------ |
| [[thisValue]]         | Any                                           | 用于函数调用的 **this** 值                                   |
| [[thisBindingStatus]] | "lexical" \| "initialize" \| "uninintialized" | 如果为 "lexcial"，函数是 *ArrowFunction*，没有本地 **this** 值 |
| [[FunctionObject]]    | Object                                        | 其调用导致这个环境记录被创建的函数对象                       |
| [[HomeObject]]        | Object \| undefined                           | 如果关联函数有 **super** 属性且并非一个 *ArrowFunction*，[[HomeObjec]] 为绑定函数为其方法的那个对象。[[HomeObjec]] 的默认为 undefined |
| [[NewTarget]]         | Object \| undefined                           | 如果环境记录是由内部方法 [[Construct]] 创建，[[NewTarget]] 的则为 [[Construct]] 的参数 *newTarget* 的值。否则为 undefined |

函数环境记录支持表 15 中列出的所有声明式环境记录方法而且除了 HasThisBinding 和 HasSuperBinding 两个方法以外有着相同的规范。此外，函数环境记录支持表 17 中列出的方法。

##### 表 17 —— 函数环境记录的其他的方法

| 方法                                                         | 目的                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [BindThisValue](https://262.ecma-international.org/6.0/#sec-bindthisvalue)(V) | 设置 [[thisValue]] 并记录其为已经初始化                      |
| GetThisBinding()                                             | 返回环境记录的 **this** 绑定值。如果其未初始化，引发 **ReferenceError** 异常 |
| [GetSuperBase](https://262.ecma-international.org/6.0/#sec-getsuperbase)() | 返回作为此环境记录中绑定的 **super** 属性访问基础的对象。对象是从此环境记录的 [[HomeObject]] 字段派生的。值 undefined 表示超级属性访问将产生运行时错误 |

函数环境记录的具体规范方法的行为定义如下面算法：

###### 8.1.1.3.1 BindThisValue(V)

1. 让 *envRec* 为调用方法的函数环境记录
2. Assert：*envRec*.[[thisBindingStatus]] 非 "lexical"
3. 如果 *envRec*.[[thisBindingStatus]] 为 `"initialized"`，引发 **ReferenceError** 异常
4. 设置 *envRec*.[[thisValue]] 为 *V*
5. 设置 *envRec*.[[thisBindingStatus]] 为 `"initialized"`
6. 反正 *V*

###### 8.1.1.3.2 HasThisBinding ()

1. 让 *envRec* 为调用方法的函数环境记录
2. 如果 *envRec*.[[thisBindingStatus]] 为 `"lexical"`，返回 false，否则返回 true

###### 8.1.1.3.3 HasSuperBinding ()

1. 让 *envRec* 为调用方法的函数环境记录
2. 如果 *envRec*.[[thisBindingStatus]] 为 `"lexical"`，返回 false
3. 如果 *envRec*.[[HomeObject]] 为 undefined，返回 false，否则返回 true

###### 8.1.1.3.4 GetThisBinding ()

1. 让 *envRec* 为调用方法的函数环境记录
2. Assert：*envRec*.[[thisBindingStatus]] 非 "lexical"
3. 如果 *envRec*.[[thisBindingStatus]] 为 `"uninitialized"`，引发 **ReferenceError** 异常
4. 返回 *envRec*.[[thisValue]]

###### 8.1.1.3.5 GetSuperBase ()

1. 让 *envRec* 为调用方法的函数环境记录
2. 让 *home* 为 *envRec*.[[HomeObject]] 的值
3. 如果 *home* 值为 **undefined**, return **undefined**
4. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*home*) 为 Object
5. 返回 *home.*\[[GetPrototypeOf]\]()

##### 8.1.1.4 全局环境记录

全局环境记录用于表示被由通用 [Realm](https://262.ecma-international.org/6.0/#sec-code-realms) ([8.2](https://262.ecma-international.org/6.0/#sec-code-realms)) 处理的所有 ECMAScript 脚本元素共享的最外层作用域。全局记录环境为全局对象内置全局变量、属性、以及所有脚本里出现的顶层声明提供绑定。

逻辑上，全局环境记录是单个记录，但是它被指定为封装对象环境记录和声明式环境记录的复合记录。对象环境记录具有关联 [Realm](https://262.ecma-international.org/6.0/#sec-code-realms) 的全局对象作为其基础对象。这个全局对象为全局环境记录的 GetThisBinding 具体方法的返回值。全局环境记录的对象环境记录组件包含所有内置全局变量的绑定（第 [18](https://262.ecma-international.org/6.0/#sec-global-object) 节）以及全局代码中包含的 *FunctionDeclaration*、*GeneratorDeclaration* 或 *VariableStatement* 引入的所有绑定。全局代码中所有其他 ECMAScript 声明的绑定则被包含在全局环境记录的声明式环境记录中。

属性可能被直接创建在全局对象上。因此，全局环境记录的对象环境记录组件可能包括由 *FunctionDeclaration*, *GeneratorDeclaration*, or *VariableDeclaration* 声明显示创建的绑定以及通过为全局对象添加属性而隐式创建的绑定。为区分哪些是通过显示声明创建的绑定，全局环境记录通过其具体方法 CreateGlobalVarBindings 和 CreateGlobalFunctionBindings 维护绑定的名称的列表。

全局环境记录拥有的其他字段如表 18 所示，其他方法由表 19 所示。

##### 表 18 全局环境记录的其他字段

| 字段名                | 值                 | 意义                                                         |
| --------------------- | ------------------ | ------------------------------------------------------------ |
| [[ObjectRecord]]      | 对象环境记录       | 绑定对象为全局对象。包含全局内置的绑定以及相关[Realm](https://262.ecma-international.org/6.0/#sec-code-realms)的全局代码中的 *FunctionDeclaration*，*GeneratorDeclaration* 和 *VariableDeclaration* 绑定。 |
| [[DeclarativeRecord]] | 声明式环境记录     | 包含全局内置的绑定以及相关 [Realm](https://262.ecma-international.org/6.0/#sec-code-realms)的全局代码中所有除 *FunctionDeclaration*，*GeneratorDeclaration* 和 *VariableDeclaration* 绑定之外的声明绑定。 |
| [[VarNames]]          | String 组成的 List | 在相关 *Realm* 的全局代码中，通过 *FunctionDeclaration*，*GeneratorDeclaration* 和 *VariableDeclaration* 声明创建的绑定的字符串名称。 |

##### 表 19 —— 全局环境记录的其他方法

| 方法                                                         | 目的                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| GetThisBinding()                                             | 返回环境记录的 **this** 绑定值                               |
| HasVarDeclaration(N)                                         | 确定环境记录的变量标识符是否有一个通过 *VariableDeclaration*、*FunctionDeclaration* 或 *GeneratorDeclaration* 创建的绑定 |
| [HasLexicalDeclaration](https://262.ecma-international.org/6.0/#sec-haslexicaldeclaration) (N) | 确定环境记录的变量标识符是否有一个通过词法声明比如 *LexicalDeclaration*、或 *ClassDeclaration* 创建的绑定 |
| [HasRestrictedGlobalProperty](https://262.ecma-international.org/6.0/#sec-hasrestrictedglobalproperty) (N) | 确定参数是否为可能不被全局词法绑定遮盖的全局对象属性的名称   |
| [CanDeclareGlobalVar](https://262.ecma-international.org/6.0/#sec-candeclareglobalvar) (N) | 确定如果为相同的参数 *N* 调用相应的 CreateGlobalVarBinding，调用是否将成功 |
| [CanDeclareGlobalFunction](https://262.ecma-international.org/6.0/#sec-candeclareglobalfunction) (N) | 确定如果为相同的参数 *N* 调用相应的 CreateGlobalFunctionBinding，调用是否将成功 |
| [CreateGlobalVarBinding](https://262.ecma-international.org/6.0/#sec-createglobalvarbinding)(N, D) | 用于为全局环境记录的 [[ObjectRecord]] 组件创建和初始化 undefined 一个全局 **var** 绑定。这个绑定是一个可变的绑定。对应全局对象属性将有个合适与 **var** 的特性值。字符串值 *N* 为绑定名。如果 *D* 为 true，绑定可能将被删除。逻辑上等价于 CreateMutableBinding 后跟着 SetMutableBinding，但是 var 声明允许特殊的处理。 |
| [CreateGlobalFunctionBinding](https://262.ecma-international.org/6.0/#sec-createglobalfunctionbinding)(N, V, D) | 用于为全局环境记录的 [[ObjectRecord]] 组件创建和初始化一个全局 **function** 绑定。这个绑定是一个可变的绑定。对应全局对象属性将有个合适与 **function** 的特性值。字符串值 *N* 为绑定名。如果 *D* 为 true，绑定可能将被删除。逻辑上等价于 CreateMutableBinding 后跟着 SetMutableBinding，但是 function 声明允许特殊的处理。 |

全局环境记录的具体规范方法的行为如下面的算法所定义。

###### 8.1.1.4.1 HasBinding(N)

用于全局环境记录的具体环境记录方法 HasBinding 仅确定参数标识符是否是记录绑定的标识符之一：

1. 让 *envRec* 为调用方法的全局环境记录
2. 让 *DclRec* 为 *envRec*.[[DeclarativeRecord]]
3. 如果 *DclRec.*HasBinding(*N*) 为 **true**，返回 **true**
4. 让 *ObjRec* 为 *envRec*.[[ObjectRecord]]
5. 返回 *ObjRec.*HasBinding(*N*)

###### 8.1.1.4.2 CreateMutableBinding (N, D)

用于全局环境记录的具体环境记录方法 CreateMutableBinding 创建一个名为 *N* 的新的、未初始化的可变绑定。绑定创建在关联的 DeclarativeRecord 中。*N* 的绑定在 DeclarativeRecord 中必须不能是已经存在的。 如果提供了布尔参数 *D* 并具有值 true，则将新绑定标记为要删除。

1. 让 *envRec* 为调用方法的全局环境记录
2. 让 *DclRec* 为 *envRec*.[[DeclarativeRecord]]
3. 如果 *DclRec.*HasBinding(*N*) 为 **true**，引发 **TypeError** 异常
4. 返回 *DclRec*.CreateMutableBinding(*N*, *D*)

###### 8.1.1.4.3 CreateImmutableBinding (N, S)

用于全局环境记录的具体环境记录方法 CreateImmutableBinding 创建一个名为 *N* 的新的、未初始化的不可变绑定。*N* 的绑定在环境记录中必须不能是已经存在的。 如果提供了布尔参数 *S* 并具有值 true，则将新绑定标记为严格绑定。

1. 让 *envRec* 为调用方法的全局环境记录
2. 让 *DclRec* 为 *envRec*.[[DeclarativeRecord]]
3. 如果 *DclRec.*HasBinding(*N*) 为 **true**，引发 **TypeError** 异常
4. 返回 *DclRec*.CreateImmutableBinding(*N*, *D*)

###### 8.1.1.4.4 InitializeBinding (N,V)

用于全局环境记录的具体环境记录方法 InitializeBinding 用于为当前名 *N* 对应的绑定的值设置为 *V*。一个未初始化的绑定 *N* 必须已经存在。

1. 让 *envRec* 为调用方法的全局环境记录
2. 让 *DclRec* 为 *envRec*.[[DeclarativeRecord]]
3. 如果 *DclRec.*HasBinding(*N*) 为 **true**，则：
   1. 返回 *DclRec*.InitializeBinding(*N*, *V*)
4. Assert：如果绑定存在，那么它必须存在于对象环境记录中
5. 让 *ObjRec* 为 *envRec*.[[ObjectRecord]]
6. 返回 *ObjRec.*InitializeBinding(*N*, *V*)

###### 8.1.1.4.5 SetMutableBinding (N,V,S)

用于全局环境记录的具体环境记录方法 SetMutableBinding 尝试将名称为参数 *N* 的值的标识符的当前绑定的绑定值更改为参数 *V* 的值。如果绑定为不可变且 *S* 为 true，引发一个 **TypeError**。通常已经存在一个名为 *N* 的属性，但是如果该属性不存在或当前不可写，则错误处理由布尔参数 *S* 的值确定。

1. 让 *envRec* 为调用方法的全局环境记录
2. 让 *DclRec* 为 *envRec*.[[DeclarativeRecord]]
3. 如果 *DclRec.*HasBinding(*N*) 为 **true**，则：
   1. 返回 *DclRec*.SetMutableBinding(*N*, *V*)
4. 让 *ObjRec* 为 *envRec*.[[ObjectRecord]]
5. 返回 *ObjRec.*SetMutableBinding(*N*, *V*, *S*)

###### 8.1.1.4.6 GetBindingValue(N,S)

用于全局环境记录的具体环境记录方法  GetBindingValue(N,S) 返回其绑定标识符的值，该标识符的名称为参数 *N* 的值。如果绑定未初始化，引发一个 **ReferenceError** 异常。通常已经存在一个名为 *N* 的属性，但是如果该属性不存在或当前不可写，则错误处理由布尔参数 *S* 的值确定。

1. 让 *envRec* 为调用方法的全局环境记录
2. 让 *DclRec* 为 *envRec*.[[DeclarativeRecord]]
3. 如果 *DclRec.*HasBinding(*N*) 为 **true**，则：
   1. 返回 *DclRec.*GetBindingValue(*N*, *S*)
4. 让 *ObjRec* 为 *envRec*.[[ObjectRecord]]
5. 返回 *DclRec.*GetBindingValue(*N*, *S*)

###### 8.1.1.4.7 DeleteBinding (N)

用于全局环境记录的具体环境记录方法  DeleteBinding(N) 只能删除已明确指定要删除的绑定。

1. 让 *envRec* 为调用方法的全局环境记录
2. 让 *DclRec* 为 *envRec*.[[DeclarativeRecord]]
3. 如果 *DclRec.*HasBinding(*N*) 为 **true**，则：
   1. 返回 *DclRec.*DeleteBinding(*N*)
4. 让 *ObjRec* 为 *envRec*.[[ObjectRecord]]
5. 让 *globalObject* 为 *ObjRec* 的绑定对象
6. 让 *existingProp* 为 [HasOwnProperty](https://262.ecma-international.org/6.0/#sec-hasownproperty)(*globalObject*, *N*)
7. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*existingProp*)
8. 如果 *existingProp* 为 true，那么：
   1. 让 *status* 为 *ObjRec.*DeleteBinding(*N*)
   2. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*status*)
   3. 如果 *status* 为 true，那么：
      1. 让 *varNames* 为 *envRec*.[[VarNames]]
      2. 如果 *N* 是 *varNames* 中的一员，从 *varNames* 中移除之
   4. 返回 *status*
9. 返回 true

###### 8.1.1.4.8 HasThisBinding ()

全局环境记录总是提供一个其值为关联全局对象的 **this** 绑定

1. 返回 true

###### 8.1.1.4.9 HasSuperBinding()

1. 返回 false

###### [8.1.1.4.10 ](https://262.ecma-international.org/6.0/#sec-global-environment-records-withbaseobject)WithBaseObject()

全局环境记录总是返回 undefined 作为其 WithBaseObject

1. 返回 false

###### 8.1.1.4.11 GetThisBinding ()

1. 让 *envRec* 为调用方法的全局环境记录
2. 让 *ObjRec* 为 *envRec*.[[ObjectRecord]]
3. 让 *bindings* 为 *ObjRec* 的绑定对象
4. 返回 *bindings*

###### 8.1.1.4.12 HasVarDeclaration (N)

全局环境记录的具体环境记录方法 HasVarDeclaration 确定在此记录中参数标识符是否具有使用 *VariableStatement* 或 *FunctionDeclaration* 创建的绑定：

1. 让 *envRec* 为调用方法的全局环境记录
2. 让 *varDeclaredNames* 为 *envRec*.[[VarNames]]
3. 如果 *varDeclaredNames* 包含 *N* 对应的值，返回 true
4. 返回 false

###### 8.1.1.4.13 HasLexicalDeclaration (N)

全局环境记录的具体环境记录方法 HasLexicalDeclaration 确定在此记录中参数标识符是否具有使用 *LexicalDeclaration* 或 *ClassDeclaration* 创建的绑定：

1. 让 *envRec* 为调用方法的全局环境记录
2. 让 *DclRec* 为 *envRec*.[[DeclarativeRecord]]
3. 返回 *DclRec.*HasBinding(*N*)

###### 8.1.1.4.14 HasRestrictedGlobalProperty (N)

全局环境记录的具体环境记录方法 HasRestrictedGlobalProperty 确定参数标识符是否是全局对象的属性的名称，该名称不能被全局词法绑定所遮盖：

1. 让 *envRec* 为调用方法的全局环境记录
2. 让 *ObjRec* 为 *envRec*.[[ObjectRecord]]
3. 让 *globalObject* 为 *ObjRec* 的绑定对象
4. 让 *existingProp* 为 *globalObject*.\[[GetOwnProperty]\](*N*)
5. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*existingProp*)
6. 如果 *existingProp* 为 **undefined**，返回 **false**
7. 如果 *existingProp*.[[Configurable]] 为 **true，**返回 **false**
8. 返回 true

注：属性可能存在于直接创建的全局对象上，而不是使用 var 或 function 声明来声明。可能无法创建与全局对象的不可配置属性同名的全局词法绑定。未定义的全局属性是此类属性的一个示例。

###### 8.1.1.4.15 CanDeclareGlobalVar (N)

全局环境记录的具体环境记录方法 CanDeclareGlobalVar 确定如果为相同的参数 *N* 调用相应的 [CreateGlobalVarBinding](https://262.ecma-international.org/6.0/#sec-createglobalvarbinding) 调用是否成功。允许冗余的 var 声明和用于预先存在的全局对象属性的 var 声明。

1. 让 *envRec* 为调用方法的全局环境记录
2. 让 *ObjRec* 为 *envRec*.[[ObjectRecord]]
3. 让 *globalObject* 为 *ObjRec* 的绑定对象
4. 让 *hasProperty* 为 [HasOwnProperty](https://262.ecma-international.org/6.0/#sec-hasownproperty)(*globalObject, N*)
5. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*hasProperty*)
6. 如果 *hasProperty* 为 true，返回 true
7. 返回 [IsExtensible](https://262.ecma-international.org/6.0/#sec-isextensible-o)(*globalObject*)

###### 8.1.1.4.16 CanDeclareGlobalFunction (N)

全局环境记录的具体环境记录方法 CanDeclareGlobalFunction 确定如果为相同的参数 *N* 调用相应的 [CreateGlobalFunctionBinding](https://262.ecma-international.org/6.0/#sec-createglobalfunctionbinding) 调用是否成功。

1. 让 *envRec* 为调用方法的全局环境记录
2. 让 *ObjRec* 为 *envRec*.[[ObjectRecord]]
3. 让 *globalObject* 为 *ObjRec* 的绑定对象
4. 让 *existingProp* 为 *globalObject*.\[[GetOwnProperty]\](*N*)
5. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*existingProp*)
6. 如果 *existingProp* 为 **undefined**，返回 [IsExtensible](https://262.ecma-international.org/6.0/#sec-isextensible-o)(*globalObject*)
7. 如果 *existingProp*.[[Configurable]] 为 **true**，返回 **true**
8. 如果 [IsDataDescriptor](https://262.ecma-international.org/6.0/#sec-isdatadescriptor)(*existingProp*) 为 **true** 而且 *existingProp* 的特性值为  {[[Writable]]: **true**, [[Enumerable]]: **true**}, return **true**
9. 返回 false

###### 8.1.1.4.17 CreateGlobalVarBinding (N, D)

全局环境记录的具体环境记录方法 CreateGlobalVarBinding 在相关的对象环境记录中创建、初始化一个可变的绑定并将绑定名记录在相关的 [[VarNames]] List 中。如果绑定已经存在，绑定会被重新使用并且被假定是初始化的。

1. 让 *envRec* 为调用方法的全局环境记录
2. 让 *ObjRec* 为 *envRec*.[[ObjectRecord]]
3. 让 *globalObject* 为 *ObjRec* 的绑定对象
4. 让 *hasProperty* 为 [HasOwnProperty](https://262.ecma-international.org/6.0/#sec-hasownproperty)(*globalObject, N*)
5. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*hasProperty*)
6. 让  *extensible* 为 [IsExtensible](https://262.ecma-international.org/6.0/#sec-isextensible-o)(*globalObject*)
7. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*extensible*)
8. 如果 *hasProperty* 为 **false** 且 *extensible* 为 **true**，那么：
   1. 让 *status* 为 *ObjRec.*CreateMutableBinding(*N*, *D*)
   2. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*status*)
   3. 让 *status* 为 *ObjRec.*InitializeBinding(*N*, **undefined**)
   4. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*status*)
9. 让 *varDeclaredNames* 为 *envRec*.[[VarNames]]
10. 如果 *varDeclaredNames* 不包含 *N*，那么：
    1. 添加 *N* 到 *varDeclaredNames*
11. 返回 [NormalCompletion](https://262.ecma-international.org/6.0/#sec-normalcompletion)(empty)

###### 8.1.1.4.18 CreateGlobalFunctionBinding (N, V, D)

全局环境记录的具体环境记录方法 CreateGlobalFunctionBinding 在相关的对象环境记录中创建、初始化一个可变的绑定并将绑定名记录在相关的 [[VarNames]] List 中。如果绑定已经存在，则会被替换。

1. 让 *envRec* 为调用方法的全局环境记录
2. 让 *ObjRec* 为 *envRec*.[[ObjectRecord]]
3. 让 *globalObject* 为 *ObjRec* 的绑定对象
4. 让 *existingProp* 为 *globalObject*.\[[GetOwnProperty]\](*N*)
5. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*existingProp*)
6. 让  *existingProp* 为 **undefined** 且 *existingProp*.[[Configurable]] 为 **true**，那么：
   1. 让 *desc* 为 PropertyDescriptor{[[Value]]:*V*, [[Writable]]: **true**, [[Enumerable]]: **true** , [[Configurable]]: *D*}
7. 否则：
   1. 让 *desc* 为 PropertyDescriptor{[[Value]]:*V* }
8. 让 *status* 为 [DefinePropertyOrThrow](https://262.ecma-international.org/6.0/#sec-definepropertyorthrow)(*globalObject*, *N*, *desc*)
9. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*status*)
10. 让 *status* 为 [Set](https://262.ecma-international.org/6.0/#sec-set-o-p-v-throw)(*globalObject*, *N*, *V*, **false**)
11. 记录 *ObjRec* 中名为 *N* 的绑定为已初始化
12. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*status*)
13. 让 *varDeclaredNames* 为 *envRec*.[[VarNames]].
14. 如果 *varDeclaredNames* 不包含 *N*，那么：
    1. 添加 *N* 到 *varDeclaredNames*
15. 返回 [NormalCompletion](https://262.ecma-international.org/6.0/#sec-normalcompletion)(empty)

注：全局函数声明始终表示为全局对象的自身属性。如果可能，将现有的自己的属性重新配置为具有一组标准的属性值。步骤 10-12 等效于调用 InitializeBinding 具体方法将执行的操作，并且如果 *globalObject* 是 Proxy ，则将产生相同的 Proxy trap 调用序列。

##### 8.1.1.5 模块环境记录

模块环境记录是用于表现一个 ECMAScript 模块最外层作用域的声明式环境记录。除了正常的可变绑定和不可变绑定之外，模块环境记录还提供了不可变导入绑定，这些导入绑定提供了对另一个环境记录中存在的目标绑定的间接访问。

模块环境记录支持表 15 中列出的所有声明式环境记录方法，而且除了 GetBindingValue、DeleteBinding、HasThisBinding 和 GetThisBinding 以外有着相同的规范。此外，模块环境记录还支持表 20 里列出的方法。

##### 表 20 —— 模块环境记录的其他方法

| 方法                                                         | 目的                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [CreateImportBinding](https://262.ecma-international.org/6.0/#sec-createimportbinding)(N, M, N2 ) | 在模块环境记录中创建一个简洁绑定。字符串值 *N* 是绑定的文本。*M* 是 [Module Record](https://262.ecma-international.org/6.0/#sec-abstract-module-records) ([见 15.2.1.15](https://262.ecma-international.org/6.0/#sec-abstract-module-records))，*N2* 是 *M* 的模块环境记录里的绑定。 |
| GetThisBinding()                                             | 返回当前环境记录的 **this** 绑定                             |

模块环境记录的其他具体规范方法的行为由以下算法定义：

###### 8.1.1.5.1 GetBindingValue(N,S)

模块环境记录的具体环境记录方法 GetBindingValue 返回其绑定标识符的值，该标识符的名称是参数 *N* 的值。如果绑定为一个间接绑定，则返回目标绑定的值。如果绑定存在但是未初始化的。引发一个 **ReferenceError** 异常，不管 *S* 为何值。

1. 让 *envRec* 为调用方法的模块环境记录
2. Assert：*envRec* 有 *N* 的绑定
3. 如果 *N* 的绑定是一个间接绑定，那么：
   1. 让 *M* 和 *N2* 为创建 *N* 的绑定时提供的间接值
   2. 让 *targetEnv* 为 *M*.[[Environment]]
   3. 如果 *targetEnv* 为 undefined，引发一个 **ReferenceError** 异常
   4. 让 *targetER* 为 *targetEnv*’s [EnvironmentRecord](https://262.ecma-international.org/6.0/#sec-lexical-environments)
   5. 返回 *targetER*.GetBindingValue(*N2*, *S*)
4. 如果 *envRec* 里 *N* 的绑定未初始化，引发一个 **ReferenceError** 异常
5. 返回 *envRec* 里 *N* 当前绑定的值

注：因为模块总是严格模式代码，调用 GetBindingValue 时应该永远传值为 true 的 *S*

###### 8.1.1.5.2 DeleteBinding(N)

模块环境记录的具体环境记录方法 DeleteBinding 不能删除绑定。

1. 让 *envRec* 为调用方法的模块环境记录
2. 如果 *envRec* 里没有名为 *N* 的绑定，返回 true
3. 返回 false

注：模块环境记录里的绑定是无法删除的

###### 8.1.1.5.3 HasThisBinding()

模块环境记录提供 **this** 绑定

1. 返回 true

###### 8.1.1.5.4 GetThisBinding()

1. 返回 undefined

###### 8.1.1.5.5 CreateImportBinding (N, M, N2)

模块环境记录的具体环境记录方法 CreateImportBinding 创建一个名为 *N* 新的、已经初始化的、不可变的间接绑定。当前环境记录里必须不能已经存在名为 *N* 的绑定。*M* 是一个模块记录（见 [15.2.1.15](https://262.ecma-international.org/6.0/#sec-abstract-module-records)），*N2* 是 *M* 的模块环境记录里已经存在的绑定的名称。对新绑定的值的访问会间接访问到目标绑定的绑定值。

1. 让 *envRec* 为调用方法的模块环境记录
2. Assert：*envRec* 里不存在 *N* 的绑定
3. Assert：*M* 是一个模块记录
4. Assert：当 *M*.[[Environment]] 实例化时，其将会有一个 *N2* 的直接绑定
5. 在 *envRec* 中为 *N* 创建一个不可变的间接绑定，该绑定将 *M* 和 *N2* 引用为其目标绑定，并记录该绑定已初始化
6. 返回 [NormalCompletion](https://262.ecma-international.org/6.0/#sec-normalcompletion)(empty)

#### 8.1.2 词法环境操作

以下抽象操作在本规范中用于操作词法环境：

#### 8.1.2.1 GetIdentifierReference (lex, name, strict)

抽象操作 GetIdentifierReference 以词法环境 *lex*、字符串 *name* 和一个布尔标记 *flag* 为参数调用。*lex* 的值可能为 null。调用时，执行以下步骤：

1. 如果 *lex* 为 null，那么：
   1. 返回一个 Reference 类型的值，值的 base 值为 undefined，引用名为 *name*，严格引用标记为 *strict*
2. 让 *envRec* 为 *lex* 的 EnvironmentRecord
3. 让 *exists* 为 *envRec*.HasBinding(*name*)
4. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*exists*)
5. 如果 *exists* 为 true，那么：
   1. 返回一个 Reference 类型的值，值的 base 值为 *envRec*，引用名为 *name*，严格引用标记为 *strict*
6. 否则：
   1. 让 *outer* 为 *lex* 的外部环境引用
   2. 返回 GetIdentifierReference(*outer*, *name*, *strict*)

##### 8.1.2.2 NewDeclarativeEnvironment (E)

当抽象操作 NewDeclarativeEnvironment 以一个词法环境 *E* 为参数调用时，执行以下步骤：

1. 让 *env* 为一个新的词法环境
2. 让 *envRec* 为一个新的不包含任何绑定的声明式环境记录
3. 让 *env* 的 EnvironmentRecord 为 *envRec*
4. 让 *env* 的外部词法环境引用为 *E*
5. 返回 *env*

##### 8.1.2.3 NewObjectEnvironment (O, E)

当抽象操作 NewObjectEnvironment 以 ECMAScript Object *O* 和词法环境 *E* 为变量调用时，执行以下步骤：

1. 让 *env* 为一个新的词法环境
2. 让 *envRec* 为一个新的包含 *O* 作为绑定对象的词法环境记录
3. 让 *env* 的 [EnvironmentRecord](https://262.ecma-international.org/6.0/#sec-lexical-environments) 为 *envRec*
4. 让 *env* 的外部词法环境引用为 *E*
5. 返回 *env*

##### 8.1.2.4 NewFunctionEnvironment ( F, newTarget )

当抽象操作 NewFunctionEnvironment 以 *F* 和 *newTarget* 为参数调用时，执行以下步骤：

1. Assert：*F* 是一个 ECMAScript 函数
2. Assert：Type(*newTarget*) 为 Undefined 或 Object
3. 让 *env* 为一个新的词法环境
4. 让 *envRec* 为一个新的不包含绑定的函数环境记录
5. 设置 *envRec*.[[FunctionObject]] 为 *F*
6. 如果 *F* 的 [[ThisMode]] 内部插槽为词法的，设置 *envRec*.[[thisBindingStatus]] 为 "**lexical**"
7. 否则，设置 *envRec*.[[thisBindingStatus]] 为 `"uninitialized"`
8. 让 *home* 为 *F* 的  [[HomeObject]] 内部插槽值
9. 让 *envRec*.[[HomeObject]] 为 *home*
10. 让 *envRec*.[[NewTarget]] 为 *newTarget*
11. 让 *env* [EnvironmentRecord](https://262.ecma-international.org/6.0/#sec-lexical-environments) 为 *envRec*
12. 让 *env* 的外部词法环境引用为 *F* 的 [[Environment]] 内部插槽值
13. 返回 *env*

##### 8.1.2.5 NewGlobalEnvironment ( G )

抽象操作以 ECMAScript Object *G*  为参数调用时，执行以下步骤：

1. 让 *env* 为一个新的词法环境
2. 让 *objRec* 为一个新的包含 *G* 作为其绑定对象的对象环境记录
3. 让 *dclRec* 为一个不包含任何绑定的新的声明式环境记录
4. 让 *globalRec* 为一个新的全局环境记录
5. 设置 *globalRec*.[[ObjectRecord]] 为 *objRec*
6. 设置 *globalRec*.[[DeclarativeRecord]] 为 *dclRec*
7. 设置 *globalRec*.[[VarNames]] 为新的空 List
8. 设置 *env’s* [EnvironmentRecord](https://262.ecma-international.org/6.0/#sec-lexical-environments) 为 *globalRec*
9. 设置 *env* 的外部环境引用为 null
10. 返回 *env*

##### 8.1.2.6 NewModuleEnvironment (E)

当抽象操作 NewModuleEnvironment 以词法环境 *E* 为变量调用时，执行如下步骤：

1. 让 *env* 为一个新的词法环境
2. 让 *envRec* 为一个新的不包含绑定的模块环境记录
3. 设置 *env* 的 [EnvironmentRecord](https://262.ecma-international.org/6.0/#sec-lexical-environments) 为 *envRec*
4. 设置 *env* 的外部词法环境引用为 *E*
5. 返回 *env*

### 8.2 Code Realms（译者注：后统一翻译为「代码领域」）

在开始求值之前，所有 ECMAScript 代码必须与一个「领域」关联。从概念上讲，领域由一组固有对象，一个 ECMAScript 全局环境，在该全局环境范围内加载的所有 ECMAScript 代码以及其他关联的状态和资源组成。

领域被指定为一个记录，它有如表 21 所指定的字段：

##### 表 21 —— 领域记录字段

| 字段名          | 值                                                           | 意义                                                         |
| --------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| [[intrinsics]]  | 字段名为固有键名对应值为对象组成的记录                       | 这些是与此领域相关联的代码使用的固有值                       |
| [[globalThis]]  | Object                                                       | 此领域的全局对象                                             |
| [[globalEnv]]   | 词法环境                                                     | 此领域的全局环境                                             |
| [[templateMap]] | 一个由 Record {[[strings]]: [List](https://262.ecma-international.org/6.0/#sec-list-and-record-specification-type), [[array]]: Object} 组成的 List | 使用 [[templateMap]] 为每个领域分别规范化模板对象。每个 [[strings]] 值都是一个 List，按源文本顺序包含已求值的 TemplateLiteral 的原始 String 值。关联的 [[array]] 值是传递给标签函数的相应模板对象。 |

一个实现可以定义其他实现特定的字段。

#### 8.2.1 CreateRealm()

抽象操作 CreateRealm 执行以下步骤：

1. 让 *realmRec* 为一个新的记录
2. 执行 [CreateIntrinsics](https://262.ecma-international.org/6.0/#sec-createintrinsics)(*realmRec*)
3. 设置 *realmRec*.[[globalThis]] 为 undefined
4. 设置 *realmRec*.[[globalEnv]] 为 undefined
5. 设置 *realmRec*.[[templateMap]] 为一个新的空 List
6. 返回 *realmRec*

##### 8.2.2 CreateIntrinsics(realmRec)

当抽象操作 CreateIntrinsics 以 *realmRec* 为参数调用时，执行如下步骤：

1. 让 *intrinsics* 为一个新的记录
2. 设置 *realmRec*.[[intrinsics]] 为 *intrinsics*
3. 让 *objProto* 为 [ObjectCreate](https://262.ecma-international.org/6.0/#sec-objectcreate)(**null**)
4. 设置 *intrinsics*.[[%ObjectPrototype%]] 为 *objProto*
5. 让 *throwerSteps* 为 [9.2.7.1](https://262.ecma-international.org/6.0/#sec-%throwtypeerror%) 为 [%ThrowTypeError%](https://262.ecma-international.org/6.0/#sec-%throwtypeerror%) 函数指定的算法步骤
6. 让 *thrower* 为 [CreateBuiltinFunction](https://262.ecma-international.org/6.0/#sec-createbuiltinfunction)(*realmRec*, *throwerSteps*, **null**)
7. 设置 *intrinsics*.[[[%ThrowTypeError%](https://262.ecma-international.org/6.0/#sec-%throwtypeerror%)]] 为 *thrower*
8. 让 *noSteps* 为空的算法步骤序列
9. 让 *funcProto* 为 [CreateBuiltinFunction](https://262.ecma-international.org/6.0/#sec-createbuiltinfunction)(*realmRec*, *noSteps*, *objProto*)
10. 设置 *intrinsics*.[[%FunctionPrototype%]] 为 *funcProto*
11. 调用 *thrower*.\[[SetPrototypeOf]\](*funcProto*)
12. 执行 [AddRestrictedFunctionProperties](https://262.ecma-international.org/6.0/#sec-addrestrictedfunctionproperties)(*funcProto*, *realmRec*)
13. 为 *intrinsics* 设置表 7 中列出的且未被上面步骤处理的字段。字段名称是表第一列中列出的名称。每个字段的值都是一个新的对象值，该对象值完全并递归地填充有第 18-26 章中每个对象的规范所定义的属性值。所有对象属性值都是新建的对象值。所有都是内置函数对象的值都是通过执行 [CreateBuiltinFunction](https://262.ecma-international.org/6.0/#sec-createbuiltinfunction)(*realmRec*, <steps>, <prototype>, <slots>)  新建的，其中 <steps> 是本规范提供的函数定义，<prototype> 是函数的内部插槽 [[Prototype]] 的指定值，<slots> 是内部插槽中指定的功能的名称（如果有）的列表。必须对固有函数及其属性的创建进行排序，以避免依赖于尚未创建的对象。
14. 返回 *intrinsics*

#### 8.2.3 SetRealmGlobalObject ( realmRec, globalObj )

抽象操作 SetRealmGlobalObject 以 *realmRec* 和 *globalObj* 为参数调用时，执行如下步骤：

1. 如果 *globalObj* 为 undefined，则：
   1. 让 *intrinsics* 为 *realmRec*.[[intrinsics]]
   2. 让 *globalObj* 为 [ObjectCreate](https://262.ecma-international.org/6.0/#sec-objectcreate)(*intrinsics*.[[%ObjectPrototype%]])
2. Assert: [Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*globalObj*) 为 Object
3. 设置 *realmRec*.[[globalThis]] 为 *globalObj*
4. 让 *newGlobalEnv* 为 [NewGlobalEnvironment](https://262.ecma-international.org/6.0/#sec-newglobalenvironment)(*globalObj*)
5. 让 *realmRec*.[[globalEnv]] 为 *newGlobalEnv*
6. 返回 *realmRec*

#### 8.2.4 SetDefaultGlobalBindings ( realmRec )

抽象操作 SetDefaultGlobalBindings 以 *realmRec* 为参数调用时，执行以下步骤：

1. 让 *global* 为 *realmRec*.[[globalThis]]
2. 对全局对象的每个在 [18](https://262.ecma-international.org/6.0/#sec-global-object) 章中定义的属性，执行：
   1. 让 *name* 为属性名的 String 值
   2. 让 *desc* 为该属性的完全填充的数据属性描述符，其中包含该属性的指定特性。对 [18.2](https://262.ecma-international.org/6.0/#sec-function-properties-of-the-global-object)、 [18.3](https://262.ecma-international.org/6.0/#sec-constructor-properties-of-the-global-object) 或 [18.4](https://262.ecma-international.org/6.0/#sec-other-properties-of-the-global-object) 中列出的属性，[[Value]] 特性的值对应于 *realmRec* 里的固有对象
   3. 让 *status* 为 [DefinePropertyOrThrow](https://262.ecma-international.org/6.0/#sec-definepropertyorthrow)(*global*, *name*, *desc*)
   4. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*status*)
3. 返回 *global*

### 8.3 执行上下文

执行上下文是一种规范设备，用于跟踪 ECMAScript 实现对代码的运行时求值。在任何时间点，最多有一个实际正在执行代码的执行上下文。这称为「正在运行的执行上下文」。执行上下文的跟踪是通过栈来进行的。正在运行的执行上下文总是在栈顶。不管何时控制权从与当前正在运行的执行上下文关联的可执行代码转移到与当前正在运行的执行上下文不相关的可执行代码，一个新的执行上下文就会被创建。新创建的执行上下文则被推到栈顶，即成为正在运行的执行上下文。

执行上下文包含跟踪其关联代码的执行进度所需的任何特定于实现的状态。每个执行上下文至少包含表 22 中列出的状态组件。

##### 表 22 —— 所有执行上下文的状态组件

| 组件         | 目的                                                         |
| ------------ | ------------------------------------------------------------ |
| 代码求值状态 | 与执行上下文相关的代码执行、挂起以及恢复求值需要的任何状态   |
| 函数         | 如果执行上下文求值的是一个函数对象的代码，那么此组件的值则是那个函数对象。如果是脚本或是模块的代码，那么值为 null |
| 领域         | 相关代码访问 ECMASscript 资源的领域                          |

通过运行的执行上下文对代码的求值可以在本规范中定义的各个点挂起。一旦运行中的执行上下文被挂起，另一个执行上下文可能会变成运行中的执行上下文并开始求值其代码。在稍后的某个时间，挂起的执行上下文可能会再次变为运行中的执行上下文，并在先前被挂起的位置继续求值其代码。执行上下文之间正在运行的执行上下文状态的转换通常以类似堆栈的后进/先出方式发生。 但是，某些 ECMAScript 功能要求正在运行的执行上下文进行非 LIFO 转换。正在运行的执行上下文的领域组件的值也称为「当前领域」。 正在运行的执行上下文的函数组件的值也称为「活动函数对象」。

ECMAScript 代码的执行上下文具有表 23 中列出的其他状态组件。

##### 表 23 —— ECMAScript 代码执行上下文的其他状态组件

| 组件     | 目的                                                         |
| -------- | ------------------------------------------------------------ |
| 词法环境 | 标识用于解析此执行上下文中的代码进行的标识符引用的词法环境。 |
| 变量环境 | 标识其 EnvironmentRecord 包含在此执行上下文中由 *VariableStatements* 创建的绑定的词法环境。 |

一个执行上下文的词法环境和变量环境组件永远是一个词法环境。创建执行上下文时，其词法环境和变量环境组件最初具有相同的值。

代表生成器对象求值的执行上下文有表 24 中列举的其他状态组件。

##### 24 生成器执行上下文的其他状态组件

| 组件   | 目的                         |
| ------ | ---------------------------- |
| 生成器 | 执行环境正在求值的生成器对象 |

在大多数情况下，仅运行中的执行上下文（执行上下文堆栈的顶部）由本规范中的算法直接操作。 因此，当不加限定地使用术语「词法环境」和「变量环境」时，它们是指正在运行的执行上下文的那些组件。

执行上下文纯粹是一种规范机制，不需要与 ECMAScript 实现的任何特定工件相对应。 ECMAScript 代码不可能直接访问或观察执行上下文。

#### 8.3.1 ResolveBinding ( name, [env] )

抽象操作 ResolveBinding 用于确定值为字符串的变量 *name* 的绑定。可选参数 *env* 可用于显示的提供一个词法环境供搜索。在 ECMAScript 代码的求值中，ResolveBinding 执行如下算法：

1. 如果 *env* 未传或者其值为 undefined，那么：
   1. 让 *env* 为当前执行上下文的词法环境
2. Assert：*env* 是一个词法环境
3. 如果要求值的语法产生匹配的代码包含在严格模式下，则使 *strict* 为 true，否则使 *strict* 为false 
4. 返回 [GetIdentifierReference](https://262.ecma-international.org/6.0/#sec-getidentifierreference)(*env*, *name*, *strict* )

注：ResolveBinding 的结果始终是一个 Reference 值，其引用的名称组件等于 *name* 参数。

#### 8.3.2 GetThisEnvironment ( )

抽象操作 GetThisEnvironment 找寻当前为 *this* 关键字提供绑定的环境记录。执行如下步骤：

1. 让 *lex* 为正在运行的执行上下文的词法环境
2. 重复：
   1. 让 *envRec* 为 *lex* 的环境记录
   2. 让 *exists* 为 *envRec*.HasThisBinding()
   3. 如果 *exists* 为 true，返回 *envRec*
   4. 让 *outer* 为 *lex* 的外部环境引用
   5. 让 *lex* 为 *outer*

注：循环中的步骤 2 最终肯定会终止，因为环境列表以全局环境结尾，而全局环境有 *this* 绑定

#### 8.3.3 ResolveThisBinding ( )

抽象操作 ResolveThisBinding 用正在运行的执行上下文的 LexicalEnvironment 确定关键字 *this* 的绑定。执行如下步骤：

1. 让 *envRec* 为 [GetThisEnvironment](https://262.ecma-international.org/6.0/#sec-getthisenvironment)()
2. 返回 *envRec*.GetThisBinding()

#### 8.3.4 GetNewTarget ( )

抽象操作 GetNewTarget 用正在运行的执行上下文的 LexicalEnvironment 确定 NewrTarget 值。执行如下步骤：

1. 让 *envRec* 为 [GetThisEnvironment](https://262.ecma-international.org/6.0/#sec-getthisenvironment)( )
2. Assert：*envRec* 有 [[NewTarget]] 字段
3. 返回 *envRec*.[[NewTarget]]

#### 8.3.5 GetGlobalObject ( )

抽象操作 GetGlobalObject 用正在运行的执行上下文返回全局对象。执行如下步骤：

1. 让 *ctx* 为正在运行的执行上下文
2. 让 *currentRealm* 为 *ctx* 的领域
3. 返回 *currentRealm*.[[globalThis]]

### 8.4 作业和作业队列

作业是一种抽象操作，当当前没有其他 ECMAScript 计算正在进行时，它将启动 ECMAScript 计算。 作业抽象操作可以定义为接受任意一组作业参数。

仅当没有正在运行的执行上下文并且执行上下文堆栈为空时，才能启动作业的执行。PendingJob 是对将来执行作业的请求。PendingJob 是一个字段如表 25 规定的内部记录。一旦作业开始执行，作用就会一直执行完成。直到当前执行的作业完成前，没有其他作业会被启动。但是，当前正在运行的作业或外部事件可能会导致其他 PendingJob 排队，这些附加的 PendingJob 可能在当前正在运行的作业完成后的某个时间启动。

##### 表 25 —— PendingJob 记录字段

| 字段名          | 值                       | 意义                                                         |
| --------------- | ------------------------ | ------------------------------------------------------------ |
| [[Job]]         | 抽象操作作业的名称       | 这是启动此 PendingJob 的执行时执行的抽象操作。作业是使用 NextJob 而不是 Return 来表示它们已完成的抽象操作。 |
| [[Arguments]]   | List                     | 一个当 [[Job]] 激活时传给它的参数值 List                     |
| [[Realm]]       | 领域记录                 | 启动此挂起作业时的初始执行上下文的领域                       |
| [[HostDefined]] | 任意，默认值为 undefined | 保留给需要将其他信息与待处理作业关联的宿主环境使用的字段。   |

作业队列是一个 FIFO 的 PendingJob 记录队列。每个作业队列都有一个名称，并且可用的作业队列的完整集合由 ECMAScript 实现定义。每个 ECMAScript 实现都至少具有表 26 中定义的作业队列。

##### 表 26 —— 所需的作业队列

| 名称        | 目的                                                         |
| ----------- | ------------------------------------------------------------ |
| ScriptJobs  | 验证和求值 ECMAScript 脚本和模块源文本的作业。 参见第 10 和 15 章。 |
| PromiseJobs | 响应 Promise 的解决的作业                                    |

通过在作业队列中将包含作业抽象操作名称和任何必要参数值的 PendingJob 记录加入队列，来请求将来执行作业。如果没有正在运行的执行上下文并且执行上下文堆栈为空，则 ECMAScript实现将从作业队列中删除第一个 PendingJob，并使用其中包含的信息来创建执行上下文并开始执行关联的 Job 抽象操作。

来自单个作业队列的 PendingJob 记录始终以 FIFO 顺序启动。该规范未定义服务多个作业队列的顺序。ECMAScript 实现可以将作业队列的 PendingJob 记录的 FIFO 求值与一个或多个其他作业队列的 PendingJob 记录的求值交织在一起。一个实现必须定义当没有运行的执行上下文并且所有作业队列为空时会发生什么。

注：通常，ECMAScript 实现将使用至少一个 PendingJob 预先初始化其作业队列，并且其中一个作业将是第一个要执行的作业。如果当前作业完成并且所有作业队列为空，则实现可以选择释放所有资源并终止。或者，它可以选择等待某些特定于实现的代理或机制来排队新的 PendingJob 请求。

以下抽象操作用于创建和管理作业以及作业队列：

#### 8.4.1 EnqueueJob (queueName, job, arguments)

抽象操作 EnqueueJob 需要传三个参数：*queueName*、*job* 和 *arguments* 执行如下步骤：

1. Assert：[Type](https://262.ecma-international.org/6.0/#sec-ecmascript-data-types-and-values)(*queueName*) 为 String 而且其值为实现所能识别的作业队列名
2. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): *job* 为一个作业名
3. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): *arguments* 是一个与 *job* 要求的参数的有着相同数目的 [List](https://262.ecma-international.org/6.0/#sec-list-and-record-specification-type)
4. 让 *callerContext* 为 正在运行的执行上下文
5. 让 *callerRealm* 为 *callerContext* 的 [Realm](https://262.ecma-international.org/6.0/#sec-code-realms)
6. 让 *pending* 为 PendingJob{ [[Job]]: *job*, [[Arguments]]: *arguments*, [[Realm]]: *callerRealm*, [[HostDefined]]: **undefined** }.
7. 执行任何规范和宿主定义的对 *pending* 的处理。这可能包括修改 [[HostDefined]] 字段或任何其他未决字段。
8. 将 *pending* 以 *queueName* 之名加到作业队列的后面
9. 返回 [NormalCompletion](https://262.ecma-international.org/6.0/#sec-normalcompletion)(empty).

#### 8.4.2 NextJob result

 算法步骤比如：

1. NextJob *result*.

在作业抽象操作中被用于替换：

1. Return *result*.

作业抽象操作必须包含一个返回或是一个 ReturnIfAbrupt 步骤。结果操作等效于以下步骤：

1. 如果 *result* 是 abrupt completion，执行实现定义的未处理异常处理。
2. 挂起正在运行的执行上下文，并将其从执行上下文堆栈中删除。
3. Assert：执行上下文栈为空
4. 令 *nextQueue* 为以实现定义的方式选择的非空作业队列。如果所有作业队列都为空，则结果是实现定义的。
5. 令 *nextPending* 为 *nextQueue* 前面的 PendingJob 记录。从 *nextQueue* 删除该记录
6. 让 *newContext* 为一个新的执行上下文
7. 设置 *newContext* 的 [Realm](https://262.ecma-international.org/6.0/#sec-code-realms) 为 *nextPending*.[[Realm]]
8. 将 *newContext* 推送到执行上下文堆栈中；*newContext* 现在是运行中的执行上下文
9. 使用 *nextPending* 执行任何实现或宿主环境定义的作业初始化
10. 使用 *nextPending*.[[Arguments]] 的元素作为其参数，执行以 *nextPending*.[[Job]] 命名的抽象操作。

### 8.5 ECMAScript Initialization()

ECMAScript 实现在执行任何作业或求值任何 ECMAScript 代码之前执行以下步骤：

1. 让 *realm* 为 [CreateRealm](https://262.ecma-international.org/6.0/#sec-createrealm)()
2. 让 *newContext* 为一个新的执行上下文
3. 设置 *newContext* 的 Function 为 **null**
4. 设置 *newContext* 的 Realm 为 *realm*
5. 将 *newContext* 入执行上下文栈；*newContext* 现在是正在运行的执行上下文
6. 让 *status* 为 [InitializeHostDefinedRealm](https://262.ecma-international.org/6.0/#sec-initializehostdefinedrealm)(*realm*).
7. 如果 *status* 是 abrupt completion，那么
   1. [Assert](https://262.ecma-international.org/6.0/#sec-algorithm-conventions): 首个 realm 则不能被创建
   2. 终止 ECMAScript 的执行
8. 以依赖于实现的方式，获取零个或多个 ECMAScript 脚本和/或 ECMAScript 模块的ECMAScript 源文本（请参见第10节）。对每个 *sourceText* ，执行：
   1. 如果 sourceText 是脚本的源代码，那么：
      1. 执行 [EnqueueJob](https://262.ecma-international.org/6.0/#sec-enqueuejob)(`"ScriptJobs"`, [ScriptEvaluationJob](https://262.ecma-international.org/6.0/#sec-scriptevaluationjob), « *sourceText* »).
   2. 否则 *sourceText* 是模块的源代码：
      1. Perform [EnqueueJob](https://262.ecma-international.org/6.0/#sec-enqueuejob)(`"ScriptJobs"`, [TopLevelModuleEvaluationJob](https://262.ecma-international.org/6.0/#sec-toplevelmoduleevaluationjob), « *sourceText* »).
9. NextJob [NormalCompletion](https://262.ecma-international.org/6.0/#sec-normalcompletion)(**undefined**).

#### 8.5.1 InitializeHostDefinedRealm ( realm )

以 *realm* 为参数的抽象操作 InitializeHostDefinedRealm 执行如下步骤：

1. 如果此实现要求使用奇异对象作为领域的全局对象，则使 *global* 为以实现定义的方式创建的此类对象。否则，请使 *global* 为 undefined，以指示应将普通对象创建为全局对象。
2. 执行 [SetRealmGlobalObject](https://262.ecma-international.org/6.0/#sec-setrealmglobalobject)(*realm*, *global*)
3. 让 *globalObj* 为 [SetDefaultGlobalBindings](https://262.ecma-international.org/6.0/#sec-setdefaultglobalbindings)(*realm*)
4. [ReturnIfAbrupt](https://262.ecma-international.org/6.0/#sec-returnifabrupt)(*globalObj*)
5. 在 *globalObj* 上创建任何实现定义的全局对象属性
6. 返回 [NormalCompletion](https://262.ecma-international.org/6.0/#sec-normalcompletion)(**undefined**)