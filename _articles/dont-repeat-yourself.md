---
title: "Don't Repeat Yourself, Don't Repeat Yourself"
header:
  teaser: /assets/images/dont-repeat-yourself.png
number: 6
---
The most known principle in software engineering is the DRY, Don't Repeat Yourself. Juniors learn it at first. They master it so profoundly in their early years that they apply it instantaneously and unconsciously in their later career. But it's not mistakenly like that. It is a no-brainer, a child's play. It sticks easily into the heads because of its simplicity. As it says, reuse your code instead of writing it again. Easy-peasy.

But, like with so many things in life, balance is essential. As Robert Downey Jr. as Kirk Lazarus famously said in the Tropic Thunder movie: "Never go full retard". I want you to focus on the first "Never go full..." part and ignore the last word, which is not my point here. Taking it more seriously, I will show some non-obvious consequences of the overused DRY principle in this article.

![](/assets/images/dont-repeat-yourself.png)

I will use an example from the real world since people can often think with physical objects more easily than theoretical ones. Let's have an automobile factory where we focus on two aspects only.

At first, let's see how the vehicles get painted. The car manufacturing factories usually have a centralized paint shop. It's an absolute singleton reused instance within the entire facility. There are numerous reasons for that. First of all, the vehicles' colour is business significant. The buyers can choose colours for their dream cars from a wide range. Second, painting is a multistep complex process. It requires an isolated area and extreme cleanliness. It is also highly toxic and flammable. Costs, logistical and other aspects are also there. To sum it up, these reasons, even separately, could already justify why a painting shop is a singleton, shared and reused service within the facility.

The second aspect of our car manufacturing facility is screw driving. We can agree on its necessity and importance in car manufacturing. There are thousands of bolts in a vehicle, and every assembling employee should be able to tighten each perfectly, not force or leave it loose. Does it sound like a BoltTighteningService in our codebase? While you might have such a service in a codebase, there is no such in the automaker industry. Let's compare it to the painting to figure out why. Business point of view, it is not relevant. We all know they are there just like the blue sky. It is a simple process. It does not require isolation or extensive space. Finally, a cheap compressed air impact screwdriver can easily ensure speed and precision. Of course, the facility has such screwdrivers at every assembling stage for all those reasons. While no car would exist without bolts and screwdrivers, it is not a topic. We don't expose it to the outside world. It is like the air we breathe in every moment. Yet, we don't talk about it.

These examples provided a good insight into what to consider before extracting and reusing any artefact, whether a car manufacturing process or a piece of code. But now, let's look at the consequences if we push the DRY principal too much.

We are switching our car manufacturing example to a trading application we recently started working on. The application provides only the user interface for the trading backend system. Hence, we need to send all transactions through the network. We want to avoid any integrity issues during the transmission, so we add a SHA256 hash value as a checksum to each trading request. So far, so good.

Later in the development, we are switching focus to user authentication. As experienced software engineers, we store only the hashed password in our database, following best practices. Because our product already uses SHA256 for the trading checksums, we decided to reuse the algorithm and, as a DRY zealot developer, our previous implementation as well. To deal with the encapsulation in the trading code, we extract the hashing logic into a new package, module or artefact, and we give it a good name like ChecksumManager. We are ending up with the following structure.

Unquestionably, we reached our goal. No code got duplicated. But what have we sacrificed to achieve it? The most important side effect is that we have connected two utterly irrelevant business functionalities of our code base with a shared dependency. It's not a substantial dependency, but it's undoubtedly there and slowly starts to impact us in the future. Whenever we would like to change the checksum algorithm for the tradings, we would affect user authentications, and vice versa. No product owner or business representative would be happy with our work. Returning to the cars for a moment, a tire change on your vehicle should be possible without checking the oil level.

If we walk this path further, more and more such extracted dependencies will arise in our code base, connecting completely irrelevant business functions. After a while, even the extracted codes will start depending on other extracted codes, ultimately heading to the famous spaghetti code.

