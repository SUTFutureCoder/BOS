# BOS
开放云存储（Bricky Open Storage）
##欢迎使用开放云存储  
###项目说明  
该项目为**仿制**某云存储，各个模块松耦合。该项目支撑了[Mnemosyne - 同学录项目](https://github.com/SUTFutureCoder/Mnemosyne)，以及本人为EX开发的[教学资源云平台](https://github.com/SUTFutureCoder/Cloud-platform-for-teaching-resources)数据存放、浏览需求。服务端放置在某低价折扣买来的阿里云辣鸡虚拟共享主机上。  

支持分享码、防盗链、举报、bucket-object分离、用户控制、在线预览（图片、视频流跳转、pdf文档、图片实时缩放、质量控制）等特征。并且服务端能够平稳运行在辣鸡共享主机上，不依赖redis等各种拓展即可跑起来。目前没时间开发界面……但五脏俱全。  

另外客户端附赠了一些自己实现的库，只模仿了最小集合，但足够项目跑起来了。客户端使用CI框架，但应该比较好适应其他框架。  
####配置文件地址  
数据库文件bos_server/bos_struct.sql  
配置文件样例 bos_server/config.php  
####客户端文件夹
bos_client/  
使用时放到框架library下面，依赖curl、redis。  
####图片浏览及实时缩放、质量控制  
例如：  
http://localhost:10090/bos/file.php?file=0b28d97a77822d27c2695caea196596c003e91fb&w=300&q=70  

w 宽
h 长  
两者指定其一则等比缩放  

q 图片质量

可以通过这样直接进行外链  
####上传流程  
调用BosClient::putObjectFromFile方法进行上传，上传成功后会返回url用于保存到数据库中。  
注意bucketId和key要匹配～～  


####义务支持 
如果有任何问题，欢迎提交issue～～最后非常感谢关注这个项目！  