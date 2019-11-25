#### 垃圾分类

##### 代码

> setwd("~/Desktop")

> library(ggplot2)

> library(readxl)

> garbage <- read_excel("garbage.xlsx",sheet=1)
                                                                                                 
> p <- ggplot(garbage, aes(x = date,y = number,fill=mode))

> p + geom_bar(aes(colour = factor(mode)),stat="identity",width=0.5) + scale_fill_manual(values=c('#999999','#f9f2ff','#555555'))

> garbage2 <- read_excel("garbage.xlsx",sheet=2)
                                                                                                 
> p2 <- ggplot(garbage2, aes(x = date,y = percent,group=1))

> p2 + geom_line() + geom_point(size=2, shape=5) + geom_text(aes(label=percent),vjust=-1.5)

##### 垃圾分类

原图：
![原图](https://github.com/renee-j/visualization/blob/master/garbage%20classification/WeChatb77706e407131678dbd9fe659ccd3d0c.png)

重新制图：
![R绘图](https://github.com/renee-j/visualization/blob/master/R绘图/WechatIMG5.png)
![R绘图](https://github.com/renee-j/visualization/blob/master/R绘图/折线.png)

说明：

按照原图重新制图无法显示双y轴，于是没有把无害化处理率计入，单画了无害化处理率，不知道为什么，调整了数据的位置以后只要高一点点97.7就无法完整显示，图表仿佛y轴到了100就被截断了。同时用r语言写内容制图无法显示中文字符……就对处理方法重新进行了命名。单位均为万吨。（与第一张图在2011年稍有出入，最开始的图自己是用ps手绘的，可能出现了一些问题……）

##### 未成年人犯罪

代码：

> crime <- read_excel("young crime.xlsx",sheet = 1)

> pc <- ggplot(crime, aes(x = age,y = numbers))

> pc + geom_bar(aes(colour = factor(numbers)),stat="identity",width=0.5)

> pc + geom_bar(stat="identity",width=0.5)

> crime2 <- read_excel("young crime.xlsx",sheet = 2)

> pc2 <- ggplot(crime2, aes(x = charge,y = numbers,fill=ages))

> pc2 + geom_bar(aes(colour = factor(ages)),stat="identity",width=0.5) + coord_flip() + scale_fill_manual(values=c('#990000','#999999'))

原图：
![原图2](https://github.com/renee-j/visualization/blob/master/young%20crime/图2.png)

重新制图：
![R绘图2](https://github.com/renee-j/visualization/blob/master/R绘图/年龄分布.png)
![R绘图3](https://github.com/renee-j/visualization/blob/master/R绘图/WechatIMG7.png)

说明：

原来一个图表示了两个图的信息，但用r写的时候就不知道该如何合到一起了orz……思考呈现方式的时候发现，这张图表和垃圾分类的图表在实质的呈现形式上没有区别，因为原图更想体现的是比例，但当呈现形式被固定后好像也落入了柱状图的泥淖，但自己剩下的两张图数据更无法用r处理于是就出了两个柱状图，还不知道如何让柱横过来……（r可以直观呈现比例嘛？）另外，因为原数据无法直接被r处理，所以自己这次两个制图都提前在excel里对数据进行了加工，把年龄和犯罪情况、数量和比率两个数据分列到了两个表里，不知道有没有什么更好地处理方式。（也是因为之前是自己手工制图，所以14岁以下的数据缺失在原图里有所表达，但r制图的时候就不知道如何是好了。）
