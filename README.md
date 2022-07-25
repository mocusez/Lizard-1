# Lizard

![](https://img.shields.io/badge/language-python3.x-informational?style=flat&logo=python&logoColor=white&color=2bbc8a)
![](https://img.shields.io/badge/features-convenient-informational?style=flat&color=2bbc8a)
![](https://img.shields.io/badge/--informational?style=flat&logo=Linux&logoColor=white&color=2bbc8a)

Lizard是一款基于python的全自动化渗透脚本，小巧轻便，功能丰富，可在多平台快速部署；整体采用模块化设计，可自行改装

功能
----
* 嗅探：端口扫描、IP探测、ssh爆破、shodan扫描、网站目录后台扫描、whois查询，poc检测
    * 目前可支持的poc有：
    * cve_2016_0638
    * cve_2016_3510
    * cve_2017_10271
    * cve_2017_3248
    * cve_2017_3506
    * cve_2018_2628
    * cve_2018_2893
    * cve_2018_2894
    * cve_2018_3191
    * cve_2018_3245
    * cve_2018_3252
    * cve_2019_2618
    * cve_2019_2725
    * cve_2019_2729
    * cve_2019_2888
    * cve_2019_2890
    * cve_2020_14750
    * cve_2020_14882
    * cve_2020_14883
    * cve_2020_2551
    * cve_2020_2555
    * cve_2020_2883
    * （不断更新中）
* webshell一句话连接（目前只支持模拟终端功能，以后会完善）
* dos攻击，ddos攻击(外接模块，需要python2，python3的正在开发中)
* exp利用
    * 目前支持的exp有：
    * cve-2022-21907
    * cve-2018-9995
    * （不断更新中）

已测试环境
------
* Windows
* kali Linux
* termux(Android)
* Debian

安装
--
      git clone https://github.com/wr0x00/Lizard
使用
---
       python lizard.py --help
* -m 连接MySQL，依次输入地址，用户名，密码
   * 例：python lizard.py -m localhost root 1234
* -sp 扫描端口，输入IP
   * 例：python lizard.py -sp 192.168.1.1
* -whois whois查询，输入网址
   * 例：python lizard.py -whois www.xxx.com
* -shodan shodan关键字批量搜索IP，也可单个扫描端口
   * 例：python lizard.py -shodan abc
   * 例：python lizard.py -shodan 192.168.1.1
* -sw 扫描网站目录，输入网址,-d指定字典,默认字典dict.txt,-t指定线程，默认60
   * 例：python lizard.py -sw www.xxx.com (-d xxx.txt)(-t xx)
* -ssh ssh爆破，-rh指定地址，-u指定用户(默认root)，-rp指定端口（默认22），-d指定字典（默认modules\pwddic\password\top1000.txt）
   * 例：python lizard.py -ssh -rp 192.168.1.1 (-u xxx -rp xx -d xxx.txt)
* -webshell 连接php,asp一句话，依次输入网址、密码
   * 例：python lizard.py -webshell www.xxx.com/abc.php 123
* -ddos ddos攻击
   * 例：python lizard.py -ddos
* -exp -指定多个exp(漏洞名称去掉cve后面短横，写成cveXXXX-XXXX格式) -expip目标ip
   * 例：python lizard.py -exp cve2018-9995 -expip xxx.xxx.xxx.xxx
   * 例：python lizard.py -exp cve2018-9995 cve2022-21907 -expip xxx.xxx.xxx.xxx

顺便吐槽一下pxssh不支持windows,塌蚂的
