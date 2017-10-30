---
title: "Drosophila"
excerpt: "Genetic algorithms applied to LED badges <br/><img src='/images/droso.gif'>"
collection: portfolio
date: 2017-06-23
enddate: 'none'
---

<img src='images/drosophila.jpg'>

Introduction
============
Named after the countless genetic studies done on the species, the Drosophila project uses genetic algorithms to produce unique light patterns on a "badge" display that can be "recombined" with other nearby badges.

The Genetic Material
====================
The genome in this project operates on traits which are discrete from one another, but which operate under unique rules. The traits modeled in this genome are light color, flash pattern, genetic greediness, and When badges swap material over NFC, they algorithmically recombine, and each badge becomes an offspring of the two parent badges. Interestingly, when offspring badges repeatedly recombine with only each other, the traits of the badges quickly converge to form not-very-interesting and highly-likely patterns, and their genetic variation approaches 0. We've never been able to totally remove all genetic variation, but we have observed totally stagnant phenotypic variation.

Flash Pattern
=============
There are five unique flash patterns modeled in this version of the badge, which operate under straightfoward dominance/recessive trait characteristics. The patterns are:
all on
clockwise rotation
counterclockwise rotation
every other LED flashes
every LED flashes

Color
=====
Colors per genome are described using one RGB value and a function vs. time per LED of variance from one RGB value. When badges recombine, their starting RGB values average and one function is randomly selected for all offspring. Note that this means that if badge A has color pattern f(x), it could recombine with badge B and both A and B would end with color pattern f(x) -- overwriting B's function -- and recombine with f(c) and end with both A and C with color pattern g(x). No function is automatically dominant over any other.

Greediness
==========
"Greediness" is defined in this project as a genotypes affinity to "protect itself," or its' likelihood to pass its' own traits onto offspring. Genotypes with high greediness are more likely to produce offspring with at least one trait exactly like the parent. The implementation of this is straightforward, as parameter G in each algorithm is evaluated prior to genetic exchange for each trait, and if exceeds a threshold within a percentage for each trait, the recombination does not occur and only that parents genotype is in the pool of offspring. In recombination, greediness averages with its co-parent for each offspring. For example, if badge A has G=0.1 and badge B has G=0.6, prior to each trait recombination will come this evaluation: r = randint(1, 100) // get a threshold to exceed
m = randint(1, 100) // get a multiplier
aExceeds = m(A.G) > r
bExceeds = m(B.G) > r
if both numbers exceed the threshold, they recombine as normal.