<img src="assets/media/image2.png" style="width:0.98958in;height:0.98958in" alt="LOGO800E" />

**DX-CT511/DX-CT511N**

**4G串口应用指导**

> 版本：2.2
>
> 日期：2026-6-12

**更新记录**

|          |            |                          |          |
|:--------:|:----------:|:------------------------:|:--------:|
| **版本** |  **日期**  |         **说明**         | **作者** |
|   V1.0   | 2023/10/10 |         初始版本         |   SML    |
|   V1.1   | 2023/12/20 |         增加示例         |   SML    |
|   V2.0   | 2024/02/18 |       增加GPS指令        |   SML    |
|   V2.1   | 2024/04/16 |     增加AT指令一览表     |   SML    |
|   V2.2   | 2026/06/12 | 更改查询定位信息指令错误 |   SML    |

**联系我们**

**深圳大夏龙雀科技有限公司**

邮箱：sales@szdx-smart.com

电话：0755-2997 8125

网址：[www.szdx-smart.com](http://www.szdx-smart.com)

地址：深圳市宝安区航城街道航空路庄边工业园厂房A栋4层

**目录**

[1. 引言 [- 5 -](#引言)](#引言)

[1.1. 串口基本参数 [- 5 -](#_Toc5020)](#_Toc5020)

[2. PC端测试工具 [- 5 -](#pc端测试工具)](#pc端测试工具)

[2.1. 电脑端测试软件 [- 5 -](#_Toc239)](#_Toc239)

[3. 串口使用 [- 6 -](#串口使用)](#串口使用)

[3.1. 使用串口读写AT命令 [- 6 -](#_Toc25258)](#_Toc25258)

[3.1.1. 模块测试最小系统 [- 6 -](#_Toc23463)](#_Toc23463)

[3.1.2. 模块指令示例 [- 7 -](#_Toc9918)](#_Toc9918)

[3.1.2.1. TCP示例 [- 7 -](#_Toc15382)](#_Toc15382)

[3.1.2.2. UDP示例 [- 8 -](#_Toc2529)](#_Toc2529)

[3.1.2.3. MQTT示例 [- 9 -](#_Toc24826)](#_Toc24826)

[3.1.2.4. HTTP示例 [- 9 -](#_Toc7280)](#_Toc7280)

[3.1.2.5. GNSS示例 [- 10 -](#_Toc24895)](#_Toc24895)

[4. 相关AT命令详解 [- 10 -](#相关at命令详解)](#相关at命令详解)

[4.1. 命令格式说明 [- 10 -](#_Toc7294)](#_Toc7294)

[4.2. 回应格式说明 [- 11 -](#_Toc27749)](#_Toc27749)

[4.3. AT命令一览表 [- 11 -](#_Toc10097)](#_Toc10097)

[5. AT命令详解 [- 13 -](#at命令详解)](#at命令详解)

[5.1. 基础指令 [- 13 -](#_Toc19371)](#_Toc19371)

[5.1.1. 测试指令 [- 13 -](#_Toc32020)](#_Toc32020)

[5.1.2. 设置指令回显 [- 13 -](#_Toc9061)](#_Toc9061)

[5.1.3. 查询模块信息 [- 14 -](#_Toc12948)](#_Toc12948)

[5.1.4. 查询/设置串口波特率 [- 14 -](#_Toc3198)](#_Toc3198)

[5.1.5. 查询SIM卡ICCID [- 15 -](#_Toc32470)](#_Toc32470)

[5.1.6. 重启模块 [- 15 -](#_Toc2556)](#_Toc2556)

[5.2. 网络服务指令 [- 15 -](#_Toc23213)](#_Toc23213)

[5.2.1. 查询/设置网络注册状态 [- 15 -](#_Toc2075)](#_Toc2075)

[5.2.2. 查询信号质量 [- 16 -](#_Toc32637)](#_Toc32637)

[5.2.3. 配置APN [- 17 -](#_Toc16326)](#_Toc16326)

[5.2.4. 数据网络开关 [- 17 -](#_Toc23372)](#_Toc23372)

[5.2.5. 关闭数据网络 [- 18 -](#_Toc17546)](#_Toc17546)

[5.2.6. 同步服务器时间 [- 18 -](#_Toc8846)](#_Toc8846)

[5.2.7. 查询时间 [- 19 -](#_Toc5056)](#_Toc5056)

[5.2.8. 查询给定域名的IP地址 [- 19 -](#_Toc21792)](#_Toc21792)

[5.2.9. Ping目标地址 [- 20 -](#_Toc28172)](#_Toc28172)

[5.3. 功耗指令 [- 21 -](#_Toc30800)](#_Toc30800)

[5.3.1. 指令控制休眠设置 [- 21 -](#_Toc21980)](#_Toc21980)

[5.3.2. 硬件控制休眠设置 [- 21 -](#_Toc5601)](#_Toc5601)

[5.4. TCP/UDP相关指令 [- 22 -](#_Toc8901)](#_Toc8901)

[5.4.1. 配置TCP/UDP传输模式 [- 22 -](#_Toc20587)](#_Toc20587)

[5.4.2. 配置TCP/UDP心跳间隔 [- 22 -](#_Toc22776)](#_Toc22776)

[5.4.3. 建立TCP/UDP连接 [- 23 -](#_Toc8073)](#_Toc8073)

[5.4.4. TCP/UDP发送数据 [- 24 -](#_Toc11550)](#_Toc11550)

[5.4.5. 进入TCP/UDP透传模式 [- 25 -](#_Toc6836)](#_Toc6836)

[5.4.6. 退出TCP/UDP透传模式 [- 25 -](#_Toc8288)](#_Toc8288)

[5.4.7. 关闭TCP/UDP连接 [- 25 -](#_Toc12224)](#_Toc12224)

[5.5. MQTT相关命令 [- 26 -](#_Toc15720)](#_Toc15720)

[5.5.1. 配置MQTT客户端信息 [- 26 -](#_Toc19016)](#_Toc19016)

[5.5.2. 配置MQTT服务器信息 [- 26 -](#_Toc1684)](#_Toc1684)

[5.5.3. 连接MQTT服务器 [- 27 -](#_Toc23448)](#_Toc23448)

[5.5.4. 发布主题 [- 27 -](#_Toc26306)](#_Toc26306)

[5.5.5. 订阅主题 [- 28 -](#_Toc28376)](#_Toc28376)

[5.5.6. 取消订阅 [- 28 -](#_Toc16716)](#_Toc16716)

[5.5.7. 查询MQTT连接状态 [- 29 -](#_Toc4986)](#_Toc4986)

[5.5.8. 断开MQTT连接 [- 29 -](#_Toc25404)](#_Toc25404)

[5.5.9. 释放MQTT资源 [- 29 -](#_Toc30787)](#_Toc30787)

[5.6. HTTP相关指令 [- 29 -](#_Toc26298)](#_Toc26298)

[5.6.1. 开启HTTP服务 [- 29 -](#_Toc27753)](#_Toc27753)

[5.6.2. 关闭HTTP服务 [- 30 -](#_Toc22634)](#_Toc22634)

[5.6.3. 配置HTTP的URL信息 [- 30 -](#_Toc22543)](#_Toc22543)

[5.6.4. 发送HTTP请求 [- 30 -](#_Toc837)](#_Toc837)

[5.6.5. 设置请求头字段 [- 31 -](#_Toc27681)](#_Toc27681)

[5.6.6. 设置请求体数据 [- 31 -](#_Toc30528)](#_Toc30528)

[5.6.7. 提交请求体数据 [- 32 -](#_Toc13632)](#_Toc13632)

[5.6.8. HTTP错误码 [- 32 -](#_Toc3035)](#_Toc3035)

[5.7. GPS相关指令（模块名称带N的支持GNSS功能） [- 33 -](#_Toc2599)](#_Toc2599)

[5.7.1. GPS开关 [- 33 -](#_Toc11552)](#_Toc11552)

[5.7.2. 设置GPS模式 [- 33 -](#_Toc15882)](#_Toc15882)

[5.7.3. 设置NMEA数据输出 [- 34 -](#_Toc25467)](#_Toc25467)

[5.7.4. 查询定位信息 [- 34 -](#_Toc22922)](#_Toc22922)

[5.7.5. AGNSS辅助数据下载 [- 34 -](#_Toc14180)](#_Toc14180)

[5.7.6. AGNSS辅助数据应用 [- 35 -](#_Toc17460)](#_Toc17460)

[5.8. 错误码 [- 36 -](#_Toc14177)](#_Toc14177)

[6. 增值服务 [- 37 -](#增值服务)](#增值服务)

**图片索引**

[图 1 ：电脑端串口软件图 [- 6 -](#_Toc15038)](#_Toc15038)

[图 2 ：模块最小系统图 [- 7 -](#_Toc5152)](#_Toc5152)

# 引言

DX-CT511/DX-CT511N（模块名称带N的支持GNSS功能）是深圳大夏龙雀科技有限公司的一款4G模块，是为IoT行业研发的一款CAT1通信模组，采用LCC+LGA封装，尺寸为17.7mm×15.8mm×2.3mm。具备多种接口和丰富协议，多版本USB驱动，应用简单便捷。能很好满足客户对高性价比、低功耗的应用要求。该模组主要应用于POS、POC、共享经济、追踪器、IPC、智慧城市和智慧农业等场景。

1.  <span id="_Toc5020" class="anchor"></span>**串口基本参数**

- 模块串口默认参数：115200bps/8/n/1（波特率/数据位/无校验/停止位）

- 模块的三种模式：AT指令模式；数据传输模式；休眠模式

- 默认模式：AT指令模式

# PC端测试工具

1.  <span id="_Toc239" class="anchor"></span>**电脑端测试软件**

> 电脑端测试软件请在资料包中下载安装sscom5.13.1电脑串口软件进行测试，串口软件界面如下图：

<figure>
<img src="assets/media/image4.png" style="width:5.88472in;height:4.64583in" />
<figcaption><p><strong>图 1</strong><span id="_Toc15038" class="anchor"></span><strong>：电脑端串口软件图</strong></p></figcaption>
</figure>

# 串口使用

1.  <span id="_Toc25258" class="anchor"></span>**使用串口读写AT命令**

    1.  <span id="_Toc23463" class="anchor"></span>**模块测试最小系统**

<img src="assets/media/image5.png" style="width:5.73333in;height:4.27222in" alt="1711016646350" />

**图 2**<span id="_Toc5152" class="anchor"></span>**：模块最小系统图**

2.  <span id="_Toc9918" class="anchor"></span>**模块指令示例**

    1.  <span id="_Toc15382" class="anchor"></span>**TCP示例**

<!-- -->

1.  **TCP单连接**

<!-- -->

1.  配置APN：AT+QICSGP=1,1,"","",""

2.  开启移动网络：AT+NETOPEN

3.  建立连接会话：AT+CIPOPEN=1,"TCP","122.114.122.174",41017

4.  发送数据 (未指定长度)：AT+CIPSEND=1

    *注*：返回提示符 \> ，即可发送数据；数据发送完毕后需要以HEX格式发送1A作为结束符

5.  发送数据 (指定长度)：AT+CIPSEND=1,5

    *注*：返回提示符 \> ，即可发送数据；数据的长度需与\<length\>参数一致，不足则会等待数据输入

6.  关闭指定会话：AT+CIPCLOSE=1

<!-- -->

2.  **TCP多连接**

<!-- -->

1.  配置APN：AT+QICSGP=1,1,"","",""

2.  开启移动网络：AT+NETOPEN

3.  创建 会话0：AT+CIPOPEN=0,"TCP","122.114.122.174",41017

4.  创建 会话1：AT+CIPOPEN=1,"TCP","122.114.122.174",41017

5.  会话0发送数据 (未指定长度)：AT+CIPSEND=0

6.  会话1发送数据 (未指定长度)：AT+CIPSEND=1

    *注*：返回提示符 \> ，即可发送数据；数据发送完毕后需要以HEX格式发送1A作为结束符

7.  关闭 会话0：AT+CIPCLOSE=0

8.  关闭 会话1：AT+CIPCLOSE=1

<!-- -->

3.  **TCP透传**

<!-- -->

1.  配置APN：AT+QICSGP=1,1,"","",""

2.  设置为透传模式：AT+CIPMODE=1

3.  开启移动网络：AT+NETOPEN

4.  建立连接会话：AT+CIPOPEN=0,"TCP","122.114.122.174",41017

    *注*：1. 返回提示符 \> ，即可发送数据，该模式下可一直收发数据

<!-- -->

2.  退出透传模式：发送+++，该指令无结束符，即指令结尾无回车换行

3.  进入透传模式：ATO

<!-- -->

5.  关闭会话：AT+CIPCLOSE=0

    1.  <span id="_Toc2529" class="anchor"></span>**UDP示例**

<!-- -->

1.  **UDP单连接**

<!-- -->

1.  配置APN：AT+QICSGP=1,1,"","",""

2.  开启移动网络：AT+NETOPEN

3.  建立UDP连接会话：AT+CIPOPEN=1,"UDP",,

4.  发送数据 (指定长度)：AT+CIPSEND=1,5,"182.148.114.87",6600

    *注*：返回提示符 \> ，即可发送数据；数据的长度需与\<length\>参数一致，不足则会等待数据输入

5.  关闭指定会话：AT+CIPCLOSE=1

<!-- -->

2.  **UDP多连接**

<!-- -->

1.  配置APN：AT+QICSGP=1,1,"","",""

2.  开启移动网络：AT+NETOPEN

3.  建立UDP会话0：AT+CIPOPEN=0,"UDP",,

4.  会话0发送数据 (指定长度)：AT+CIPSEND=0,5,"182.148.114.87",6600

    *注*：返回提示符 \> ，即可发送数据；数据的长度需与\<length\>参数一致，不足则会等待数据输入

5.  建立UDP会话1：AT+CIPOPEN=1,"UDP",,

6.  会话1发送数据 (指定长度)：AT+CIPSEND=1,5,"182.148.114.87",6600

    *注*：返回提示符 \> ，即可发送数据；数据的长度需与\<length\>参数一致，不足则会等待数据输入

7.  关闭 会话0：AT+CIPCLOSE=0

8.  关闭 会话1：AT+CIPCLOSE=1

<!-- -->

3.  **UDP透传**

<!-- -->

1.  配置APN：AT+QICSGP=1,1,"","",""

2.  设置为透传模式：AT+CIPMODE=1

3.  开启移动网络：AT+NETOPEN

4.  建立连接会话：AT+CIPOPEN=0,"UDP","122.114.122.174",41017

    *注*：1. 返回提示符 \> ，即可发送数据，该模式下可一直收发数据

<!-- -->

2.  退出透传模式：发送+++，该指令无结束符，即指令结尾无回车换行

3.  进入透传模式：ATO

<!-- -->

5.  关闭会话：AT+CIPCLOSE=0

    1.  <span id="_Toc24826" class="anchor"></span>**MQTT示例**

<!-- -->

1.  配置APN：AT+QICSGP=1,1,"","",""

2.  开启移动网络：AT+NETOPEN

3.  配置MQTT客户端信息：AT+MCONFIG="4G_TEST"

    *注*：如需配置用户名和密码等参数，可参考该手册5.5.1指令部分

4.  配置MQTT服务器信息：AT+MIPSTART="broker.emqx.io",1883

5.  连接MQTT服务器：AT+MCONNECT=1,60

6.  订阅主题：AT+MSUB="phone",0

7.  发布消息 ：AT+MPUB="4G",0,0,"hello world"

8.  发布长消息：AT+MPUBEX="4G",0,0,20

    *注*：1. 返回提示符 \> ，即可发送数据，发送成功后自动退出数据传输模式

<!-- -->

2.  发送的数据长度需要与\<msgLen\>参数一致，长度不足则会等待输入

    3\. 超过10秒未成功发送，则自动退出数据传输模式，返回ERROR

<!-- -->

9.  取消订阅：AT+MUNSUB="phone"

10. 断开MQTT连接：AT+MDISCONNECT

11. 释放MQTT资源：AT+MIPCLOSE

    1.  <span id="_Toc7280" class="anchor"></span>**HTTP示例**

<!-- -->

1.  **GET请求**

<!-- -->

1.  配置APN：AT+QICSGP=1,1,"","",""

2.  开启HTTP服务：AT\$HTTPOPEN

3.  配置URL信息：AT\$HTTPPARA=http://httpbin.org/get,80

4.  发送HTTP请求：AT\$HTTPACTION=0

5.  关闭HTTP服务：AT\$HTTPCLOSE

<!-- -->

2.  **POST请求 (小数据)**

<!-- -->

1.  配置APN：AT+QICSGP=1,1,"","",""

2.  开启HTTP服务：AT\$HTTPOPEN

3.  配置URL信息：AT\$HTTPPARA=http://httpbin.org/post,80

4.  设置请求头字段：AT\$HTTPRQH=Content-Length,10

5.  设置请求体数据：AT\$HTTPDATAEX=10,"ABCDE12345"

6.  发送HTTP请求：AT\$HTTPACTION=3

7.  关闭HTTP服务：AT\$HTTPCLOSE

<!-- -->

3.  **POST请求 (大数据)**

<!-- -->

1.  配置APN：AT+QICSGP=1,1,"","",""

2.  开启HTTP服务：AT\$HTTPOPEN

3.  配置URL信息：AT\$HTTPPARA=http://httpbin.org/post,80

4.  设置请求头字段：AT\$HTTPRQH=Content-Length,10

    设置请求头字段：AT\$HTTPRQH=Connection,keep-alive

5.  发送HTTP请求：AT\$HTTPACTION=1

6.  设置请求体数据：(1) 设置数据长度：AT\$HTTPDATA=5

    \(2\) 数据输入：ABCDE

    \(3\) 提交数据：AT\$HTTPSEND

    设置请求体数据：(1) 设置数据长度：AT\$HTTPDATA=5

    \(2\) 数据输入：12345

    \(3\) 提交数据：AT\$HTTPSEND

    *注*：请求体数据长度之和，需要与请求体字段Content-Length设置的一致

7.  结束请求体数据提交：(1) 设置数据长度：AT\$HTTPDATA=0

    \(2\) 提交数据：AT\$HTTPSEND

<!-- -->

8.  关闭HTTP服务：AT\$HTTPCLOSE

    1.  <span id="_Toc24895" class="anchor"></span>**GNSS示例**

<!-- -->

1.  打开GPS：AT+MGPSC=1

2.  等待一分钟，搜索定位

3.  查询定位信息：AT+GPSST

4.  返回：+GPSST: 1, 1, 113.83, 23.33, 22.61; 0, 119; 0, 77; 0, 76; 0, 37; 0, 72; 0, 71;

    OK

5.  关闭GPS：AT+MGPSC=0

# 相关AT命令详解

1.   <span id="_Toc7294" class="anchor"></span>**命令格式说明**

**AT+Command=\<param1，param2，param3\>\[,\<param\>\] \<CR\>\<LF\>**

- 所有的指令以AT开头，\<CR\>\<LF\>结束，在本文档中表现命令和响应的表格中，省略了 \<CR\>\<LF\>，仅显示命令和响应。

- 所有AT命令字符都为大写。

- \<\>内为可选内容，如果命令中有多个参数，以逗号“，”隔开，实际命令中不包含尖括号。

- \<CR\>为回车字符\r，十六进制为0X0D。

- \<LF\>为换行字符\n，十六进制为0X0A。

- 指令执行成功，返回相应命令以OK结束，失败返回ERROR或者+CME ERROR:\<err\>，“\<err\>”内容为对应错误码（错误码请参考5.10）。

- \[,\<param\>\]，中括号\[\]为可选参数，可根据需求选择发送。

  1.  <span id="_Toc27749" class="anchor"></span>**回应格式说明**

**+Indication:\<param1，param2，param3\>\<CR\>\<LF\>**

- 回应指令以加号“+”开头，\<CR\>\<LF\>结束

- “ : ”后面为回应参数

- 如果回应参数中有多个参数，会以逗号“，”隔开

  1.  <span id="_Toc10097" class="anchor"></span>**AT****命令一览表**

**备注：以下AT命令为最简版，具体格式及说明请参考5.AT命令详解。**

<table style="width:99%;">
<colgroup>
<col style="width: 21%" />
<col style="width: 33%" />
<col style="width: 44%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td style="text-align: center;">AT</td>
<td style="text-align: center;">测试指令</td>
<td style="text-align: center;">用于测试串口</td>
</tr>
<tr>
<td style="text-align: center;">ATE&lt;mode&gt;</td>
<td style="text-align: center;">设置指令回显</td>
<td style="text-align: center;">默认：1，开启指令回显</td>
</tr>
<tr>
<td style="text-align: center;">ATI</td>
<td style="text-align: center;">查询模块信息</td>
<td style="text-align: center;">制造商，模块型号，版本信息，国际移动设备识别码</td>
</tr>
<tr>
<td style="text-align: center;">AT+IPR</td>
<td style="text-align: center;">查询/设置波特率</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT+ICCID</td>
<td style="text-align: center;">查询ICCID</td>
<td style="text-align: center;">用于查询SIM卡是否处于正常工作状态，返回ICCID值则正常</td>
</tr>
<tr>
<td style="text-align: center;">AT+RESET</td>
<td style="text-align: center;">重启模块</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT+CEREG</td>
<td style="text-align: center;">查询注册状态</td>
<td style="text-align: center;">查询是否可以上网</td>
</tr>
<tr>
<td style="text-align: center;">AT+CSQ</td>
<td style="text-align: center;">查询信号质量</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT+QICSGP</td>
<td style="text-align: center;">查询/配置APN</td>
<td style="text-align: center;">不同的厂家的物联卡会有不同的访问点名称。</td>
</tr>
<tr>
<td style="text-align: center;">AT+NETOPEN</td>
<td style="text-align: center;">查询/开启数据网络</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT+NETCLOSE</td>
<td style="text-align: center;">关闭数据网络</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT+QNTP</td>
<td style="text-align: center;">查询/设置NTP服务器</td>
<td style="text-align: center;">用于同步服务器时间</td>
</tr>
<tr>
<td style="text-align: center;">AT+CCLK</td>
<td style="text-align: center;">查询时间</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT+MDNSGIP</td>
<td style="text-align: center;">查询给定域名的IP地址</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT+MPING</td>
<td style="text-align: center;">Ping目标地址</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT+SYSSLEEP</td>
<td style="text-align: center;">指令控制休眠设置</td>
<td style="text-align: center;">该指令可用于降低功耗；DX-CT511N模块GPS开启后该指令无效。</td>
</tr>
<tr>
<td style="text-align: center;">AT+CSCLK</td>
<td style="text-align: center;">硬件控制休眠设置</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT+CIPMODE</td>
<td style="text-align: center;">查询/设置TCP/UDP传输模式</td>
<td style="text-align: center;"><p>需要建立连接前使用该指令</p>
<p>默认：0，AT指令</p></td>
</tr>
<tr>
<td style="text-align: center;">AT+MCIPCFG</td>
<td style="text-align: center;">查询/设置TCP/UDP心跳间隔</td>
<td style="text-align: center;"><p>使用该指令前，需要断开所有通信连接</p>
<p>默认：0秒</p></td>
</tr>
<tr>
<td style="text-align: center;">AT+CIPOPEN</td>
<td style="text-align: center;">查询/建立连接</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT+CIPSEND</td>
<td style="text-align: center;">TCP/UDP发送数据</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">ATO</td>
<td style="text-align: center;">进入TCP/UDP透传模式</td>
<td style="text-align: center;">该指令只能在数据传输模式下，即AT+CIPMODE=1时才可以使用。</td>
</tr>
<tr>
<td style="text-align: center;">+++</td>
<td style="text-align: center;">退出TCP/UDP透传模式</td>
<td style="text-align: center;">该指令只能在数据传输模式下，即AT+CIPMODE=1时才可以使用；该指令结尾无结束符，即指令结尾无回车换行。</td>
</tr>
<tr>
<td style="text-align: center;">AT+CIPCLOSE</td>
<td style="text-align: center;">查询/关闭连接</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT+MCONFIG</td>
<td style="text-align: center;">查询/配置MQTT客户端信息</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT+MIPSTART</td>
<td style="text-align: center;">查询/配置MQTT服务器信息</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT+MCONNECT</td>
<td style="text-align: center;">查询/连接MQTT服务器</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT+MPUB</td>
<td style="text-align: center;">发布消息</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT+MPUBEX</td>
<td style="text-align: center;">发布长消息</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT+MSUB</td>
<td style="text-align: center;">查询/订阅主题</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT+MUNSUB</td>
<td style="text-align: center;">取消订阅</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT+MQTTSTATU</td>
<td style="text-align: center;">查询MQTT连接状态</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT+MDISCONNECT</td>
<td style="text-align: center;">断开MQTT连接</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT+MIPCLOSE</td>
<td style="text-align: center;">释放MQTT资源</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT$HTTPOPEN</td>
<td style="text-align: center;">查询/开启HTTP服务</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT$HTTPCLOSE</td>
<td style="text-align: center;">查询/关闭HTTP服务</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT$HTTPPARA</td>
<td style="text-align: center;">查询/配置HTTP的URL信息</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT$HTTPACTION</td>
<td style="text-align: center;">发送HTTP请求</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT$HTTPRQH</td>
<td style="text-align: center;">查询/设置请求头字段</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT$HTTPDATAEX</td>
<td style="text-align: center;">设置请求体数据</td>
<td style="text-align: center;">适用于AT$HTTPACTION=3的情况</td>
</tr>
<tr>
<td style="text-align: center;">AT$HTTPDATA</td>
<td style="text-align: center;">设置请求体数据</td>
<td style="text-align: center;">适用于AT$HTTPACTION=1的情况</td>
</tr>
<tr>
<td style="text-align: center;">AT$HTTPSEND</td>
<td style="text-align: center;">提交请求体数据</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT+MGPSC</td>
<td style="text-align: center;">查询/设置GPS开关</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT+GPSMODE</td>
<td style="text-align: center;">查询/设置GPS模式</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT+MGPSGET</td>
<td style="text-align: center;">设置NMEA数据输出</td>
<td style="text-align: center;">关闭输出：0，开启输出：1</td>
</tr>
<tr>
<td style="text-align: center;">AT+GPSST</td>
<td style="text-align: center;">查询定位信息</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT+AGNSSGET</td>
<td style="text-align: center;">AGNSS辅助数据下载</td>
<td style="text-align: center;">-</td>
</tr>
<tr>
<td style="text-align: center;">AT+AGNSSSET</td>
<td style="text-align: center;">AGNSS辅助数据应用</td>
<td style="text-align: center;">-</td>
</tr>
</tbody>
</table>

# AT命令详解

1.  <span id="_Toc19371" class="anchor"></span>**基础指令**

    1.  <span id="_Toc32020" class="anchor"></span>**测试指令**

|          |          |          |          |
|:--------:|:--------:|:--------:|:--------:|
| **功能** | **指令** | **响应** | **说明** |
| 测试指令 |    AT    |    OK    |          |

2.  <span id="_Toc9061" class="anchor"></span>**设置指令回显**

<table style="width:100%;">
<colgroup>
<col style="width: 17%" />
<col style="width: 21%" />
<col style="width: 17%" />
<col style="width: 42%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td style="text-align: center;">设置指令回显</td>
<td style="text-align: center;">ATE&lt;mode&gt;</td>
<td style="text-align: center;">OK</td>
<td style="text-align: center;"><p>&lt;mode&gt;：</p>
<p>0：关闭指令回显</p>
<p>1：开启指令回显</p>
<p>默认：1</p></td>
</tr>
</tbody>
</table>

**备注：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: left;"><p>1. 开启回显：先返回输入的指令，再输出响应</p>
<p>2. 关闭回显：模块直接输出响应</p></td>
</tr>
</tbody>
</table>

3.  <span id="_Toc12948" class="anchor"></span>**查询模块信息**

<table style="width:100%;">
<colgroup>
<col style="width: 19%" />
<col style="width: 19%" />
<col style="width: 25%" />
<col style="width: 35%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td style="text-align: center;">查询模块信息</td>
<td style="text-align: center;">ATI</td>
<td style="text-align: center;"><p>Manufacturer:&lt;mfr&gt;</p>
<p>Model:&lt;model&gt;</p>
<p>Revision:&lt;revision&gt;</p>
<p>IMEI: &lt;IMEI&gt;</p>
<p>OK</p></td>
<td style="text-align: center;"><p>&lt;mfr&gt;：制造商</p>
<p>&lt;model&gt;：模块型号</p>
<p>&lt;revision&gt;：版本信息</p>
<p>&lt;IMEI&gt;：国际移动设备识别码</p></td>
</tr>
</tbody>
</table>

**举例：**

<table style="width:100%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: left;"><p>发送：ATI</p>
<p>返回：ATI</p>
<p>Manufacturer:"LYNQ"</p>
<p>Model:"LYNQ_L511C_2C"</p>
<p>Revision:L511C_2Cv02.01b03.00</p>
<p>IMEI: 865357063779217</p>
<p>OK</p></td>
</tr>
</tbody>
</table>

4.  <span id="_Toc3198" class="anchor"></span>**查询/设置串口波特率**

<table style="width:100%;">
<colgroup>
<col style="width: 17%" />
<col style="width: 23%" />
<col style="width: 22%" />
<col style="width: 35%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td style="text-align: center;">查询波特率</td>
<td style="text-align: center;">AT+IPR?</td>
<td style="text-align: center;"><p>+IPR: &lt;baud&gt;</p>
<p>OK</p></td>
<td rowspan="2" style="text-align: center;"><p>&lt;baud&gt;：波特率</p>
<p>范围：300,1200,2400,4800,</p>
<p>9600,14400,19200,28800,</p>
<p>38400,56000,57600,115200,</p>
<p>128000,230400,460800,921600</p>
<p>默认：115200</p></td>
</tr>
<tr>
<td style="text-align: center;">设置波特率</td>
<td style="text-align: center;">AT+IPR=&lt;baud&gt;</td>
<td style="text-align: center;">OK</td>
</tr>
</tbody>
</table>

**备注：**

|                                    |
|:-----------------------------------|
| 设置指令立即生效，且该指令断电保存 |

**举例：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: left;"><p>发送：AT+IPR=115200</p>
<p>返回：AT+IPR=115200</p>
<p>OK</p></td>
</tr>
</tbody>
</table>

5.  <span id="_Toc32470" class="anchor"></span>**查询SIM卡ICCID**

<table style="width:100%;">
<colgroup>
<col style="width: 17%" />
<col style="width: 22%" />
<col style="width: 26%" />
<col style="width: 34%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td style="text-align: center;">查询ICCID</td>
<td style="text-align: center;">AT+ICCID</td>
<td style="text-align: center;"><p>+ICCID: &lt;iccid&gt;</p>
<p>OK</p></td>
<td style="text-align: center;">&lt;iccid&gt;：ICCID</td>
</tr>
</tbody>
</table>

**备注：**

|  |
|:---|
| 此指令用于读取SIM卡的ICCID。如返回+CME ERROR: 10，则说明模块未识别到SIM卡 |

**举例：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: left;"><p>发送：AT+ICCID</p>
<p>返回：AT+ICCID</p>
<p>+ICCID:89860435192290069851</p>
<p>OK</p></td>
</tr>
</tbody>
</table>

6.  <span id="_Toc2556" class="anchor"></span>**重启模块**

|          |          |          |          |
|:--------:|:--------:|:--------:|:--------:|
| **功能** | **指令** | **响应** | **说明** |
| 重启模块 | AT+RESET |    OK    |          |

2.  <span id="_Toc23213" class="anchor"></span>**网络服务指令**

    1.  <span id="_Toc2075" class="anchor"></span>**查询/设置网络注册状态**

<table style="width:100%;">
<colgroup>
<col style="width: 15%" />
<col style="width: 18%" />
<col style="width: 24%" />
<col style="width: 41%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td style="text-align: center;">查询注册状态</td>
<td style="text-align: center;">AT+CEREG?</td>
<td style="text-align: center;"><p>+CEREG: &lt;n&gt;,&lt;stat&gt;[,&lt;other&gt;]</p>
<p>OK</p></td>
<td style="text-align: center;"><p>&lt;n&gt;：主动通知类型</p>
<p>0：禁用网络注册通知</p>
<p>1~5：启用网络注册通知</p></td>
</tr>
<tr>
<td style="text-align: center;">设置通知类型</td>
<td style="text-align: center;">AT+CEREG=&lt;n&gt;</td>
<td style="text-align: center;">OK</td>
<td style="text-align: center;"><p>&lt;stat&gt;：注册状态</p>
<p>0：未注册, 不尝试搜索新运营商注册</p>
<p>1：已注册，本地网络</p>
<p>2：未注册, 尝试搜索新运营商注册</p>
<p>3：注册被拒绝</p>
<p>4：未知状态</p>
<p>5：已注册，漫游中</p></td>
</tr>
</tbody>
</table>

**备注：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td><ol type="1">
<li><p>&lt;n&gt;=0时，关闭主动通知，手动查询时，注册状态返回 +CREG:&lt;n&gt;,&lt;stat&gt;</p></li>
<li><p>&lt;n&gt;=1~5时，开启主动通知，手动查询时，注册状态返回 +CREG:&lt;n&gt;,&lt;stat&gt;[,&lt;other&gt;]</p></li>
<li><p>&lt;other&gt;，该参数 根据 主动通知类型&lt;n&gt; 变化</p></li>
<li><p>&lt;stat&gt;=1或5时，模块可正常接入网络</p></li>
</ol></td>
</tr>
</tbody>
</table>

**举例：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: left;"><p>查询是否可以上网</p>
<p>发送：AT+CEREG?</p>
<p>返回：AT+CEREG?</p>
<p>返回：+CEREG=0,0（未连接网络）</p>
<p>返回：+CEREG=0,1（已连接网络）</p></td>
</tr>
</tbody>
</table>

1.  <span id="_Toc32637" class="anchor"></span>**查询信号质量**

<table style="width:100%;">
<colgroup>
<col style="width: 17%" />
<col style="width: 17%" />
<col style="width: 30%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td rowspan="2" style="text-align: center;">查询</td>
<td rowspan="2" style="text-align: center;">AT+CSQ</td>
<td rowspan="2" style="text-align: center;"><p>+CSQ: &lt;rssi&gt;,&lt;ber&gt;</p>
<p>OK</p></td>
<td style="text-align: center;"><p>&lt;rssi&gt;：信号强度</p>
<p>0：&lt;= (-113) dBm</p>
<p>1：(-111) dBm</p>
<p>2~30： (-109)~(-53) dBm</p>
<p>31：&gt;= (-51) dBm</p>
<p>99：未知或无信号</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;ber&gt;：信道误码率</p>
<p>0~7：RXQUAL值</p>
<p>99：未知或无检测到误码率</p></td>
</tr>
</tbody>
</table>

**举例：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: left;"><p>查询当前信号值</p>
<p>发送：AT+CSQ</p>
<p>返回：AT+CSQ</p>
<p>+CSQ: 15,99</p>
<p>OK</p></td>
</tr>
</tbody>
</table>

<span id="_Toc16326" class="anchor"></span>

2.  **配置APN**

<table style="width:100%;">
<colgroup>
<col style="width: 11%" />
<col style="width: 23%" />
<col style="width: 28%" />
<col style="width: 36%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td rowspan="3" style="text-align: center;">查询APN</td>
<td rowspan="3" style="text-align: center;">AT+QICSGP=1</td>
<td rowspan="3" style="text-align: center;"><p>+QICSGP:</p>
<p>&lt;contextType&gt;,&lt;APN&gt;,</p>
<p>&lt;username&gt;,&lt;password&gt;,</p>
<p>&lt;authentication&gt;</p>
<p>OK</p></td>
<td style="text-align: center;"><p>&lt;cid&gt;: 连接标识符</p>
<p>范围：1-3</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;contextType&gt;: 连接类型</p>
<p>1：IPV4</p>
<p>2：IPV4 &amp; IPV6</p>
<p>3：IPV6</p></td>
</tr>
<tr>
<td style="text-align: center;">&lt;APN&gt;: 访问点名称</td>
</tr>
<tr>
<td rowspan="2" style="text-align: center;">配置APN</td>
<td rowspan="2" style="text-align: center;"><p>AT+QICSGP=</p>
<p>&lt;cid&gt;,&lt;contextType&gt;,</p>
<p>&lt;APN&gt;,&lt;username&gt;,</p>
<p>&lt; password&gt;</p></td>
<td rowspan="2" style="text-align: center;">OK</td>
<td style="text-align: center;"><p>&lt;username&gt;: 用户名</p>
<p>&lt;password&gt;: 密码</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;authentication&gt;：网络认证</p>
<p>0：None</p>
<p>1：PAP</p>
<p>2：CHAP</p></td>
</tr>
</tbody>
</table>

**备注：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: left;"><p>&lt;APN&gt;: 用于访问不同网络服务，由SIM卡的运营商提供</p>
<p>配置APN 此步骤国内使用略过，如有需要请按照下方“举例”操作</p></td>
</tr>
</tbody>
</table>

**举例：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: left;"><p>配置中国移动的APN</p>
<p>发送：AT+QICSGP=1,1,"CMIOT","",""</p>
<p>返回：AT+QICSGP=1,1,"CMIOT","",""</p>
<p>OK</p></td>
</tr>
</tbody>
</table>

3.  <span id="_Toc23372" class="anchor"></span>**数据网络开关**

<table style="width:100%;">
<colgroup>
<col style="width: 15%" />
<col style="width: 23%" />
<col style="width: 26%" />
<col style="width: 34%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td style="text-align: center;">查询</td>
<td style="text-align: center;">AT+NETOPEN?</td>
<td style="text-align: center;"><p>+ NETOPEN:&lt;net_state&gt;</p>
<p>OK</p></td>
<td style="text-align: center;"><p>&lt;net_state&gt;：网络状态</p>
<p>0：关闭</p>
<p>1：打开</p></td>
</tr>
<tr>
<td style="text-align: center;">开启数据网络</td>
<td style="text-align: center;">AT+NETOPEN</td>
<td style="text-align: center;"><p>OK</p>
<p>+NETOPEN:&lt;err&gt;</p></td>
<td style="text-align: center;"><p>&lt;err&gt;：结果</p>
<p>SUCCESS：成功</p>
<p>ONGOING：正在开启</p>
<p>FAIL：失败</p>
<p>Error: 902：已激活</p></td>
</tr>
</tbody>
</table>

**举例：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: left;"><p>发送：AT+NETOPEN</p>
<p>返回：AT+NETOPEN</p>
<p>OK</p>
<p>+NETOPEN:SUCCESS</p></td>
</tr>
</tbody>
</table>

4.  <span id="_Toc17546" class="anchor"></span>**关闭数据网络**

<table style="width:100%;">
<colgroup>
<col style="width: 17%" />
<col style="width: 22%" />
<col style="width: 28%" />
<col style="width: 30%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td style="text-align: center;">关闭数据网络</td>
<td style="text-align: center;">AT+NETCLOSE</td>
<td style="text-align: center;"><p>OK</p>
<p>+NETCLOSE:&lt;err&gt;</p></td>
<td style="text-align: center;"><p>&lt;err&gt;：结果</p>
<p>SUCCESS：成功</p>
<p>ONGOING：正在关闭</p>
<p>FAIL：失败</p></td>
</tr>
</tbody>
</table>

**举例：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: left;"><p>发送：AT+NETCLOSE</p>
<p>返回：AT+NETCLOSE</p>
<p>OK</p>
<p>+NETCLOSE:SUCCESS</p></td>
</tr>
</tbody>
</table>

5.  <span id="_Toc8846" class="anchor"></span>**同步服务器时间**

<table style="width:100%;">
<colgroup>
<col style="width: 17%" />
<col style="width: 27%" />
<col style="width: 25%" />
<col style="width: 28%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td rowspan="2" style="text-align: center;">查询NTP服务器</td>
<td rowspan="2" style="text-align: center;">AT+QNTP?</td>
<td rowspan="2" style="text-align: center;"><p>+QNTP:</p>
<p>&lt;serverAddr&gt;,&lt;port&gt;</p>
<p>OK</p></td>
<td style="text-align: center;"><p>&lt;cid&gt;：连接标识符</p>
<p>范围：1-15</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;serverAddr&gt;：</p>
<p>NTP服务器的IP或域名</p></td>
</tr>
<tr>
<td rowspan="2" style="text-align: center;">同步服务器时间</td>
<td rowspan="2" style="text-align: center;"><p>AT+QNTP=</p>
<p>&lt;cid&gt;,&lt;serverAddr&gt;,</p>
<p>&lt;port&gt;,1</p></td>
<td rowspan="2" style="text-align: center;"><p>OK</p>
<p>+QNTP：0,&lt;time&gt;</p></td>
<td style="text-align: center;"><p>&lt;port&gt;：NTP服务器端口</p>
<p>范围：1-65535</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;time&gt;：时间</p>
<p>yy/MM/dd,hh:mm:ss+32</p></td>
</tr>
</tbody>
</table>

**备注：**

|                                |
|--------------------------------|
| 该指令需要在开启数据网络后使用 |

**举例：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: left;"><p>发送：AT+QNTP=1,"tms.dynamicode.com.cn",123,1</p>
<p>返回：AT+QNTP=1,"tms.dynamicode.com.cn",123,1</p>
<p>OK</p>
<p>+QNTP：0,"24/04/07,14:25:51+32"</p></td>
</tr>
</tbody>
</table>

6.  <span id="_Toc5056" class="anchor"></span>**查询时间**

<table style="width:100%;">
<colgroup>
<col style="width: 17%" />
<col style="width: 22%" />
<col style="width: 22%" />
<col style="width: 37%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td style="text-align: center;">查询时间</td>
<td style="text-align: center;">AT+CCLK?</td>
<td style="text-align: center;"><p>+CCLK: &lt;time&gt;</p>
<p>OK</p></td>
<td style="text-align: center;"><p>&lt;time&gt;：时间</p>
<p>yy/MM/dd,hh:mm:ss+32</p></td>
</tr>
</tbody>
</table>

**备注：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td><ol type="1">
<li><p>该指令查询的时间默认为UTC时间，对应时区是0时区</p></li>
<li><p>AT+QNTP同步服务器时间后，该指令查询的时间为服务器提供的时间</p></li>
</ol></td>
</tr>
</tbody>
</table>

**举例：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: left;"><p>发送：AT+CCLK?</p>
<p>返回：AT+CCLK?</p>
<p>+CCLK:"24/04/07,06:25:51+32"</p>
<p>OK</p></td>
</tr>
</tbody>
</table>

1.  <span id="_Toc21792" class="anchor"></span>**查询给定域名的IP地址**

<table style="width:100%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 25%" />
<col style="width: 33%" />
<col style="width: 26%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td rowspan="2" style="text-align: center;">查询</td>
<td rowspan="2" style="text-align: center;"><p>AT+MDNSGIP=</p>
<p>&lt;domain name&gt;</p></td>
<td rowspan="2" style="text-align: center;"><p>+MDNSGIP:</p>
<p>&lt;domain name&gt;,&lt;IP address&gt;</p>
<p>OK</p></td>
<td style="text-align: center;">&lt;domain name&gt;：域名</td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;IP address&gt;：</p>
<p>域名对应的IP</p></td>
</tr>
</tbody>
</table>

**举例：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: left;"><p>发送：AT+MDNSGIP=test.ranye-iot.net</p>
<p>返回：AT+MDNSGIP=test.ranye-iot.net</p>
<p>+MDNSGIP:test.ranye-iot.net,47.92.129.18</p>
<p>OK</p></td>
</tr>
</tbody>
</table>

2.  <span id="_Toc28172" class="anchor"></span>**Ping目标地址**

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 23%" />
<col style="width: 25%" />
<col style="width: 35%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td rowspan="9" style="text-align: center;">Ping目标地址</td>
<td rowspan="9" style="text-align: center;"><p>AT+MPING=</p>
<p>&lt;addr&gt;,</p>
<p>&lt;addr_type&gt;</p>
<p>[,&lt;num_pings&gt;,</p>
<p>&lt;packet_size&gt;,</p>
<p>&lt;wait_time&gt;]</p></td>
<td rowspan="2" style="text-align: center;"><p>&lt;result_type&gt;=1时：</p>
<p>+MPING:</p>
<p>&lt;result_type&gt;,</p>
<p>&lt;ip_addr&gt;,</p>
<p>&lt;packet_size&gt;,</p>
<p>&lt;rtt&gt;,&lt;TTL&gt;</p></td>
<td style="text-align: center;"><p>&lt;addr&gt;：目标域名/IP</p>
<p>&lt;addr_type&gt;：地址类型</p>
<p>1：IPv4</p>
<p>2：IPv6 (保留)</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;num_pings&gt;：ping请求次数</p>
<p>范围：1 - 100（默认: 4）</p></td>
</tr>
<tr>
<td rowspan="2" style="text-align: center;"><p>&lt;result_type&gt;=2时：</p>
<p>+MPING:</p>
<p>&lt;result_type&gt;</p></td>
<td style="text-align: center;"><p>&lt;packet_size&gt;：ping数据包长度</p>
<p>范围：32 - 256字节 (默认: 32)</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;wait_time&gt;：响应等待时间</p>
<p>范围：1 - 255 秒 (默认: 3)</p></td>
</tr>
<tr>
<td rowspan="5" style="text-align: center;"><p>&lt;result_type&gt;=3时：</p>
<p>+MPING:</p>
<p>&lt;result_type&gt;,</p>
<p>&lt;pkts_sent&gt;,</p>
<p>&lt;pkts_recvd&gt;,</p>
<p>&lt;pkts_lost&gt;,</p>
<p>&lt;min_rtt&gt;,&lt;max_rtt&gt;,</p>
<p>&lt;avg_rtt&gt;</p></td>
<td style="text-align: center;"><p>&lt;result_type&gt;：结果</p>
<p>1：ping成功</p>
<p>2：ping超时</p>
<p>3：ping结果</p></td>
</tr>
<tr>
<td style="text-align: center;">&lt;ip_addr&gt;：解析的IP地址</td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;pkts_sent&gt;：ping请求次数</p>
<p>&lt;pkts_recvd&gt;：ping响应次数</p>
<p>&lt;pkts_lost&gt;：未响应ping请求次数</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;rtt&gt;：RTT</p>
<p>&lt;min_rtt&gt;：最小RTT</p>
<p>&lt;max_rtt&gt;：最大RTT</p>
<p>&lt;avg_rtt&gt;：平均RTT</p></td>
</tr>
<tr>
<td style="text-align: center;">&lt;TTL&gt;：TTL</td>
</tr>
</tbody>
</table>

**举例：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: left;"><p>发送：AT+MPING=test.ranye-iot.net,1</p>
<p>返回：AT+MPING=test.ranye-iot.net,1</p>
<p>+MPING:1,47.92.129.18,32,210,51</p>
<p>+MPING:1,47.92.129.18,32,100,51</p>
<p>+MPING:1,47.92.129.18,32,90,51</p>
<p>+MPING:1,47.92.129.18,32,90,51</p>
<p>+MPING:3,4,4,0,90,210,122</p>
<p>OK</p></td>
</tr>
</tbody>
</table>

1.  <span id="_Toc30800" class="anchor"></span>**功耗指令**

    1.  <span id="_Toc21980" class="anchor"></span>**指令控制休眠设置**

<table style="width:100%;">
<colgroup>
<col style="width: 17%" />
<col style="width: 23%" />
<col style="width: 28%" />
<col style="width: 30%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td style="text-align: center;">查询</td>
<td style="text-align: center;">AT+SYSSLEEP?</td>
<td style="text-align: center;"><p>+SYSSLEEP:&lt;n&gt;</p>
<p>OK</p></td>
<td rowspan="2" style="text-align: center;"><p>&lt;n&gt;：模式</p>
<p>0：不休眠</p>
<p>1：休眠</p>
<p>默认：0</p></td>
</tr>
<tr>
<td style="text-align: center;">设置</td>
<td style="text-align: center;">AT+SYSSLEEP=&lt;n&gt;</td>
<td style="text-align: center;">OK</td>
</tr>
</tbody>
</table>

**备注：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td><ol type="1">
<li><p>该指令可用于降低功耗</p></li>
<li><p>待机时，进入休眠模式，串口使用时会唤醒模块，串口使用结束后，重新进入休眠模式</p></li>
</ol></td>
</tr>
</tbody>
</table>

**举例：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: left;"><p>发送：AT+SYSSLEEP=0</p>
<p>返回：AT+SYSSLEEP=0</p>
<p>OK</p></td>
</tr>
</tbody>
</table>

1.  <span id="_Toc5601" class="anchor"></span>**硬件控制休眠设置**

<table>
<colgroup>
<col style="width: 17%" />
<col style="width: 20%" />
<col style="width: 27%" />
<col style="width: 34%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td style="text-align: center;">查询</td>
<td style="text-align: center;">AT+CSCLK?</td>
<td style="text-align: center;"><p>+CSCLK:&lt;n&gt;</p>
<p>OK</p></td>
<td rowspan="2" style="text-align: center;"><p>&lt;n&gt;：模式</p>
<p>0：禁用DTR控制</p>
<p>1：启用DTR控制</p></td>
</tr>
<tr>
<td style="text-align: center;">设置</td>
<td style="text-align: center;">AT+CSCLK=&lt;n&gt;</td>
<td style="text-align: center;">OK</td>
</tr>
</tbody>
</table>

**备注：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td><ol type="1">
<li><p>&lt;n&gt;=0，模块不会进入休眠模式</p></li>
<li><p>&lt;n&gt;=1，DTR为高电平时，模块进入休眠模式；DTR为低电平时，模块退出休眠模式</p></li>
<li><p>启用DTR控制，网络状态灯会常亮，如需取消常亮模式，可通过AT+NETOPEN或AT+NETCLOSE控制</p></li>
<li><p>禁用DTR控制，需要先发送AT+SYSSLEEP=0，再发送AT+CSCLK=0</p></li>
<li><p>我司的底板，DTR脚默认高电平，初次进入休眠模式，需要先将DTR脚的电平拉低再拉高</p></li>
<li><p>待机时，进入休眠模式，串口使用时会唤醒模块，串口使用结束后，重新进入休眠模式</p></li>
</ol></td>
</tr>
</tbody>
</table>

**举例：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: left;"><p>发送：AT+CSCLK=0</p>
<p>返回：AT+CSCLK=0</p>
<p>OK</p></td>
</tr>
</tbody>
</table>

1.  <span id="_Toc8901" class="anchor"></span>**TCP/UDP相关指令**

    1.  <span id="_Toc20587" class="anchor"></span>**配置TCP/UDP传输模式**

<table style="width:100%;">
<colgroup>
<col style="width: 22%" />
<col style="width: 25%" />
<col style="width: 29%" />
<col style="width: 21%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td style="text-align: center;">查询</td>
<td style="text-align: center;">AT+CIPMODE?</td>
<td style="text-align: center;"><p>+CIPMODE: &lt;mode&gt;</p>
<p>OK</p></td>
<td rowspan="2" style="text-align: center;"><p>&lt;mode&gt;：模式</p>
<p>0：AT指令模式</p>
<p>1：透传模式</p>
<p>默认：0</p></td>
</tr>
<tr>
<td style="text-align: center;">模式选择</td>
<td style="text-align: center;">AT+CIPMODE=&lt;mode&gt;</td>
<td style="text-align: center;">OK</td>
</tr>
</tbody>
</table>

**备注：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td><ol type="1">
<li><p>该指令需要在开启数据网络前，以及建立连接前使用</p></li>
<li><p>AT指令模式：每次数据发送都需要用AT指令进行，具体参考5.4.4部分</p></li>
<li><p>透传模式：允许直接传输数据，可通过指令进入或退出透传模式，具体参考5.4.5和5.4.6部分</p></li>
</ol></td>
</tr>
</tbody>
</table>

**举例：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: left;"><p>发送：AT+CIPMODE=1</p>
<p>返回：AT+CIPMODE=1</p>
<p>OK</p></td>
</tr>
</tbody>
</table>

1.  <span id="_Toc22776" class="anchor"></span>**配置TCP/UDP心跳间隔**

<table style="width:100%;">
<colgroup>
<col style="width: 18%" />
<col style="width: 25%" />
<col style="width: 23%" />
<col style="width: 31%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td style="text-align: center;">查询</td>
<td style="text-align: center;">AT+MCIPCFG?</td>
<td style="text-align: center;"><p>+MCIPCFG:</p>
<p>&lt;heartbeat_time&gt;</p>
<p>OK</p></td>
<td rowspan="2" style="text-align: center;"><p>&lt;heartbeat_time&gt;：心跳间隔</p>
<p>范围：0 - 7200 秒</p>
<p>默认：0</p></td>
</tr>
<tr>
<td style="text-align: center;">配置参数</td>
<td style="text-align: center;"><p>AT+MCIPCFG=</p>
<p>&lt;heartbeat_time&gt;</p></td>
<td style="text-align: center;">OK</td>
</tr>
</tbody>
</table>

**备注：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td><ol type="1">
<li><p>该指令需要在建立连接前使用</p></li>
<li><p>&lt;heartbeat_time&gt;=0时，关闭保持连接功能</p></li>
</ol></td>
</tr>
</tbody>
</table>

**举例：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: left;"><p>发送：AT+MCIPCFG=0</p>
<p>返回：AT+MCIPCFG=0</p>
<p>OK</p></td>
</tr>
</tbody>
</table>

1.  <span id="_Toc8073" class="anchor"></span>**建立TCP/UDP连接**

<table style="width:100%;">
<colgroup>
<col style="width: 12%" />
<col style="width: 26%" />
<col style="width: 31%" />
<col style="width: 28%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td rowspan="3" style="text-align: center;">查询</td>
<td rowspan="3" style="text-align: center;">AT+CIPOPEN?</td>
<td rowspan="3" style="text-align: center;"><p>+CIPOPEN: &lt;link_num&gt;,&lt;type&gt;,</p>
<p>&lt;serverIP&gt;,&lt;serverPort&gt;,</p>
<p>&lt;index&gt;</p>
<p>OK</p></td>
<td style="text-align: center;"><p>&lt;link_num&gt;：连接标识</p>
<p>范围：0 - 2</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;type&gt;：传输协议类型</p>
<p>范围：TCP、UDP</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;serverIP&gt;：服务器IP 地址</p>
<p>&lt;serverPort&gt;：服务器端口号</p>
<p>范围：0-65535</p></td>
</tr>
<tr>
<td rowspan="2" style="text-align: center;">连接</td>
<td rowspan="2" style="text-align: center;"><p>AT+CIPOPEN=</p>
<p>&lt;link_num&gt;,&lt;type&gt;,</p>
<p>&lt;serverIP&gt;,&lt;serverPort&gt;</p>
<p>[,&lt;localPort&gt;]</p></td>
<td rowspan="2" style="text-align: center;"><p>OK</p>
<p>+CIPOPEN:</p>
<p>&lt;err&gt;,&lt;link_num&gt;</p></td>
<td style="text-align: center;"><p>&lt;localPort&gt;：本地端口号</p>
<p>范围：0-65535</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;err&gt;：操作结果</p>
<p>SUCCESS：成功</p>
<p>FAIL：失败</p></td>
</tr>
</tbody>
</table>

**备注：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td><ol type="1">
<li><p>AT+CIPMODE=0，且&lt;type&gt;为UDP时，&lt;serverIP&gt;和&lt;serverPort&gt;需设置为空</p></li>
<li><p>AT+CIPMODE=1时，&lt;link_num&gt;需要设置为0</p></li>
</ol></td>
</tr>
</tbody>
</table>

**举例：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: left;"><p>发送：AT+CIPOPEN=1,"TCP","122.114.122.174",41017</p>
<p>返回：AT+CIPOPEN=1,"TCP","122.114.122.174",36733</p>
<p>OK</p>
<p>+CIPOPEN: SUCCESS,1</p></td>
</tr>
</tbody>
</table>

1.  <span id="_Toc11550" class="anchor"></span>**TCP/UDP发送数据**

<table style="width:100%;">
<colgroup>
<col style="width: 17%" />
<col style="width: 30%" />
<col style="width: 22%" />
<col style="width: 28%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td rowspan="2" style="text-align: center;">TCP数据发送</td>
<td rowspan="2" style="text-align: center;"><p>AT+CIPSEND=</p>
<p>&lt;link_num&gt;[,&lt;length&gt;]</p></td>
<td rowspan="6" style="text-align: center;"><p>OK</p>
<p>+CIPSEND:</p>
<p>&lt;err&gt;,&lt;link_num&gt;,</p>
<p>&lt;reqLen&gt;,&lt;cnfLen&gt;</p></td>
<td style="text-align: center;"><p>&lt;link_num&gt;：连接标识</p>
<p>范围：0 - 2</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;length&gt;：数据长度</p>
<p>范围：0 - 1500 字节</p></td>
</tr>
<tr>
<td rowspan="2" style="text-align: center;">TCP数据直发模式</td>
<td rowspan="2" style="text-align: center;"><p>AT+CIPSEND=</p>
<p>&lt;link_num&gt;,,,,&lt;data&gt;</p></td>
<td style="text-align: center;"><p>&lt;serverIP&gt;：服务器IP地址</p>
<p>&lt;serverPort&gt;：服务器端口号</p>
<p>范围：0-65535</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;data&gt;：数据内容</p>
<p>范围：0-512 字节</p></td>
</tr>
<tr>
<td rowspan="2" style="text-align: center;">UDP数据发送</td>
<td rowspan="2" style="text-align: center;"><p>AT+CIPSEND=</p>
<p>&lt;link_num&gt;,[&lt;length&gt;],</p>
<p>&lt;serverIP&gt;,&lt;serverPort&gt;</p></td>
<td style="text-align: center;"><p>&lt;reqLen&gt;：需传输的字节数</p>
<p>&lt;cnfLen&gt;：已传输的字节数</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;err&gt;：操作结果</p>
<p>SUCCESS：成功</p>
<p>FAIL：失败</p></td>
</tr>
</tbody>
</table>

**备注：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td><ol type="1">
<li><p>除TCP数据直发模式外，&lt;length&gt;参数忽略时，数据发送完毕后需要HEX格式发送1A作为结束符</p></li>
<li><p>设置&lt;length&gt;参数后，发送数据的长度需要与&lt;length&gt;一致，不足则会等待数据输入</p></li>
</ol></td>
</tr>
</tbody>
</table>

**举例：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: left;"><p>发送：AT+CIPSEND=1</p>
<p>返回：AT+CIPSEND=1</p>
<p>&gt;</p>
<p>发送：222</p>
<p>返回：222</p>
<p>16进制：发送：1A</p>
<p>16进制：返回：1A</p>
<p>返回：OK</p>
<p>+CIPSEND:SUCCESS,1,5,5</p></td>
</tr>
</tbody>
</table>

1.  <span id="_Toc6836" class="anchor"></span>**进入TCP/UDP透传模式**

|          |          |          |          |
|:--------:|:--------:|:--------:|:--------:|
| **功能** | **指令** | **响应** | **说明** |
| 进入透传 |   ATO    |          |          |

**备注：**

|                                                        |
|--------------------------------------------------------|
| 该指令只能在数据传输模式下，即AT+CIPMODE=1时才可以使用 |

2.  <span id="_Toc8288" class="anchor"></span>**退出TCP/UDP透传模式**

|          |          |          |          |
|:--------:|:--------:|:--------:|:--------:|
| **功能** | **指令** | **响应** | **说明** |
| 退出透传 |   +++    |          |          |

**备注：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td><ol type="1">
<li><p>该指令只能在数据传输模式下，即AT+CIPMODE=1时才可以使用</p></li>
<li><p>该指令结尾无结束符，即指令结尾无回车换行</p></li>
</ol></td>
</tr>
</tbody>
</table>

1.  <span id="_Toc12224" class="anchor"></span>**关闭TCP/UDP连接**

<table style="width:100%;">
<colgroup>
<col style="width: 17%" />
<col style="width: 21%" />
<col style="width: 32%" />
<col style="width: 28%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td rowspan="2" style="text-align: center;">查询</td>
<td rowspan="2" style="text-align: center;">AT+CIPCLOSE?</td>
<td rowspan="2" style="text-align: center;"><p>+CIPCLOSE: &lt;link_num&gt;,&lt;status&gt;</p>
<p>OK</p></td>
<td style="text-align: center;"><p>&lt;link_num&gt;：连接标识</p>
<p>范围：0-2</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;status&gt;：连接状态</p>
<p>0: 断开</p>
<p>1: 连接</p></td>
</tr>
<tr>
<td style="text-align: center;">关闭连接</td>
<td style="text-align: center;"><p>AT+CIPCLOSE=</p>
<p>&lt;link_num&gt;</p></td>
<td style="text-align: center;"><p>OK</p>
<p>+CIPCLOSE:</p>
<p>&lt;err&gt;,&lt;link_num&gt;</p></td>
<td style="text-align: center;"><p>&lt;err&gt;：操作结果</p>
<p>SUCCESS：成功</p>
<p>FAIL：失败</p></td>
</tr>
</tbody>
</table>

**举例：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: left;"><p>发送：AT+CIPCLOSE=1</p>
<p>返回：AT+CIPCLOSE=1</p>
<p>OK</p>
<p>+CIPCLOSE:SUCCESS,1</p></td>
</tr>
</tbody>
</table>

1.  <span id="_Toc15720" class="anchor"></span>**MQTT相关命令**

    1.  <span id="_Toc19016" class="anchor"></span>**配置MQTT客户端信息**

<table style="width:100%;">
<colgroup>
<col style="width: 11%" />
<col style="width: 30%" />
<col style="width: 29%" />
<col style="width: 28%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td rowspan="3" style="text-align: center;">查询</td>
<td rowspan="3" style="text-align: center;">AT+MCONFIG?</td>
<td rowspan="3" style="text-align: center;"><p>+MCONFIG:</p>
<p>&lt;clientid&gt;,</p>
<p>&lt;username&gt;,&lt;password&gt;,</p>
<p>&lt;will_flag&gt;,&lt;will_qos&gt;,</p>
<p>&lt;will_retain&gt;,&lt;will_topic&gt;,</p>
<p>&lt;will_message&gt;</p>
<p>OK</p></td>
<td style="text-align: center;"><p>&lt;clientid&gt;：客户端ID</p>
<p>&lt;username&gt;：用户名</p>
<p>&lt;password&gt;：密码</p>
<p>最大长度为256</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;will_flag&gt;：遗嘱开关</p>
<p>0：关闭遗嘱</p>
<p>1：启用遗嘱</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;will_qos&gt;：遗嘱Qos</p>
<p>0：最多一次</p>
<p>1：至少一次</p>
<p>2：只有一次</p></td>
</tr>
<tr>
<td rowspan="3" style="text-align: center;">配置参数</td>
<td rowspan="3" style="text-align: center;"><p>AT+MCONFIG=</p>
<p>&lt;clientid&gt;</p>
<p>[,&lt;username&gt;,&lt;password&gt;]</p>
<p>[,&lt;will_flag&gt;,&lt;will_qos&gt;,</p>
<p>&lt;will_retain&gt;,&lt;will_topic&gt;,</p>
<p>&lt;will_message&gt;]</p></td>
<td rowspan="3" style="text-align: center;">OK</td>
<td style="text-align: center;"><p>&lt;will_retain&gt;：保留标志</p>
<p>0：不保留</p>
<p>1：保留</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;will_topic&gt;：遗嘱主题</p>
<p>最大长度256</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;will_message&gt;：遗嘱内容</p>
<p>最大长度1024</p></td>
</tr>
</tbody>
</table>

2.  <span id="_Toc1684" class="anchor"></span>**配置MQTT服务器信息**

<table style="width:100%;">
<colgroup>
<col style="width: 12%" />
<col style="width: 24%" />
<col style="width: 25%" />
<col style="width: 36%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td rowspan="2" style="text-align: center;">查询</td>
<td rowspan="2" style="text-align: center;">AT+MIPSTART?</td>
<td rowspan="2" style="text-align: center;"><p>+MIPSTART:&lt;address&gt;,</p>
<p>&lt;port&gt;,&lt;version&gt;</p>
<p>OK</p></td>
<td style="text-align: center;"><p>&lt;address&gt;：服务器IP/域名</p>
<p>最大长度256</p>
<p>&lt;port&gt;：服务器端口号</p>
<p>范围：0-65535</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;version&gt;：MQTT协议版本</p>
<p>3：3.1版本</p>
<p>4：3.1.1版本</p></td>
</tr>
</tbody>
</table>

<table style="width:100%;">
<colgroup>
<col style="width: 12%" />
<col style="width: 24%" />
<col style="width: 25%" />
<col style="width: 36%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;">配置参数</td>
<td style="text-align: center;"><p>AT+MIPSTART=</p>
<p>&lt;address&gt;,&lt;port&gt;</p>
<p>[,&lt;version&gt;]</p></td>
<td style="text-align: center;"><p>OK</p>
<p>+MIPSTART: &lt;result&gt;</p></td>
<td style="text-align: center;"><p>&lt;result&gt;：</p>
<p>SUCCESS：成功</p>
<p>FAILURE：失败</p></td>
</tr>
</tbody>
</table>

3.  <span id="_Toc23448" class="anchor"></span>**连接MQTT服务器**

<table style="width:100%;">
<colgroup>
<col style="width: 12%" />
<col style="width: 24%" />
<col style="width: 33%" />
<col style="width: 29%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td rowspan="2" style="text-align: center;">查询</td>
<td rowspan="2" style="text-align: center;">AT+MCONNECT?</td>
<td rowspan="2" style="text-align: center;"><p>+MCONNECT:&lt;clean_session&gt;,&lt;keepalive&gt;</p>
<p>OK</p></td>
<td style="text-align: center;"><p>&lt;clean_session&gt;：会话模式</p>
<p>0：持久会话模式</p>
<p>1：临时会话模式</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;keepalive&gt;：心跳间隔</p>
<p>范围：30-1800 S</p></td>
</tr>
<tr>
<td style="text-align: center;">连接</td>
<td style="text-align: center;"><p>AT+MCONNECT=</p>
<p>&lt;clean_session&gt;,</p>
<p>&lt;keepalive&gt;</p></td>
<td style="text-align: center;"><p>OK</p>
<p>+MCONNECT: &lt;result&gt;</p></td>
<td style="text-align: center;"><p>&lt;result&gt;：</p>
<p>SUCCESS：成功</p>
<p>FAILURE：失败</p></td>
</tr>
</tbody>
</table>

4.  <span id="_Toc26306" class="anchor"></span>**发布主题**

<table style="width:100%;">
<colgroup>
<col style="width: 12%" />
<col style="width: 23%" />
<col style="width: 34%" />
<col style="width: 29%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td rowspan="3" style="text-align: center;">发布消息</td>
<td rowspan="3" style="text-align: center;"><p>AT+MPUB=</p>
<p>&lt;topic&gt;,&lt;qos&gt;,</p>
<p>&lt;retain&gt;,&lt;message&gt;</p></td>
<td rowspan="3" style="text-align: center;"><p>OK</p>
<p>+MPUB:&lt;result&gt;</p></td>
<td style="text-align: center;"><p>&lt;topic&gt;：主题</p>
<p>最大长度256</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;qos&gt;：服务质量等级</p>
<p>0：最多一次</p>
<p>1：至少一次</p>
<p>2：只有一次</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;retain&gt;：保留标志</p>
<p>0：不保留</p>
<p>1：保留</p></td>
</tr>
<tr>
<td rowspan="3" style="text-align: center;">发布长消息</td>
<td rowspan="3" style="text-align: center;"><p>AT+MPUBEX=</p>
<p>&lt;topic&gt;,&lt;qos&gt;,</p>
<p>&lt;retain&gt;,&lt;msgLen&gt;</p></td>
<td rowspan="3" style="text-align: center;"><p>OK</p>
<p>+MPUBEX:&lt;result&gt;</p></td>
<td style="text-align: center;"><p>&lt;message&gt;：消息内容</p>
<p>最大长度512</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;msgLen&gt;：消息长度</p>
<p>最大长度4096</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;result&gt;：</p>
<p>SUCCESS：成功</p>
<p>FAILURE：失败</p></td>
</tr>
</tbody>
</table>

**备注：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td><p>发布长消息，AT+MPUBEX指令说明：</p>
<ol type="1">
<li><p>指令发送后进入数据传输模式，返回提示符 &gt;，即可发送数据，发送成功后自动退出数据传输模式</p></li>
<li><p>发送的数据长度需要与&lt;msgLen&gt;参数一致，数据长度不足则会等待继续输入</p></li>
<li><p>超过10秒未成功发送，则自动退出数据传输模式，返回ERROR</p></li>
</ol></td>
</tr>
</tbody>
</table>

1.  <span id="_Toc28376" class="anchor"></span>**订阅主题**

<table style="width:100%;">
<colgroup>
<col style="width: 10%" />
<col style="width: 23%" />
<col style="width: 34%" />
<col style="width: 30%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td rowspan="2" style="text-align: center;">查询</td>
<td rowspan="2" style="text-align: center;">AT+MSUB?</td>
<td rowspan="2" style="text-align: center;"><p>+MSUB:&lt;topic&gt;,&lt;qos&gt;</p>
<p>OK</p></td>
<td style="text-align: center;"><p>&lt;topic&gt;：主题</p>
<p>最大长度256</p>
<p>最多订阅50个主题</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;qos&gt;：服务质量等级</p>
<p>0：最多一次</p>
<p>1：至少一次</p>
<p>2：只有一次</p></td>
</tr>
<tr>
<td style="text-align: center;">订阅主题</td>
<td style="text-align: center;"><p>AT+MSUB=</p>
<p>&lt;topic&gt;,&lt;qos&gt;</p></td>
<td style="text-align: center;">+MSUB:&lt;result&gt;</td>
<td style="text-align: center;"><p>&lt;result&gt;：</p>
<p>SUCCESS：成功</p>
<p>FAILURE：失败</p></td>
</tr>
</tbody>
</table>

**备注：**

|                                      |
|--------------------------------------|
| 查询指令，只能查询最后一个订阅的主题 |

2.  <span id="_Toc16716" class="anchor"></span>**取消订阅**

<table style="width:100%;">
<colgroup>
<col style="width: 11%" />
<col style="width: 25%" />
<col style="width: 30%" />
<col style="width: 31%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td rowspan="2" style="text-align: center;">取消订阅</td>
<td rowspan="2" style="text-align: center;">AT+MUNSUB=&lt;topic&gt;</td>
<td rowspan="2" style="text-align: center;">+MUNSUB:&lt;result&gt;</td>
<td style="text-align: center;"><p>&lt;topic&gt;：主题</p>
<p>最大长度256</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;result&gt;：</p>
<p>SUCCESS：成功</p>
<p>FAILURE：失败</p></td>
</tr>
</tbody>
</table>

3.  <span id="_Toc4986" class="anchor"></span>**查询MQTT连接状态**

<table style="width:100%;">
<colgroup>
<col style="width: 10%" />
<col style="width: 23%" />
<col style="width: 34%" />
<col style="width: 30%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td style="text-align: center;">查询</td>
<td style="text-align: center;">AT+MQTTSTATU</td>
<td style="text-align: center;"><p>+MQTTSTATU:&lt;statu&gt;</p>
<p>OK</p></td>
<td style="text-align: center;"><p>&lt;statu&gt;：状态</p>
<p>0：未建立连接</p>
<p>1：已建立连接</p></td>
</tr>
</tbody>
</table>

4.  <span id="_Toc25404" class="anchor"></span>**断开MQTT连接**

<table style="width:100%;">
<colgroup>
<col style="width: 10%" />
<col style="width: 23%" />
<col style="width: 34%" />
<col style="width: 30%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td style="text-align: center;">断开连接</td>
<td style="text-align: center;">AT+MDISCONNECT</td>
<td style="text-align: center;"><p>OK</p>
<p>+MDISCONNECT:&lt;result&gt;</p></td>
<td style="text-align: center;"><p>&lt;result&gt;：</p>
<p>SUCCESS：成功</p>
<p>FAILURE：失败</p></td>
</tr>
</tbody>
</table>

**备注：**

|                                                   |
|---------------------------------------------------|
| 断开连接后，需要发送指令AT+MIPCLOSE，释放MQTT资源 |

5.  <span id="_Toc30787" class="anchor"></span>**释放MQTT资源**

<table style="width:100%;">
<colgroup>
<col style="width: 10%" />
<col style="width: 23%" />
<col style="width: 34%" />
<col style="width: 30%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td style="text-align: center;">释放资源</td>
<td style="text-align: center;">AT+MIPCLOSE</td>
<td style="text-align: center;"><p>OK</p>
<p>+MIPCLOSE:&lt;result&gt;</p></td>
<td style="text-align: center;"><p>&lt;result&gt;：</p>
<p>SUCCESS：成功</p>
<p>FAILURE：失败</p></td>
</tr>
</tbody>
</table>

**备注：**

|                                                              |
|--------------------------------------------------------------|
| 释放MQTT资源前，需要需要发送指令AT+MDISCONNECT，断开MQTT连接 |

1.  <span id="_Toc26298" class="anchor"></span>**HTTP相关指令**

    1.  <span id="_Toc27753" class="anchor"></span>**开启HTTP服务**

<table style="width:100%;">
<colgroup>
<col style="width: 12%" />
<col style="width: 22%" />
<col style="width: 33%" />
<col style="width: 30%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td style="text-align: center;">查询</td>
<td style="text-align: center;">AT$HTTPOPEN?</td>
<td style="text-align: center;"><p>$HTTPOPEN:&lt;stat&gt;</p>
<p>OK</p></td>
<td rowspan="2" style="text-align: center;"><p>&lt;stat&gt;：状态</p>
<p>0: 未开启</p>
<p>1: 已开启</p></td>
</tr>
<tr>
<td style="text-align: center;">开启服务</td>
<td style="text-align: center;">AT$HTTPOPEN</td>
<td style="text-align: center;">OK</td>
</tr>
</tbody>
</table>

2.  <span id="_Toc22634" class="anchor"></span>**关闭HTTP服务**

<table style="width:100%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 24%" />
<col style="width: 32%" />
<col style="width: 29%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td style="text-align: center;">查询</td>
<td style="text-align: center;">AT$HTTPCLOSE?</td>
<td style="text-align: center;"><p>$HTTPCLOSE:&lt;stat&gt;</p>
<p>OK</p></td>
<td rowspan="2" style="text-align: center;"><p>&lt;stat&gt;: 状态</p>
<p>0: 未关闭</p>
<p>1: 已关闭</p></td>
</tr>
<tr>
<td style="text-align: center;">关闭服务</td>
<td style="text-align: center;">AT$HTTPCLOSE</td>
<td style="text-align: center;">OK</td>
</tr>
</tbody>
</table>

3.  <span id="_Toc22543" class="anchor"></span>**配置HTTP的URL信息**

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 24%" />
<col style="width: 21%" />
<col style="width: 38%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td rowspan="2" style="text-align: center;">查询</td>
<td rowspan="2" style="text-align: center;">AT$HTTPPARA?</td>
<td rowspan="2" style="text-align: center;"><p>Host : "&lt;host&gt;"</p>
<p>URI : "&lt;uri&gt;"</p>
<p>Port : &lt;port&gt;</p>
<p>Cert : &lt;cert&gt;</p></td>
<td style="text-align: center;"><p>&lt;url&gt;：URL</p>
<p>范围：0-255字节</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;port&gt;：URL端口号</p>
<p>默认：80 (HTTP)</p></td>
</tr>
<tr>
<td style="text-align: center;">设置</td>
<td style="text-align: center;"><p>AT$HTTPPARA=</p>
<p>&lt;url&gt;,&lt;port&gt;</p></td>
<td style="text-align: center;">OK</td>
<td style="text-align: center;"><p>&lt;host&gt;：主机域名/IP</p>
<p>&lt;uri&gt;：URI</p>
<p>&lt;cert&gt;：证书 (默认：0无证书)</p></td>
</tr>
</tbody>
</table>

4.  <span id="_Toc837" class="anchor"></span>**发送HTTP请求**

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 24%" />
<col style="width: 21%" />
<col style="width: 38%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td rowspan="2" style="text-align: center;">发送请求</td>
<td rowspan="2" style="text-align: center;"><p>AT$HTTPACTION=</p>
<p>&lt;request&gt;</p></td>
<td rowspan="2" style="text-align: center;"><p>$HTTPRECV: DATA,&lt;len&gt;</p>
<p>......</p></td>
<td style="text-align: center;"><p>&lt;request&gt;：请求类型</p>
<p>0: GET</p>
<p>1: POST (大数据量)</p>
<p>2: HEAD</p>
<p>3: POST（小数据量）</p></td>
</tr>
<tr>
<td style="text-align: center;">&lt;len&gt;：响应的数据长度</td>
</tr>
</tbody>
</table>

**备注：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td><ol type="1">
<li><p>请求成功后，模块返回HTTP响应头或HTML文本等信息</p></li>
<li><p>发送POST请求，需要设置请求头和请求体，请求头需包含Content-Length字段</p></li>
<li><p>&lt;request&gt;=1时，请求体数据需要在该指令发送后提交</p></li>
<li><p>&lt;request&gt;=3时，请求体数据需要在该指令发送前提交</p></li>
<li><p>返回ERROR 202时，需先发送AT$HTTPCLOSE，再发送AT$HTTPOPEN，重启HTTP服务</p></li>
</ol></td>
</tr>
</tbody>
</table>

1.  <span id="_Toc27681" class="anchor"></span>**设置请求头字段**

<table style="width:100%;">
<colgroup>
<col style="width: 17%" />
<col style="width: 27%" />
<col style="width: 23%" />
<col style="width: 30%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td style="text-align: center;">查询</td>
<td style="text-align: center;">AT$HTTPRQH?</td>
<td style="text-align: center;"><p>List:{&lt;key&gt;:&lt;value&gt;}</p>
<p>OK</p></td>
<td style="text-align: center;"><p>&lt;key&gt;：请求头字段的键</p>
<p>范围：0-50字节</p></td>
</tr>
<tr>
<td style="text-align: center;">设置请求头字段</td>
<td style="text-align: center;"><p>AT$HTTPRQH=</p>
<p>&lt;key&gt;,&lt;value&gt;</p></td>
<td style="text-align: center;">OK</td>
<td style="text-align: center;"><p>&lt;value&gt;：请求头字段的值</p>
<p>范围：0-255字节</p></td>
</tr>
</tbody>
</table>

**备注：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td><ol type="1">
<li><p>&lt;key&gt;和&lt;value&gt;参数，若存在特殊字符，需要加上引号</p></li>
<li><p>该指令需要在发送HTTP请求前，即指令AT$HTTPACTION前发送</p></li>
</ol></td>
</tr>
</tbody>
</table>

1.  <span id="_Toc30528" class="anchor"></span>**设置请求体数据**

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 34%" />
<col style="width: 20%" />
<col style="width: 29%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td rowspan="2" style="text-align: center;">设置小数据量</td>
<td rowspan="2" style="text-align: center;"><p>AT$HTTPDATAEX=</p>
<p>&lt;short_data_len&gt;,&lt;data&gt;</p></td>
<td rowspan="2" style="text-align: center;">OK</td>
<td style="text-align: center;"><p>&lt;short_data_len&gt;：数据长度</p>
<p>范围：0 - 500</p></td>
</tr>
<tr>
<td style="text-align: center;">&lt;data&gt;：数据内容</td>
</tr>
<tr>
<td style="text-align: center;">设置大数据量</td>
<td style="text-align: center;"><p>AT$HTTPDATA=</p>
<p>&lt;long_data_len&gt;</p></td>
<td style="text-align: center;">&gt;&gt;</td>
<td style="text-align: center;"><p>&lt;long_data_len&gt;：数据长度</p>
<p>范围：0 - 1024字节</p></td>
</tr>
</tbody>
</table>

**备注：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td><p>AT$HTTPDATAEX指令说明：</p>
<ol type="1">
<li><p>该指令只能在发送小数据量的POST请求，即AT$HTTPACTION=3时使用</p></li>
<li><p>&lt;short_data_len&gt;长度需要与请求头字段Content-Length的一致</p>
<p>AT$HTTPDATA指令说明：</p></li>
</ol>
<ol type="1">
<li><p>该指令只能在发送大数据量的POST请求，即AT$HTTPACTION=1时使用</p></li>
<li><p>该指令响应提示符&gt;&gt;后即可输入数据，数据长度不足则会等待输入</p></li>
<li><p>每次设置完请求体数据后，需要发送AT$HTTPSEND，提交请求体数据</p></li>
<li><p>该指令可多次发送，结束请求体数据提交时，会把多次设置的请求体数据整合到一起提交</p></li>
<li><p>结束请求体数据提交，需要发送AT$HTTPDATA=0和AT$HTTPSEND</p></li>
<li><p>&lt;long_data_len&gt;之和的长度需要与请求头字段Content-Length的一致</p></li>
</ol></td>
</tr>
</tbody>
</table>

1.  <span id="_Toc13632" class="anchor"></span>**提交请求体数据**

|                |              |          |          |
|:--------------:|:------------:|:--------:|:--------:|
|    **功能**    |   **指令**   | **响应** | **说明** |
| 提交请求体数据 | AT\$HTTPSEND |    OK    |          |

2.  <span id="_Toc3035" class="anchor"></span>**HTTP错误码**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: left;"><p>200：子系统已建立并可用</p>
<p>201：子系统建立正在进行中</p>
<p>202：网络子系统不可用</p>
<p>203：PPP正在关闭</p>
<p>204：已存在网络子系统资源</p>
<p>205：物理链路进入休眠状态</p>
<p>300：HTTP服务未开启</p>
<p>301：HTTP服务已开启</p>
<p>302：URL解析失败</p>
<p>303：DNS错误</p>
<p>304：操作错误</p>
<p>305：请求超时</p>
<p>306：文件下载中</p>
<p>307：URL未设置</p>
<p>308：请求头字段数量超过限制</p>
<p>309：请求头字段错误，如POST请求未设置"Content-Length"</p>
<p>310：响应头异常</p>
<p>311：正在发送POST数据</p>
<p>312：POST请求未启动，仅适用于$HTTPACTION=1</p>
<p>313："Content-Length"的值与内容长度不一致</p>
<p>314：请求失败，需关闭套接字</p>
<p>315：连接服务器失败</p>
<p>316：EFS空间不足</p>
<p>317：EFS操作失败</p>
<p>350：未知HTTP错误</p></td>
</tr>
</tbody>
</table>

1.  <span id="_Toc2599" class="anchor"></span>**GPS相关指令（模块名称带N的支持GNSS功能）**

    1.  <span id="_Toc11552" class="anchor"></span>**GPS开关**

<table style="width:99%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 26%" />
<col style="width: 27%" />
<col style="width: 30%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td style="text-align: center;">查询</td>
<td style="text-align: center;">AT+MGPSC?</td>
<td style="text-align: center;"><p>+MGPSC:&lt;mode&gt;</p>
<p>OK</p></td>
<td rowspan="2" style="text-align: center;"><p>&lt;mode&gt;：模式</p>
<p>0：关闭GPS</p>
<p>1：开启GPS</p></td>
</tr>
<tr>
<td style="text-align: center;">设置</td>
<td style="text-align: center;">AT+MGPSC=&lt;mode&gt;</td>
<td style="text-align: center;">OK</td>
</tr>
</tbody>
</table>

**备注：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td><ol type="1">
<li><p>GPS相关指令，需要开启定位功能后使用</p></li>
<li><p>我司的底板，若GNSS天线为有源天线时，开启定位功能前需要按顺序发送以下指令：</p></li>
</ol>
<p>AT+CGDRT=12,1</p>
<p>AT+CGSETV=12,1</p>
<p>AT+CGGETV=12</p></td>
</tr>
</tbody>
</table>

**举例：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: left;"><p>发送：AT+MGPSC=1</p>
<p>返回：AT+MGPSC=1</p>
<p>OK</p>
<p>+GPS: start up success.</p></td>
</tr>
</tbody>
</table>

1.  <span id="_Toc15882" class="anchor"></span>**设置GPS模式**

<table style="width:99%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 28%" />
<col style="width: 26%" />
<col style="width: 29%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong><br />
功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td style="text-align: center;">查询</td>
<td style="text-align: center;">AT+GPSMODE?</td>
<td style="text-align: center;"><p>+GPSMODE: &lt;mode&gt;</p>
<p>OK</p></td>
<td rowspan="2" style="text-align: center;"><p>&lt;mode&gt;：模式</p>
<p>1：热启动</p>
<p>2：温启动</p>
<p>3：冷启动</p></td>
</tr>
<tr>
<td style="text-align: center;">设置</td>
<td style="text-align: center;">AT+GPSMODE=&lt;mode&gt;</td>
<td style="text-align: center;">OK</td>
</tr>
</tbody>
</table>

**备注：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td><ol type="1">
<li><p>热启动：</p>
<p>GPS保存其最后计算的可视卫星的位置、历书和UTC时间。重启后，GPS基于该数据来获取和计算当前卫星的最新位置 (一般适用于距离上次定位时间小于两个小时的情况)</p></li>
<li><p>温启动：</p>
<p>GPS保存其最后计算的卫星位置、历书和UTC时间，但该数据不包含当前可视卫星数据。重启后，GPS尝试获取当前卫星信号并计算其新位置 (一般适用于距离上次定位时间超过两个小时的情况)</p></li>
<li><p>冷启动：</p>
<p>GPS清空所有历史信息，并重新开始定位锁定卫星。由于没有先前的数据支持，定位过程会非常缓慢。GPS采用类似于轮询的方式，从所有卫星中逐一锁定信号 (一般适用于电池耗尽导致星历信息丢失，或者设备在关机状态下移动超过1000公里的距离)</p></li>
</ol></td>
</tr>
</tbody>
</table>

**举例：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: left;"><p>发送：AT+GPSMODE=1</p>
<p>返回：AT+GPSMODE=1</p>
<p>OK</p>
<p>$ACKOK,*61</p>
<p>$FW_VER:Jacana 1.065.033 Dec 21 2023 13:41:27</p></td>
</tr>
</tbody>
</table>

1.  <span id="_Toc25467" class="anchor"></span>**设置NMEA数据输出**

<table style="width:100%;">
<colgroup>
<col style="width: 15%" />
<col style="width: 32%" />
<col style="width: 24%" />
<col style="width: 27%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td style="text-align: center;">设置</td>
<td style="text-align: center;">AT+MGPSGET=ALL,&lt;stat&gt;</td>
<td style="text-align: center;">OK</td>
<td style="text-align: center;"><blockquote>
<p>&lt;stat&gt;:状态</p>
<p>0：关闭输出</p>
<p>1：开启输出 (默认)</p>
</blockquote></td>
</tr>
</tbody>
</table>

2.  <span id="_Toc22922" class="anchor"></span>**查询定位信息**

<table style="width:99%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 18%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><span id="_Toc14180" class="anchor"></span><strong><br />
功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td rowspan="4" style="text-align: center;">查询</td>
<td rowspan="4" style="text-align: center;">AT+GPSSTEX</td>
<td rowspan="4" style="text-align: center;"><p>&lt;fix_status&gt;,&lt;module_status&gt;,</p>
<p>&lt;longitude&gt;,&lt;high&gt;,</p>
<p>&lt;latitude&gt;,&lt;speed&gt;,</p>
<p>&lt;sta_num0&gt;,&lt;sta_num1&gt;</p>
<p>OK</p></td>
<td style="text-align: center;"><p>&lt; fix_status&gt;: 定位状态</p>
<p>0: 未定位成功</p>
<p>1: 定位成功</p></td>
</tr>
<tr>
<td style="text-align: center;">&lt;module_status&gt;：1</td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt; longitude &gt;: 经度值</p>
<p>&lt;high&gt;：高度值</p>
<p>&lt; latitude &gt;: 纬度值</p>
<p>&lt;speed&gt;：GPS对地速度</p></td>
</tr>
<tr>
<td style="text-align: center;"><p>&lt;sta_num0&gt;: 可见卫星数量</p>
<p>&lt;sta_num1&gt;：参与定位卫星数量</p></td>
</tr>
</tbody>
</table>

**备注：**

|  |
|----|
| 该指令的经纬度值的坐标系为WGS-84，地图坐标系为其他坐标系时，需要做坐标系转换才能应用 |

**举例：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: left;"><p>发送：AT+GPSSTEX</p>
<p>返回：AT+GPSSTEX</p>
<p>+GPS5TEX：1, 1,113.831385, 12.166000, 22.606304, 0.013000, 15, 14</p>
<p>OK</p>
<p>数据解析：</p>
<blockquote>
<p>定位状态：1，&lt;module_status&gt;：1，经度值：113.831385，高度值：12.166000，纬度值：22.606304，GPS对地速度：0.013000，可见卫星数量：15，参与定位的卫星数量：14</p>
</blockquote></td>
</tr>
</tbody>
</table>

3.  **AGNSS辅助数据下载**

<table style="width:99%;">
<colgroup>
<col style="width: 12%" />
<col style="width: 24%" />
<col style="width: 18%" />
<col style="width: 43%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong><br />
功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td style="text-align: center;">查询</td>
<td style="text-align: center;">AT+AGNSSGET?</td>
<td style="text-align: center;"><p>+AGNSSGET:</p>
<p>OK</p></td>
<td rowspan="2" style="text-align: center;">&lt;agps_server_addr&gt;：AGPS服务器域名pos.asrmicro.com</td>
</tr>
<tr>
<td style="text-align: center;">设置</td>
<td style="text-align: center;"><p>AT+AGNSSGET=</p>
<p>&lt;agps_server_addr&gt;</p></td>
<td style="text-align: center;">OK</td>
</tr>
</tbody>
</table>

**备注：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td><ol type="1">
<li><p>该指令需要连接网络后使用，如未连接网络使用该指令，则提示下载失败</p></li>
<li><p>该指令通过网络下载星历等数据，用于实现快速定位，需要配合AT+AGNSSSET指令使用</p></li>
</ol></td>
</tr>
</tbody>
</table>

**举例：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: left;"><p>发送：AT+AGNSSGET=pos.asrmicro.com</p>
<p>返回：AT+AGNSSGET=pos.asrmicro.com</p>
<p>OK</p></td>
</tr>
</tbody>
</table>

1.  <span id="_Toc17460" class="anchor"></span>**AGNSS辅助数据应用**

<table style="width:100%;">
<colgroup>
<col style="width: 11%" />
<col style="width: 23%" />
<col style="width: 30%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>功能</strong></td>
<td style="text-align: center;"><strong>指令</strong></td>
<td style="text-align: center;"><strong>响应</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
</tr>
<tr>
<td style="text-align: center;">查询</td>
<td style="text-align: center;">AT+AGNSSSET</td>
<td style="text-align: center;"><p>+AGNSSSET:</p>
<p>OK</p></td>
<td style="text-align: center;"></td>
</tr>
</tbody>
</table>

**备注：**

|                                                                        |
|:-----------------------------------------------------------------------|
| 将辅助数据下载到GPS芯片，用于实现快速定位，需要配合AT+AGNSSGET指令使用 |

**举例：**

<table style="width:99%;">
<colgroup>
<col style="width: 99%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: left;"><p>发送：AT+AGNSSSET</p>
<p>返回：AT+AGNSSSET</p>
<p>OK</p></td>
</tr>
</tbody>
</table>

1.  <span id="_Toc14177" class="anchor"></span>**错误码**

|            |                          |
|:----------:|:------------------------:|
| **错误码** |         **说明**         |
|     3      |        操作不允许        |
|     4      |        操作不支持        |
|     10     |       SIM卡未识别        |
|     13     |        SIM卡故障         |
|     14     |        SIM卡繁忙         |
|     15     |        SIM卡异常         |
|     20     |         内存已满         |
|     23     |         内存故障         |
|     24     |       文本长度过长       |
|     25     |     文本包含无效字符     |
|     30     |        无网络服务        |
|     31     |       网络注册超时       |
|     32     | 网络不允许，仅限紧急呼叫 |
|     50     |         无效参数         |
|    100     |         未知错误         |
|    103     |          MS非法          |
|    106     |          ME非法          |
|    107     |      GPRS服务不允许      |
|    111     |       PLMN禁止连接       |
|    112     |     当前区域禁止连接     |
|    113     |     当前区域禁止漫游     |
|    132     |      服务选项不支持      |
|    133     |      服务选择未订阅      |
|    134     |      服务选项不可用      |
|    148     |       未知GPRS错误       |
|    149     |       PDP认证失败        |
|    150     |         无效设备         |
|    151     |        AT指令超时        |
|    300     |          ME故障          |
|    302     |        操作不允许        |
|    303     |        操作不支持        |
|    304     |     PDU模式参数无效      |
|    305     |     文本模式参数无效     |
|    310     |      (U)SIM卡未识别      |
|    313     |       (U)SIM卡故障       |
|    314     |       (U)SIM卡繁忙       |
|    315     |       (U)SIM卡异常       |
|    320     |         内存故障         |
|    322     |         内存已满         |
|    331     |        无网络服务        |
|    332     |       网络注册超时       |
|    340     |       无+CNMA认证        |
|    500     |         未知错误         |
|    902     |        网络已开启        |

# 增值服务

为满足客户各种功能要求，我司可以提供以下技术增值服务：

- 模块程序定制，如：IO功能口定制，AT指令定制，广播包定制等。

- 模块PCB硬件定制，可定制成客户需要的硬件要求。

- 各种蓝牙方案定制，可以根据客户需要，定制全套蓝牙软硬件解决方案。

- 全套联网解决方案定制，可以根据客户需求，定制全套可联网，网关解决方案。

|                                              |
|----------------------------------------------|
| 如有以上定制需求，请直接跟我司业务人员联系。 |
