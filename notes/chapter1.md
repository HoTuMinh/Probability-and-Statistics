# CHAPTER I. SAMPLE SPACE AND PROBABILITY 

### Introduction 

**_What even is probability anyway?_** <br/>

Well there're 2 ways to think about the term
1. probability is the **frequency of occurence**
2. it expresses a subjective belief <br/>

$\rightarrow$ Overall, probability is used when discussing an **uncertain** situation <br/>

**_What you will learn after reading the book_**
- the art of **describing uncertainty in terms of probabilistic models**
- the skill of **probabilistic reasoning**

### Sets (probability makes extensive use of set operations)

- **set**: a collection of objects 
  - $S = \lbrace x_1, x_2, ..., x_n \rbrace$
  - die roll $\rightarrow \lbrace 1, 2, 3, 4, 5, 6 \rbrace$
  - coin toss $\rightarrow \lbrace H, T \rbrace$

- **elements**: objects of the set 
  - element $x$ is in the set: $x \in S$
  - element $x$ is not the set: $x \notin S$

- **empty set**: $ \emptyset $ 

- the set of all $x$ that have **certain property** $P$: $\lbrace x |x \space satisfies \space P \rbrace$

- there are **uncountable sets**
  - example $\lbrace x|0\le x \le 1 \rbrace $

- **subset**: if every element of a set $S$ is also an element of a set $T$, we say that $S$ is a subset of $T$
  - $S \subset T$
  - $T \supset  S$
  - if $S \subset T\space and \space T \subset T$, then $S =T$

- **universal set** (everything): $\varOmega$

- the **complement** of a set $S$
  - $\lbrace x\in \varOmega | x \notin S \rbrace$
  - $\varOmega ^c = \emptyset$

- **union** $\cup$: belongs to $S$ or $T$

- **intersection** $\cap$: belongs to both sets 

- 2 sets are **disjoint** if there intersection is empty

- a collection of sets is said to be a **partition** of a set $S$ if the sets in the collection are disjoint and their union is $S$

- **algebra of sets** 
  - properties of set operations
![properties of set operations](/notes/images/1.1.jpg)
  - properties of set operations given by the De Morgan's law
![properties of set operations_given by De Morgans law](/notes/images/1.2.png)
  - proof: to establish the 1st law, suppose that $x \in (\cup_nS_n)^c$. Then $x \notin \cup_nS_n$, which implies that for every $n$, we have $x \notin S_n$. Thus, $x$ belongs to the complement of every $S_n$, and $x \in \cap_nS^c_n$. This shows that $(\cup_nS_n)^c \subset \cap_nS^c_n$. The converse inclusion is established by reversing the above argument, and the 1st law follows. The argument for the 2nd law is similar. 

### Probabilistic Models
- a probabilistic model is a **mathematical description** of an **uncertain situation** <br/>
- it contains
![a probabilistic model](/notes/images/1.3.png)

1. the **sample space**
- is the set of all **possible outcomes** of an experiment ($\varOmega$)
  - may consist of a finite or infinite number of possible outcomes
  - **event** → a subset of the sample space - a collection of possible outcomes
  - there is only 1 experiment
  - different elements of the sample space should be **mutually exclusive** (whenever the experiment is carried out there is a unique outcome)
  - the sample space must be **collectively exhaustive** → we always obtain an outcome that has been included in the sample space
- natural properties of a probability model
  - $1=P(\Omega)=P(\Omega \cup \emptyset) = P(\Omega)+P(\emptyset)=1+P(\emptyset)$
  - $P(\emptyset)=0$
  - $P(A_1\cup A_2 \cup A_3) = P(A_1 \cup (A_2 \cup A_3)) = P(A_1)+P(A_2+A_3)=P (A_1) + P (A_2) + P (A_3)$

2. the **probability law**
- assigns to a set of $A$ possible outcomes (events) a nonnegative number $P(A)$ (the **probability** of $A$) that encode our knowledge or belief about the collective “likelihood” of the elements of $A$
- The probability law must satisfy certain properties (**probability axioms**):
  1. **Nonnegativity**: $P(A) \le 0$, for every event $A$
  2. **Additivity**: if $A$ and $B$ are 2 disjoint events, then the probability of their union satisfies $P(A\cup B) = P(A) + P(B)$ (generally, for $n$ events)
  3. **Normalization**: the probability of the entire sample space $\Omega$ is equal to $1$, that is, $P(\Omega) = 1$
- properties of probability laws
  - consider a probability law, and let $A, B, C$ be events
    - if $A \subset B$, then $P(A) \le P(B)$
    - $P(A\cup B)=P(A) + P(B) - P(A\cap B)$
    - $P(A\cup B) \le P(A) + P(B)$
    - $P(A\cup B \cup C) = P(A) + P (A^c \cap B) + P(A^c \cap B^c \cap C)$

#### Sequential models 
- example: tossing a coin 3 times
- we often use a **tree-based sequential description** to visualize

![tree-based sequential description](/notes/images/1.4.jpg)

#### Discrete models 
- example: an experiment involving a single coin toss
- $\Omega = \lbrace H,T \rbrace$
- the events are $P(\lbrace H,T\rbrace)=P(\lbrace H \rbrace) + P(\lbrace T \rbrace) = 1$
- the probability is given by
  - $P(\lbrace H, T \rbrace) = 1$
  - $P(\lbrace H \rbrace) = 0.5$
  - $P(\lbrace T \rbrace) = 0.5$
  - $P(\lbrace \emptyset \rbrace) = 0$
- **discrete probability law**: the probability of any event $\lbrace s_1, s_2,...,s_n \rbrace$ is the sum of the probabilities of its elements (if the sample space consists of a finite number of possible outcomes)
- $ P(\lbrace s_1,s_2,...,s_n \rbrace) = P(s_1) + P(s_2) + ... + P(s_n)$
- **discrete uniform probability law**: if the sample space consist of $n$ possible outcomes which are equally likely, then the probability of any event $A$ is given by
    
    $P(A)=\frac{number \space of \space elements \space of \space A}{n}$

#### Continuous models 
- in continuous models, the probabilities of single-elment events may not be sufficient to characterize the probability law
- example: wheel of fortune with values $[0,1]$ → assign probability $b-a$ to any subinterval $[a,b]$ of $[0,1]$

#### Models in real-world context 
- when constructing a model IRL, there are 2 steps
1. construct a probabilistic model by specifying a probability law on a suitably defined sample space (must conform to the 3 axioms)
    - there is a trade-off between accuracy - simplicity - tractability
2. work within a fully specified probabilistic model & derive the probabilities of certain events 

### Conditional Probability 

### Total Probability Theorem and Bayes' Rule 

### Independence 

### Counting 

### Summary and Discussion 
