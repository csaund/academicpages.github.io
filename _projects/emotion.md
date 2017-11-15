---
title: "Emotional System"
excerpt: "Bi-Axial Emotional System<br/><img src='/images/emotion.png'>"
collection: portfolio
date: 2017-03-15
enddate: 'none'
---

Bi-Axial Emotional System
=========================

Introduction
============
This emotion system is meant to be an abstract representation of an agent's 
internal emotional state that is influenced with a combination of external
 input sensors and sentiment appraisal rules. Emotional Cognition is a 
  subfield of cognitive science, with many potential emotional models.

This Space
==========
This Emotion Space uses a 2D representation of an emotional plane, with the 
axis Valence and Confidence. The ranges of these two factors map out the 
Emotional Space, which creates a mapping of Valence and Confidence values 
to labeled emotions, shown below. I settled on a 2D emotional graph (omitting
 the academically popular energy or arousal axis) for simplicity. Ultimately,
  these 8 labeled emotions capture quite a large range of expressivity, and 
  the system is designed such that adding another axis later on, if we decide
   it is necessary, would be quite simple. An example of a differentiation 
   that might happen would be Joyful (1, 1, 0) (neutral energy) could become
    either Ecstatic (1, 1, 1) (high energy) or Satisfied (1, 1, -1)
     (low energy). As a proof of concept for the emotion system, it was 
     decided these nuances represent far more work than I was comfortable 
     investing without user feedback.

Axis
====
Valence, as used in psychology, especially in discussing emotions, means the
 intrinsic attractiveness/"good"-ness (positive valence) or 
 averseness/"bad"-ness (negative valence) of an event, object, or situation.
  The term is also used to characterize and categorize specific emotions. 
  Confidence refers to an emotional sentiments' reflection of personal self-
  confidence.

Decay
=====
Emotions decay. This emotional baseline is 0.45 valence, 0.2 confidence. The 
decay rate of this emotional state varies based on the difference between 
emotional state and baseline emotions. Without any interaction, the state 
will always return to this state within an hour, despite any original impact.