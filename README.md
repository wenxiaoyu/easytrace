easytrace
=========

Java 命令行诊断工具

目前该工具代码暂不开源，原因如下：<br>
1、由于处于初期的开发和小面积试用阶级，代码还需整理。<br>
2、对于代码的结构还需进一步调整，以达到方便的扩展性。<br>

当完成以上工作后，会把所有代码进行开源。

# 简介
easytrace 是一款Java的运行时诊断工具（采用动态字节码注入技术），可以在不停止程序的情况下查看Java程序运行时状况。
当初的开发的设想是在Btrace 的基础上改进成一个命令行的工具，当基本对Btrace代码有一定了解的时候，发现Btrace代码复杂，改造工程也比较麻烦，后来发现HouseMD的作者在微博上发布了[HouseMD](https://github.com/zhongl/HouseMD)，
在了解HouseMD后，决定自己开发一套Java版本的诊断工具，原因有两点：1、不熟scala，不能对HouseMD进行定制  2、需自己根据自己要求定制。当然，easytrace 很大部分是参考了HouseMD的功能（但实现方式不太相同），这里特别感谢HouseMD、Btrace的作者。

# 功能
* 动态方法跟踪功能，可针对调用方法，查看当时的返回对象、this对象、传入参数的值。
* 查看具体类的类装载器层次和来源路径功能，这个在多类加载器的程序比较有用。比如ClassCastException异常和ClassNotFoundException异常时有用。
* static 属性查看功能，可单独查看当时的static 属性值。
* Class 字节码导出功能，这个功能可能比较少用，主要用在运行期修改字节码的时候，想知道修改的内容时，可用该功能导出当时运行时的Class字节码。


# 支持
* JDK1.6+
* 本地诊断，不支持远程方式

# 特点
* 命令行诊断（非Btrace的脚本方式）
* 诊断后对程序无残留代码段（Btrace 脚本执行后有残留代码）
* 安全性和易用性高（对于异常的情况，大多数都会使注入程序端的easytrace代码中断和恢复原有更改，从而保证目标程序的安全和无残留）
* 文件小、无依赖jar（所有需要的jar包都已经打进jar中，或者自己实现）


# 安装
无需安装，直接下载后，运行即可。

·····

详细的指南可查看：https://github.com/zhxing/easytrace/wiki/%E7%94%A8%E6%88%B7%E6%8C%87%E5%8D%97

诊断示例可查看：https://github.com/zhxing/easytrace/wiki/%E8%AF%8A%E6%96%AD%E7%A4%BA%E4%BE%8B
