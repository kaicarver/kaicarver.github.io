# Basic explanation

This morning over coffee I tried to explain to a computer programmer friend how the dog and cat recognizer works.

It was surprising to me that someone who knows a lot about programming knows nothing about how AI works.

And it was a bit difficult for me to explain, and I worry that I said it wrong, so here's my attempt to a quick explanation for people who know nothing of how the cat and dog recognizer works.

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
