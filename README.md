# Review: Ndepend 2017.3

After using Visual studio enterprise (VS) and Resharper (R#), a while, following design patterns such as **MVVM**, **DI**, we might want to have a more precise overview of the application being developed. But not Visual studio enterprise nor Resharper can give any significant, relevant view on the code and what it does, and how well, how ideas are organized, etc.

I have a medium-big progam involving both **computer vision** and **realtime image/video editing**; it involves c#, c++, matlab, MKL, cuda code, but most of it is **c#**; it has about 10k LOCs, has a computing part and a graphical user interface (GUI) part, it has **MVVM** pattern, and uses **Prism** and **Unity** for **DI** patterns; it has unit tests, even though it's not **TDD**; it has metrics for performance measurements in many critical places.

I often have the practice of having everything in mind and then I write code: I have the global ideas and architecture in mind as I code and craft my local ideas. With this project, I needed some time to just have the global feeling back (yes, you can say I was not able to read my code). Hum. Not that good, but I have no means to know if it was me or my implementation.

I have a quite big **ViewModel** class, which is classical, with implementation in several files (partial public class), for different aspects.

Question: is it a code smell despite I'm following the MVVM pattern ?

## Why and when Ndepends ?

Here comes the necessity of Ndepend as static code analyser to understand better differents aspects of the program, and have quite specific requests about the code.

Ndepend is quite rich and has many already implemented **rules**, **quality gates**, and **issues**. Those rules are totally transparent: they are open source, they are commented and explained, they can be changed, eg., to match our interpretation of **too big**, and _we can implement new ones_ !

 In version 2017.2 there was many "false positives", and it was corrected in 2017.3, but actually all those metrics, thresholds are kind of personnal and depend on your style, organization needs, and so on.

## How does Ndepend work ? The power of linq into static analysis.

c# is an amazing language to read, write and craft, for the sake of the language, but also thanks to the ecosystem: IDEs, libraries, SO (stack overflow), support, the compiler Roslyn being open source. c# is amazing. Linq is amazing: well written, flexible, simple and extremely powerful. The core of Ndepend is to do Linq over our code (rules) and to have a GUI over that to present the results, which can be instantaneous as well as dynamic, ie, how those metrics evolve in time.

Ndepend is totally transparent about the requests (rules, quality gates and issues), which can be modified according to our needs and tastes, which are explained: Ndepend provides **description** of the rule and **how to fix**.

Let's have here an example, a code smell rule called "avoid types with too many methods": ![linq rules][linqrules]

[linqrules] :https://github.com/mprevot/ReviewNdepend/tree/master/images/linqrules.jpg "linq rule example"

## The analysis power of Ndepend.




## Ideas of future evolution of Ndepend

### Automation on code refactoring

I would love to be able to ask to Ndepend to (semi-)automatically refactor my code to solve the bad metrics and improve the code. Actually it goes beyond refactoring since the architecture is changed, and refactoring is not supposed to affect the architecture.

### Market place on code crafting, patterns matching

### Realtime metrics



