# Translating DYNAMO

This document provides resources for reading and translating DYNAMO system dynamics models into current languages and modeling software. 

## Background

DYNAMO was the first dedicated programming language for system dynamics. Orginally developed by Jack Pugh (1963) and Phyllis Fox (2005), DYNAMO provided the first high-level domain specific language for building, simulating and analyzing system dynamics models. DYNAMO was the main system dynamics programming language from 1963 through the mid 1980's when microcomputers started to become widely avaialble, especially the orginal Macintosh computer that led to the creation of Stella/iThink by Barry Richmond, Vensim by David Petersen and Bob Eberlein on Windows systems, and Powersim by ??. 

Today, there is no known working version of DYNAMO available. Despite this, DYNAMO models can be translated and reproduced using available tools--a testament to the idea of reproducibilty of computational models developed when the original software, operating systems, or source code are available. 

There are many benefits to learning to read and translate DYNAMO. First and foremost, it provides access to a large class of fundamental models and lessons in system dynamics. For example, people regularly refer to the Urban Dynamics model, which was written in DYNAMO. Translating and rebuilding Urban Dynamics not only provides access to the model, but familiarity and insights into Forrester's style of modeling. Second, translating and rebuilding models is a great practice for developing modeling skills and learnign the nuances of different implementations. The experience of building and comparing models and various implementations provides a foundation for appreciating the nuances of numerical methods and interpreting results to inform policy and program design.   

## DYNAMO syntax

DYNAMO syntax looks something like the following with the first letter indicating the type of equation or expression, which is followed by the actual equation/expression. For example, L designates a level variable, A an auxilary equation, and C a constant. 

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
The easiest way to start with the translation is to draw the diagram. 

Level equations
Defined as “L” equations and written as a difference equation: <name of variable>.K=<name of variable>.J + DT*(<rate variable>+/-<rate variable>)


### Rate equations
Defined as “R” equations with the variable = the expression or value. E.g., 

```
R  TRYAPP.KL=((TOLRAT.K*(LEGIT.K/100)+(CONSTR/100)))/TIMEGONE.K  
```

### Auxiliary equations
Defined as “A” equations with <name of variable>=<algebraic expression or value>

### Constants
Defined as “C” equations: <name of constant>=<value>

### TABLE functions
Appear in equations as …TABLE(<table name>, <input variable>, <x min, x max>, <x increment>
Defined separately as “T” equations: T <table name>=<y0>, <y1>, …, <Yn>

### Initial values
Defined as “N” equations: <name of level>=<algebraic expression or value>

## Resources

While out of print, Richardon and Pugh (1986) provide a solid introduction to the DYNAMO language and system dynamics modeling. More recently, Walker and Malczynski (2014) provide an overview of translating DYNAMO models to Powersim, a modern platform for system dynamics modeling. 

## References
Fox, P. A. (2005). *An interview with Phyllis A. Fox* [Interview]. 

Pugh, A. L. (1963). *The DYNAMO User’s Manual.* The MIT Press. 

Richardson, G. P., & Pugh, A. L. (1986). *Introduction to system dynamics modeling with DYNAMO.* MIT Press. 

Walker, L. T. N., & Malczynski, L. (2014). *Converting DYNAMO simulations to Powersim Studio simulations.* Springfield, VA

