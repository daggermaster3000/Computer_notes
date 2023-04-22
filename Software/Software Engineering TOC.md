
> The use of systematic mehods for the production of programs

```toc
```

**Goal**
To produce cheaper, better and faster software. Today the focus is on reducing the total cost of ownership (acquisition,maintenance,support,... cost)
- Improve correctness, robustness, reliability of programs
- Improve usability
- Improve adaptibility
- Good documentation
- Efficiency is secondary

## Why is it complex?

- It depends on the complexity of the application
- Hard to organise code when working in a team, miscommunication, shitload of code
- The flexibility of the software is a constraint (each programmer will have it's own building blocks) $\rightarrow$ standardization efforts are undermined
- A continous system will be described in a discrete manner. This could lead any small event or change to be catastrophic in the discrete model

## Mastering complexity

**Inherent complexity**
Specific to the application, must be solved by the programmer

**Arbitrary complexity**
Can be minimized by a systemic approach:
- Divide and conquer
- Recognition of hierarchical structures
- Generalization
- Common patterns

## Structural analysis

![[Pasted image 20221220134618.png]]

### Data flow diagram (DFD)
DFD shows transformations without making assumptions about the implementation. Each transformation corresponds to a program unit.

### Structure diagram
It shows the hierarchy or structure of the different components or modules of the system and shows how they connect and interact with each other

### Advantages/Disadvantages
![[Pasted image 20221220135618.png]]

## Trends
- OOP programming (eliminates the disadvantages of structural analysis)
- Trend towards 4GL (easy du cul to program)