

Java 常见问题处理

# `Remove '@Override' annotation`
> 来源 ： https://my.oschina.net/u/1450300/blog/822393

最近刚刚配置了新机器，将原来的代码放在eclipse上执行，总会出现 `Remove '@override' annotation`，如果要一个个手动删除相当麻烦，最后在网上找了一下原因原来是 **编译器版本(Java Complie)**的问题。

@override：表示一个方法声明打算重写超类中的另一个方法声明。如果方法利用此注释类型进行注解但没有重写超类方法，则编译器会生成一条错误消息。

问题原因：Java 1.5的编译器默认对父类的方法进行覆盖，采用@Override进行说明；**但1.6已经扩展到对`接口的`方法；**所以如果还是以Java 1.5的编译器来编译的话，会出现错误。

解决办法如下：
在eclipse中，compiler 都得设置到1.6。这包括preference->java->compiler 下要改成1.6, 同时，project里的build path 里jdk 也得改成1.6。 这主要是针对同时装了1.5, 1.6,而default is 1.5这种情况的。
