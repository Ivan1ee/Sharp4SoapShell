# Sharp4SoapShell
4个 .soap 版本的WebShell，优点：可以运行于子目录，突破了过去只能运行于根目录的限制。4个脚本分别支持调用cmd.exe/哥斯拉/冰蝎/天蝎客户端
具有广泛的实用性，理论上兼容.NET 2.0 - .NET 4.x 环境

## 背景
这4款.soap脚本，是专为.NET Framework环境设计的Webshell工具，最引人注目的特点在于克服了传统 *.soap扩展名Webshell只能运行于根目录下的限制。这一技术突破性的进展，使该工具能够灵活运行在服务器的根目录或任意子目录下，即便文件名被更改，其功能依然有效，由于.soap扩展名并不常见，因此该工具在文件系统中具有较高的隐蔽性，有助于攻击者避开安全检测。

我们知道，哥斯拉WebShell工具默认生成的SOAP马和dot.Net安全矩阵星球以前发过的ShellInject.soap无法在子目录下运行，shell.soap只能上传至站点根目录下运行才能正常连接

![image](https://github.com/user-attachments/assets/4bac5ceb-1ce5-4e94-b99b-c5775d0126c9)

因此，结论就是目前的*.soap马，在.NET平台下只能位于站点根目录下才能正常工作解析，传到其他任何一个子目录都会连接报错，这便形成了一个技术瓶颈，急需解决。

## 1. 支持调用cmd.exe

默认执行 whoami 命令，可以编辑脚本第18行，修改变量c的值即可

![image](https://github.com/user-attachments/assets/336bb323-fc85-41d4-a881-f9b958af5221)


## 2. 适配支持哥斯拉

### 2.1 Sharp4SoapGodzilla.soap

通过上传Sharp4SoapGodzillia.soap文件到子目录UploadFiles，可以植入支持哥斯拉的内存马，成功植入后，Sharp4SoapGodzillia能够返回详细的服务器环境信息，包括内存马具体的访问路径、网站当前的绝对路径、.NET Framework版本以及Windows操作系统版本等，为后续的渗透攻击提供了重要参考。

![image](https://github.com/user-attachments/assets/6c395989-def9-4151-ab6a-d9bfb899572b)

从图上soap Webshell 返回的信息，我们可以得知支持哥斯拉工具的内存马访问路径为:uploadfiles/dotNetMatrix/Godzllia.aspx
打开哥斯拉客户端测试连接效果，选择有效载荷和加密器，连接密码为：dotnet001，返回Success。如下图所示

![image](https://github.com/user-attachments/assets/c88d1231-6203-417f-aa93-b2e4809506dc)


### 2.2 Sharp4SoapRootShell.soap

众所周知，哥斯拉的某个版本客户端支持根目录下soap马的连接，并且可以生成 SOAP Webshell，但有个局限性，该 Webshell 必须部署在网站根目录下才能运行。然而，在某些特定场景中，需要使用 Sharp4SoapRootShell.soap 在根目录下生成一个名为 SoapRootShell4Godzilla.soap 的 Webshell，专门用于哥斯拉客户端的连接。默认连接密码为 pass。

![image](https://github.com/user-attachments/assets/533cd7a7-a50c-4afa-a29c-2a2fad46d906)

![image](https://github.com/user-attachments/assets/fead0203-d387-4475-9918-ce723eeef075)

## 3. 适配支持冰蝎
Sharp4SoapBehinder.soap作为冰蝎Webshell的服务端脚本，在此基础上进行了优化和扩展。通过上传Sharp4SoapBehinder.soap文件到子目录UploadFiles，可以植入支持冰蝎的内存马，从图上soap Webshell 返回的信息，我们可以得知支持冰蝎工具的内存马访问路径为 uploadfiles/dotNetMatrix/Behinder.aspx，打开冰蝎客户端Behinder.jar测试连接效果，连接密码：rebeyond，返回站点环境变量基本信息。如下图所示。

![image](https://github.com/user-attachments/assets/c0b13c75-6a6c-4996-94f6-28d8139a2651)

## 4. 适配支持天蝎
Sharp4SoapSky.soap与天蝎Webshell管理工具无缝连接，能够充分利用天蝎提供的所有功能，包括但不限于命令执行、文件上传下载等，通过上传Sharp4SoapSky.soap文件到子目录UploadFiles，可以植入支持天蝎客户端工具的内存马，内存马路径：uploadfiles/dotNetMatrix/Sky.aspx ，打开天蝎权限管理工具.jar测试连接效果，连接密码：sky，点击验证后，下方状态栏返回连接成功。如下图所示。

![image](https://github.com/user-attachments/assets/660bd99c-2b1d-4aba-b4b4-21f49bb626f1)

## 压缩包密码获取和互动交流
能帮到大家我们团队很开心，建群的初心是为了相互交流，加群后可以查看群置顶公告获取压缩包密码。另外本群讨论话题主要聚焦于该工具，但也包括 .NET 安全大领域技术的知识交流。识别下方二维码，或者满员后，通过关注dot.Net安全矩阵公众号给我们反馈留言，我们后续会更新微信群二维码（2024.10.25已更新）邀请大伙入群。

![image](https://github.com/user-attachments/assets/4504c869-82b1-4e78-b9e8-9c21267c9c09)


最后，希望大伙爱护这个开放的大家庭，愿我们一起相互学习，共同进步！


# 更新日志

- 2024-11-13 
  - [更新 | 适配天蝎的修正版 SoapWebShell](https://mp.weixin.qq.com/s/xTlUQsOXf4RkN6jsW9s69A)
- 2024-10-14 
  - [.NET SoapShell 更新 | 发布增强免杀版适配哥斯拉客户端的WebShell](https://mp.weixin.qq.com/s/RUinIKDpDa7yIAfoddFl-w)
- 2024-09-20 
  - [SoapShell 更新 | 新增站点根目录下适配某版本哥斯拉的WebShell](https://mp.weixin.qq.com/s/zjEX6WNfbuZZEcUNbP9wVQ)
- 2024-09-14 
  - [SoapShell 更新 | 新增调用cmd执行系统命令](https://mp.weixin.qq.com/s/H_2AEwtjTp6e2wVd2Qr1ZA)
- 2024-09-05 
  - [.NET攻防新突破，开源3个强大的SoapShell](https://mp.weixin.qq.com/s/XAIkMBGO43vYqxsfZ2OcGA)



