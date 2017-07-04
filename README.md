## Find-Train-Ticket-Check-in

### 开发背景
来自于[ecmadao](https://github.com/ecmadao)的项目 [Train-12306](https://github.com/ecmadao/Train-12306) 的启发

PS:检票口的查询其实是一个用户的硬伤，目前高铁动车在打印火车票时会写上检票口的名称
市面上了解到的是路路通的APP可以提供部分的列车的检票口查询，应该是有对应的数据接口支持。

原由：近日多地大雨导致铁路多趟列车停运，自己关注成都铁路12306微信公众号，发现一个新的侯乘信息查询功能。
该功能提供了动车和高铁的列车检票口的信息，正好圆了自己的之前挖的坑建的这个仓库。
微信公众号地址：http://kf.cd-rail.com/CTKF/CTZX/view/mainFrame/wx_hcxx.html

### 开发环境

腾讯云服务器  python 2.7.6

### 第三方依赖

[prettytable](https://pypi.python.org/pypi/PrettyTable/0.7.2)

[click](https://pypi.python.org/pypi/click/6.7)


### 做出来的效果

1. 车次查询
```bash
ubuntu@VM-68-117-ubuntu:~/maling/workspace/FindTrainTicketCheck-in$ python run.py 
查询车站 [成都东站]: 成都东站
查询车次 []: D368
查询日期 [20170704]: 20170704
+------+--------+------+-------+--------+-----------+----------+
| 车次 |  始发  | 终到 |  发时 | 检票口 |   候车区  | 检票状态 |
+------+--------+------+-------+--------+-----------+----------+
| D368 | 成都东 | 武汉 | 10:55 | B8、B9 | 2层候车区 | 停止检票 |
+------+--------+------+-------+--------+-----------+----------+
ubuntu@VM-68-117-ubuntu:~/maling/workspace/FindTrainTicketCheck-in$ 

```
2. 车站查询
```bash
ubuntu@VM-68-117-ubuntu:~/maling/workspace/FindTrainTicketCheck-in$ python run.py 
查询车站 [成都东站]: 
查询车次 []: 
查询日期 [20170704]: 
+-------+--------+----------+-------+-------------------+---------------------+----------+
|  车次 |  始发  |   终到   |  发时 |       检票口      |        候车区       | 检票状态 |
+-------+--------+----------+-------+-------------------+---------------------+----------+
| G8541 | 成都东 |  重庆北  | 21:00 | A12、A13,B12、B13 |      2层候车区      | 正在检票 |
| D5180 | 成都东 |  广安南  | 21:03 |   A4、A5,B4、B5   |      2层候车区      | 正在检票 |
| G8543 | 成都东 |  重庆北  | 21:40 | A14、A15,B14、B15 |      2层候车区      | 未开检票 |
| D2244 | 成都东 |   福州   | 06:44 |       A6、A7      |      2层候车区      | 停止检票 |
| D2202 | 成都东 |   郑州   | 07:05 |       A8、A9      |      2层候车区      | 停止检票 |
|  D638 | 成都东 | 上海虹桥 | 07:12 |       B6、B7      |      2层候车区      | 停止检票 |
|  G308 | 成都东 |  北京西  | 07:18 |         A1        | 1层候车区,2层候车区 | 停止检票 |
| D5176 | 成都东 |  广安南  | 07:30 |       A2、A3      |      2层候车区      | 停止检票 |
| D2224 | 成都东 |  杭州东  | 07:36 |       A4、A5      |      2层候车区      | 停止检票 |
| G8501 | 成都东 |  重庆北  | 07:41 |      A24、A25     |      2层候车区      | 停止检票 |
| D5124 | 成都东 |   阆中   | 07:48 |       检票口      |      2层候车区      | 停止检票 |
| G1318 | 成都东 |  广州南  | 07:54 |       B4、B5      |      2层候车区      | 停止检票 |
|  D954 | 成都东 |   上海   | 08:00 |       A8、A9      |      2层候车区      | 停止检票 |
|  D354 | 成都东 | 上海虹桥 | 08:12 |       A6、A7      |      2层候车区      | 停止检票 |
| G8701 | 成都东 |  万州北  | 08:22 |      A26,B26      |      2层候车区      | 停止检票 |
| D2256 | 成都东 |  南京南  | 08:30 |       B4、B5      |      2层候车区      | 停止检票 |
| G8603 | 成都东 |  隆昌北  | 08:31 |      A10、A11     |      2层候车区      | 停止检票 |
|  D364 | 成都东 |   武汉   | 08:40 |       B8、B9      |      2层候车区      | 停止检票 |
| D2264 | 成都东 |  杭州东  | 09:05 |       A6、A7      |      2层候车区      | 停止检票 |
| D2238 | 成都东 |   南昌   | 09:11 |       A4、A5      |      2层候车区      | 停止检票 |
|  G314 | 成都东 |  广州南  | 09:17 |       B8、B9      |      2层候车区      | 停止检票 |
| G8751 |  德阳  |  重庆北  | 09:24 |      A24、A25     |      2层候车区      | 停止检票 |
| D2374 | 成都东 |  南京南  | 09:29 |       A2、A3      |      2层候车区      | 停止检票 |
| G8503 | 成都东 |  重庆北  | 09:33 |      A10、A11     |      2层候车区      | 停止检票 |
| G8505 | 成都东 |  重庆北  | 09:56 |      A14、A15     |      2层候车区      | 停止检票 |
| D5186 | 成都东 |   达州   | 10:14 |       A4、A5      |      2层候车区      | 停止检票 |
| G8607 | 成都东 |  资中北  | 10:15 |      A22、A23     |      2层候车区      | 停止检票 |
| D2260 | 成都东 |   汉口   | 10:20 |       A6、A7      |      2层候车区      | 停止检票 |
| D5196 | 成都东 |   达州   | 10:27 |       A8、A9      |      2层候车区      | 停止检票 |
| G8507 | 成都东 |  重庆北  | 10:33 |      A12、A13     |      2层候车区      | 停止检票 |
|  D368 | 成都东 |   武汉   | 10:55 |       B8、B9      |      2层候车区      | 停止检票 |
| G8705 | 成都东 |  万州北  | 10:57 |      A14、A15     |      2层候车区      | 停止检票 |
| G8509 | 成都东 |  重庆北  | 11:30 |      A12、A13     |      2层候车区      | 停止检票 |
| D5116 | 成都东 |   南部   | 11:43 |       B2、B3      |      2层候车区      | 停止检票 |
| G8511 | 成都东 |  重庆北  | 11:45 |      A10、A11     |      2层候车区      | 停止检票 |
| G8513 | 成都东 |  重庆北  | 12:13 |      A14、A15     |      2层候车区      | 停止检票 |
| D5172 | 成都东 |  广安南  | 12:30 |       B4、B5      |      2层候车区      | 停止检票 |
| G8515 | 成都东 |  重庆北  | 12:50 |      A10、A11     |      2层候车区      | 停止检票 |
| G8709 | 成都东 |  万州北  | 13:08 |      A12、A13     |      2层候车区      | 停止检票 |
| G8517 | 成都东 |  重庆北  | 13:35 |      A14、A15     |      2层候车区      | 停止检票 |
| D5178 | 成都东 |  广安南  | 13:47 |       A8、A9      |      2层候车区      | 停止检票 |
| G8519 | 成都东 |  重庆北  | 13:59 |      A12、A13     |      2层候车区      | 停止检票 |
| G8521 | 成都东 |  重庆北  | 14:24 |      A14、A15     |      2层候车区      | 停止检票 |
| D5188 | 成都东 |   达州   | 14:35 |       A8、A9      |      2层候车区      | 停止检票 |
| G8713 | 成都东 |  万州北  | 14:59 |      A10、A11     |      2层候车区      | 停止检票 |
| D5128 | 成都东 |   广元   | 15:16 |       A2、A3      |      2层候车区      | 停止检票 |
| G8523 | 成都东 |  重庆北  | 15:21 |      A12、A13     |      2层候车区      | 停止检票 |
| G8717 | 成都东 |  万州北  | 15:49 |      A14、A15     |      2层候车区      | 停止检票 |
| D5164 | 成都东 |   遂宁   | 16:02 |       A8、A9      |      2层候车区      | 停止检票 |
| G8525 | 成都东 |  重庆北  | 16:05 |      A10、A11     |      2层候车区      | 停止检票 |
| D5190 | 成都东 |   达州   | 16:09 |       A4、A5      |      2层候车区      | 停止检票 |
| G8527 | 成都东 |  重庆北  | 16:32 |      A12、A13     |      2层候车区      | 停止检票 |
| D5192 | 成都东 |   达州   | 16:50 |   A6、A7,B6、B7   |      2层候车区      | 停止检票 |
| D5160 | 成都东 |   武胜   | 16:56 |         A1        | 1层候车区,2层候车区 | 停止检票 |
| G8721 | 成都东 |  万州北  | 17:05 |      A10、A11     |      2层候车区      | 停止检票 |
| G8529 | 成都东 |  重庆北  | 17:23 |      A12、A13     |      2层候车区      | 停止检票 |
| G8531 | 成都东 |  重庆北  | 17:53 |      A12、A13     |      2层候车区      | 停止检票 |
| D5174 | 成都东 |  广安南  | 17:49 |         A1        | 1层候车区,2层候车区 | 停止检票 |
| G8533 | 成都东 |  重庆北  | 18:14 |      A10、A11     |      2层候车区      | 停止检票 |
| D5102 | 成都东 |   丰都   | 18:36 |         A1        | 1层候车区,2层候车区 | 停止检票 |
| D5156 | 成都东 |   营山   | 18:44 |       A4、A5      |      2层候车区      | 停止检票 |
| G8752 | 重庆北 |   德阳   | 18:42 |      A10、A11     |      2层候车区      | 停止检票 |
| G8535 | 成都东 |  重庆北  | 19:35 |      A14、A15     |      2层候车区      | 停止检票 |
| G8537 | 成都东 |  重庆北  | 19:52 |      A10、A11     |      2层候车区      | 停止检票 |
| D5194 | 成都东 |   达州   | 20:03 |       B4、B5      |      2层候车区      | 停止检票 |
| G8539 | 成都东 |  重庆北  | 20:41 |      A10、A11     |      2层候车区      | 停止检票 |
+-------+--------+----------+-------+-------------------+---------------------+----------+

```

### TODO

- [x] 简单交互查询
- [ ] 历史数据保存，做数据分析，提供检票口的分布概率，做一些预测工作
- [ ] 原来功能在微信公众号，考虑是否有更为方便的载体提供？
- [ ] and so on
