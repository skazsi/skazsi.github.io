---
title: "Don't Repeat Yourself, Don't Repeat Yourself"
header:
  teaser: /assets/images/dont-repeat-yourself.png
number: 6
---
The most famous principle in software engineering is the DRY, Don't Repeat Yourself. Juniors learn it at first together with the KISS. They master it so profoundly in their early years that they apply it instantaneously and unconsciously in their later career. But it's not mistakenly like that. It is a no-brainer, a child's play. You need to use your existing code whenever you develop something similar to what you already have. Easy-peasy.

But, like with so many things in life, balance is essential. As Robert Downey Jr. as Kirk Lazarus famously said in the Tropic Thunder movie: "Never go full retard". I want you to focus on the first "Never go full..." part and ignore the last word, which is not my point here. Taking it more seriously, I will show some non-obvious consequences of the overused DRY principle in this article.

![](/assets/images/dont-repeat-yourself.png)

I will use an example from the real world since people can often think with physical objects more easily than theoretical ones. We have an automobile factory where we focus on two aspects only. At first, let's see how the vehicles get painted. The car manufacturing factories usually have a centralized paint shop. It's an absolute singleton reused instance within the entire facility. There are numerous reasons for that. First of all, the vehicles' colour is business significant. The buyers can choose colours for their dream cars from a wide range. Second, painting is a multistep complex process. It requires an isolated area and extreme cleanliness. It is highly toxic and flammable. Costs, logistical and other aspects are also there. To sum it up, these reasons, even separately, could already justify why a painting shop is a singleton, shared and reused service within the facility.

The second aspect of our car manufacturing facility is screw driving. We can agree on its necessity and importance in car manufacturing. There are thousands of bolts in a vehicle, and every assembling employee should be able to tighten each perfectly, not force or leave it loose. Does it sound like a BoltTighteningService in our codebase? While you might have such a service in a codebase, there is no such in the automaker industry. Let's compare it to the painting to figure out why. Business point of view, it is not relevant. We all know they are there just like the blue sky. It is a simple process. It does not require isolation or extensive space. Finally, a cheap compressed air impact screwdriver can easily ensure speed and precision. Of course, the facility has such screwdrivers at every assembling stage for all those reasons. While no car would exist without bolts and screwdrivers, it is not a topic. We don't expose it to the outside world. It is like the air we breathe in every moment. Yet, we don't talk about it.
