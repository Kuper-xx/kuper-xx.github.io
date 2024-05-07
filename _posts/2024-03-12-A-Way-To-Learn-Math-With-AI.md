---
title: A Way To Learn Math With AI
published: true
---

[Link to index page](/).

### [](#header-1)First step - requirements

The first step is install all the requirements that we need, they are: _LaTeX, Manim, Ffmpeg and Scoop_

1. **Scoop installation**
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression
```
2. **Ffmpeg installation**
```
scoop install ffmpeg
```
3. **Manim installation**
```
pip install manim
```
Manim is the library created by 3Blue1Brown to help us to render a beautiful videos that we will see in the result.
4. **LaTeX installation** \
Here we will need to enter here [Here](https://miktex.org/download) if we have Windows and install MiKTeX that is a distribution of LaTeX for Windows, and you can enter to this [Link](https://miktex.org/howto/install-miktex) to see a tutorial of how to install it.

Now we have all the libraries and dependencies for this task we can go to the second step...

## [](#header-2)Second step - preparation

Here we all have to learn to use this libraries and do handwork or... just... Use AI, for this task I used a new version of Claude 3, to be clear `Claude 3 Opus` and I just asked to the AI that create for me a python code using MANIM Library to create a video of a simple explanation of what is it an integral.

The answer of Claude 3 Opus was this code:

```python
from manim import *

class IntegralTutorial(Scene):
    def construct(self):
        # Create axes
        ax = Axes(
            x_range=[0, 5],
            y_range=[0, 6],
            x_axis_config={"numbers_to_include": [2, 3]},
            tips=False,
        )
        labels = ax.get_axis_labels()

        # Create curve and area under the curve
        curve = ax.plot(lambda x: 4 * x - x ** 2, color=BLUE)
        area = ax.get_area(curve, x_range=[2, 3], color=GREY, opacity=0.5)

        # Create equation and explanation text
        equation = MathTex(r"\int_a^b f(x) dx")
        explanation = Text("The integral represents the area under the curve.")

        # Position the equation and explanation
        equation.move_to(ax.get_center() + DOWN * 2)
        explanation.next_to(equation, DOWN)

        # Animate the scene
        self.play(Write(ax), Write(labels))
        self.play(Create(curve))
        self.wait()
        self.play(FadeIn(area))
        self.wait()
        self.play(Write(equation))
        self.wait()
        self.play(Write(explanation))
        self.wait(2)
```

After this we will need to create a Folder I just named "Integral" and after this I created a python file and copy-paste this code.

### [](#header-3)Third step - execution
This is the final step, and the simplest we need to open a Command Control of windows and write:

```
manim integral_tutorial.py IntegralTutorial -p -ql
```

In this case the python file name is 'integral_tutorial.py' and the name I want to have the mp4 file (the video result with out the music) is 'IntegralTutorial', and the result it's just beautiful.

### Click the image to see the Youtube video of the result with music:
[![What-is-it-an-integral](https://i.ytimg.com/vi/Gabdib6CLLk/hqdefault.jpg?sqp=-oaymwE2CPYBEIoBSFXyq4qpAygIARUAAIhCGAFwAcABBvABAfgB1AaAAuADigIMCAAQARhlIGUoZTAP&rs=AOn4CLBJUPwpT9ZS3JY2N8FqhjPk2bJ7tQ)](https://www.youtube.com/watch?v=Gabdib6CLLk)

