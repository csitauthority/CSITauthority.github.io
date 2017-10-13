+++
title = "I am my own grandfather problem"
date = 2017-10-11T22:13:18+05:45
draft = false

tags = ["algorithm"]
math = false

summary = """
An interesting problem with a bonus predicate calculus challenge
"""

[header]
image = ""
caption = ""

+++

Many, many years ago when I was twenty-three<br/>
I was married to a widow who was pretty as could be<br/>
This widow had a grownup daughter who had hair of red<br/>
My father fell in love with her, and soon they too were wed<br/>
This made my Dad my son-in-law and really changed my life<br/>
For now my daughter was my mother, 'cause she was my father's wife<br/>
And to complicate the matter, even though it brought me joy,<br/>
I soon became the father of a bouncing baby boy<br/>
My little baby then became a brother-in-law to Dad<br/>
And so became my uncle, though it made me very sad<br/>
For if he were my uncle, then that also made him brother<br/>
Of the widow's grownup daughter, who was of course my stepmother<br/>
Father's wife then had a son who kept them on the run<br/>
And he became my grandchild, for he was my daughter's son<br/>
My wife is now my mother's mother, and it makes me blue<br/>
Because although she is my wife, she's my grandmother too<br/>
Now if my wife is my grandmother, then I'm her grandchild<br/>
And every time I think of it, it nearly drives me wild<br/>
'Cause now I have become the strangest case you ever saw<br/>
As husband of my grandmother, I am my own grandpa<br/>


{{% alert note %}}

CHALLENGES:<br/>

1. Write Predicate Calculus representing the situation with a series of expressions 
1. Use modus ponens to conclude that “I am my own grandfather”.
{{% /alert %}}

## First Try it out yourself!
{{% expand "Solution" %}}
```prolog
Predicate Calculus representing the situation with a series of expressions: 
married(i,w).
mother(w,d).
mother(d,s1).
father(f,s1).
father(f,i).
father(i,s2).
mother(w,s2).
use modus ponens on this system to prove the conclusion that “I am my own grandfather”.
1. ∀ X Y ∃ Z married(X,Z)∧mother(Z,Y)⇒ father(X,Y).
2. ∀ X Y ∃ Z father(Z,X)∧father(Z,Y)⇒ brother(X,Y).
3. ∀ X Y ∃ Z father(X,Z),mother(Z,Y)⇒ grandfather(X,Y).
4. ∀ X Y ∃ Z grandfather(X,Z)∧brother(Z,Y)⇒ grandfather(X,Y).
5. married(i,w).
6. mother(w,d).
7. mother(d,s1).
8. father(f,s1).
9. father(f,i).
10. From 1,5,6::
	married(i,w)∧mother(w,d)⇒ father(i,d).
11. From 3,7,10 ::
	father(i,d),mother(d,s1)⇒ grandfather(i,s1).
12. From 2,8,9 ::
	father(f,s1)∧father(f,i)⇒ brother(s1,i).
13. From 4,11,12 ::
	grandfather(i,s1)∧brother(s1,i)⇒ grandfather(i,i).
```
Hence, I'm my own grandfather. 

{{% /expand %}}

### Now, a video..

{{< youtube lRkKBKyBoFM >}}

> I'm my own Grandpa. Interesting idea, isn't it?
