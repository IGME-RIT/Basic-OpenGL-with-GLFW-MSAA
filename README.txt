Documentation Author: Niko Procopi 2019

This tutorial was designed for Visual Studio 2017 / 2019
If the solution does not compile, retarget the solution
to a different version of the Windows SDK. If you do not
have any version of the Windows SDK, it can be installed
from the Visual Studio Installer Tool

Welcome to the Multisample Anti-Aliasing Tutorial!
Prerequesites: Intro Graphics

Please see screenshots: BeforeMSAA.png and AfterMSAA.png

What is Anti-Aliasing?
Anti-Aliasing removes pixelation from images by blurring pixels on the edges of polygons

When do I want to use Anti-Aliasing?
When you want your image quality to improve, without requiring the user to increase 
	the resolution, which saves performance

When should I not use Anti-Aliasing?
For simple tutorials like these (all of Atlas), Anti-Aliasing should always be used.
In huge games like Call of Duty or Halo, Anti-Aliasing can be sacraficed for higher frame-rate.

How do I use MSAA?
With GLFW, you only need two lines of code:
	1. Prior to creating a window with glfwCreateWindow(), we need to set a value for MSAA level
If we want 4x MSAA, we would use the line glfwWindowHint(GLFW_SAMPLES, 4);
However, just cause we felt like it, we bumped it up to glfwWindowHint(GLFW_SAMPLES, 99);
The computer won't actually take 99 into effect, but it will use the highest supported level
of MSAA on the computer that it is running on
	2. Prior to starting the game loop at "while (!glfwWindowShouldClose(window))", we need
to enable MSAA with the line glEnable(GL_MULTISAMPLE);

That's it, MSAA is that easy. You can comment out those two lines to see the difference between
before and after MSAA
