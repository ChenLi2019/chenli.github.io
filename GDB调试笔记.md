# 网站：
- GDB常用的命令做成了表格，方便查阅。  
https://darkdust.net/files/GDB%20Cheat%20Sheet.pdf
- 简单的调试实例，源文件有点问题，编译根据提示修改
https://www.cs.cmu.edu/~gilpin/tutorial/

# 实践
## 安装调试信息包  
    启动gdb时，提示"Missing separate debuginfos, use: debuginfo-install glibc-2.12-1.47.el6_2.9.i686 libgcc-4.4.6-3.el6.i686 libstdc++-4.4.6-   3.el6.i686"  
    解决方法：
    ```
    yum install yum-utils
    debuginfo-install glibc-2.12-1.47.el6_2.9.i686 libgcc-4.4.6-3.el6.i686 libstdc++-4.4.6-3.el6.i686
    ```
## 常用命令
### 执行
- run/r
- start //从main开始运行。

### 显示
list/l
### 单步
- step/s 单步进入
- finish 返回函数
- next/n 单步不进入
### stack
- backtrace/bt //显示堆栈信息

### 打印
 print [格式] 变量  
 print *argv@10 //打印字符串数组前10个变量

### 断点
- break/b 函数或行号 if <condition>
    
## 格式
Format
a Pointer.
c Read as integer, print as character.
d Integer, signed decimal.
f Floating point number.
o Integer, print as octal.
s Try to treat as C string.
t Integer, print as binary (t = „two“).
u Integer, unsigned decimal.
x Integer, print as hexadecimal.
