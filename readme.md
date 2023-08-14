```
   __ ___   ___   __          ____ 
  / // / | / / | / /__ ___ __/ / /_
 / _  /| |/ /| |/ / _ `/ // / / __/
/_//_/ |___/ |___/\_,_/\_,_/_/\__/ 
                                   
```
<h4 align="center">基于Nuclei扫描模板的POC仓库集成</h4>

### 项目说明
借2023HVV之机梳理【护网高利用率POC】并集成Nuclei模板仓库，针对网上同一资产漏洞一键检测工具参次不齐问题。

- 免责：文库POC以及测试目标只允许在目标授权的情况下进行测试，利用此仓库造成的任何直接或者间接的后果及损失，均由使用者本人负责，作者不为此承担任何责任。若不同意以上警告信息请立即退出使用。
- 开源：我认为开源才是最好的交流方式，仓库的POC都是公开可以任意下载的。希望能帮助到各位学习与测试。希望大家可以通过提出建设性意见或者赞助项目来给予我更多更新的动力～
- 参考：
  - 漏洞来源：https://github.com/PeiQi0/PeiQi-WIKI-Book
  - 模板说明：https://nuclei.projectdiscovery.io/

### 索引相关
```
targets    # fofa导出的测试资产列表
domestic   # yaml列表
- 畅捷通T+ 命令执行 QVD-2023-13615 /tplus/ajaxpro/Ufida.T.CodeBehind._PriorityLevel,App_Code.ashx?method=GetStoreWarehouseByStore
- 畅捷通T+ 文件上传 CNVD-2022-60632 /tplus/SM/SetupAccount/Upload.aspx?preload=1

- 大华智慧园区 账户密码泄露 2023HVV /admin/user_getUserInfoByUserName.action
- 大华智慧园区 SQL注入 2023HVV /portal/services/carQuery/getFaceCapture/searchJson/
- 大华智慧园区 文件上传 2023HVV /publishing/publishing/material/file/video
- 大华智慧园区 文件上传 CVE-2023-3836 /emap/devicePoint_addImgIco?hasSubsystem=true

- 海康威视综合安防 命令执行 --- /bic/ssoService/v1/applyCT
- 海康威视综合安防 命令执行 --- /bic/ssoService/v1/keepAlive
- 海康威视综合安防 文件上传 2023HVV /center/api/files;.png
- 海康威视综合安防 文件上传 2023HVV /svm/api/external/report  # 待验证
- 海康威视综合安防 文件读取 2023HVV /artemis-portal/artemis/env
- 海康威视IVMS8700 文件上传 2023HVV /eps/api/resourceOperations/upload?token=
- 海康威视IVMS8700 文件上传 2023HVV /eps/resourceOperations/upload.action
- 海康威视IVMS8700 文件下载 2023HVV /eps/api/triggerSnapshot/download?token=

- 金蝶云星空 命令执行 2023 /Kingdee.BOS.ServiceFacade.ServicesStub.DevReportService.GetBusinessObjectData.common.kdsvc
- 金蝶云星空 文件读取 2023 /CommonFileServer/c%3A%2Fwindows%2Fwin.ini

- 绿盟SAS堡垒机 登录绕过 2023HVV /api/virtual/home/status?cat=
- 绿盟SAS堡垒机 命令执行 2023HVV /webconf/Exec/index?cmd=
- 绿盟SAS堡垒机 文件读取 2023HVV /webconf/GetFile/index?path=

- 网神SecGate3600 文件上传 2023HVV /?g=obj_app_upfile

- 深信服应用交付管理系统 命令执行 2023HVV /rep/login
- 深信服应用交付报表系统 文件读取 2023HVV /report/download.php?pdf=

- 泛微EOffice 文件上传 2023HVV /webservice/upload.php

- 用友NC 命令执行 2022 /servlet/~ic/bsh.servlet.BshServlet
- 用友NC 文件上传 2022 /aim/equipmap/accept.jsp
- 用友NC 文件读取 2022  /NCFindWeb?service=IPreAlertConfigService&filename=
- 用友NC-Cloud 命令执行 CNVD-C-2023-76801 /uapjs/jsinvoke/?action=invoke
- 用友移动系统管理 文件上传 2023HVV /maportal/appmanager/uploadApk.do?pk_obj=

- 广联达Linkworks办公OA SQL注入 /Webservice/IM/Config/ConfigService.asmx/GetIMDictionary
- MilesightVPN 文件读取 2023HVV /../etc/passwd
- 企业微信 信息泄露 2023HVV /cgi-bin/gateway/agentinfo
- 金盘微信管理平台 账户密码泄露 2023HVV /admin/weichatcfg/getsysteminfo
- 企望制造ERP系统 SQL注入+RCE 2023HVV  /mainFunctions/comboxstore.action

- 
```
