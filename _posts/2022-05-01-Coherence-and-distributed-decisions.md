---
title: Coherence arguments lead to utility theory
subtitle: Theory of mind in intelligent agents
layout: default
date: 2022-05-02
keywords: decision theory, utility theory
published: true
permalink: /blog/coherence-arguments-lead-to-utility-theory
---
### Motivation
Are there “correct” ways of thinking about how an intelligent agent reasons? 

We present some fundamental properties an intelligent agent should posses, motivate this with the concrete examples of the pizza party and hospital budget. 

Observing an intelligent agent's behavior(externally) we reason about how they are thinking(internally) [1].

### Optimal behavior respects transience

We are in a pizza party. Everyone is there to eat their favorite pizza. Also there, we observe the actions of an intelligent agent, that has some money in their pocket and has come to eat some good pizza. 

Suppose now that we can read that agent's mind, and that we see their underlying pizza slice preferences. They are the following:
{% katexmm %}
$$
\text{onion}>_P \text{pineapple}>_P \text{mushroom}>_P \text{onion},
$$
{% endkatexmm %}
where the relationship {% katexmm %}$a >_P b${% endkatexmm %} indicates that the agent prefers pizza {% katexmm %}$a${% endkatexmm %} to pizza {% katexmm %}$b${% endkatexmm %}.

We see the agent holding a slice of mushroom pizza. 

They are offered the following deal by the pizza-maker: "You can give me your mushroom slice back, and pay {% katexmm %}$1\$${% endkatexmm %} to switch to pineapple." Since they prefer pineapple pizza to mushroom (see Figure 1), if they deem the cost low enough, they should switch. Let’s say that {% katexmm %}$1\$${% endkatexmm %} is low enough according to their budget, and thus they choose to switch (acting according to their preferences). 

Suppose that switching to any other pizza is free for them, i.e. they can go from pineapple to onion and onion to mushroom for free.

We notice that these actions are consistent with their preferences (they acted on them). 

But what has happened overall? 

The agent started from a mushroom slice, payed {% katexmm %}$1\$${% endkatexmm %}, wasted a bunch of time switching pizza slices and ended up with the same mushroom slice! 

Hmm, this doesn't seem that intelligent to me... "If they wanted a mushroom slice why didn't they just hold the original in their hands?", you ask. Well, you just discovered a strategy that could have worked out better for them!

What can we abstract away from this reasoning? 

Surely, any agent that is at least as intelligent as a human being (or seems to be that way, judging from their actions), should have an underlying preference ordering by which the actions they takes are not worse by any other action they could have taken. 

What we mean is that there should be no action that we can come up with that is stricly better than the one the agent took. That is, for any strategy the agent takes, there exists no other it could have taken such that it performed better (with a specific goal in mind, in this case to eat their favorite pizza). 

Hence, suppose we train a system (agent), through an optimization procedure, whereby they learn some preference ordering. 

Now it is time for it to make an action in the real world, according to those preferences. 

If a system (agent) is sufficiently optimized (intelligent), then the preference ordering {% katexmm %}$>_p${% endkatexmm %} it seems to operate by should respect the property of transience
{% katexmm %}
$$
\text{if }x>_p y,\:\text{and }y>_p z,\:\text{then }x>_p z.
$$
{% endkatexmm %}

From an observer's perspective, this is a property that needs to hold for a system that seems to take behave optimally.

Maybe now you say: “Let's fix the problem above by assigning a specific value to each possible outcome of an agent's action. If the agent "weighs" their options carefully, they could then behave optimally.” 

This goes one more step into the right direction. Let's investigate via a concrete example!

### Dutch-book arguments: consistent values in actions

Suppose Mary runs a hospital. She has some overall budget, and can take certain actions to pursue her goal: maximize the number of lives saved. 

Bellow are some possible choices she has, along with the expected number of lives each choice saves.

* {% katexmm %}$100,000\$${% endkatexmm %} to buy an x-ray machine, and save 5 lives
* {% katexmm %}$400,000\$${% endkatexmm %} to perform a heart transplant to John, and save 1 life
* {% katexmm %}$10,000\$${% endkatexmm %} for a special machine to detect COVID-19 in visitors within 1 minute, and save 10 lives
* {% katexmm %}$1,000,000\$${% endkatexmm %} to perform a brain surgery for an infant, and save 1 life

Now suppose two things. 

Firstly, Mary has an overall fixed budget of {% katexmm %}$1,000,000\$${% endkatexmm %}, and only cares about maximizing the number of lives the hospital saves. 

Secondly, suppose Mary values each human life equally. 

Then, we will argue the following: Mary has to behave as someone placing a consistent dollar value to saving a human life. 

Meaning, if Mary is doing a perfect job (saving the most lives she can), we should be able to infer a statement as follows:
{% katexmm %}
$$
\text{Mary took any action costing }\leq 500,000\$,\text{  if it saved more than one life.}
$$
{% endkatexmm %}

Otherwise, if we cannot externally see Mary doing this, that means she is not taking the best actions to save the most people. 

That is, there would be a different sequence of actions she could have taken to save more lives. 

Does this reasoning tell us how to value each life saved in dollars? 

No. What we understand though is that from the outside, to claim that a system performs optimal choices (there exist no other strategy strictly better), it must then be assigning some value to each human life. 

What are the caveats of this approach? Do we know the specific dollar value that Mary is valuing lives at? 

Well, it could be anything from {% katexmm %}$500,000\$${% endkatexmm %}, up to {% katexmm %}$1,000,000\$${% endkatexmm %}. 

Also, we haven’t proven any property about Mary’s inner thinking, we only asked: "Is Mary's outward behavior consistent with her goal of maximizing lives?"

Maybe now you ask: "What if each life is not worth the same to Mary? Could it be that she values 3 adolescents as much as 1 grandmother, 2 adults as much as 6 grandparents, and so on?" 

Well, if we cannot infer an ordering of her outward behavior that respects the property of transience, we cannot claim that Mary is doing the best she can in maximizing the number of lives saved. 

This means that in Mary’s behavior, there should be some relative value of how much a 22-year-old man is worth, compared to a 42-year-old woman.

## Pretty disturbing so far, what's next?

With the above two examples we infer that: 

a) we should describe each of our transience-respecting preferences by a value, say a multiple of 1 utilon, and 

b) we can adjust this by setting the value of a specific choice by 10 utilons, and according to our preferences give consistent values to everything else. 

Remember, you can prefer specific onion slices over other onion slices. You can have whatever preferences you want. 

However, when you have stated your qualitative preferences of some things over others, if you claim to make optimal trades (that can be viewed as not qualitatively leaving behind things you wanted), we can view you as assigning coherent quantitative utilities to everything you want.

Neat!

## How does probability play into this?

Let's dig into an example.

I am usually tired by lunch time, and after lunch it helps me to do one of two things: go for a walk if the weather is sunny, or take a nap if the weather is not sunny. 

I use these two strategies to recover, and as they are different, one might help me more than the other. Or one could hurt me more than the other. 

It could be that I go for a walk and my mind gets de-clogged and I can work better, or it could be that I take a nap, and need an hour to really wake up afterwards to get to work. 

Thus, different actions lead to different rewards, depending on which action we take.

**Theorem**
If you’re using qualitatively optimal strategies, then you must behave as if you are multiplying utilities by numbers. These numbers must add up to 1.

**Proof**
We will prove this by contradiction. 

Suppose we call the utilities of your actions/decisions {% katexmm %}$u_i${% endkatexmm %}, and the numbers they are multiplied by {% katexmm %}$p_i${% endkatexmm %}. 

We have two cases.

Case 1: {% katexmm %}$\sum_{i} p_i >1${% endkatexmm %} , for events that are mutually exclusive

Let’s the following example. 

I present you with the following gamble. You give me one onion slice, and then we flip a coin: if it lands head (with {% katexmm %}$p_1 = 2${% endkatexmm %}), I give you 0.5 onion slices, and if it lands tails (with {% katexmm %}$p_2=1${% endkatexmm %}), I’ll give you 0.5 onion slices as well. 

Then, you would expect to get
{% katexmm %}
$$
2\times\frac{1}{2}\text{ onion slice}+1\times\frac{1}{2}\text{ onion slice}=\frac{3}{2}\text{ onion slices }.
$$
{% endkatexmm %}

So you would take the gable, and end up with 0.5 onion slices! Something's wrong here...

Your strategy seems to be strictly worse than doing nothing. 

Thus, it is not optimal! 

So, the sum of the coefficients of your utilities should not bigger than one. 

Case 2: {% katexmm %}$\sum_{i} p_i <1${% endkatexmm %}, for events that are exhaustive

Can you imagine how to break this case? 

See if you can construct an example!


This concludes why the sum of the coefficients of the utilities should be 1, if we want the agent to behave optimally. 

*Remark*

Notice that we started from utility functions, and concluded for the presence of probability!

### Conclusions

Suppose we want to reason about an agent, whose aim is to act optimally according to their objective. 

Then, for the agent to avoid the above pitfalls, their preference ordering must be coherent. 

This implies that each action {% katexmm %}$a${% endkatexmm %} the agent performs, has some value to them {% katexmm %}$u(a=\text{action})${% endkatexmm %}. 

For the agent to behave optimally, the sum of the weights {% katexmm %}$p_i${% endkatexmm %} they multiply the utility of each action by should be 1. 

#### References
[1] Original [post](https://www.alignmentforum.org/posts/GnMWifHzAknqJsLnv/request-for-distillation-coherence-of-distributed-decisions) by johnswentworth.

[2] Most of the ideas presented are from [here](https://arbital.com/p/expected_utility_formalism/?l=7hh).



