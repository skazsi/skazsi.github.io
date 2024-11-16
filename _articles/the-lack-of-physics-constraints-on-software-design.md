---
title: "The Lack of Physics Constraints on Software Design"
header:
  teaser: /assets/images/physics.png
number: 5
---
Software engineering is undoubtedly a branch of engineering. It utilizes scientific and mathematical principles to address problems. It requires a creative application of knowledge and technology to create solutions that improve the functionality and efficiency of various processes, products, and infrastructures. However, there is a crucial difference between software engineering and traditional engineering disciplines. While the laws of physics constrain traditional engineering designs, software designs do not face these limitations. This freedom can be appealing for software engineers, but it also presents its own set of challenges. Before exploring those challenges, let's examine how traditional engineering is influenced by the laws of physics.

An average passenger can hardly spot significant differences between planes while waiting for their next flight. They generally share similar silhouettes, wing profiles, landing gear, and engine placement. The internal layout and structure are likely identical, although these details may not be visible to the average observer. While regulations certainly influence their design, planes primarily adhere to the laws of physics related to motion, gravity, aerodynamics, and thermodynamics. Even seemingly minor differences in design could compromise the plane's flight efficiency, pose safety risks, or even prevent the aircraft from taking off altogether.

Boeing 737 MAX is a tragic example of such consequences. The world was shocked when two of the brand-new 737 MAX planes crashed in late 2018 and early 2019 in less than five months. Investigations revealed that the famous Maneuvering Characteristics Augmentation System (MCAS) was the direct cause of the tragedies, as it overrode the pilots' control to prevent assumed stalls at elevated angles of attack.

What is less known is that the MCAS was a patch intended to fix a design flaw in the 737 MAX. In pursuit of fuel efficiency and cost savings, Boeing installed much larger engines on the 737 airframe and named it MAX. However, they faced a significant issue: the new engines were so large that they did not provide enough ground clearance on the 737 airframe. Repositioning the engines higher on the wings was the only possible solution. However, this seemingly insignificant modification altered the plane's flight characteristics and increased the likelihood of stalling at full thrust, leading to the installation of the MCAS system. It sounds like Boeing took shortcuts one after the other, and they indeed did.

The tragic story of the Boeing 737 MAX clearly illustrates the constraints physics imposes on traditional engineering design. These constraints are unbreakable, so planes are similar; there is no other way.

On the other hand, if the 737 MAX were a software product, Boeing could have quickly fixed the ground clearance problem by increasing the height of the landing gears since the landing gear is a loosely coupled component to the airframe in well-written software. Moreover, A software-based landing gear has nothing to do with Newton's Laws of Motion. So why would the plane have any landing gear after all? Finally, Boeing could have addressed the issue entirely differently by taking inspiration from podracers from the movie Star Wars: The Phantom Menace. Arranging the two engines in front of the airframe, connected by energy binders that appear as beams of light or energy streams. While it sounds sarcastic, some software engineers would certainly consider such an idea.

But why?! Why a software engineer would ever consider a seemingly illogical design? The answer lies in the software's softness. Rober C. Martin, a.k.a Uncle Bob, wrote the following in his Clean Craftsmanship book.

"_The first word in software is soft. Software is supposed to be SOFT. It's supposed to be easy to change. If we didn't want it to be easy to change, we'd have called it hardware.<br/>
It's important to remember why software exists at all. We invented it as a means to make the behavior of machines easy to change. To the extend that our software is hard to change, we have thwarted the very reason that software exists._"
{: .notice}

While Uncle Bob wrote the above in the context of easily changeable software, he inadvertently also explains why it is so difficult to create good software designs. Software is purposefully detached from our physical world and its laws by placing it in an abstract or utopian dimension. We invented it like this. Otherwise, it would make the behavior of machines hard to change. It is like in the movie Inception, where the architect creates imaginary places without being bound by the laws of physics, or like slime, the children's toy that can be stretched and shaped in any direction.
