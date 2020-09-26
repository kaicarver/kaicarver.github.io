# L

Sanyam suggested we could write a blog post about **L**.

So here goes, this what I have learned.

The [documentation about **L**](https://fastcore.fast.ai/#L) references Larry Wall's dictum that "commonly used things should be shorter". That's why **L** is the very short class name of fastai's list object.

I'm not a Python expert, so I'll gladly admit I'm confused by the large number of list-like objects that we deal with in Python and its fast.ai dialect. 

As far as I can tell, there are lists, tuples, arrays, numpy arrays, tensors (PyTorch), and these fast.ai lists of class **L**.

[discuss the different kinds in more detail]

**L** is defined in the "fastcore" part of the fast.ai libraries. as can be checked by just typing "L" into the standard REPL or IPython in a terminal, or in a Jupyter notebook cell.

Here's what you get in IPython, which is the terminal version of what you interact with when using Python in a Jupyter notebook:

```python
$ ipython
...
In [1]: from fastcore.foundation import L

In [2]: L
Out[2]: fastcore.foundation.L
```

we get a bit of documentation with the `?` operator, like this:

```python
In [2]: L?
Init signature: L(items=None, *rest, use_list=False, match=None)
Docstring:      Behaves like a list of `items` but can also index with list of indices or masks
File:           ~/anaconda3/lib/python3.7/site-packages/fastcore/foundation.py
```

(to be continued)
