---
layout: post
title: "Truth and potentialism"
date: 2019-06-18 ## need to change this when done to be accurate
---

Consider the following set-up, arising from discussion with [Neil Barton](https://neilbarton.net/) over multiple coffees at [Das Voglhaus](http://www.das-voglhaus.de/). You think that classes are objects. And you think that if are committed to some object, then you should also be committed to the truth predicate about that object. So you should always be able to expand your classes by adding truth predicates. This can naturally be interpreted in a potentialist framework. What is the nature of the corresponding potentialist system? The answer, as I would like to explicate in this blog post, is that it depends.
<!--more-->

Let me begin by recalling the potentialist framework for you, putting it in the relevant context. Our worlds are models $(M,\mathcal{X})$ of second-order set theory, with $M$ being the sets and $\mathcal X$ being the classes. A *potentialist system* is a collection of worlds ordered by a relation which refines the submodel relation. We are specifically interested in the case where all worlds have the same sets and the accessibility relation is just the inclusion relation.

A potentialist system has a natural associated modal logic. Namely, we say that $\diamondsuit \phi$ holds at a world if $\phi$ holds in some extension of that world, and $\square \phi$ holds at a world if $\phi$ holds in every extension of that world. A natural question is then: which modal assertions are valid for the potentialist system? The modal theory S4 is always a lower bound for this, because S4 is valid on any reflexive, transitive frame. (A precise axiomatization of S4 can be found on [The Stanford Encyclopedia of Philosophy](https://plato.stanford.edu/entries/logic-modal/), but you're better off thinking in terms of the frame condition.)

The basic properties we would like our classes to satisfy are encapsulated by the Gödel–Bernays axioms GB. We can uses classes in Replacement and we can define classes by quantifying over sets, but we don't guarantee that second-order quantification can be used to define classes, nor do we assume any form of Global Choice. In terms of models, if $M$ is any model of ZF then adjoining its definable classes to get $(M,\mathrm{Def}(M))$ yields a model of GB. More generally, if $A$ is any sufficiently amenable class then $(M,\mathrm{Def}(M,A))$, where we are allowed to use $A$ as a parameter in definitions, is also a model of GB. The idea is that if we can talk about a class, we can also talk about any classes predicatively definable from it. Because the sets are fixed, these definitions only quantifying over sets are stable across adding more classes.

Fix some transitive model $M$ of ZF, which we will think of as being the universe of sets we work over. Thinking about the set-up sketched above we can extract three properties we need from our potentialist system. First, $(M,\mathrm{Def}(M))$ should be one of the worlds. Second, if $(M,\mathcal X)$ is any world then it should satisfy GB. Third, if $(M,\mathcal X)$ is any world and $A \in \mathcal X$ is a class in that world, then $(M,\mathcal X[\mathrm{Tr}(A)])$ is also a world. To explain the notation, $\mathrm{Tr}(A)$ is the Tarskian truth predicate relative to the parameter $A$, giving us the satisfaction relation for the structure $(M,\in^M,A)$. And $\mathcal X[B]$ is the smallest GB model over $M$ extending $\mathcal X$ which contains $B$. Specifically, $\mathcal X[B]$ consists of all classes over $M$ definable using $B$ and finitely many classes from $\mathcal X$. 

These three minimal requirements already limit what $M$ could be. If we have $\mathrm{Tr} = \mathrm{Tr}(\emptyset)$ as a class, then we can reflect it down to get club many $\alpha$ so that $V_\alpha$ is an elementary submodel of the whole universe. In particular, our $M$ must have many undefinable ordinals. This rules out, for instance, $M$ being a Paris model.

Given these three requirements and given a fixed appropriate $M$, there is a smallest potentialist system we can consider which satisfies them. Namely, set $\mathcal X_0 = \mathrm{Def}(M)$ and for $n > 0$ set $\mathcal X_n = \mathrm{Def}(M,\mathrm{Tr}_n)$. Here, $\mathrm{Tr}_n$ is the iterated truth predicate (relative to the parameter $\emptyset$) of length $n$. It is inter-definable with $\mathrm{Tr}(\mathrm{Tr}(\cdots(\mathrm{Tr}\cdots)))$ ($n$ times, of course). Then the collection of the worlds $(M,\mathcal X_n)$ for $n \in \omega$ is the smallest potentialist system over $M$ which satisfies these three requirements. 

It is easy to see that S4.3 is a lower bound for the modal validities, assuming that you remember what S4.3 is. Let me help: S4.3 is the extension of S4 by the .3 axiom. And now you know everything!

To actually help: the .3 axiom expresses a kind of linearity. Formally it is $(\diamondsuit\varphi \wedge \diamondsuit\psi) \Rightarrow (\diamondsuit(\varphi \wedge \diamondsuit \psi) \vee \diamondsuit(\diamondsuit \varphi \wedge \psi))$. In plain language, it asserts that if two propositions are possible then it is possible to have one true while the other remains possible. It is now a straightforward exercise to check that any linearly ordered frame validates .3. 

If we allow ourselves to build upward a little further, there is an easy argument to obtain the modal validities to be precisely S4.3. Let me motivate this further upward climb. In our smallest potentialist system over $M$, our worlds only have $n$-iterated truth for finite $n$. But we might think that if we have all these truth predicates, then we ought to go one step further and have uniform access to the entire sequence. Such uniform access cannot be definable from a single one of these truth predicates, as that would contradict Tarski. So this represents a further step. 

This can be formalized by allowing iterated truth predicates of transfinite length. For the case from the previous paragraph, the length is $\omega$. But once you accept going to $\omega$, it's clear to see how you could go even further and talk about iterated truth predicates of length $\alpha$ for any ordinal $\alpha$. We could go even further and index the levels of a truth predicate by a class well-order, possibly of length $> \mathrm{Ord}$. (The reader who wants a formal definition is encouraged to check out [this paper]({{ site.baseurl }}/research/pubs/class-forcing-theorem/).) 

Given an ordinal $\beta$, we can ask about the smallest potentialist system over $M$ where we can always expand the classes by adding an iterated truth predicate of length $<\beta$. (So the finite case above is for $\beta = \omega$.) If $\beta$ is additively decomposible then this potentialist system has worlds with classes $\mathcal X_\alpha = \mathrm{Def}(M,\mathrm{Tr}_\alpha)$, for $\alpha < \beta$. Call this the *$<\beta$-iterated truth potentialist system for $M$*.

**Fact**: The modal validities of the $<\beta$-iterated truth potentialist system for $M$ are precisely S4.3, provided $\beta \ge \omega^2$.

*Proof*: We already know S4.3 is a lower bound. It remains to see that S4.3 is also an upper bound for the validities. To do this we will use the device of a *long ratchet*, adapting a definition due to George Leibman. Recall that a *button* is a statement $\beta$ so that $\beta \Rightarrow \square \beta$. That is, once you push a button by making it true it stays true forever. A *long ratchet* is a uniformly definable sequence of buttons $r_\alpha$, indexed by ordinals $\alpha$ so that pushing $r_\alpha$ pushes $r_\beta$ for all $\beta < \alpha$ and so that in no world are all buttons on the ratchet pushed. Observe that this second condition forces the ratchet to have limit length, as if there were a last button then we could push it to push all the buttons.

**Lemma**: If a potentialist system admits a long ratchet of length $\ge \omega^2$ then S4.3 is an upper bound for its modal validities.

*Proof*: This goes through the fact that having arbitrarily long finite ratchets which are independent with arbitrarily large independent families of switches gives S4.3 as the upper bound. A *ratchet* is like a long ratchet, except finite in length (and so you don't require it to not be fully pushed) and a *switch* is a statement you can switch on or off freely. The idea is that you can simulate these by thinking of your index on the long ratchet as $\omega \cdot \alpha + k$, where $k < \omega$. The $\alpha$ part gives you the index on the (short) ratchet, where we declare that if $\alpha$ is too big then we sit at the last stage on the ratchet. Meanwhile the bits of $k$ simulate the switches. These can freely be changed without increasing the index on the ratchet. Having length at least $\omega^2$ on the long ratchet gives us enough space to do this.

It is now clear how to proceed. Let $r_\alpha$ be the assertion that the $\alpha$-iterated truth predicate exists. Then $\langle r_\alpha : \alpha < \beta \rangle$ gives a long ratchet for the potentialist system. So S4.3 is an exact upper bound for the modal validities. 

The takeaway from this fact is that if you look at this smallest potentialist system that might capture your intuition about building up more and more classes by adding truth predicates, then it exhibits a linear character, and validates exactly S4.3. This is one answer for the "it depends" from the introduction to this blog post. Let me now give an alternative picture, which may have a different answer.

Start with just the definable classes seems reasonably safe. Under most conceptions of class, we need at least the definable classes. And extending by adding truth predicates also seems reasonable (or at least, I have stipulated that it is worth consideration). But these may not be enough. We may think that there should be a global well-order, even if it is not (first-order) definable. But it's consistent to have as long of iterated truth predicates as you like without having a global well-order. So we must have something more for our potentialist system.

I will discuss two possibilities. The first is that rather than starting off with the definable classes, we start off with the classes definable from a fixed global well-order. The second is that we allow ourselves to add a generic global well-order by class forcing.

Let's start by looking at the first possibility. I wish to argue that the choice of starting global well-order may affect the nature of the corresponding potentialist system. As a warmup, let's see that some global well-orders are inter-definable with Cohen-generic classes of ordinals. For one direction of this, note that if $C \subseteq \mathrm{Ord}$ is Cohen-generic then, by density, every set is coded into the bit pattern of $C$. So we can define a global well-order by comparing where sets are first coded. Now note that if we take such a global well-order we can rearrange it so that it has the ordinals, in increasing order, placed precisely on the indices where $C$ has value $1$. Such a global well-order is still definable from $C$, and notice that if we have such a global well-order we can recover $C$ by looking at the indices for where ordinals appear. So the two are inter-definable. 

For what follows I will work directly with the Cohen-generics. I claim that we can have a Cohen-generic which codes two Cohen-generics $C$ and $D$ satisfying the following properties: (1) $\mathrm{Tr}_i(C)$ and $\mathrm{Tr}_j(D)$ are not definable from $\mathrm{Tr}_k$ for any ordinals $i,j,k$; (2) $\mathrm{Tr}_i(C)$ is not definable from $\mathrm{Tr}_j(D)$ for any ordinals $i,j$; and (3) $\mathrm{Tr}_j(D)$ is not definable from $\mathrm{Tr}_i(C)$ for any ordinals $i,j$. Note that to arrange this we really have to only find such $C$ and $D$ which are mutually generic; we can code them into a single Cohen generic using that Cohen forcing is equivalent to its finite product with itself.

To find these $C$ and $D$, we simply take $(M,\mathcal Y)$ a model of GB + ETR($\mathrm{Ord}$) and force over it to produce two mutually generic Cohen subclasses of $\mathrm{Ord}$. Here, ETR($\mathrm{Ord}$) is the axiom asserting that $\mathrm{Ord}$-length iterated truth predicates always exist. (It is equivalent to a certain transfinite recursion principle; see [this paper]({{ site.baseurl }}/research/pubs/class-forcing-theorem/) for details.) Gitman and Hamkins showed that tame class forcing, such as Cohen forcing, preserves ETR($\mathrm{Ord}$). From this fact one can easily check that (1–3) of the previous paragraph are obtained. 

Consider now the $<\mathrm{Ord}$-potentialist system obtained over $M$ by starting with $(M,\mathrm{Def}(M,C,D))$ as the smallest world. That is, we can extend a world in this potentialist system by adding a length $\alpha$ iterated truth predicate relative to an extant class, where $\alpha$ is any ordinal in $M$. The reader should convince herself that we can index worlds by three ordinals, call them $\gamma, \delta, \eta$, with $\eta \ge \max\{\gamma,\delta\}$. Namely, $\gamma$ tells us how long an iterated truth predicate relative to $C$ we have, $\delta$ tells us the length for $D$, and $\eta$ tells us the length for the iterated truth predicate relative to no parameter. 

**Fact**: The modal validities for this potentialist system contain S4.2 and are strictly contained within S4.3.

*Proof*: Recall that the .2 axiom is $\diamondsuit \square \varphi \Rightarrow \square \diamondsuit \varphi$. This axiom is valid on any directed frame. Our potentialist system is directed, so it validates S4.2. It remains only to see that .3 is not valid. Let $\varphi$ assert that $\mathrm{Tr}_7(C)$ exists but $\mathrm{Tr}_7(D)$ does not exist, and let $\psi$ assert that $\mathrm{Tr}_7(C)$ does not exist but $\mathrm{Tr}_7(D)$ does exist. Then in the world indexed by $(0,0,0)$ we have that $\varphi$ and $\psi$ are both possible. However, if $\varphi$ is true then $\psi$ is impossible, and if $\psi$ is true then $\varphi$ is impossible. This witnesses a failure of .3.

The lesson here is that if we just randomly pick a global well-order to throw into our classes, then it's possible that .3 gets invalidated. On the other hand, if we happened to start with a model with a definable global well-order, then the earlier analysis shows we do get a potentialist system which validates S4.3. So the choice of a global well-order can matter.

Let's now turn to the other option, where we allow ourselves to add a global well-order by class forcing. That is, we want to expand our potentialist system by adding a new rule to get new worlds: if $(M,\mathcal X)$ is a world then so is $(M,\mathcal X[G])$ whenever $G$ is a Cohen subclass of $\mathrm{Ord}$ generic over $(M,\mathcal X)$. We will start with the definable classes as the smallest world, and keep the old rule about being able to add truth predicates relative to extant classes. 

The problem is that this potentialist system is actually quite destructive. Specifically, adding a global well-order may kill off the possibility of adding a truth predicate while preserving the basic axioms of GB.

**Fact**: Let $M$ be a countable transitive model of ZF. Then there is $G$ Cohen-generic over $(M,\mathrm{Def}(M))$ so that no GB realization for $M$ can contain both $G$ and the truth predicate for $M$ (relative to no parameter).

*Proof*: First observe that from the truth predicate we can define $\langle D_\alpha : \alpha \in \mathrm{Ord} \rangle$ a sequence of dense subclasses of the Cohen partial order to add a generic class of ordinals so that meeting every $D_\alpha$ guarantees genericity over $(M,\mathrm{Def}(M))$. This is because we can take $D_\alpha$ to be the intersection of all open dense classes definable with parameters from $V_\alpha$. The point is, from the truth predicate we can define this sequence, because the truth predicate gives us uniform access to definability. Then $D_\alpha$ is open dense because the forcing is $\kappa$-distributive for every $\kappa$. And clearly meeting $D_\alpha$ implies getting below every definable dense class. 

Now let's use this sequence of $D_\alpha$s to code a bad real into a generic. Fix a binary sequence $B : \mathrm{Ord} \to 2$ so that the set of $i$ so that $B(i) = 1$ is cofinal in the ordinals of $M$ and has ordertype $\omega$. Note that no GB realization for $M$ can contain $B$, as $B$ reveals that $M$'s ordinals have countable cofinality. Define a sequence of conditions: start with $p_0 = \emptyset$. Given $p_\alpha$, extend to meet $D_\alpha$, where we require the extension to be of minimal length to get into $D_\alpha$. Then add on the bit $B(\alpha)$ to get $p_{\alpha+1}$. And at limit stages, set $p_\lambda = \bigcup_{\alpha < \lambda} p_\alpha$. Then $G = \bigcup p_\alpha$ meets every definable dense class. 

Finally, note that if you have the sequence $\langle D_\alpha \rangle$ and $G$, you can recover the coding points. This is because it is a definable, in this data, property to see the shortest distance you had to extend to meet the next dense class. So if you had both $G$ and the truth predicate in a GB realization for $M$, then you would also have $B$ in the GB realization. This is a contradiction. 

To be a bit flippant, the problem with this would-be potentialist system is that there was too much freedom. We had too much freedom to allow generics, and this allowed the freedom to construct a post-truth universe. (I leave it to the reader to draw any political conclusions from this 😘)

In terms of the modal logic, this witnesses a failure of the .2 axiom. At the world $(M,\mathrm{Def}(M))$ we have that "the truth predicate exists" is possibly necessary, but it is not necessarily possible. There is a fundamental branching going on here. Once we decide to add in this specific generic $G$, we have permanently committed to never adding in a truth predicate. Of course, the point of this potentialist system was to try to capture the idea of being able to extend the classes by adding truth predicates. In this light, we should see the potentialist system as failing at its intended purpose. 



To try to draw a moral from this story of three potentialist systems: the specifics of how you try to formulate things can have a big impact. We started with a basic, seemingly harmless idea—you should be able to analyze the classes potentialistically by considering adding truth predicates for extant classes—and once we combined it with the another seemingly harmless idea—Global Choice should be true, even if there is no definable global well-order—we saw some friction appeared. The friction could be, on one way of formulating things, relatively benign. We have a different modal logic attached to the potentialist system, but the rest is okay. But the friction could also be more destructive, if we made other decisions about how to formulate things. 
