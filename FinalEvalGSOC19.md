---
layout: page
title: Google Summer of Code 2019
---  
  
## <span style="text-align:center;">Organization:  R project for statistical computing  
### <span style="text-align:center;">Project: State-of-the-art geometric random walks in R
#### <span style="text-align:center;">Topic:  Computational Statistics and Geometry 
  
#### *mentors:* Vissarion Fisikopoulos, Ilias Tsigaridas, Zafeirakis Zafeirakopoulos  
#### *Student:* Apostolos Chalkis
  
---------------------------------------------------------------------------  
    
### *Final Evaluation*  

The main goals of this project was: a) to implement state-of-the-art geometric random walks for convex polytopes, b) to add them to package `volesti` (https://github.com/GeomScale/volume_approximation) in order to support `R` with efficient implementations, able to scale in thousands of dimensions for the first time and c) fast volume computation methods for all the representations of polytopes that `volesti` supports, using the implemented random walks. Indeed, HMC and billiard random walks converges very fast to the target distribution allowing us to sample in thousands of dimensions and obtain faster volume computations.  
  
In particular, I implemented the following:  

 - Hamiltonian Monte Carlo random walk for sampling from the Gibbs distribution using the logbarrier function in the Hamiltonian (PR 1).  
 - Hamiltonian Monte Carlo random walk with reflections from the multidimensional spherical Gaussian distribution (PR 1).  
 - Billiard walk for uniform sampling for all the representations (PR 2).  
 - Dikin, John and Vaidya random walks for uniform sampling from convex polytopes (PR 3).  
 - New volume computation method with simulated annealing for cooling convex bodies (BAN method) (PR 2).  
 - Faster volume computation using billiard walk in BAN method for V-polytopes and zonotopes (PR 2) and HMC with reflections in CG method (PR 1). We moreover, experimentally optimize the parameters that both methods use for these random walks. For billiard walk we implement heuristics to estimate the diameter of special convex bodies that appear in volume computation methods.  
 - Boundary uniform sampling for convex polytopes that are given in any representation (PR 2).  
 - New random V-polytope and zonotope generators (PR 2).  
 - Code optimizations: a) for Hit-and-Run and billiard walk and b) Rcpp wrapping (PR 2).  

#### *List of Pull Requests*  
 1. [Implementation of HMC random walks](https://github.com/GeomScale/volume_approximation/pull/38)  
 2. [Implementation of billiard walk and new volume computation method for V-polytioes and zonotopes](https://github.com/GeomScale/volume_approximation/pull/31)  
 3. [Add Dikin, John and Vaidya random walks to volesti](https://github.com/GeomScale/volume_approximation/pull/39)  
   
#### *Further work*  
 - Improve `C++` code general functionality.  
 - Improve the `R` documentation.  
 - Submit a new version of `volesti` to CRAN.  
