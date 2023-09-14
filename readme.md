
```
                     __     _             __  ___    ___    __            ____ 
   ____  __  _______/ /__  (_)    __     / / / / |  / / |  / /___ ___  __/ / /_
  / __ \/ / / / ___/ / _ \/ /  __/ /_   / /_/ /| | / /| | / / __ `/ / / / / __/
 / / / / /_/ / /__/ /  __/ /  /_  __/  / __  / | |/ / | |/ / /_/ / /_/ / / /_  
/_/ /_/\__,_/\___/_/\___/_/    /_/    /_/ /_/  |___/  |___/\__,_/\__,_/_/\__/  
                                                                               
```

<h4 align="center">HVVault - 基 于 Nuclei 扫 描 模 板 的 POC 仓 库 集 成</h4>
<p align="center">
<a href="https://opensource.org/licenses/MIT"><img src="https://img.shields.io/badge/license-MIT-_red.svg"></a>
<a href="https://github.com/asaotomo/fofamap/issues"><img src="https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat"></a>
</p>


### 0x00. 项目说明
- 2023.08.10 2023HVV期间出现的可以验证的漏洞POC；
- 0000.00.00 计划参照佩奇文库已公开POC完成POC仓库集成；
- 2023.09.15 目前支持81个护网漏洞验证：**[点击查看支持清单](支持清单.md)** 。


### 0x01. 免责声明
<h4 align="center">免责声明</h4>
<p align="center">1. 仅用于技术交流，目的是向相关安全人员展示漏洞利用方式，以便更好地提高网络安全意识和技术水平。</p>
<p align="center">2. 任何人不得利用本仓库进行非法攻击和侵犯他人的隐私和财产权利。一旦发生任何违法行为，责任自负。</p>
<p align="center">3. 本仓库仅用于授权测试，任何未经授权的测试均属于非法行为。请在法律许可范围内使用。</p>
<p align="center">4. 作者对使用此仓库导致的任何直接或间接损失不承担任何责任。使用此仓库的风险由使用者自行承担。</p>

### 0x02. 联系方式
![wx.png](docs%2Fwx.png)

### 0x03. 编写规范
**规范说明**
1. 所有PoC命名为**小写**，且**不允许**存在下划线"_"等方式，空格用"-"做替换。
2. PoC id命名规范为：***厂商名称-产品名称-漏洞路径/影响版本/-漏洞类型\*** , 例如 `fanwei-ecology-bsh-servlet-bshservlet-rce` ，`fanwei` = `厂商名称` ，`ecology` = `产品名称` ，`bsh-servlet-bshservlet` = `漏洞路径` ，`rce` = `漏洞类型` 
3. 为避免触发Waf，PoC编写过程中涉及到上传文件或者执行命令需要验证的情况下，尽量做**无害化**处理，例如上传的文件后缀尽量选择为 `txt`  内容为正常随机字符串，命令执行尽量避免 `whoami` 等一些高危命令。
4. 未避免触发Waf，漏洞验证可以分为三步来实现，例如一个文件上传漏洞：
   1. 第一步首先去探测漏洞路径是否存在，根据回显来判断；
   2. 第二步进行文件上传进行判断回显是否上传成功；
   3. 第三步进行上传文件的访问来判断文件是否存在。这样做的好处是：第一步的操作仅仅是探测不会触发Waf，如果第二步因为上传文件被Waf拦截，也可以后期手动去复制上传包进行bypass.
5. tags标签要求全部为**小写**，标签一般分为四大类，`漏洞类型` and `产品名称` and `厂商名称` and `产品性质归属` ，例如`泛微ecology文件上传漏洞` ，标签则为：`ecology,fanwei,fileupload,oa` , 其中OA是一个大类，用来标记所有的OA办公系统，包括但不限于"宏景OA","致远OA"等。﻿

**漏洞类型**

| 中文名称    | 英文名称            |
| ----------- | ------------------- |
| SQL注入     | sqli                |
| 本地文件包含 | lfi                 |
| 远程文件包含 | rfi                 |
| 文件上传    | fileupload          |
| 命令执行    | rce                 |
| 文件下载    | filedownload        |
| 路径穿越    | directory-traversal |
| 信息泄露    | infoleak            |
| 未授权      | unauth              |
| XSS         | xss                 |
| 任意文件读取 | fileread            |
| SSRF        | ssrf                |
| xxe         | xxe                 |
| 身份认证绕过 | bypassauth          |
| 默认密码    | default-password    |
| 任意用户登录 | userlogin           |
| 目录遍历    | dirlist             |
| 重置密码    | reset-password      |
