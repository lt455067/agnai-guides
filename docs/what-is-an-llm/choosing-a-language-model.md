---
title: "Choosing an LLM"
layout: default
parent: "What is an LLM"
---

# Choosing an LLM

Language models are constantly evolving, and as such there are many to choose from.  

For example, some popular choices at the time of writing:

* Mistral 7b: A smaller, faster language model.  Cheaper to host (and thus cheaper to use).  Many fine-tuned models exist.
* Mixtral 8x7b: a "Mixture of Experts" using 8x Mistral 7b.  New, and therefore not supported everywhere.
* Mythomax 13b: Older model but has more parameters than Mistral so might be better at some tasks.
* Tiefighter 13b: A 13b model trained by the team behind Kobold AI for roleplaying, adventure games, and similar usage.
* Lzlv 70b: A more intelligent language model, but more expensive to run.
* Goliath 120b: A "frankenmerge" of two 70b models.  An experiment in making bigger models from smaller models.  Very costly to run.
* Yi 34b: A new base model with better support for international languages.  Unfortunately, it has a restrictive license.
* GPT-3.5 Turbo: The cheaper version of the OpenAI GPT model.  Trained for question answering, tries to avoid giving NSFW answers.
* GPT-4 Turbo: The more expensive version of the OpenAI GPT model.  Trained for question answering, tries to avoid giving NSFW answers.

There are also countless finetunes of those models that you can choose from.

Choosing which LLM to use comes down to availability, cost, and performance.  Assuming the model you want to use is available, and assuming you're willing to pay the cost to use it (if there is a cost), then it comes down to a question of how well that model performs for your specific use-case and preferences.  The only way to answer the last question is to try the model and see, or to read the model card and see what it was fine-tuned to do.

## Recommendation

If you're looking for NSFW content on the cheap, it's tough to beat the free Agnaistic models.  The 7b will do quite swimmingly with some light adjustments to your UJB and/or your advanced settings.  The response times are quite fast and the queue is likely shorter than the 13b.

If you want a bit more creativitiy and you're willing to wait slightly longer for responses, the 13b models are quite good.

If you want more than the stock 4k context or want really fast response times, pay the $5 and get the 8k context models and priority in the response queues.

For the $20 tier, you get access to a 70b model which is great for the most creativity and best instruction following (for really specific characters).  It only comes with 6k context and the response times are a tad slower but otherwise they're quite good.

## Third Party Recommendations

You can often find excellent models on Horde, like Psyfighter 2, Tiefighter, and ocasionally even 70b and 120b models.  Horde models are free.

If you're using Agnaistic for schoolwork, setting up OpenAI can allow you to leverage memory books and other settings for specific applications.

## Troubleshooting
Sometimes a model doesn't behave quite the way youwant.  Check out [tips-tricks-and-troubleshooting](/docs/tips-tricks-and-troubleshooting) for various issues and how they might be addressed.
