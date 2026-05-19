#### Late 变量

`late` 修饰符号有两种使用情况：
+ 声明一个在声明之后被初始化的非空变量
+ 延迟初始化一个变量

通常，Dart的控制流分析可以在使用非空变量之前检测到它是否被设置为非空值，但有时分析失败。两个常见的情况是顶层变量和实例变量：Dart通常无法确定它们是否被设置，所以它不会尝试。

如果你确定一个变量在使用前会被赋值，但是Dart不同意，你可以通过声明这个变量为 `Late` 来修复这个错误:
```dart
late String description;

void main() {
  description = 'Feijoada!';
  print(description);
}
```

> -- ***NOTICE*** --  
> 如果你没有初始化一个 `late` 变量，当使用它的时候就会报一个运行时错误。

如果将变量声明为late，但在声明时初始化它，那么在第一次使用该变量时，初始化程序就会运行。这种延迟初始化在以下几种情况下很方便：
- 可能不需要该变量，并且初始化它的开销很大
- 你在初始化一个实例变量，它的初始化方法需要访问 `this`

在下面的例子中，如果从来没有使用过 `temperature` 变量，那么开销大的 `readThermometer()` 函数就永远不会被调用:
```dart
// This is the program's only call to readThermometer().
late String temperature = readThermometer(); // Lazily initialized.
```

#### Final 和 const

如果一个变量不会被重新赋值，应使用 `final` 或 `const` 来声明，可以替换 `var`，也可以在类型的基础上补充使用。final变量只能赋值一次；const变量是编译时常量。（Const变量隐式声明为final）

> -- ***NOTE*** --  
> 实例变量可以是 `final`，但不能是 `const`

下面是创建和设置 `final` 变量的例子：