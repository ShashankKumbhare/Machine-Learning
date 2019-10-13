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
  
```
x<sub>j</sub><sup>(i)</sup> = value of feature j in the i<sup>th</sup> training example  
x<sup>(i)</sup> = the input (features) of the ith training example  
m = the number of training examples  
n = the number of features  
```  
  
The multivariable form of the hypothesis function accommodating these multiple features is as follows:

hθ(x)=θ0+θ1x1+θ2x2+θ3x3+⋯+θnxn
In order to develop intuition about this function, we can think about \theta_0θ 
0
​	  as the basic price of a house, \theta_1θ 
1
​	  as the price per square meter, \theta_2θ 
2
​	  as the price per floor, etc. x_1x 
1
​	  will be the number of square meters in the house, x_2x 
2
​	  the number of floors, etc.

Using the definition of matrix multiplication, our multivariable hypothesis function can be concisely represented as:

hθ(x)=[θ0θ1...θn]⎡⎣⎢⎢⎢x0x1⋮xn⎤⎦⎥⎥⎥=θTx
This is a vectorization of our hypothesis function for one training example; see the lessons on vectorization to learn more.

Remark: Note that for convenience reasons in this course we assume x(i)0=1 for (i∈1,…,m). This allows us to do matrix operations with theta and x. Hence making the two vectors '\thetaθ' and x^{(i)}x 
(i)
  match each other element-wise (that is, have the same number of elements: n+1).]  
  
---  
  
### ```2-1-2 <txt>```    
<
txt
>  
  
---  
  
### ```3-1-3 <txt>```   
<
txt
>   
   
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
  