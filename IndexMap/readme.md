# Introduction

这个程序构建某个文件夹下从多个文件的文件名到数字Index的映射。

This program construct a map from file names to index numbers in a specific directory.

Index是用正则表达式从文件名中提取出来的。

Index is extracted from file names by regular expression matching.

此程序可以用于批量处理文件时按一定顺序遍历文件。比如你有个`image`文件夹，下面有`001.jpg`……`100.jpg`，你想按序遍历它们。但是Python中的`os.listdir`方法返回的list可能并非这个顺序。那么你可以用这个程序构建映射，然后通过遍历`index`间接按序遍历文件。

This program can be used to iterate files in a specifc order. For example, you  have `001.jpg`……`100.jpg` in directory `image`. You want to iterate them from `001.jpg` to`100.jpg`, but the `os.listdir` method in Python may not return a list at this order. Then you can use this program to construct a map and iterate index from 1 to 100 so as to iterate the jpg files indirectly.

# Usage

```python
# Import the module
from IndexMap import IndexMap

# Construct an object
filemap = IndexMap()

# Call the input_dir method to input directory
filemap.input_dir()
# Or call the ser_dir method to set directory
files.set_dir()

# Input regular expressions
filemap.input_patterns()
# Or set regular expressions using a list
RE_LIST = [
	'-{1,1}\d+',
	'\d+'
]
files.set_patterns(RE_LIST)

# Construct the map
# Pass True to the method to print some infomations when constructing the map.
# Otherwise you can pass no parameters (False by default): filemap.construct_map()
filemap.construct_map(True)

# You can print the result when construction ends.
filemap.print_info()
```



