occiwrapper
===========

occiwrapper is an open source and cross platform Oracle Driver that delivers efficient access to Oracle databases.It was writen by C++, and offers a rich, full featured and easy to use API.


开发occiwrapper这个库，主要是为了封装一个跨平台的OCCI的访问组件，方使C++开发者们灵活地操作oracle数据库。为了方便使用，组件中的接口形式参考的POCO库的使用方式。<br />
使用如下的形式执行SQL语句：<br />

>        occiwrapper::Session s = SessionInstance( connection );
>        s << "truncate table TBL_TEST ", now;

通过session对象维护一个到oracle的会话。类似于流的操作方式，向session中传入SQL语句，并执行。<br />
在oracle参数绑定方面，可以直接将C++变量绑定给oracle参数中，在以后的文档说明中详细介绍。<br />

>        occiwrapper::Session s = SessionInstance( info );
>        struct tm tm_value; 
>        s << "insert into TBL_TEST( date_value ) values ( :1 )", use( tm_value ), now;

同时，对于vector等容量变量，可以灵活地直接绑定到oracle的绑定变量上，同时也可以灵活的将select语句返回的结果绑定到容器中，而且对于使用者来讲，并不用关心类型的对应关系。为了提高存取的性能，写入和读取都采入批量操作的方式，同时采用智能指针自动管理内存缓冲池，最大限度地解放了oracle开发者。<br />
组件中使用的很多技术都是在工作中一些经验的积累与总结，由于自己认识oracle不够深刻，对C++的理解也可能不够深入，希望大家多多讨论。对于大家发现的Bug，我也会尽快修改，同时热情欢迎大家积极参与库的修改。<br />
在此深深感谢我的母校西安交通大学、南京841所。感谢我的父母、爱人、同学、朋友，你们带给了我幸福的生活。还有我逝去的哈里、活着的蛋蛋，臭臭的小小。<br />

> 联系作者：CUCmehp@foxmail.com QQ交流群：348648166


				

