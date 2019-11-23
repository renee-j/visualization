#### 垃圾分类

##### 代码

> setwd("~/Desktop")
> library(ggplot2)
> library(readxl)
> garbage <- read_excel("garbage.xlsx")
> p <- ggplot(garbage, aes(x = 年份,y = 数值))
> p
> p + geom_bar(aes(colour = factor(项目)),stat="identity",width=0.5)

[处理后的数据形式](https://github.com/renee-j/visualization/blob/master/R绘图/garbage.xlsx)
![原图](https://github.com/renee-j/visualization/blob/master/garbage%20classification/WeChatb77706e407131678dbd9fe659ccd3d0c.png)
![R绘图](https://github.com/renee-j/visualization/blob/master/R绘图/垃圾分类.png)
