# Translating DYNAMO

This document provides resources for reading and translating DYNAMO system dynamics models into current languages and modeling software. 

# Background

DYNAMO was the first dedicated programming language for system dynamics. Orginally developed by Jack Pugh (1963) and Phyllis Fox (2005), DYNAMO provided the first high-level domain specific language for building, simulating and analyzing system dynamics models. DYNAMO was the main system dynamics programming language from 1963 through the mid 1980's when microcomputers started to become widely avaialble, especially the orginal Macintosh computer that led to the creation of Stella/iThink by Barry Richmond, Vensim by David Petersen and Bob Eberlein on Windows systems, and Powersim by ??. 

# DYNAMO syntax


```
.
.
.
N  APPROVE=VALUES
C  VALUES=24
L  APPROVE.K=APPROVE.J+DT*(TRYAPP.JK+JOINUP.JK-LETUP.JK)

A  REWARD.K=APPROVE.K/CONSTR
  
N  TOLRAT=STRAIN
C  STRAIN=1
L  TOLRAT.K=TOLRAT.J+DT*(OVERLK.JK-TRYAPP.JK)

N  SUFFER=CONSTR
C  CONSTR=4
L  SUFFER.K=SUFFER.J+DT*(NOTICE.JK-TRYCON.JK)
.
.
.
```


# References
Fox, P. A. (2005). *An interview with Phyllis A. Fox* [Interview]. 

Pugh, A. L. (1963). *The DYNAMO User’s Manual.* The MIT Press. 

Richardson, G. P., & Pugh, A. L. (1986). *Introduction to system dynamics modeling with DYNAMO.* MIT Press. 
