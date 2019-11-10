## Part 2  
#### Content     
  
[**2-1 Multivariate Linear Regression**](#2-1-Multivariate-Linear-Regression)    
2-1-1 Multiple Features    
2-1-2 Gradient Descent For Multiple Variables  
2-1-3 Gradient Descent in Practice I - Feature Scaling   
2-1-4 Gradient Descent in Practice II - Learning Rate  
2-1-5 Features and Polynomial Regression  
  
[**2-2 Computing Parameters Analytically**](#2-2-Computing-Parameters-Analytically)  
2-2-1 <txt>  
2-2-2 <txt>  
2-2-3 <txt>  
2-2-4 <txt>  
  
[**2-3 <txt>**](21-1-<txt>)    
2-3-1 <txt>  
2-3-2 <txt>  
2-3-3 <txt>  
  
[**2-4 <txt>**](21-1-<txt>)    
2-4-1 <txt>  
2-4-2 <txt>  
2-4-3 <txt>  
2-4-4 <txt>  
2-4-5 <txt>  
2-4-6 <txt>  
  
---  
    
  
## 2-1 Multivariate Linear Regression  
### ```2-1-1 Multiple Features```         
Linear regression with multiple variables is also known as "multivariate linear regression".  
  
We now introduce notation for equations where we can have any number of input variables.  
  
<p align="left"><img src=images/mad.jpg></p>    
  
The multivariable form of the hypothesis function accommodating these multiple features is as follows:  
  
h<sub>θ</sub>(x) = θ<sub>0</sub>x<sub>0</sub> + θ<sub>1</sub>x<sub>1</sub> + θ<sub>2</sub>x<sub>2</sub> +....+ θ<sub>n</sub>x<sub>n</sub>  
  
In order to develop intuition about this function, we can think about θ<sub>0</sub> as the basic price of a house, θ<sub>1</sub> as the price per square meter, θ<sub>2</sub> as the price per floor, etc. x<sub>1</sub> will be the number of square meters in the house, x<sub>2</sub> the number of floors, etc.  
  
Using the definition of matrix multiplication, our multivariable hypothesis function can be concisely represented as:  
   
<p align="left"><img src=images/matrix.jpg></p>  
  
This is a vectorization of our hypothesis function for one training example; see the lesson on vectorization to learn more.  
  
Remark: Note that for convenience reasons in this course we assume x<sub>0</sub><sup>(i)</sup> for (i=1,2,…,m). This allows us to do matrix operations with 'θ' and x. Hence making the two vectors 'θ' and x<sup>(i)</sup> match each other element-wise (that is, have the same number of elements: n+1).    
  
---  
  
### ```2-1-2 Gradient Descent For Multiple Variables```    
The gradient descent equation itself is generally the same form; we just have to repeat it for our 'n' features:  
   
<p align="left"><img src=images/conv.png></p>
  
In other words:  
   
<p align="left"><img src=images/conv1.png></p>  
    
The following image compares gradient descent with one variable to gradient descent with multiple variables:  
<p align="centre"><img src=images/gd.png></p>  
  
---  
  
### ```2-1-3 Gradient Descent in Practice I - Feature Scaling```   
We can speed up gradient descent by having each of our input values in roughly the same range. This is because θ will descend quickly on small ranges and slowly on large ranges, and so will oscillate inefficiently down to the optimum when the variables are very uneven.  
  
The way to prevent this is to modify the ranges of our input variables so that they are all roughly the same. Ideally:    
  
−1 ≤ x<sub>(i)</sub> ≤ 1  
  
or  
  
-0.5 ≤ x<sub>(i)</sub> ≤ 0.5  
  
These aren't exact requirements; we are only trying to speed things up. The goal is to get all input variables into roughly one of these ranges, give or take a few.  
   
Two techniques to help with this are feature scaling and mean normalization. Feature scaling involves dividing the input values by the range (i.e. the maximum value minus the minimum value) of the input variable, resulting in a new range of just 1. Mean normalization involves subtracting the average value for an input variable from the values for that input variable resulting in a new average value for the input variable of just zero. To implement both of these techniques, adjust your input values as shown in this formula:  
  
<p align="left"><img src=images/eq.png></p>
  
Where μi is the average of all the values for feature (i) and s<sub>i</sub> is the range of values (max - min), or s<sub>i</sub> is the standard deviation.  
  
Note that dividing by the range, or dividing by the standard deviation, give different results. The quizzes in this course use range - the programming exercises use standard deviation.  
  
For example, if x<sub>i</sub> represents housing prices with a range of 100 to 2000 and a mean value of 1000, then,  

<p align="left"><img src=images/eq2.png></p>  
   
---  	 

### ```2-1-4 Gradient Descent in Practice II - Learning Rate```      
**Debugging gradient descent.** Make a plot with number of iterations on the x-axis. Now plot the cost function, J(θ) over the number of iterations of gradient descent. If J(θ) ever increases, then you probably need to decrease α.  
  
**Automatic convergence test.** Declare convergence if J(θ) decreases by less than E in one iteration, where E is some small value such as 10−3. However in practice it's difficult to choose this threshold value.  
  
<p align="center"><img src=images/gd1.png></p>  
  
It has been proven that if learning rate α is sufficiently small, then J(θ) will decrease on every iteration.  
  
<p align="center"><img src=images/gd2.png></p>  
  
To summarize:  
  
If α is too small: slow convergence.  
  
If α is too large: J(θ) may not decrease on every iteration and thus may not converge.  
  
---  
  
## 2-2 <txt>  
### ```2-2-1 <txt>```       
<
txt
>    
    
---  
  
### ```2-2-2 <txt>```     
<
txt
>  
  
---  
  
### ```2-2-3 <txt>```       
<
txt
>  
  
---  
  
### ```2-2-4 <txt>```      
<
txt
>  
  
---  
  
## 2-3 <txt>  
### ```2-3-1 <txt>```        
<
txt
>  
  
---  
### ```2-3-2 <txt>```    
<
txt
>  
  
---  
### ```2-3-3 <txt>```     
<
txt
>  

---  
  
## 2-4 <txt>  
### ```2-4-1 <txt>```       
<
txt
>  
  
---  
### ```2-4-2 <txt>```    
<
txt
>  
  
---  
### ```2-4-3 <txt>```     
<
txt
>  
  
---  
### ```2-4-4 <txt>```    
<
txt
>  
  
---  
### ```2-4-5 <txt>```    
<
txt
>  
  
---  
### ```2-4-6 <txt>```    
<
txt
>	
  