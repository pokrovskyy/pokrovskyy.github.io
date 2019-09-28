---
layout: post
title: Basics of Simplifying High-Dimensional Datasets
---

Every year we generate more and more data, and this rate is just increasing for the past years. In fact, according to this [Visual Capitalist article](https://www.visualcapitalist.com/how-much-data-is-generated-each-day) it is expected that the entire digital universe is to reach 44 zettabytes by 2020. Big (and small) companies use tracked data for various purposes – from suggesting your next read or film to autonomous vehicles and much more. 

At first glance, having more data may seem great for decision making – the more data you have, the more precise decisions you make. That is only correct if you have a valid model to run your data through. However, in fact, the more variables (features or **dimensions**) are present in your data – the harder it is to understand and construct such a model.

### Curse of Dimensionality

Imagine it’s a hot Sunday and you come to an ice-cream shop to buy your favorite salted-caramel ice-cream cone. But they got an upgrade - and instead of just a few flavors as usual, you are now presented with dozens of new flavors, a ton on new delicious options for the cones, mixes, additions, marmalades, and of course countless all-different combo suggestions. Oh, and did I mention a brand-new rewards program with multi-level membership? Now you’re puzzled – what seemed to be a great improvement has become a great curse. Think of it as a **curse of dimensionality** – problems that did not arise on lower-dimensional spaces occur on higher-dimensional ones.

![Ice-cream cone in front of the wall menu at famous “La Heladería Coromoto” ice-cream shop in Mérida, Venezuela, holding the Guinness Record for having nearly 870 kinds of ice cream flavours](/images/la-heladeria.jpg)
<br>
[Source: Ice-cream cone in front of the wall menu at famous “La Heladería Coromoto” ice-cream shop in Mérida, Venezuela, holding the Guinness Record for having nearly 870 kinds of ice cream flavours](https://www.paginasiete.bo/miradas/2017/9/14/cierra-venezuela-heladeria-guinness-falta-azucar-151991.html)

In real world, there are cases when we have to work with thousands or even dozens of thousands of variables in a single dataset. This obviously creates a number of problems:
- Effective data storage and retrieval
- Computational complexity
- Visualization

### Dimensionality Reduction to the Rescue

In order to simplify this, in machine learning we use a set of techniques collectively named **dimensionality reduction**. Generally, the idea is to eliminate redundant, highly correlated or mutually incompatible variables (dimensions) Consider the following two variables from our ice-cream example – “salted-caramel and mint combo” and “scoop of mint”. It is quite obvious that these variables are correlated, and we may want to select just one or squeeze them. 

Dimensionality reduction employs two main approaches:
- **Feature selection** – emphasizes on identifying and selecting most relevant and important variables while omitting redundant ones
- **Feature extraction** (or projection) – is a bit more complex mathematical approach that achieves similar effect by transforming higher-dimensional dataset into a lower-dimensional by identifying least correlated variables

### Principal Component Analysis

One of the most popular methods to reduce dimensionality is the **Principal Component Analysis**. Typical application of this algorithm involves:
1.	Prepare (organize) the dataset accordingly
2.	Calculate empirical mean (based on actual data)
3.	Calculate deviations from the mean calculated above
4.	Compute an empirical covariance matrix from the above deviations
5.	Compute an eigenvectors matrix from the above covariance matrix (diagonalize)
6.	Select a subset of eigenvectors as basis vectors (see image below)
7.	Project the data onto the new basis

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/f5/GaussianScatterPCA.svg/1920px-GaussianScatterPCA.svg.png" width="500"><br>
[Source: Principal component analysis at Wikipedia](https://en.wikipedia.org/wiki/Principal_component_analysis)

Such approach is almost purely mathematical and lets us employ it in our research relatively easily. The downside, though, is potential data loss in favor of generalization of the dataset, unless we want to take over the steering wheel and make adjustments (which is not always possible, especially when dealing with multi-thousand-dimensional datasets)

I will cover this algorithm step-by-step in detail in my next blog posts, so stay tuned!

### Conclusion

As the data inflow grows, it’s crucial to be able to pick the most important variables for our analysis, and dimensionality reduction is here to the rescue. Hope this article helped you understand basics of such an important concept in machine learning and decision making.
