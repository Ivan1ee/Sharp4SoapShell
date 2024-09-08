# Sharp4SoapShell
3个 .soap 版本的WebShell，优点：可以运行于子目录，突破了过去只能运行于根目录的限制。3个脚本分别支持哥斯拉/冰蝎/天蝎客户端
具有广泛的实用性，理论上兼容.NET 2.0 - .NET 4.x 环境

## 适配支持哥斯拉
通过上传Sharp4SoapGodzillia.soap文件到子目录UploadFiles，可以植入支持哥斯拉的内存马，成功植入后，Sharp4SoapGodzillia能够返回详细的服务器环境信息，包括内存马具体的访问路径、网站当前的绝对路径、.NET Framework版本以及Windows操作系统版本等，为后续的渗透攻击提供了重要参考。

![image](https://github.com/user-attachments/assets/6c395989-def9-4151-ab6a-d9bfb899572b)

从图上soap Webshell 返回的信息，我们可以得知支持哥斯拉工具的内存马访问路径为:uploadfiles/dotNetMatrix/Godzllia.aspx
打开哥斯拉客户端测试连接效果，选择有效载荷和加密器，连接密码为：dotnet001，返回Success。如下图所示

![image](https://github.com/user-attachments/assets/c88d1231-6203-417f-aa93-b2e4809506dc)

## 适配支持冰蝎
Sharp4SoapBehinder.soap作为冰蝎Webshell的服务端脚本，在此基础上进行了优化和扩展。通过上传Sharp4SoapBehinder.soap文件到子目录UploadFiles，可以植入支持冰蝎的内存马，从图上soap Webshell 返回的信息，我们可以得知支持冰蝎工具的内存马访问路径为 uploadfiles/dotNetMatrix/Behinder.aspx，打开冰蝎客户端Behinder.jar测试连接效果，连接密码：rebeyond，返回站点环境变量基本信息。如下图所示。

![image](https://github.com/user-attachments/assets/c0b13c75-6a6c-4996-94f6-28d8139a2651)

## 适配支持天蝎
Sharp4SoapSky.soap与天蝎Webshell管理工具无缝连接，能够充分利用天蝎提供的所有功能，包括但不限于命令执行、文件上传下载等，通过上传Sharp4SoapSky.soap文件到子目录UploadFiles，可以植入支持天蝎客户端工具的内存马，内存马路径：uploadfiles/dotNetMatrix/Sky.aspx ，打开天蝎权限管理工具.jar测试连接效果，连接密码：sky，点击验证后，下方状态栏返回连接成功。如下图所示。

![image](https://github.com/user-attachments/assets/660bd99c-2b1d-4aba-b4b4-21f49bb626f1)

## 压缩包密码获取和互动交流
能帮到大家我们团队很开心，建群的初心是为了相互交流，加群后可以查看群置顶公告获取压缩包密码。另外本群讨论话题主要聚焦于该工具，但也包括 .NET 安全大领域技术的知识交流。识别下方二维码，或者满员后，通过关注dot.Net安全矩阵公众号给我们反馈留言，我们后续会更新微信群二维码邀请大伙入群。

![image](https://github.com/user-attachments/assets/b8dea98c-9588-4c3f-b200-6b199e33d306)

最后，希望大伙爱护这个开放的大家庭，愿我们一起相互学习，共同进步！

