---
Title: Calibration of Default Correlation in Copula Function
Template: LeafPage
---

#Calibration of Default Correlation in Copula Function

Having chosen the copula function, we need to compute the pairwise correlation of time-until-default. As highlighted by Li (2000) [1] and presented below, this can be done in two (equivalent) ways.

##CreditMetrics Asset Correlation Approach

Using the CreditMetrics (J.P. Morgan’s 1997 software system to measure credit risk) asset correlation approach, we can obtain the default correlation of two discrete events over one year period:

Let A and B be two credits and suppose the one year default probabilities for A and B are $q_A$ and $q_B$ respectively. 

First obtain $Z_A$ and $Z_B$ such that

	$q_A = Pr(Z < Z_A)$
	$q_B = Pr(Z < Z_B)$
	where $Z$ is a standard normal random variable. 

If $\rho$ is the asset correlation, the joint default probability for credit A and B is calculated as follows

	$Pr(Z < Z_A, Z < Z_B) = \int_{-\infty}^{Z_A}\int_{-\infty}^{Z_B} \phi_2(x, y|\rho)dxdy = \Phi_2(Z_A, Z_B, \rho)$
	where $\phi_2(x,y|\rho)$ is the standard bivariate normal density function with a correlation coefficient $\rho$, 
	and $\Phi_2$ is the bivariate cumulative normal distribution function. 

##Bivariate Normal Copula Function Approach

Consider using a bivariate normal copula function with a correlation parameter $\gamma$, and denote the survival times for A and B as $T_A, T_B$, the joint default probability after one year can be calculated by

	$Pr(T_A < 1, T_B < 1) = \Phi_2(\Phi^{-1}(F_A(1), \Phi^{-1}(F_B(1)), \gamma)$ 
	where $F_A, F_B$ are the distribution functions for the survival times $T_a, T_B$.

##Equivalence Between the Two Approaches

Noting that

	$q_i = Pr(T_i < 1) = F_j(1)$ and
	$Z_i = \Phi^{-1}(q_i)$ for $i = A, B$

we see that the two methods above give the same joint default probability over one year period for $\rho = \gamma$.

Hence, to generate time-until-default of two credit risks, we can use a bivariate normal copula function with correlation parameter equal to the CreditMetrics asset correlation. As a result, using these asset correlations, we can construct high dimensional normal copula functions to model the credit portfolio of any size.

##References

[1] David X. Li. On Default Correlation: A copula function approach. *Journal of Fixed Income,*: (4):43-54, April 2000.
