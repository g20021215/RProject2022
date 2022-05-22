# RProject2022        Group 10
This repository is used for R Presentation.

王一安 2030005058 Problem1

侯香伶 2030005029 Problem2

陈韵扬 2030005011 Problem3

李文锐 2030005036 Problem4

陈郅涵 2030005013 Problem5

![test image size]<img src="https://github.com/g20021215/RProject2022/blob/main/R.png" width="450" height="400">
%
![image](https://github.com/g20021215/RProject2022/blob/main/1.png)
# Problem 1 王一安
![image](https://github.com/g20021215/RProject2022/blob/main/Q1.png)
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
Estimated Regression Model:
![image](https://github.com/g20021215/RProject2022/blob/main/1f.png)


(C)
The R^2 and adjusted R^2 are all approximate 0.35, which means the fitting level is okay.

F statistic: The F value (8,+infty) is 2.93,and it is less than the model F-value = 25.91,so the model is significant at 0.05 level.


![image](https://github.com/g20021215/RProject2022/blob/main/10.1test.png)

(D)

P-value: X5,X6 are not significant here. There are two independent variables are not significant in this model at 0.05 significant level.

(E)(F)

```R
lm2 = lm(Y~X1+X2+X3+X4+X5+X6+X7)
windows()
par(mfrow=c(2,2))

plot(lm2)

#link:https://zhuanlan.zhihu.com/p/34627302

```



![image](https://github.com/g20021215/RProject2022/blob/main/10.1.png)



# Problem 2 侯香伶
![image](https://github.com/g20021215/RProject2022/blob/main/Q2.png)
```R
(a)
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
```

b),d)
according to Q1, the p-value of variables x1,x2,x3,x4,x7 are all<0.05,these are significant variables we should choose. so we need to use `lm(y~x1+x2+x3+X4+x7)` and the regression model is:
![image](https://github.com/g20021215/RProject2022/blob/main/2f.png)

c)
Since the p-values of the two models are same, the adjusted R-squared of them is similar, and the F-value of model in Question 1 is 25.91, the F-value of model in Question 2 is 33.89>25.91, so model in Question 2 is better than model in Question 1.

![image](https://github.com/g20021215/RProject2022/blob/main/10.2test.png)

(e)(f)
```R
summary(model)
windows()
par(mfrow=c(2,2))
plot(model)

```


![image](https://github.com/g20021215/RProject2022/blob/main/10.2.png)

# Problem 3 陈韵扬
![image](https://github.com/g20021215/RProject2022/blob/main/Q3.png)
(a)
```R
lm1 = lm(Y~X1+X2+X3+X4+X5+X6+X7)
step(lm1,direction = "both")

```
![image](https://github.com/g20021215/RProject2022/blob/main/step.jpg)

(b)&(c)
```R
Lm3<-lm(Y~X1+X2+X3+X4+X5+X7)
summary(lm3)
```
![image](https://github.com/g20021215/RProject2022/blob/main/10.3test.png)
F-statistic in `lm3` is 29.69, greater than F-statistic in lm1=25.91

New model `lm3` is better than the model in Question 1

(d)

![image](https://github.com/g20021215/RProject2022/blob/main/10.1test.png)

(e)&(f)
```R
windows()
par(mfrow=c(2,2))
plot(lm3)
```
![image](https://github.com/g20021215/RProject2022/blob/main/10.3.png)


# Problem 4  李文锐
![image](https://github.com/g20021215/RProject2022/blob/main/Q4.png)

The final estimated regression model in Problem 3 is 

![image](https://github.com/g20021215/RProject2022/blob/main/3f.png)

if one-car garage, z=1; else z=0.

(a)
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


X3_sqr<-X3^2
s4<-lm(Y~X1+X2+X3_sqr+X4+X5+X7)
summary(s4)
```


 (b)
 
The estimated regression model is 
![image](https://github.com/g20021215/RProject2022/blob/main/4f.png)
If one-car garage, z=1; else z=0.

 (c)
 
Since the p-value of the new model is equal to the p-value of Q3, F-value of the new model is larger than F-value of Q3. Also, the adjusted R-squared of them is similar. We can conclude that this new model is better than the model in Q3.


![image](https://github.com/g20021215/RProject2022/blob/main/10.4test.png)

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

# Problem 5 陈郅涵

![image](https://github.com/g20021215/RProject2022/blob/main/Q5.png)

The final estimated regression model in Problem 4 is 
![image](https://github.com/g20021215/RProject2022/blob/main/4f.png)
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


(b)

The estimated regression model is 
![image](https://github.com/g20021215/RProject2022/blob/main/5f.png)
if one-car garage, z=1;else z=0.

(c)

Since the p-value of the new model is equal to the p-value of Q4, F-value of the new model is smaller than F-value of Q4. Also, the adjusted R-squared of them is similar. We can conclude that this new model isn’t better than the model in Q4.


![image](https://github.com/g20021215/RProject2022/blob/main/10.5test.png)

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

## Table:
```R

M<-  c("Q1","Q2","Q3","Q4","Q5")
pValue<- c("< 2.2E-16","< 2.2E-16","< 2.2E-16","< 2.2E-16","< 2.2E-16" )
Sig<- c("No","Yes","No", "No","No")
Rsqure <- c(0.3699, 0.3642, 0.3699, 0.3846,0.3617)
ProjectData <- data.frame(M, pValue , Sig, Rsqure)
colnames(ProjectData) <- c("Models","p-value of F-test","Sig. of all x-var.","R-Square" )
write.table(ProjectData,"/Users/chenzhihan/Desktop/R/ProjectData.txt")
write.csv(ProjectData,"/Users/chenzhihan/Desktop/R/ProjectData.csv")

```

![image](https://github.com/g20021215/RProject2022/blob/main/table.jpg)




By this table, we can find that the model in Problem 2 is the best. And all the variables are significant.
So the model is 
![image](https://github.com/g20021215/RProject2022/blob/main/2f.png)
