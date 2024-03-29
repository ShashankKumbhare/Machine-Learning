## Part 2  
#### Content     
  
[**2-1 Multivariate Linear Regression**](#2-1-Multivariate-Linear-Regression)    
2-1-1 Multiple Features    
2-1-2 Gradient Descent For Multiple Variables  
2-1-3 Gradient Descent in Practice I - Feature Scaling   
2-1-4 Gradient Descent in Practice II - Learning Rate  
2-1-5 Features and Polynomial Regression  
  
[**2-2 Computing Parameters Analytically**](#2-2-Computing-Parameters-Analytically)  
2-2-1 Normal Equation  
2-2-2 Normal Equation Noninvertibility  
  
[**2-3 Review Part 2**](#2-3-Review-Part-2)     
  
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
  
    
### ```2-1-5 Features and Polynomial Regression```   
We can improve our features and the form of our hypothesis function in a couple different ways.

We can **combine** multiple features into one. For example, we can combine x<sub>1</sub> and x<sub>2</sub> into a new feature x<sub>3</sub> by taking x<sub>1</sub>.x<sub>2</sub>.  
  
#### **Polynomial Regression**  
Our hypothesis function need not be linear (a straight line) if that does not fit the data well.  
  
We can **change the behavior or curve** of our hypothesis function by making it a quadratic, cubic or square root function (or any other form).  
  
For example, if our hypothesis function is h<sub>θ</sub>(x) = θ<sub>0</sub> + θ<sub>1</sub>x<sub>1</sub> then we can create additional features based on x<sub>1</sub>, to get the quadratic function h<sub>θ</sub>(x) = θ<sub>0</sub> + θ<sub>1</sub>x<sub>1</sub> + θ<sub>2</sub>x<sub>2</sub> + or the cubic function h<sub>θ</sub>(x) = θ<sub>0</sub> + θ<sub>1</sub>x<sub>1</sub> + θ<sub>2</sub>x<sub>2</sub> + θ<sub>3</sub>x<sub>3</sub>.  
  
In the cubic version, we have created new features x<sub>2</sub> and x<sub>3</sub> where x<sub>2</sub> = x<sub>1</sub><sup>2</sup> and x<sub>3</sub> = x<sub>1</sub><sup>3</sup>.  
  
To make it a square root function, we could do: h<sub>θ</sub>(x) = θ<sub>0</sub> + θ<sub>1</sub>x<sub>1</sub> + <span>&radic;x<sub>1</sub></span>.  
  ​	 
One important thing to keep in mind is, if you choose your features this way then feature scaling becomes very important.  
  
eg. if x<sub>1</sub> has range 1 - 1000 then range of x<sub>1</sub><sup>2</sup> becomes 1 - 1000000 and that of x<sub>1</sub><sup>3</sup> becomes 1 - 1000000000.  
  
---   
  
## 2-2 Computing Parameters Analytically  
### ```2-2-1 Normal Equation```       
Gradient descent gives one way of minimizing J. Let’s discuss a second way of doing so, this time performing the minimization explicitly and without resorting to an iterative algorithm. In the "Normal Equation" method, we will minimize J by explicitly taking its derivatives with respect to the θj ’s, and setting them to zero. This allows us to find the optimum theta without iteration. The normal equation formula is given below:  
  
θ = (X<sup>T</sup>X)<sup>-1</sup>X<sup>T</sup>y  
  
<p align="center"><img src=images/normal_equation.png></p>      
  
There is **no need** to do feature scaling with the normal equation.  
  
The following is a comparison of gradient descent and the normal equation:  
  
<p align="center"><img src=images/normal_equation_table.jpg></p>    
  
With the normal equation, computing the inversion has complexity O(n<sup>3</sup>). So if we have a very large number of features, the normal equation will be slow. In practice, when n exceeds 10,000 it might be a good time to go from a normal solution to an iterative process.  
  
---  
  
### ```2-2-2 Normal Equation Noninvertibility```     
When implementing the normal equation in octave we want to use the 'pinv' function rather than 'inv.' The 'pinv' function will give you a value of θ even if X<sup>T</sup>X is not invertible.  
  
If X<sup>T</sup>X is **noninvertible**, the common causes might be having :  
  
* Redundant features, where two features are very closely related (i.e. they are linearly dependent)  
* Too many features (e.g. m ≤ n). In this case, delete some features or use "regularization" (to be explained in a later lesson).  
  
Solutions to the above problems include deleting a feature that is linearly dependent with another or deleting one or more features when there are too many features.  
  
---  
  
  
## 2-3 Review Part 2  
[Review Part 2](multivariate_linear_regression.pdf)  
    