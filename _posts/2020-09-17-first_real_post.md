# First real post?

This is supposed to be my first real post.

Working on it...

My idea is to 

- introduce myself very briefly
- talk briefly about setting up
- give a real example, which may just be discussion of cats and dogs and alligators

It's just to get my feet wet, and I need to do more studying, not spend too long on blogging.

So I'll start by showing my first notebook.

This is the example from chapter 1: a dog and cat recognizer in 15 lines of code!

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

