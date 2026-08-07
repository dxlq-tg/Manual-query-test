<img src="assets/media/image2.png" style="width:0.98958in;height:0.98958in" alt="LOGO800E" />

**DX-CT511N**

**NMEA0183协议规范**

版本：1.0

日期：2024-07-30

**更新记录**

|          |            |          |          |
|:--------:|:----------:|:--------:|:--------:|
| **版本** |  **日期**  | **说明** | **作者** |
|   V1.0   | 2024/07/30 | 初始版本 |   SZY    |

**联系我们**

**深圳大夏龙雀科技有限公司**

邮箱：sales@szdx-smart.com

电话：0755-2997 8125

网址：[www.szdx-smart.com](http://www.szdx-smart.com)

地址：深圳市宝安区航城街道航空路华丰智谷A1座601

**目录**

[1. NMEA协议规范 [4](#nmea协议规范)](#nmea协议规范)

[1.1. 发送器标识符 [4](#_Toc27906)](#_Toc27906)

[1.2. GGA [4](#_Toc32702)](#_Toc32702)

[1.3. GLL [5](#_Toc1910)](#_Toc1910)

[1.4. GSA [7](#_Toc27386)](#_Toc27386)

[1.5. GSV [8](#_Toc24856)](#_Toc24856)

[1.6. RMC [9](#_Toc362283959)](#_Toc362283959)

[1.7. VTG [11](#_Toc24651)](#_Toc24651)

[1.8. ZDA [12](#_Toc1474)](#_Toc1474)

[1.9. TXT [12](#_Toc2595)](#_Toc2595)

[1.10. GST [13](#_Toc1954)](#_Toc1954)

# 

# NMEA协议规范

1.  <span id="_Toc27906" class="anchor"></span>**发送器标识符**

|                                 |        |
|:-------------------------------:|:------:|
|             发送器              | 标识符 |
|     北斗导航卫星系统（BDS）     |   BD   |
| 全球定位系统（GPS、SBAS、QZSS） |   GP   |
|   全球导航卫星系统（GLONASS）   |   GL   |
|    全球导航卫星系统（GNSS）     |   GN   |
|           自定义信息            |   P    |

2.  <span id="_Toc32702" class="anchor"></span>**GGA**

|  |  |  |  |  |
|:--:|:--:|:--:|:--:|:--:|
| **信息** | **描述** | **类型** | **格式** | **示例** |
| GGA | 接收机时间、位置及定位相关的数据 | 输出 | \$--GGA,UTCtime,lat,uLat,lon,uLon,FS,numSv,HDOP,msl,uMsl,sep,uSep,diffAg e,diffSta\*CS\<CR\> \<LF\> | \$GNGGA,073028.600,2236.40101,N,11349.73472,E,1,19,0.8,14.2,M,-4.0,M,,\*6E |

|  |  |  |  |
|:--:|:--:|:--:|:--:|
| **格式** | **说明** | **实例** | **参数说明** |
| \$--GGA | 消息ID | \$GNGGA | GGA语句头，’--‘为系统标识 |
| UTCtime | 当前定位的UTC时间 | 073028.600 | 格式：时时分分秒秒.秒秒秒（hhmmss.sss） |
| lat | 纬度，前2字符表示度，后面的字符表示分 | 2236.40101 | 格式：度度分分.分分分分 |
| uLat | 纬度方向 | N | 北半球（N）或南半球（S） |
| lon | 经度，前3字符表示度，后面的字符表示分 | 11349.73472 | 格式：度度度分分.分分分分 |

|  |  |  |  |
|:--:|:--:|:--:|:--:|
| uLon | 经度方向 | E | 东（E）半球或西（W）半球 |
| FS | 指示当前定位质量 | 1 | 参考：备注1 |
| numSv | 定位的卫星数目 | 19 | 范围：00 - 24 |
| HDOP | 水平精度因子（HDOP） | 0.8 | 范围：0.5 - 99.9 |
| msl | 海拔高度，即接收机天线相对于大地水准面的高度 | 14.2 | 范围：-9999.9 - 99999.9 |
| uMsl | 高度单位，米 | M | 固定字符M |
| sep | 参考椭球面与大地水准面之间的距离，“-”表示大地 水准面低于参考椭球面 | -4.0 | 范围：-9999.9 - 99999.9 |
| uSep | 高度单位，米 | M | 固定字符M |
| diffAge | 差分修正DGPS |  | 差分修正的数据龄期，未使用 DGPS 时该域为空 |
| diffSta | 差分参考基站标号 |  | 差分参考站的 ID |
| CS | 校验和 | 6E | \$和\*之间（不包括\$和\*）所有字符的异或结果 |
| \<CR\> \<LF\> | 结束符 | \<CR\> \<LF\> | 回车与换行符 |

**备注1：定位质量标志**

|          |                                               |
|:--------:|:---------------------------------------------:|
| **参数** |                   **说明**                    |
|    0     |               定位不可用或无效                |
|    1     |            SPS 定位模式，定位有效             |
|    6     | 估算模式（航位模式）仅NMEA 2.3 及以上版本有效 |

3.  <span id="_Toc1910" class="anchor"></span>**GLL**

|  |  |  |  |  |
|:--:|:--:|:--:|:--:|:--:|
| **信息** | **描述** | **类型** | **格式** | **示例** |
| GLL | 纬度、经度、定位时间与定位状态等信息 | 输出 | \$--GLL,lat,uLat,lon,uLon, UTCtime,valid,mode\*CS\<CR\> \<LF\> | \$GNGLL,2236.40101,N,11349.73472,E,073028.600,A,A\*45 |

|  |  |  |  |
|:--:|:--:|:--:|:--:|
| **格式** | **说明** | **实例** | **参数说明** |
| \$--GLL | 消息 ID | \$GPGLL | GLL 语句头，’--‘为系统标识 |
| lat | 纬度，前 2 字符表示度，后面的字符表示分 | 2236.40101 | 格式：度度分分.分分分分 |
| uLat | 纬度方向 | N | 北半球（N）或南半球（S） |
| lon | 经度，前3字符表示度，后面的字符表示分 | 11349.73472 | 格式：度度度分分.分分分分 |
| uLon | 经度方向 | E | 东（E）半球或西（W）半球 |
| UTCtime | 当前定位的UTC 时间 | 073028.600 | 格式：时时分分秒秒.秒秒秒（hhmmss.sss） |
| valid | 定位质量 | A | 参考：备注2 |
| mode | 定位模式 | A | 参考：备注3，仅NMEA 2.3 及以上版本有效 |
| CS | 校验和 | 45 | \$和\*之间（不包括\$和\*）所有字符的异或结果 |
| \<CR\> \<LF\> | 结束符 | \<CR\> \<LF\> | 回车与换行符 |

**备注2：定位质量标志**

|          |          |
|:--------:|:--------:|
| **参数** | **说明** |
|    A     | 数据有效 |
|    V     | 数据无效 |

**备注3：定位模式标志**

|          |                                        |
|:--------:|:--------------------------------------:|
| **参数** |                **说明**                |
|    A     |                自主模式                |
|    E     |          估算模式（航位推算）          |
|    N     |                数据无效                |
|    D     |                差分模式                |
|    M     | 未定位，但存在外部输入或历史保存的位置 |

4.  <span id="_Toc27386" class="anchor"></span>**GSA**

|  |  |  |  |  |
|:--:|:--:|:--:|:--:|:--:|
| **信息** | **描述** | **类型** | **格式** | **示例** |
| GSA | 用于定位的卫星编号与DOP信息。不管是否定位或者是否有可用卫星，都输出GSA语句；当接收机处于多系统联合工作时，每个系统的可用卫星对应一条 GSA 语句，每条 GSA 语句都包含根据组合卫星系统得到的PDOP、HDOP和 VDOP | 输出 | \$--GSA,smode,FS{,SVID},PDOP,HDOP,VDOP\*CS\<CR\>\<LF\> | \$GNGSA,A,3,11,13,15,18,20,24,29,194,195,199,,,1.4,0.8,1.1,1\*0C |

<table>
<colgroup>
<col style="width: 18%" />
<col style="width: 23%" />
<col style="width: 19%" />
<col style="width: 38%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>格式</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
<td style="text-align: center;"><strong>实例</strong></td>
<td style="text-align: center;"><strong>参数说明</strong></td>
</tr>
<tr>
<td style="text-align: center;">$--GSA</td>
<td style="text-align: center;">消息ID</td>
<td style="text-align: center;">$GNGSA</td>
<td style="text-align: center;">GSA语句头，’--‘为系统标识</td>
</tr>
<tr>
<td style="text-align: center;">smode</td>
<td style="text-align: center;">模式切换方式指示</td>
<td style="text-align: center;">A</td>
<td style="text-align: center;">参考：备注4</td>
</tr>
<tr>
<td style="text-align: center;">FS</td>
<td style="text-align: center;">定位状态标志</td>
<td style="text-align: center;">3</td>
<td style="text-align: center;">参考：备注5</td>
</tr>
<tr>
<td rowspan="4" style="text-align: center;">{,SVID}</td>
<td style="text-align: center;">卫星使用(信号频道1 )</td>
<td style="text-align: center;">11</td>
<td rowspan="4" style="text-align: center;">用于定位的卫星编号，该字段共显示12 颗可用卫星编号，多于12颗时只输出前12颗，不足12颗时不足的区域补空</td>
</tr>
<tr>
<td style="text-align: center;">卫星使用(信号频道2)</td>
<td style="text-align: center;">13</td>
</tr>
<tr>
<td style="text-align: center;">……</td>
<td style="text-align: center;">15,18,20,24,29,194,195,199,,</td>
</tr>
<tr>
<td style="text-align: center;">卫星使用(信号频道 12)</td>
<td style="text-align: center;"></td>
</tr>
<tr>
<td style="text-align: center;">PDOP</td>
<td style="text-align: center;">位置精度因子（PDOP）</td>
<td style="text-align: center;">1.4</td>
<td style="text-align: center;">范围：0.5 ~99.9</td>
</tr>
<tr>
<td style="text-align: center;">HDOP</td>
<td style="text-align: center;">水平精度因子（HDOP）</td>
<td style="text-align: center;">0.8</td>
<td style="text-align: center;">范围：0.5~99.9</td>
</tr>
<tr>
<td style="text-align: center;">VDOP</td>
<td style="text-align: center;">垂直精度因子（VDOP）</td>
<td style="text-align: center;">1.1</td>
<td style="text-align: center;">范围：0.5 ~ 99.9</td>
</tr>
<tr>
<td style="text-align: center;">systemId</td>
<td style="text-align: center;">NMEA所定义的GNSS 系统ID号</td>
<td style="text-align: center;">1</td>
<td style="text-align: center;">参考：备注6 ,仅NMEA 4.1及以上版本有效</td>
</tr>
<tr>
<td style="text-align: center;">CS</td>
<td style="text-align: center;">校验和</td>
<td style="text-align: center;">0C</td>
<td style="text-align: center;">$和*之间（不包括$和*）所有字符的异或结果</td>
</tr>
<tr>
<td style="text-align: center;">&lt;CR&gt; &lt;LF&gt;</td>
<td style="text-align: center;">结束符</td>
<td style="text-align: center;">&lt;CR&gt; &lt;LF&gt;</td>
<td style="text-align: center;">回车与换行符</td>
</tr>
</tbody>
</table>

**备注4：模式切换方式指示**

|          |                                         |
|:--------:|:---------------------------------------:|
| **参数** |                **说明**                 |
|    M     |    手动切换。强制为2D或者3D工作模式     |
|    A     | 自动切换。接收机自动切换 2D/3D 工作模式 |

**备注5：定位状态标志**

|          |          |
|:--------:|:--------:|
| **参数** | **说明** |
|    1     | 定位无效 |
|    2     |  2D定位  |
|    3     |  3D定位  |

**备注6：GNSS 系统 ID**

|          |             |
|:--------:|:-----------:|
| **参数** |  **说明**   |
|    1     |   GPS系统   |
|    2     | GLONASS系统 |
|    4     |   BDS系统   |

5.  <span id="_Toc24856" class="anchor"></span>**GSV**

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 16%" />
<col style="width: 9%" />
<col style="width: 19%" />
<col style="width: 45%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>信息</strong></td>
<td style="text-align: center;"><strong>描述</strong></td>
<td style="text-align: center;"><strong>类型</strong></td>
<td style="text-align: center;"><strong>格式</strong></td>
<td style="text-align: center;"><strong>示例</strong></td>
</tr>
<tr>
<td style="text-align: center;">GSV</td>
<td style="text-align: center;">可见卫星的卫星编号及其仰角、方位角、载噪比等信息。每条GSV语句中的{卫星编号,仰角,方位角,载噪比}参数组的数量可变，最多为4组，最少为0组</td>
<td style="text-align: center;">输出</td>
<td style="text-align: center;">$--GSV,numMsg,msgNo,numSv{,SVID,ele,az,cn0} *CS&lt;CR&gt; &lt;LF&gt;</td>
<td style="text-align: left;"><p>$GPGSV,3,1,12,05,37,054,17,11,18,134,21,13,42,032,25,15,66,347,28,0*62</p>
<p>$GPGSV,3,2,12,18,38,326,26,20,22,081,29,23,14,297,,24,42,168,30,0*62</p>
<p>$GPGSV,3,3,12,29,41,235,27,194,12,149,25,195,60,141,36,199,60,149,28,0*56</p>
<p>$BDGSV,4,1,13,03,,,30,04,,,27,06,45,176,27,10,26,213,27,0*70</p>
<p>$BDGSV,4,2,13,16,45,174,27,23,11,173,24,24,12,071,30,25,24,123,25,0*75</p>
<p>$BDGSV,4,3,13,28,64,214,30,38,53,022,26,39,56,166,29,40,,,20,0*41</p>
<p>$BDGSV,4,4,13,59,,,31,0*78</p></td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 18%" />
<col style="width: 16%" />
<col style="width: 44%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>格式</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
<td style="text-align: center;"><strong>实例</strong></td>
<td style="text-align: center;"><strong>参数说明</strong></td>
</tr>
<tr>
<td style="text-align: center;">$--GSV</td>
<td style="text-align: center;">消息ID</td>
<td style="text-align: center;">$GPGSV</td>
<td style="text-align: center;">GSV语句头，’--‘为系统标识</td>
</tr>
<tr>
<td style="text-align: center;">numMsg</td>
<td style="text-align: center;">语句总数</td>
<td style="text-align: center;">3</td>
<td style="text-align: center;">每条 GSV语句最多输出4颗可见卫星信息，因此，当该系统可见卫星多于4颗时，将需要多条GSV语句</td>
</tr>
<tr>
<td style="text-align: center;">msgNo</td>
<td style="text-align: center;">当前语句编号</td>
<td style="text-align: center;">1</td>
<td style="text-align: center;"></td>
</tr>
<tr>
<td style="text-align: center;">numSv</td>
<td style="text-align: center;">可见卫星总数</td>
<td style="text-align: center;">12</td>
<td style="text-align: center;"></td>
</tr>
<tr>
<td rowspan="9" style="text-align: center;">{,SVID,ele, az,cn0}</td>
<td style="text-align: center;">卫星编号</td>
<td style="text-align: center;">05</td>
<td rowspan="9" style="text-align: center;"><p>依次为: 卫星编号;</p>
<p>仰角，取值范围为0~90，单位是度;</p>
<p>方位角，取值范围为0~359，单位是度;</p>
<p>载噪比，取值范围为0~99，单位是dB-Hz，如果没有跟踪到当前卫星，补空</p></td>
</tr>
<tr>
<td style="text-align: center;">卫星仰角</td>
<td style="text-align: center;">37</td>
</tr>
<tr>
<td style="text-align: center;">卫星方位角</td>
<td style="text-align: center;">054</td>
</tr>
<tr>
<td style="text-align: center;">讯号噪声比(C/No)</td>
<td style="text-align: center;">17</td>
</tr>
<tr>
<td style="text-align: center;">……..</td>
<td style="text-align: center;">....</td>
</tr>
<tr>
<td style="text-align: center;">卫星编号</td>
<td style="text-align: center;">15</td>
</tr>
<tr>
<td style="text-align: center;">卫星仰角</td>
<td style="text-align: center;">66</td>
</tr>
<tr>
<td style="text-align: center;">卫星方位角</td>
<td style="text-align: center;">347</td>
</tr>
<tr>
<td style="text-align: center;">讯号噪声比(C/No)</td>
<td style="text-align: center;">28</td>
</tr>
<tr>
<td style="text-align: center;">signalId</td>
<td style="text-align: center;">NMEA 所定义的 GNSS 信号 ID</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">（0 代表全部信号）, 仅NMEA 4.1 及以上版本有效</td>
</tr>
<tr>
<td style="text-align: center;">CS</td>
<td style="text-align: center;">校验和</td>
<td style="text-align: center;">62</td>
<td style="text-align: center;">$和*之间（不包括$和*）所有字符的异或结果</td>
</tr>
<tr>
<td style="text-align: center;">&lt;CR&gt; &lt;LF&gt;</td>
<td style="text-align: center;">结束符</td>
<td style="text-align: center;">&lt;CR&gt; &lt;LF&gt;</td>
<td style="text-align: center;">回车与换行符</td>
</tr>
</tbody>
</table>

<span id="_Toc362283959" class="anchor"></span>

6.  **RMC**

|  |  |  |  |  |
|:--:|:--:|:--:|:--:|:--:|
| **信息** | **描述** | **类型** | **格式** | **示例** |
| RMC | 推荐的最小定位信息 | 输出 | \$--RMC,UTCtime,status,lat,uLat,lon,uLon,spd,cog,date,mv,mvE,mode\*CS\<CR\> \<LF\> | \$GNRMC,073028.600,A,2236.40101,N,11349.73472,E,0.00,0.00,090724,,,A,V\*00 |

<table>
<colgroup>
<col style="width: 17%" />
<col style="width: 25%" />
<col style="width: 12%" />
<col style="width: 44%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>格式</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
<td style="text-align: center;"><strong>实例</strong></td>
<td style="text-align: center;"><strong>参数说明</strong></td>
</tr>
<tr>
<td style="text-align: center;">$--RMC</td>
<td style="text-align: center;">消息ID</td>
<td style="text-align: center;">$GPRMC</td>
<td style="text-align: center;">RMC语句头，’--‘为系统标识</td>
</tr>
<tr>
<td style="text-align: center;">UTCtime</td>
<td style="text-align: center;">当前定位的UTC时间</td>
<td style="text-align: center;">073028.600</td>
<td style="text-align: center;">格式：时时分分秒秒.秒秒秒（hhmmss.sss）</td>
</tr>
<tr>
<td style="text-align: center;">status</td>
<td style="text-align: center;">位置有效标志</td>
<td style="text-align: center;">A</td>
<td style="text-align: center;"><p>V=接收机警告，数据无效</p>
<p>A=数据有效</p></td>
</tr>
<tr>
<td style="text-align: center;">lat</td>
<td style="text-align: center;">纬度，前2字符表示度，后面的字符表示分</td>
<td style="text-align: center;">2236.40101</td>
<td style="text-align: center;">格式:度度分分.分分分分</td>
</tr>
<tr>
<td style="text-align: center;">uLat</td>
<td style="text-align: center;">纬度方向</td>
<td style="text-align: center;">N</td>
<td style="text-align: center;">北半球（N）或南半球（S）</td>
</tr>
<tr>
<td style="text-align: center;">lon</td>
<td style="text-align: center;">经度，前3字符表示度，后面的字符表示分</td>
<td style="text-align: center;">11349.73472</td>
<td style="text-align: center;">格式:度度度分分.分分分分</td>
</tr>
<tr>
<td style="text-align: center;">uLon</td>
<td style="text-align: center;">经度方向</td>
<td style="text-align: center;">E</td>
<td style="text-align: center;">东（E）半球或西（W）半球</td>
</tr>
<tr>
<td style="text-align: center;">spd</td>
<td style="text-align: center;">对地速度</td>
<td style="text-align: center;">0.00</td>
<td style="text-align: center;">单位为节</td>
</tr>
<tr>
<td style="text-align: center;">cog</td>
<td style="text-align: center;">对地真航向</td>
<td style="text-align: center;">0.00</td>
<td style="text-align: center;">单位为度</td>
</tr>
<tr>
<td style="text-align: center;">date</td>
<td style="text-align: center;">日期</td>
<td style="text-align: center;">090724</td>
<td style="text-align: center;">格式:日日月月年年</td>
</tr>
<tr>
<td style="text-align: center;">mv</td>
<td style="text-align: center;">磁偏角</td>
<td style="text-align: center;"></td>
<td style="text-align: center;">单位为度。固定为空</td>
</tr>
<tr>
<td style="text-align: center;">mvE</td>
<td style="text-align: center;">磁偏角方向</td>
<td style="text-align: center;"></td>
<td style="text-align: center;">E-东，W-西。固定为空</td>
</tr>
<tr>
<td style="text-align: center;">mode</td>
<td style="text-align: center;">定位模式标志</td>
<td style="text-align: center;">A</td>
<td style="text-align: center;">参考：备注7，仅NMEA2.3及以上版本有效</td>
</tr>
<tr>
<td style="text-align: center;">navStatus</td>
<td style="text-align: center;">导航状态标示符</td>
<td style="text-align: center;">V</td>
<td style="text-align: center;">(V 表示系统不输出导航状态信息）仅NMEA 4.1 及以上版本有效</td>
</tr>
<tr>
<td style="text-align: center;">CS</td>
<td style="text-align: center;">校验和</td>
<td style="text-align: center;">00</td>
<td style="text-align: center;">$和*之间（不包括$和*）所有字符的异或结果</td>
</tr>
<tr>
<td style="text-align: center;">&lt;CR&gt; &lt;LF&gt;</td>
<td style="text-align: center;">结束符</td>
<td style="text-align: center;">&lt;CR&gt; &lt;LF&gt;</td>
<td style="text-align: center;">回车与换行符</td>
</tr>
</tbody>
</table>

**备注7：定位模式标志**

|          |                                        |
|:--------:|:--------------------------------------:|
| **参数** |                **说明**                |
|    A     |                自主模式                |
|    E     |          估算模式（航位推算）          |
|    N     |                数据无效                |
|    D     |                差分模式                |
|    M     | 未定位，但存在外部输入或历史保存的位置 |

7.  <span id="_Toc24651" class="anchor"></span>**VTG**

|  |  |  |  |  |
|:--:|:--:|:--:|:--:|:--:|
| **信息** | **描述** | **类型** | **格式** | **示例** |
| VTG | 对地速度与对地航向信息 | 输出 | \$--VTG,cogt,T,cogm,M,sog,N,kph,K,mode\*CS\<CR\> \<LF\> | \$GNVTG,0.00,T,,M,0.00,N,0.00,K,A\*23 |

**表 10：VTG数据格式**

|  |  |  |  |
|:--:|:--:|:--:|:--:|
| **格式** | **说明** | **实例** | **参数说明** |
| \$--VTG | 消息 ID | \$GPVTG | VTG语句头，’--‘为系统标识 |
| cogt | 对地真北航向 | 0.00 | 单位为度，范围：000-359度 |
| T | 真北指示 | T | 固定为T |
| cogm | 对地磁北航向 |  | 单位为度，范围：000 - 359 度 |
| M | 磁北指示 | M | 固定为M |
| sog | 对地速度 | 0.00 | 单位为节，范围：00.0-999.9节 |
| N | 速度单位节 | N | 固定为N |
| kph | 对地速度 | 0.00 | 单位为千米每小时，00.0至1851 公里／小时 |
| K | 速度单位 | K | 千米每小时，固定为K |
| mode | 定位模式标志 | A | 参考：备注8，仅NMEA 2.3及以上版本有效 |
| CS | 校验和 | 23 | \$和\*之间（不包括\$和\*）所有字符的异或结果 |
| \<CR\> \<LF\> | 结束符 | \<CR\> \<LF\> | 回车与换行符 |

**备注8：定位模式标志**

|          |                                        |
|:--------:|:--------------------------------------:|
| **参数** |                **说明**                |
|    A     |                自主模式                |
|    E     |          估算模式（航位推算）          |
|    N     |                数据无效                |
|    D     |                差分模式                |
|    M     | 未定位，但存在外部输入或历史保存的位置 |

8.  <span id="_Toc1474" class="anchor"></span>**ZDA**

|  |  |  |  |  |
|:--:|:--:|:--:|:--:|:--:|
| **信息** | **描述** | **类型** | **格式** | **示例** |
| ZDA | 时间与日期信息 | 输出 | \$--ZDA,UTCtime,day,month,year,ltzh,ltzn\*CS\<CR\>\<LF\> | \$GNZDA,073030.200,09,07,2024,00,00\*47 |

**表 10：ZDA数据格式**

|  |  |  |  |
|:--:|:--:|:--:|:--:|
| **格式** | **说明** | **实例** | **参数说明** |
| \$--ZDA | 消息ID | \$GNZDA | ZDA语句头，’--‘为系统标识 |
| UTCtime | 当前定位的UTC 时间 | 073030.200 | 格式：时时分分秒秒.秒秒秒（hhmmss.sss） |
| day | 日 | 09 | 固定两位数字，取值范围01~31 |
| month | 月 | 07 | 固定两位数字，取值范围01~12 |
| year | 年 | 2024 | 固定四位数字 |
| ltzh | 本时区小时 | 00 | 不支持，固定为00 |
| ltzn | 本时区分钟 | 00 | 不支持，固定为00 |
| CS | 校验和 | 47 | \$和\*之间（不包括\$和\*）所有字符的异或结果 |
| \<CR\> \<LF\> | 结束符 | \<CR\> \<LF\> | 回车与换行符 |

9.  <span id="_Toc2595" class="anchor"></span>**TXT**

|  |  |  |  |  |
|:--:|:--:|:--:|:--:|:--:|
| **信息** | **描述** | **类型** | **格式** | **示例** |
| TXT | 产品信息 | 输出，开机时输出一次 | \$GPTXT,xx,yy,zz,info\*hh\<CR\> \<LF\> | \$GPTXT,01,01,01,ANTENNA OPEN\*25 |

**表 10：ZDA数据格式**

<table>
<colgroup>
<col style="width: 18%" />
<col style="width: 17%" />
<col style="width: 19%" />
<col style="width: 44%" />
</colgroup>
<tbody>
<tr>
<td style="text-align: center;"><strong>格式</strong></td>
<td style="text-align: center;"><strong>说明</strong></td>
<td style="text-align: center;"><strong>实例</strong></td>
<td style="text-align: center;"><strong>参数说明</strong></td>
</tr>
<tr>
<td style="text-align: center;">$GPTXT</td>
<td style="text-align: center;">消息 ID</td>
<td style="text-align: center;">$GPTXT</td>
<td style="text-align: center;">TXT语句头，’--‘为系统标识</td>
</tr>
<tr>
<td style="text-align: center;">xx</td>
<td style="text-align: center;">当前消息的语句总数</td>
<td style="text-align: center;">01</td>
<td style="text-align: center;">范围：01~99，如果某个消息过长，需要分为多条信息显示</td>
</tr>
<tr>
<td style="text-align: center;">yy</td>
<td style="text-align: center;">语句编号</td>
<td style="text-align: center;">1</td>
<td style="text-align: center;">范围：01~99</td>
</tr>
<tr>
<td style="text-align: center;">zz</td>
<td style="text-align: center;">文本识别符</td>
<td style="text-align: center;">01</td>
<td style="text-align: center;"><p>00=错误信息；</p>
<p>01=警告信息；</p>
<p>02=通知信息；</p>
<p>07=用户信息。</p></td>
</tr>
<tr>
<td style="text-align: center;">info</td>
<td style="text-align: center;">文本信息</td>
<td style="text-align: center;">ANTENNA OPEN</td>
<td style="text-align: center;"><p>ANTENNA OPEN=天线开路</p>
<p>ANTENNA OK=天线良好</p>
<p>ANTENNA SHORT=天线短路</p></td>
</tr>
<tr>
<td style="text-align: center;">CS</td>
<td style="text-align: center;">校验和</td>
<td style="text-align: center;">25</td>
<td style="text-align: center;">$和*之间（不包括$和*）所有字符的异或结果</td>
</tr>
<tr>
<td style="text-align: center;">&lt;CR&gt; &lt;LF&gt;</td>
<td style="text-align: center;">结束符</td>
<td style="text-align: center;">&lt;CR&gt; &lt;LF&gt;</td>
<td style="text-align: center;">回车与换行符</td>
</tr>
</tbody>
</table>

10. <span id="_Toc1954" class="anchor"></span>**GST**

|  |  |  |  |  |
|:--:|:--:|:--:|:--:|:--:|
| **信息** | **描述** | **类型** | **格式** | **示例** |
| GST | 接收机伪距的测量精度详细信息 | 输出 | \$--GST,UTCtime,RMS,stdDevMaj,stdfDevMin,orientation,stdLat,stdLon,stdAlt\* CS\<CR\>\<LF\> | \$GMGST,102017.000,0.0,68.0,14.7,108.6,35.9,74.8,66.1\*4A |

|  |  |  |  |
|:--:|:--:|:--:|:--:|
| **格式** | **说明** | **实例** | **参数说明** |
| \$--GST | 消息ID | \$GMGST | GST语句头，’--‘为系统标识 |
| UTCtime | 当前消息的语句 | 102017.000 | 格式：时时分分秒秒.秒秒秒（hhmmss.sss） |
| RMS | 定位过程中接收机伪距误差标准差的RMS值 | 0.0 | 单位米 |
| stdDevMaj | 接收机椭圆半长轴方向的位置标准差 | 68.0 | 不支持 |
| stdfDevMin | 接收机椭圆半短轴方向的位置标准差 | 14.7 | 不支持 |
| orientation | 接收机椭圆半长轴方向的朝向 | 108.6 | 不支持 |
| stdLat | 接收机纬度向误差的标准差 | 35.9 | 单位米 |
| stdLon | 接收机经度向误差的标准差 | 74.8 | 单位米 |

|  |  |  |  |
|:--:|:--:|:--:|:--:|
| stdAlt | 接收机高度向误差的标准差 | 66.1 | 单位米 |
| CS | 校验和 | 4A | \$和\*之间（不包括\$和\*）所有字符的异或结果 |
| \<CR\> \<LF\> | 结束符 | \<CR\>\<LF\> | 回车与换行符 |
