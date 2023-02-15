# How to write a proof

During grading, I found many proofs with poor clarity and formatting, which makes getting full points difficult for your answer. 

First of all, please use latex's align environment (\begin{align}). Furthermore, do not leave out small details like subscripts and superscripts $a_0, b_0$ etc. If you leave these out, you could have points taken away due to lack of clarity, and even incorrectness if things are too confusing.

The main issues are:

* Begin the proof with exactly what you are given in the question.

* Do not skip to starting in the middle of the proofs, we do not know the steps you have taken to get there. 
    > Example: HW1 1a. write out the values of $a', b', s', t', \hat{s}', \hat{t}'$ in the inductive case you are trying to prove

* Do not leave out the actual final expression you are trying to prove. We will not complete the proof in our head for you. 

* Many points were lost because people proved the wrong statement, or people did not complete the proof fully (up to the actual final expression).

* You must write in your substitutions explicitly, we will not do it in our heads for you. (see next bullet point).

    >Example: HW1 1a. since $b = .. $ and $a' = b$ then the loop invariant holds.

Other big issues are:

* If a step in the proof is not a basic mathematical fact or requires many steps of manipulation, split it up or reference why it is true. 

* make sure your proof is easy to follow, break it up into referencable sections or statements (lemmas) if you need to. 

* many unnecessary variables are being introduced. This will muddle your thinking and introduce potentials for mistakes. Once you have an initial proof written down. Go back over it and make it more clear and concise. This will help you a lot with thinking clearly in the future.

* Try to format the proof so that you are working 'forwards' i.e. it is generally not permissible to start with the conclusion and then work to the premise. ex: 
> if $g = gcd(a,b)$ then $g$ is a factor of $a$ and $b$. 

But converse is not true:

> if $g$ is a factor of $a$ and $b$ then $g = gcd(a,b)$. 

# How to prove

I will demonstrate how to write a proof at different layers of abstraction. Feel free to start from whichever abstraction you want. 

## How to prove, Level 2
HW1. Q1.a: prove the following loop invariant. 

$$a = s a_0 + t b_0,\ \text{  and  }\ b = \hat{s} a_0 + \hat{t} b_0$$

Proof:

  Prove the base case (Statement $A$):
 1. *clearly* define all terms to be used for the base case
 2. prove the base case

  Prove the inductive case (Statement $B$):

 3. *clearly* define all terms for inductive case:

    > STATE what $a', b', s', t', \hat{s}', \hat{t}'$ are in the k+1 step.

 4. prove the inductive case for a, stating assumptions:

    > STATE: statement you want to prove ($A$):
    > $$ a' = s' a_0 + t' b_0$$
    > STATE: All assumptions (inductive hypothesis) i.e. $(R_{k-1} in the next level)$
    >
    > PROVE: 
    > in this case, we are trying to prove an equality. So you must pick either the LHS or RHS and then show that it is equal to the other side:
    > $$\begin{align*}
    LHS &= ...\\
        &= ...\\
        &= RHS.
     \end{align*} $$



 5. prove the inductive case for b
    > ...

## Abstraction Level 1

Given some algorithm, prove the loop invariant:

$$R$$

In the format of the below abstraction, we want to prove a statement like the following:

> if (P) the the algorithm is run, then (Q) the loop invariant $R$ holds in every state of the algorithm's loop.

Suppose now we decided to prove this with induction.
Proof:

We need to show that the following two statements, A and B, are true:

(Statement $A$) Base case: $$P \implies R_0$$

(Statement $B$) Inductive case: 

$$\text{IF  } (R_{k-1}) \text{  HOLDS, THEN  } R_k \text{ holds.}$$ 

In other words:

$$\text{ASSUME  } (P \implies R_{k-1}) \text{ THEN  } R_k \text{ holds.}$$

\n

Finally we can conclude by the Theorem of the Principle of Mathematical Induction: If $A \land B$ then $Q$ (the loop invariant hold).

### How does this work?

If we prove statements $A$ and $B$, then we can use them to show that

$$
\begin{align*}
 P & \implies R_0 & \text{by } A \\
  &\implies R_1 & \text{by } B \\
  &\implies R_2 & \text{by } B \\
  &\implies ... \\
  &\implies R_k \text{ for all } k \in \mathbb{N} & \text{by } B. 
\end{align*}
$$

## Abstraction level 0

We want to show that some statement $P$ implies $Q$.

Statement we want to prove: $$P_0 \implies Q$$

Proof:

$$
\begin{align*}

P_0 & \implies P_1 \\
& \implies P_2 \\
& ... \\
& \implies Q ~~ \square
\end{align*}
$$

Where statements $P_i$ follow from $P_{i-1}$ easily or naturally (basic mathematical facts). Or as given in class, or already proved previously (corollary, lemma, theorem). 