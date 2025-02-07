# Deep Dive into LLMs like ChatGPT
https://www.youtube.com/watch?v=7xTGNNLPyMI

### RLHF - Reinforcement Learning from Human Feedback
If we wanted to train an llm on jokes, this would be tough, because there isn't an alogrithm that can determine funny or 
not funny. The amount of training data we'd need to train the model to be really good at this would be pretty large.
  
We could have humans label the data, but almost impossible to have them score all of it. So what we can do is, have
the humans score a small sampling of the data, then train a separate neural network ("reward model") to imitate these
preferences instead. Then we can do RL while using this preference simulator instead.
  
The output of this model will be a number (0 - 1) which represents the score.
  
Upside: can run this in arbitrary domains and improve responses.

Karpathy mentions that he thinks that why this works is, it's significantly easier to ask humans to discriminate than
to generate. For instance, if we were training on poetry, it's far easier to ask humans to order 5 poems in order of 
preference than it is to ask them to write 5 poems.

Downside:
RL discovers there are ways to "game" the model. For example, after 1,000 updates, the top joke about pelicans is not the 
banger you want, but something totally nonsensical like "the the the the the". You could plug that test into the model
and get a perfect score. These are called "adversarial examples." You might naturally think to now add that to the
dataset with a very low score, but research has shown that this is often a losing battle and you will never catch them
all. 

So you want to run RL to its peak performance, and then stop before you start seeing these examples. So it's not magic, 
and infinitely scalable. The distinction here is with jokes. With a game like Go, or with a math problem with a known
result, you can scale much further, but for domains where human preference are involved (subjectivity), this is much
more difficult.

* https://arxiv.org/pdf/2203.02155
* https://deepmind.google/discover/blog/alphago-zero-starting-from-scratch/
  
### Final Thoughts and Resources
In the next year, agents. Also long, coherent, error-correcting context windows. He mentions he thinks innovations are 
needed in this area because simply extending the context window will not be enough.
  
Mentions 3 resources where he keeps up to date:
* LMArena - leaderboard where humans rate models which are A/B tested: [https://lmarena.ai/](https://lmarena.ai/) . He
mentions that he feels like in last couple months, may have been gamed (bc of Sonnet ranking etc).
* [https://buttondown.com/ainews/archive/](https://buttondown.com/ainews/archive/) - newsletter but archive can view from page
* x.com (twitter)
  
Where to run models
* TogetherAI [https://www.together.ai/](https://www.together.ai/)
* (base models) [https://hyperbolic.xyz/](https://hyperbolic.xyz/)
* (local models) [https://lmstudio.ai/](https://lmstudio.ai/)