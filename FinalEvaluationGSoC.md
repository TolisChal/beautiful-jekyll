---
layout: page
title: Google Summer of Code 2018
---  
  
## <span style="text-align:center;">Organization:  R project for statistical computing  
### <span style="text-align:center;">Project: Efficient R tools for geometrical statistics  
#### <span style="text-align:center;">Topic:  Volume approximation and sampling in high dimensions  
  
#### *mentors:* Vissarion Fisikopoulos, Zafeirakis Zafeirakopoulos  
#### *Student:* Chalkis Apostolos  
  
---------------------------------------------------------------------------  
    
### *Final Evaluation*  

The main goal of this project was to create a R package, using Rcpp, based on the [C++ package volesti](https://github.com/vissarion/volume_approximation). In addition, in the [proposal](https://drive.google.com/file/d/1CsblG42xXLoyYiDmcCSjRJhL3Eilxk5u/view) we suggested to add volume computation for non-linear convex bodies and V-polytopes and sampling from convex bodies in high dimensions.  
In bonding period we decided to implement the [randomized practical algorithm](http://mpc.zib.de/index.php/MPC/article/view/178/99) of B. Cousins and S. Vempala (CV algorithm), for volume approximation, and to focus on V-polytopes and not to non-linear convex bodies.  
  
The main repository for C++ package volesti is [here](https://github.com/vissarion/volume_approximation).  
For the CV algorithm exists a matlab implementation [here](https://www.mathworks.com/matlabcentral/fileexchange/43596-volume-computation-of-convex-bodies).  
  
Summarizing GSoC project we have succeeded the following goals:  
1. We have excluded CGAL library from the initial volesti C++ implementaion.  
2. We use RcppEigen and BH libraries in order to use Eigen and Boost libraries. To solve linear programs we use lpSolve library.  
3. We have developed a C++ implementation of CV algorithm for convex polytopes.  
4. We have added volume computation for V-polytopes, using either volesti or CV algorithm.  
5. In addition to Random Directions Hit and Run and Coordinate Directions Hit and Run, we have added ball walk method for the random walks that both algorithms require.  
6. We have implemented a R package, using Rcpp, that is able to call C++ implementaion and use all the above options.  
7. In the R package we give the additional option of sampling from a convex H or V-polytope with uniform or spherical gaussian target distribution.  
8. In the R package we give also the options of rounding and applying random rotation on a H or V-polytope.  
   
You can see the branch that we have excluded CGAL from volesti and create a basic Rcpp interface [here](https://github.com/TolisChal/volume_approximation/tree/develop).  

#### *List of Pull Requests*  
 - [Exclude CGAL dependencies](https://github.com/TolisChal/volume_approximation/pull/2)
 - [Implementation of CV algorithm](https://github.com/TolisChal/volume_approximation/pull/3)  
 - [Replace StdMatrix with Eigen::Matrix](https://github.com/TolisChal/volume_approximation/pull/6)
 - [Volume approximation for V-polytopes](https://github.com/TolisChal/volume_approximation/pull/7)  
 - [Improve and develop new function for the R package](https://github.com/TolisChal/volume_approximation/pull/8)  
 - [Improve rounding](https://github.com/TolisChal/volume_approximation/pull/9)  
   
 If you want to comment on the documentation of the R package, you can do it [here](https://drive.google.com/file/d/1htOhKLwk58Yai0a6mkHvfwpO42_0FbPy/view?usp=sharing).  
    
   
#### *Further work*  
 - Create the final version of the R package after mentors' evaluation and submit it to CRAN.  
 - Continue working on V-polytopes' volume approximation by improving parts of the current algorithms, i.e. V-polytope membership by using [CppOptimizationLibrary](https://github.com/PatWie/CppNumericalSolvers) library. Test new ideas and methods for V-polytopes.  
 - Extend current implementation to non-linear convex and non-convex bodies.  
 - Add implementations of financial applications for crisis prediction and financial modeling, that are described [here](https://arxiv.org/abs/1803.05861).  
 - Add more sampling options, i.e. different random walk algorithms or sampling from the boundary of a convex body.  
 * #### *TODO List* [here](https://github.com/TolisChal/volume_approximation/issues/4) 
