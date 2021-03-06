# server碳
微信通知推送服务，兼容[server酱](http://sc.ftqq.com/)的一对多推送服务接口([push bear](https://pushbear.ftqq.com/))

## 安装
### 源码编译
```bash
cargo install --git https://github.com/chinuno-usami/server_tan
```
### 使用预编译可执行文件
从[Release页面](https://github.com/chinuno-usami/server_tan/releases)下载对应可执行文件

## 使用
### 运行服务
0. 申请微信服务号，或者自用情况下可以使用微信接口测试号，配置好推送模板
1. 编写详情页面展示模板，可以参考[默认模板](https://github.com/chinuno-usami/server_tan/blob/master/template.html)
2. 编辑`config.toml`配置文件，配置文件可以参照[配置文件模板](https://github.com/chinuno-usami/server_tan/blob/master/config.toml)修改
3. 配置`Nginx`等web服务器
4. 直接执行`server_tan`启动服务，默认读取当前目录下的`config.toml`作为配置文件，可通过`-c`参数指定特定的配置文件

### 管理接口
因为对前端不是很熟悉，没做web交互界面，也还没有实现二维码订阅，所有操作通过微信文字发命令交互。  
具体操作可以在订阅服务号后发送`help`查看详情

### API接口
引用`push bear`的接口介绍：

> 1个接口，2个参数
> 简单很重要
> 不用再看文档看到吐。1个接口，2个参数，分分钟上手。
>
> https://pushbear.ftqq.com/sub?sendkey={sendkey}&text={text}&desp={desp}
> 
> PS: 会为每一个消息通道分配独立的SendKey和二维码。
