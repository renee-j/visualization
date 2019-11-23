#### 垃圾分类

##### 代码

> setwd("~/Desktop")

> library(ggplot2)

> library(readxl)

> garbage <- read_excel("garbage.xlsx")

> p <- ggplot(garbage, aes(x = 年份,y = 数值))

> p

> p + geom_bar(aes(colour = factor(项目)),stat="identity",width=0.5)

[处理后的数据xlsx](https://github.com/renee-j/visualization/blob/master/R绘图/garbage.xlsx)

原图：
![原图](https://github.com/renee-j/visualization/blob/master/garbage%20classification/WeChatb77706e407131678dbd9fe659ccd3d0c.png)

重新制图：
![R绘图](https://github.com/renee-j/visualization/blob/master/R绘图/垃圾分类.png)

说明：

按照原图重新制图无法显示双y轴，于是没有把无害化处理率计入，同时用r语言写内容制图无法显示中文字符……红色框是堆肥，绿色是焚烧，无框线是卫生填埋的处理量，单位均为万吨。

