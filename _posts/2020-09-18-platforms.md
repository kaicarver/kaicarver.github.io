# How to run AI programs

One of the first stumbling blocks when you want to learn about AI is finding a way to run programs.

A complete program like the cat and dog recognizer is amazingly simple and approachable, but the difficulty is not just understanding it, but being able to run it yourself!

To run a program you need an environment or platform for it to run on. An AI program depends upon a software and hardware environment, which can be a pain to obtain and install.

Fortunately, there are some easy ways to get your feet wet. Here's what I found.

These are the options I have explored for running fast.ai software:

* Gradient Paperspace
* Google Colab
* running on my own PC (just to try)

There are several things to consider when choosing a platform:

* availability
  * how easy is it to just run it?
* ease of use
  * how complicated to use it, share things
* features
  * upload widget
* speed
  * how long to do basic AI test like the cat and dog example?
* cost
  * free instances are great, but not always available

## Paperspace

Spoiler alert: I am currently using Paperspace. It works, free instances are available sometimes, and anyway we get a 15-dollar credit as fast.ai students.

I "upgraded" by paying 8 dollars a month, because I was a bit confused and thought it might make things easier for me. But as far as I can tell this does nothing for me, since I currently don't need private instances. I'd be happy to hear from others on this.

speed:

K80 pretty fast, and pre-emptible version is cheaper

Free-P5000 very fast!

No GPU: doesn't work!

## Colab

instructions here:
[https://course.fast.ai/start_colab.html](https://course.fast.ai/start_colab.html)

the instructions say:

> in some places we use a file upload button, which is also not supported by Colab

I found the upload widget works fine on Colab

I initially wrote:

> very slow, I suppose there are faster options if you pay?

but if I had read the instructions properly

> Select ‘GPU’ from the menu and click ‘Save’.

## My own PC

I currently don't have a GPU on my own PC, so key libraries cannot work.

Much more could be said, but in conclusion, Paperspace is the way to go for me for now!

Update: now that I figured out the GPU part, when I have too much trouble with getting a free Paperspace, I use Colab. 
