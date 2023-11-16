# Touchdesigner Text Feedback

**On how to modify with a video with feedback effects.**

Template file to download : feedback_video_text.toe

## To begin with

- My [Introduction to Touchdesigner](https://github.com/LucieMrc/IntroTD)

- Intro + tutorial about [Feedback loop in TD (EN)](https://github.com/LucieMrc/TD_feedback_love_EN)

## The template

The template is showing you two examples of feedback look, + pre feedback and post feedback nodes.

![screen de TD](./images/screen1.png)

From left to right : 

- the `Movie File In` TOP in which you can add your video

- the Pre Feedback container, with a `Level` TOP allowing you to adjust your video contrast, brightness, black level, color range, and more; and a `Displace` TOP (+ its noise) which deforms the video.

- The 2 Feedback containers, with 2 differents loops.

- The Post Feedback container, with a `Transform` TOP adding a black background behind transparent pixels, and a `Lookup` TOP which recolorize the video with a given color ramp.

## The feedback loops

To understand better feedback loops, its structure and basic components, you should read the intro + tutorial about [Feedback loop in TD (EN)](https://github.com/LucieMrc/TD_feedback_love_EN).

One of the most important thing in your feedback loop will be the mode of your `Composite` TOP at the end of the loop. It will define how you blend each frame that has passed through all the modifier nodes, with the precedent frame.

Each TOP node in your feedback loop between the `Feedback` TOP and the `Composite` TOP should have their parameters very low, as the frames will goes through the nodes very fast, compared to a node before or after the feedback loop.

![screen de TD](./images/screen2.png)

The first network is the video going through a `Level` TOP to add contrast, then through a `Displace` TOP to sligthly deform it.

The second network is the same video and the same nodes, but in a feedback loop. We can see the video became too distorted to read the text, and the image eventually become full black if we let it run for a few seconds, because each frame add atop of the precedents.

# To go further

# TD_textFeedback
