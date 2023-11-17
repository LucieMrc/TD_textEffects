# Touchdesigner Text Effects

**On how to play around with text with Touchdesigner effects.**

## To begin with

- My [Introduction to Touchdesigner](https://github.com/LucieMrc/IntroTD)

- Intro + tutorial about [Feedback loop in TD (EN)](https://github.com/LucieMrc/TD_feedback_love_EN).

# Text Feedback

![screen de TD](./images/feedback.gif)

Template file to download : feedback_video_text.toe

## The template

The template is showing you two examples of feedback look, + pre feedback and post feedback nodes.

![screen de TD](./images/screen1.png)

From left to right : 

- the `Movie File In` TOP in which you can add your video, or replace by whatever TOP you want.

- the Pre Feedback container, with a `Level` TOP allowing you to adjust your video contrast, brightness, black level, color range, and more; and a `Displace` TOP (+ its noise) which deforms the video.

- The 2 Feedback containers, with 2 differents loops.

- The Post Feedback container, with a `Transform` TOP adding a black background behind transparent pixels, and a `Lookup` TOP which recolorize the video with a given color ramp.

## The feedback loops

To understand better feedback loops, its structure and basic components, you should read the intro + tutorial about [Feedback loop in TD (EN)](https://github.com/LucieMrc/TD_feedback_love_EN).

One of the most important thing in your feedback loop will be the mode of your `Composite` TOP at the end of the loop. It will define how you blend each frame that has passed through all the modifier nodes, with the precedent frame.

Each TOP node in your feedback loop between the `Feedback` TOP and the `Composite` TOP should have their parameters very low, as the effect of the nodes will be added on top on each other, as opposed to a node before or after the feedback loop.

![screen de TD](./images/screen2.png)

The first network is the video going through a `Level` TOP to add contrast, then through a `Displace` TOP to sligthly deform it.

The second network is the same video and the same nodes, but in a feedback loop. We can see the video became too distorted to read the text, and the image eventually become full black if we let it run for a few seconds, because each frame add atop of the precedents. 

# Text letter by letter

![screen de TD](./images/letters.gif)

Template file to download : feedback_video_text.toe

## The template

The template is showing you a very basic animation of a word or group of words appearing letter by letter.

![screen de TD](./images/screen3.png)

All the magic is happening inside a custom base named LetterByLetter, with an `Out` TOP to display and modify the result.

In the parameters of the base, there is a `Parameters` page where we can input the text, change the delay between the letters (in seconds). We can also choose the X and Y position of the text, and the font size.

![screen de TD](./images/screen4.png)

To start the animation, we click on the `Start` pulse button.

The `Start` button is linked to a `Keyboard In` CHOP to also start the animation when we press "q".

## Inside the base

If you look inside the `LetterByLetter` base, there is a `Parameter` DAT, `Select` DAT and `DAT to` CHOP to get informations from the parameters page of the base, a `Timer` CHOP to start and choose the timing of the animation, and a `Text` TOP going into an `Out` TOP to display and output the text.

![screen de TD](./images/screen5.png)

The only things you should really modify here are the `Text` TOP parameters, and mostly the `Font` page and and the `Common` page to change the resolution.

![screen de TD](./images/screen6.png)

# To go further (if you understand Touchdesigner)

- Youtube tuto : [Time displacement and click transitions controlled by the mouse](https://www.youtube.com/watch?v=l4IZdNPrKAI&t=1s&ab_channel=PPPANIK)

- Youtube tuto : [Typography adventures](https://www.youtube.com/watch?v=-XdpLPIXmxA&ab_channel=PPPANIK)

- Youtube tuto : [Sliced Type](https://www.youtube.com/watch?v=DeCaJ5EwyIg&ab_channel=threedashes)