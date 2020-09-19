# First experiment: cats and dogs

This is supposed to be my first real post about fast.ai after playing around with this nice blogging software.

My original idea was to:

- introduce myself briefly
- talk briefly about setting up to run AI experiments
- give a real example matching a lesson in the book

But I'm just going to skip the introductions and start by just showing my first bit of code.

This is the classic example from [chapter 1 of the fast.ai book](https://github.com/fastai/fastbook/blob/master/01_intro.ipynb): 
an AI dog and cat recognizer in only 15 lines of code!

```python
from fastai.vision.all import *
path = untar_data(URLs.PETS)/'images'

def is_cat(x): return x[0].isupper()
dls = ImageDataLoaders.from_name_func(
    path, get_image_files(path), valid_pct=0.2, seed=42,
    label_func=is_cat, item_tfms=Resize(224))

learn = cnn_learner(dls, resnet34, metrics=error_rate)
learn.fine_tune(1)

uploader = widgets.FileUpload()
uploader

img = PILImage.create(uploader.data[0])
img.to_thumb(128)

is_cat,_,probs = learn.predict(my_img)
print(f"Is this a cat?: {is_cat}.")
print(f"Probability it's a cat: {probs[1].item():.6f}")
```

I'd like to write some explanation and give details about my cats and dogs (and... alligators) experiments, but...

I'm still having trouble finding a good environment to run in, and I've run out of time for blogging today.

I'll write more about cats and dogs and environments... in the coming days.

At least here's a link to [my notebook on GitHub](https://github.com/kaicarver/fastaixp/blob/master/01%20Kai's%20first%20fast.ai%20experiment.ipynb) showing some of my tests on this dog and cat recognizer.

There's also [this notebook on Paperspace Gradient](https://console.paperspace.com/kaicarver/notebook/prewwejqi), the environment that I use, but it's an old one, and I don't quite understand how to properly share notebooks on Gradient.
