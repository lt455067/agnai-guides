---
title: "Beating Repetition"
layout: default
parent: "Tips, Tricks, and Troubleshooting"
nav_order: 9
---

# Beating Repetition

> TLDR: put your advanced settings to the following:
>   * repetition penalty at 1.1
>   * range at 2048
>   * slope at 0.05
>   * frequency at .05
>   * presence at .1
>   * top K at 50
>   * temperature of 1.2 
>   * min p of 0.1
> 
> Read on for an explanation of these settings and why they may or may not work for you as expected

There are several strategies for beating repetition:

1. Increase creativity
1. Increase repetition penalty
1. Vary the context significant
1. Vary the template format
1. Switch to a different model

For increasing creativity or repetition penalties, you'll need to head to the advanced settings section of your preset.  Note the following advanced settings:

* **Increase temperature**: A temperature above 1 (i.e. 1.1 or 1.2) will give more weight to less probable tokens.  A temperature below 1 (i.e. 0.8) will favor more probable tokens.
  * Pros: An easy and effective way to increase creativity in combination with other strategies
  * Cons: Higher probability of less likely tokens can result in gibberish or 'going off script'.  If sentence structure starts to fall apart or strange gibberish is produced, you know the temperature is too high.
* **Decrease min-p**: min-p is a cut-off threshold for token probability.
  * Pros: min-p is a good balance for high temperature.  Cutting off the least-probable tokens before weighting the remaining tokens higher will result in less chance of gibberish.
  * Cons: If min-p is too high, you'll lose more tokens.  Also, min-p tends to "cancel out" temperature increases
* **Top-k**: The number of tokens to consider when randomly choosing the next token for generation
  * Pros: A solution for increasing creativity by allowing a greater range of token consideration.  You'll get more useful tokens with Top K set to 50 than you will with a higher temperature alone.
  * Cons: Top K that is too high will enable consideration of nonsense tokens
* **Mirostat Tau / Eta**: A dynamic method for balancing top p, top k, etc in order to get more creativity with longer responses.  Setting a Tau of 5 with an Eta of .1 means you're aiming for a complexity score of "5" by "learning" at a rate of ".1"
  * Pros: With all other samplers set to their disabled setting, Mirostat Tau/Eta can be a good way to get better results with minimal other adjustments
  * Cons: Mirostat is somewhat opaque and hard to dial in.  Some models like a higher Tau, some repetition needs a higher Eta, but too high Eta will result in nonsense.
* **Repetition Penalty**: P'(token) = P(token) * exp(-α * n(token))
  * Pros: A stronger repetition penalty.  As repetition increases, the multiple approaches zero quickly resulting in a heavy decrease in probability
  * Cons: Might hit too hard, good to be gentle with this setting
* **Presence Penalty**: P'(token) = P(token) * (1 - β)
  * Pros: A fixed penalty.  All tokens previously seen get the same penalty applied.  Good for discouraging repetition without harming common tokens like "*" and "the".
  * Cons: Possibly insufficent by itself to make a real impact
* **Frequency Penalty**: P(token) * (1 - β * n(token))
  * Pros: a linear penalty which hits tokens that repeat more often a bit harder, but not as hard as the exponential penalty
  * Cons: still possible to go too high and discourage common tokens like emotes and common articles like "a" and "the".
* **Repetition Range**: The number of tokens to consider for repetition in the context, starting at the bottom (i.e. most recent).
  * Pros: Higher range will help maintain creativity over longer contexts
  * Cons: Too high a range will result in repetition penalties accumulating faster for common words
* **Repetition Slope**: P'(token) = P(token) * (1 - β * slope * n(token))
  * Pros: lower slopes result in more gradual penalty accumulation
  * Cons: if your slope is too low, recent repetitions will still accumulate


## Varying the context

Switching the template format or modifying the UJB with {{random choice A, choice B, choice C}} options are both ways of causing the prompt to vary.  Repetition happens when the model sees enough consistency in the prompt to predict the same or similar outputs.  Changing your instructions to the LLM significantly, either by switching your prompt format (for example from Vicuna to Alpaca or vice versa) or otherwise modifying your context significantly can help beat repetition.

An example of a UJB that might help with repetition is as follows:

```
{% raw %}
Describe {{random feelings, sounds, sights, thoughts, smells}} {{random in vivid detail, using colorful language, focusing on the environment, briefly, and then talk about something else, and then say something random}}.
{% endraw %}
```

The above will generate UJBs that vary each message, so one message you might get "Describe feelings in vivid detail" while another you might get "Describe smells focusing on the environment".  Changing the dominant instructions in your prompt (i.e. the UJB) can have a direct effect on the model's output -- for better or worse.  Feel free to pick your own options for the random tag.

## Change the model

A potentially silly but equally useful option is to pick a different model.  Given the same context, a 7b might generate different results than a 70b, so while it may have less parameters it can still be interesting to switch to the 7b or the 13b for a few generations and then switch back to the 70b (or vice versa).
