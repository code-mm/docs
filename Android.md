# Android 面试题

## Android

## 多进程如何判断主进程

### Android 可以做耗时操作的组件

    AsyncTask
    IntentServer
    HandlerThread
    Thread
    ThreadPool
    Handler

### ContentProvider 数据存储结构

### Android 特有的集合

    ArrayMap
    ArraySet
    SparseArray
    SparseIntArray
    SparseBooleanArray
    SparseLongArray

### Activity 数据存储

1、Activity 在销毁前的数据保存 是 重写  onSaveInstanceState(Bundle outState)方法，而不是  onSaveInstanceState(Bundle outState, PersistableBundle,outPersistentState)方法，这两者是不一样的，后者的方法好像没有执行 保存操作（我在测试的时候看到的现象

2、在 Activity 重建时，进行数据恢复，onCreate(Bundle)或者 onRestoreInstanceState(Bundle)方法都是可以的

### 两种序列化方式的区别

Serializable 和 Parcelable

序列化 (Serialization)将对象的状态信息转换为可以存储或传输的形式的过程。在序列化期间，对象将其当前状态写入到临时或持久性存储区。以后，可以通过从存储区中读取或反序列化对象的状态，重新创建该对象。

二进制序列化保持类型保真度，这对于在应用程序的不同调用之间保留对象的状态很有用。例如，通过将对象序列化到剪贴板，可在不同的应用程序之间共享对象。您可以将对象序列化到流、磁盘、内存和网络等等。远程处理使用序列化“通过值”在计算机或应用程序域之间传递对象。

Serializable 用来标识当前类可以被 ObjectOutputStream 序列化，以及被 ObjectInputStream 反序列化。

Serializable 有以下几个特点：

可序列化类中，未实现 Serializable 的属性状态无法被序列化/反序列化
也就是说，反序列化一个类的过程中，它的非可序列化的属性将会调用无参构造函数重新创建
因此这个属性的无参构造函数必须可以访问，否者运行时会报错
一个实现序列化的类，它的子类也是可序列化的

Parcelable 的效率高，但是使用麻烦，主要用于内存序列化。

Serializable 使用简单，但是需要做大量的 I/O 操作，开销很大，适用于储存设备，或者网络传输。

## 源码解析

### okhttp 源码解析

### IPC 进程间通信

### AIDL 原理

[https://www.jianshu.com/p/e0c583ea9289](https://www.jianshu.com/p/e0c583ea9289)

Binder 就是 Android 中最具特色的 IPC 方式，AIDL 其实就是通过 Binder 实现的，因为在我们定义好 aidl 文件后，studio 就帮我们生成了相关的 Binder 类。事实上我们在使用 AIDL 时候继承的 Stub 类，就是 studio 帮我们生成的 Binder 类，所以我们可以通过查看 studio 生成的代码来了解 Binder 的工作原理。

### 函数式编程

### Gradle 生命周期

[https://www.jianshu.com/p/b9b5acf24bb6](https://www.jianshu.com/p/b9b5acf24bb6)

### 数据库事务

[https://www.jianshu.com/p/d98be38a6d3f](https://www.jianshu.com/p/d98be38a6d3f)

### Intent 与 Intentfilter 的区别
