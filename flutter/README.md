## Flutter 安装、配置文档

### 工具
- VS code
- VS code安装插件：Flutter（Dart-Code）
- VS code安装插件：Dart（Dart-Code）
- Flutter SDK 3.22.0-stable
- Java SDK 17

### 安装
1. 下载 Flutter SDK
2. 配置环境变量
   - 设置 > 系统 > 系统信息 > 高级系统设置 > 环境变量
   - 新建用户变量：新建变量 `FLUTTER_HOME`，值为 `${指定的安装目录}\flutter_windows_3.22.0-stable\flutter`
   - 修改用户变量：修改变量 `PATH`，新增 `%FLUTTER_HOME%\bin`
   - 点击三次【确定】保存变量
3. 验证安装
   ```bash
   # 验证flutter
   flutter --version

   # 网络问题卡住时
   flutter --version --no-version-check
   
   # 验证dart
   dart --version
   ```
4. 安装成功
   - 打开 VS code
   - 快捷键 `Ctrl + Shift + P` 打开命令面板
   - 输入 `flutter`，点击 `Flutter: New Project`
   - 项目新建 `hello.dart` 文件
   - 输入以下代码
     ```dart
     void main() {
       print('Hello World!');
     }
     ```
   - 保存文件
   - 点击 `Run` 按钮，或者终端运行 `dark hello.dart`
   - 控制台输出 `Hello World!` 安装成功
5. 配置 Java SDK（同上）

### 资源
- Flutter SDK：[下载地址](https://docs.flutter.cn/install/archive)
- Flutter 安装、配置：[文档地址](https://docs.flutter.dev/install/manual)
- Java SDK：[下载地址](https://mirrors.tuna.tsinghua.edu.cn/Adoptium)

<br>
<br>

> 卸载原有 Java SDK

1. 卸载 JDK/JRE 程序
   - 按 Win + X 键，选择 “安装的应用” (Windows 11) 或 “应用和功能” (Windows 10)。
   - 在列表中找到所有带 Java、JDK、JRE 或 OpenJDK 字样的程序。
   - 逐个点击它们，选择 “卸载”，然后按照卸载向导的提示完成操作。

2. 手动删除残留文件夹
   - 卸载程序通常不会自动删除安装目录，需要手动清理：
   - 打开文件资源管理器，删除以下两个路径下的 Java 文件夹（如果存在）：
      `C:\Program Files\Java`
      `C:\Program Files (x86)\Java`
   - 同时，建议检查并删除用户目录下的配置残留：
      `C:\Users\你的用户名\AppData\LocalLow\Sun`
      `C:\Users\你的用户名\AppData\Roaming\Oracle`

3. 清理环境变量
   - 按 Win + R 键，输入 sysdm.cpl 并回车，打开“系统属性”。
   - 在 “高级” 选项卡下，点击 “环境变量”。
   - 在 “系统变量” 列表中，找到并删除与 Java 相关的变量，例如 JAVA_HOME 和 CLASSPATH。
   - 在同一个列表中找到 Path 变量，选中后点击 “编辑”，在编辑窗口中删除所有包含 java 或 %JAVA_HOME% 的条目。
   - 点击所有窗口的“确定”保存。  
