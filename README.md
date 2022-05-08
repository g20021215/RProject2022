# RProject2022
This repository is used for R Presentation.

王一安 2030005058 Q1

侯香伶 2030005029 Q2

陈韵扬 2030005011 Q3

李文锐 2030005036 Q4

陈郅涵 2030005013 Q5

![test image size]<img src="https://github.com/g20021215/RProject2022/blob/main/R.png" width="450" height="400">
%


Code Q1.R
```R
#Y=Value
#X1=Lotsize
#X2=Bedrooms
#X3=Bathrooms
#X4=Rooms
#X5=Age
#X6=Taxes
#X7=Garage



#Problem 1
#(a)
A <- read.csv("RealEstate.csv",header = TRUE)
colnames(A)
Y  <- A$Value 
X1 <- A$LotSize
X2 <- A$Bedrooms
X3 <- A$Bathrooms
X4 <- A$Rooms
X5 <- A$Age
X6 <- A$Taxes
X7 <- A$Garage

summary(lm(Y~X1+X2+X3+X4+X5+X6+X7))#此处截图
#(b)
#latex code:
#Estimated Regression Model:$Y = 201.0-2.382X_1-10.89X_2+44.56X_3+16.09X_4+0.4465XX_5-2.457\times10^{-4}X_6+13.17\timesZ_1X_7+26.96\times(1-Z_1)X_7$\\

#(C)
#The R^2 and adjusted R^2 are all approximate 0.35, which means the fitting level is okay.
#F statistic: The F value (8,+infty) is 2.93,and it is less than the model F-value = 25.91,so the model is significant at 0.05 level.
#(D)

# P-value: X5,X6 are not significant here
#There are two independent variables are not significant in this model at 0.05 significant level.
#
#（EF)
lm2 = lm(Y~X1+X2+X3+X4+X5+X6+X7)
windows()
par(mfrow=c(2,2))

plot(lm2)

#link:https://zhuanlan.zhihu.com/p/34627302

```

![image](https://github.com/g20021215/RProject2022/blob/main/10.1.png)
