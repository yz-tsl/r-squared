### Operator Overloading

In Java/Scala, we can define static `interface`/`trait`. Why can't they be dynamic? 

Python implements duck-typing, which is handy but it is error-prone. The problem with duck-typing is that it makes code inference very difficult. Consider the following script:

```python
dls = DataBlock(
    blocks=(ImageBlock, CategoryBlock),
    get_items=get_image_files,
    splitter=RandomSplitter(valid_pct=0.2, seed=42),
    get_y=parent_label,
    item_tfms=[Resize(192, method='squish')]
).dataloaders(path)

dls.show_batch(max_n=6)
```

It is very difficult to find the definition of `show_batch` without running the script.
