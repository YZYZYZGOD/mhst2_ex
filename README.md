# mhst2_ex
怪物猎人物语2毁灭之翼(monsterhunterstories2)的解包过程
# 前言
本文用来记录自己是如何解包怪物猎人物语2：毁灭之翼(以下简称MHST2)并提取其中的文本的。  
# 所需工具
MHST2游戏文件一份(需使用XCI格式，若不是XCI格式，将其转换成XCI格式，转换方式暂略)  
[Cirilla Toolkit.exe](https://www.nexusmods.com/monsterhunterworld/mods/110):从gmd文件提取文本的软件。  
[XCI2TitleConverter.zip]()将XCI文件完美解包出NCA的文件，解压备用  
[XCI_NCA_NSP_v2.rar]()将XCI/NCA/NSP解包的软件，解压备用，若是没有上面的那个也可以尝试使用这个。  
[arc.py](https://github.com/svanheulen/mhff/blob/6ef14c8ffa341ccbe44e0e6a93eb4bfe541265cf/n3ds/arc.py)，链接为原版，本文所使用的是有[@Easy World](https://github.com/easyworld)大佬修改后的版本。  
汉化包 


---
# 具体步骤
## 解包
1.使用游戏信息查看软件(这里使用```NSGame Manager```)查询游戏的```TID```(MHST2欧版1.0.1的为```0100E21011446000```)，并复制备用。  
2.打开```XCI2TitleConverter.exe```，并按照如图所示填好内容，选择要解包的文件，点击```start```开始解包，等待一段时间。[![RbBQlq.png](https://z3.ax1x.com/2021/07/07/RbBQlq.png)](https://imgtu.com/i/RbBQlq)  
3.打开```XCI_NCA_NSP_v2```文件夹，在```XCI2TitleConverter.exe```所在文件夹中的```temp```文件夹中找到刚刚解包的文件，将最大的那个```nca文件```拖到```Drag_XCI_NCA_NSP_HERE.bat```，并等待一段时间。  
4.当```Drag_XCI_NCA_NSP_HERE.bat```显示为Done时即解包结束，解包的文件存在同目录下的```ncaDecrypted```文件夹中。  
## 分析解包文件
根据分析，发现所需的文本文件基本都存在```nativeNXx64\archive\message```文件夹中，该文件夹中包含各个语言版本的全部文本文件。  
## 提取文件
> 由于本次解包使用的是欧版的游戏软件，不支持中文，因此也没有中文的语言包。因此使用[ 「高达合购群首发」怪物猎人物语2欧版中文版](https://www.91wii.com/thread-252198-1-1.html)所提供的汉化包，感谢高达合购群一直以来第一时间无私发布各种游戏资源，以及[XXGAME.NET汉化组](http://www.xxgame.net/Chinese)一直以来的汉化工作，以及XXGAME.NET汉化组 伸手党的骄傲大佬提供的汉化包。  

1.将```arc.py```复制到```message_chS.arc```所在文件夹，进入命令行操作，在命令行输入```python arc.py x message_chS.arc```回车解arc包(若电脑中同时安装了python2和python3，需注意使用python3运行)。这个过程很快，解压完后会得到一个message文件夹，文本内容就在里面。[![RbyfIS.png](https://z3.ax1x.com/2021/07/07/RbyfIS.png)](https://imgtu.com/i/RbyfIS)  
2.发现文本文件的格式为*.gmd格式，和MHW的文本格式一致，于是使用```Cirilla Toolkit.exe```提取文本内容。  
3.打开```Cirilla Toolkit.exe```，左上角```File --> Open```找到gmd文件所在目录，选择相应文件，打开(也可直接将gmd文件拖拽到程序界面)。这里以道具名称(ItemName_chS.gme)为例。[![RbsgNF.png](https://z3.ax1x.com/2021/07/07/RbsgNF.png)](https://imgtu.com/i/RbsgNF)  
4.在打开文件后的程序中，点选```Entries --> Import/Exprort CSV --> Export values to CSV```在弹出的页面中选导出的csv文件所要保存的路径以及名称。之后即可在文件夹中看到导出的csv文件。[![RbyA3j.png](https://z3.ax1x.com/2021/07/07/RbyA3j.png)](https://imgtu.com/i/RbyA3j)  
[![RbyVvn.png](https://z3.ax1x.com/2021/07/07/RbyVvn.png)](https://imgtu.com/i/RbyVvn)  
5.打开导出的csv文件如图，可以编辑csv文件
[![RbyEgs.png](https://z3.ax1x.com/2021/07/07/RbyEgs.png)](https://imgtu.com/i/RbyEgs)
