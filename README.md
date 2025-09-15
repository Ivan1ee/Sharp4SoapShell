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

## 互动交流
能帮到大家我们团队很开心，写作和分享的初心是为了相互交流，请扫描二维码关注 dot.Net安全矩阵 公众号。

<img width="159" height="156" alt="image" src="https://github.com/user-attachments/assets/7ce37734-84d8-4341-8f45-bee3aba2081d" />

我们也会不定期在知识星球里更新此工具，以及在公众号上分享更多与 .NET 安全相关的学习工具、资料和实战经验。
