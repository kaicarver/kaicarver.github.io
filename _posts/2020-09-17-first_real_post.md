# First experiment: cats and dogs

This is supposed to be my first real post about fast.ai after playing around with this nice blogging software.

My original idea was to:

- introduce myself briefly
- talk briefly about setting up to run AI experiments
- give a real example matching a lesson in the book

But I'm just going to get my feet wet, and I need to do more studying, not spend too long on blogging.

So I'll skip the introductions and start by just showing my first bit of code.

This is the example from chapter 1: an AI dog and cat recognizer in only 15 lines of code!

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

I'd like to write more and give details about my cats and dogs and... alligators experiments but...

I'm afraid I am still having trouble finding a good environment to run in, and now I've run out of time.

I'll write more tomorrow.
