```toc
```

## [[Konjunction]](and)

## [[Disjunktion]](or)

## Laws

![[Pasted image 20221109114424.png]]
## De Morgan's theorem

$$
\begin{align}
\overline{a \cup b} = \overline{a} \cap \overline{b}  \\ \\

\overline{a \cap b} = \overline{a} \cup \overline{b}
\end{align}
$$
## Disjonktive normal form
1. Take a truth table find all the outputs with value one 
2. Take the corresponding inputs and organize them into blocks ligated by $\cap$ (minterms)
3. Equate the output with an OR ($\cup$) between every block (Disjunction of minterms)
==XOR example==
![[Pasted image 20221109173723.png]]
![[Pasted image 20221109173645.png]]

My dumbass copied it wrong

## Konjunktive normal form

1. Take a truth table find all the outputs with value zero
2. Take the corresponding inputs and organize them into blocks ligated by $\cup$ (maxterms)
3. Equate the output with an OR ($\cap$) between every block (Conjunction of maxterms)