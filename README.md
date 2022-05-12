# RProject2022
This repository is used for R Presentation.

王一安 2030005058 Q1

侯香伶 2030005029 Q2

陈韵扬 2030005011 Q3

李文锐 2030005036 Q4

陈郅涵 2030005013 Q5

![test image size]<img src="https://github.com/g20021215/RProject2022/blob/main/R.png" width="450" height="400">
%

# Problem 1
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

summary(lm(Y~X1+X2+X3+X4+X5+X6+X7))#
```

(b)
latex code:
Estimated Regression Model:$Y = 201.0-2.382X_1-10.89X_2+44.56X_3+16.09X_4+0.4465XX_5-2.457\times10^{-4}X_6+13.17\timesZ_1X_7+26.96\times(1-Z_1)X_7$\\

(C)
The R^2 and adjusted R^2 are all approximate 0.35, which means the fitting level is okay.
F statistic: The F value (8,+infty) is 2.93,and it is less than the model F-value = 25.91,so the model is significant at 0.05 level.
(D)

P-value: X5,X6 are not significant here
There are two independent variables are not significant in this model at 0.05 significant level.

(E)(F)

```R
lm2 = lm(Y~X1+X2+X3+X4+X5+X6+X7)
windows()
par(mfrow=c(2,2))

plot(lm2)

#link:https://zhuanlan.zhihu.com/p/34627302

```

![image](https://github.com/g20021215/RProject2022/blob/main/10.1test.png)

![image](https://github.com/g20021215/RProject2022/blob/main/10.1.png)



# Problem 2
```R
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
model<-lm(Y~X1+X2+X3+X4+X7,data=A)

summary(model)
windows()
par(mfrow=c(2,2))
plot(model)

#b),d)
#according to Q1, the p-value of variables x1,x2,x3,x4,x7 are all<0.05,these are significant variables we should choose.
#so we need to use lm(y~x1+x2+x3+X4+x7)
#and the regression model is:
#y=177.2892-2.2128*x1-10.4201*x2+45.4787*x3+16.453*x4+13.2638*z1x7+26.1132*(1-z1)x7

#c)
#Since the p-values of the two models are  same, We just have to compare r^2.
#The r^2 of model in Question 1 is 0.3557, the r^2 of model in Question 2 is 0.3534<0.3557, so model in Question 1 is better than model in Question 2.

#(e)(f)
#summary(model)
#windows()
#par(mfrow=c(2,2))
#plot(model)
```
![image](https://github.com/g20021215/RProject2022/blob/main/10.2test.png)

![image](https://github.com/g20021215/RProject2022/blob/main/10.2.png)

# Question 4

The final estimated regression model in Question 3 is y = 200.1082 - 2.4023x1 - 10.8475x2 + 44.3613x3 + 16.0319x4 - 0.4393x5 + 13.0485z + 16.6075(1-z) if one-car garage, z=1; else z=0.

```R

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

#(a)
X3_sqr<-X3^2
s4<-lm(Y~X1+X2+X3_sqr+X4+X5+X7)
summary(s4)

```

![image](https://github.com/g20021215/RProject2022/blob/main/10.4test.png)

 (b)
 
The estimated regression model is y = 230.8968 - 2.4350x1 - 11.0383x2 + 13.4934x3^2 + 16.1508x4 - 0.3857x5 + 13.3908z + 25.2647(1-z)
If one-car garage, z=1; else z=0.

 (c)
 
Since the p-value of the new model is equal to the p-value of Q3, F-value of the new model is larger than F-value of Q3. Also, the adjusted R-squared of them is similar. We can conclude that this new model is better than the model in Q3.

(d)

From the p-value of each independent variable, the p-value of x5 is greater than alpha, but the p-value of other variables is smaller than alpha, so we can conclude that each independent variable is significant, except X5.

(e)&(f)

```R

s4<-lm(Y~X1+X2+X3_sqr+X4+X5+X7)
windows()
par(mfrow=c(2,2))
plot(s4,main = "Graph of Q4")

```
![image](https://github.com/g20021215/RProject2022/blob/main/10.4.png)

# Question 5

The final estimated regression model in Question 4 is y = 230.8968 - 2.4350x1 - 11.0383x2 + 13.4934x3^2 + 16.1508x - 0.3857x5 + 13.3908z + 25.2647(1-z) 
if one-car garage, z=1; else z=0.

```R
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

```
(a)
```R

X4_sqr<-X4^2
s5<-lm(Y~X1+X2+X3+X4_sqr+X5+X7)
summary(s5)

```
![image](https://github.com/g20021215/RProject2022/blob/main/10.5test.png)

(b)

The estimated regression model is y = 255.1323 - 2.4278x1 - 9.2637x2 + 45.7318x3 + 0.9607x4^2 - 0.4476x5 + 14.5604z + 28.7064(1-z)
if one-car garage, z=1;else z=0.

(c)

Since the p-value of the new model is equal to the p-value of Q4, F-value of the new model is smaller than F-value of Q4. Also, the adjusted R-squared of them is similar. We can conclude that this new model isn’t better than the model in Q3.

(d)

From the p-value of each independent variable, the p-value of x5 is greater than alpha, but the p-value of other variables is smaller than alpha, so we can conclude that each independent variable is significant, except X5.

(e)&(f)
```R
s5<-lm(Y~X1+X2+X3r+X4_sqr+X5+X7)
windows()
par(mfrow=c(2,2))
plot(s5,main = "Graph of Q5")
```
![image](https://github.com/g20021215/RProject2022/blob/main/10.5.png)
