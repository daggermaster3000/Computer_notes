```toc
```

We want to create a circuit to add two binary numbers. For this we have to keep in mind the logic we implement subconsiously as humans.

**For addition**
- $0+0=0$
- $0+1 = 1$
- $1+0=1$
- $1+1=0 \text{, carry }1$

**For subtraction**
- $0-0=0$
- $0-1 = 1 \text{, borrow 1}$
- $1-0=1$
- $1-1=0$
Subtracting is the same as adding two's complement (for dual numbers)

**Two's complement**
- Complement each digit 
- Add 1

## Half adder

Let's start with the MF table for two inputs bits (a and b) and a sum and carry output:
|       |     |        |     |
|:-----:| --- |:------:| --- |
| Input |     | Output |     |
| a   | b   | S   | C   |
| --- | --- | --- | --- |
| 1   | 0   | 1   | 0   |
| 1   | 1   | 0   | 1   |
| 0   | 0   | 0   | 0   |
| 0   | 1   | 1   | 0   |

From there we can get the KNF (=0, merge with conjuction (AND)) for $S$:
$(a \cup b) \cap (\overline{a} \cup \overline{b}) = S$
And the DNF (=1,merge with disjunction (OR)) for $C$:
$(a \cap b) = C$

And implement already
![[Pasted image 20221128095717.png]]

Or simplyfy some more using (NOT-OR == NAND)
![[Pasted image 20221128114511.png]]
and therefore
![[Pasted image 20221128114730.png]]
And also for the and gate
![[Pasted image 20221128115008.png]]
 Then we get using only NANDs:
 ![[Pasted image 20221128120628.png]]

## Full adder
We can then implement the full adder that takes the carry into account.
We can XOR or OR the two half adders carry outs (also they will never be both on).
![[Pasted image 20221128174206.png]]
We can then create a 4-bit adder.
![[Pasted image 20221128174626.png]]
## Subtractor
Subtracting two numbers is the same as adding the two's complement. (invert then add 1)
![[Pasted image 20221128182606.png]]
Overflow can be indicated by XOR of the two highest bits (here implemented in NANDS).

## Adding a multiplexer to switch between states

![[Pasted image 20221220113758.png]]
