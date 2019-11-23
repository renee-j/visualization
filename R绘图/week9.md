#### 垃圾分类

##### 代码

> setwd("~/Desktop")

> library(ggplot2)

> library(readxl)

> garbage <- read_excel("garbage.xlsx")
                                                                                                 
> p <- ggplot(garbage, aes(x = date,y = number))

> p + geom_bar(aes(colour = factor(mode)),stat="identity",width=0.5)

##### 垃圾分类

原图：
![原图](https://github.com/renee-j/visualization/blob/master/garbage%20classification/WeChatb77706e407131678dbd9fe659ccd3d0c.png)

重新制图：
![R绘图](https://github.com/renee-j/visualization/blob/master/R绘图/垃圾分类.png)

说明：

按照原图重新制图无法显示双y轴，于是没有把无害化处理率计入，同时用r语言写内容制图无法显示中文字符……就对处理方法重新进行了命名。单位均为万吨。（与第一张图在2011年稍有出入，最开始的图自己是用ps手绘的，可能出现了一些问题……）

##### 未成年人犯罪

原图：
![原图2](https://github.com/renee-j/visualization/blob/master/young%20crime/图2.png)

重新制图：
![R绘图2](https://github.com/renee-j/visualization/blob/master/R绘图/年龄分布.png)
![R绘图3](https://github.com/renee-j/visualization/blob/master/R绘图/犯罪情况.png)

说明：
原来两个图
