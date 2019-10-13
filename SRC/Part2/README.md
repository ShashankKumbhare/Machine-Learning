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
  
\       h<sub>θ</sub>(x) = θ<sub>0</sub>x<sub>0</sub> + θ<sub>1</sub>x<sub>1</sub> + θ<sub>2</sub>x<sub>2</sub> +....+ θ<sub>n</sub>x<sub>n</sub>  
  
In order to develop intuition about this function, we can think about θ<sub>0</sub> as the basic price of a house, θ<sub>1</sub> as the price per square meter, θ<sub>2</sub> as the price per floor, etc. x<sub>1</sub> will be the number of square meters in the house, x<sub>2</sub> the number of floors, etc.  
  
Using the definition of matrix multiplication, our multivariable hypothesis function can be concisely represented as:  
   
<p align="left"><img src=images/matrix.jpg></p>  
  
This is a vectorization of our hypothesis function for one training example; see the lesson on vectorization to learn more.  
  
Remark: Note that for convenience reasons in this course we assume x<sub>0</sub><sup>(i)</sup> for (i=1,2,…,m). This allows us to do matrix operations with 'θ' and x. Hence making the two vectors 'θ' and x<sup>(i)</sup> match each other element-wise (that is, have the same number of elements: n+1).    
  
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
  