---
layout: post
title: Practical Object Oriented Design in Ruby: An Agile Primer; Post 1
---

I recently decided to focus more attention to Object-Oriented Design in Ruby. In the past ~2 years that I have decided 
to truly learn how to write code, and more specifically, to focus on Ruby development, I have come to the conclusion that 
applications that are heavy on object orientation are very challenging. I wrote an object oriented blackjack game and I 
struggled a lot. I also wrote an object oriented script that converts a csv bank statement to HTML and seperates transactions 
based on several factors. That script was difficult to complete as well. 

In order to get a better grasp of OOP in Ruby, I have decided to start with first reading a textbook on design theory. I decided to 
read Practical Object Oriented Design in Ruby: An Agile Primer, by Sandi Metz. This book came highly recommended by several 
prominent Ruby developers whom are very active in the community. 

In chapter 1, Sandi mentions some design principles. Specifically, she mentions "SOLID", which represents five of the most 
well-known principles of object-oriented design. [S]ingle Responsibility, [O]pen-Closed, [L]iskov Substitution, [I]nterface 
Segregation, and [D]ependency Inversion. Other principles Sandi mentions are DRY(Don't Repeat Yourself), and the Law of 
Demeter(LoD). To prove the efficiency of these design principles, two researchers took OOP applications and tried to quanitify 
the code. They named and measured things like the overall size of classes, the entanglements that classes have with one another, 
the depth and breadth of inheritance hierarchies, and the number of methods that get invoked as a result of any message sent. Their 
research shows a definite correlation between use of the SOLID, DRY, and LoD techniques and high-quality code. The caveat with their study was 
that their quantitative methods were applied to relatively small applications written by other graduate students. These graduate 
student applications may not be representative of real-world applications. Luckily, their study was further validated by NASA engineers 
who were examining their applications with the express intention of finding a way to produce cheaper and higher quality software. They examined 
three applications, one of which had over 1,600 classes and a total of more than 500,000 lines of code. The NASA study supported 
the earlier study.

So, if you are not familiar with the SOLID, DRY, and LoD principles, they may be worth looking into. As for me, I totally love how Sandi's 
design principles are backed by quantitative data, and not based on opinion. More and more, the decisions being made in the world are being 
driven by data, so I am hooked on her book thus far, and I look forward to continuing to read it. Check back for more posts related to her 
textbook. Thanks for reading!
