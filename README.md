# rpcdemo
this project for rpc demo，use netty、zookeeper、reflect、spring 、动态代理，自定义注解 and go on..

#项目之间的依赖：可以查看pom文件

这里注意一下，netty中在使用Handler的过程中，需要注意：
1、ChannelInboundHandler之间的传递，通过调用 ctx.fireChannelRead(msg) 实现；调用ctx.write(msg) 将传递到ChannelOutboundHandler。
2、ctx.write()方法执行后，需要调用flush()方法才能令它立即执行。
3、流水线pipeline中outhandler不能放在最后，否则不生效
4、Handler的消费处理放在最后一个处理。

#使用：
先启动 /rpc-sample-server/src/main/java/cn/dean/rpc/sample/server/RpcBootstrap.java ，这里使用的 main方法，这里会加载spring，然后会一次加载netty以及注册zookeeper等等。。

再启动/rpc-sample-app/src/main/java/cn/dean/rpc/sample/app/HelloServiceTest.java
这使用了junit的方式测试，也会通过spring加载需要的类

#Q&A
deanadam@163.com
qq：523043518


