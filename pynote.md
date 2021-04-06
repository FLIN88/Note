## np.ascontiguousarray
ascontiguousarray函数将一个内存不连续存储的数组转换为内存连续存储的数组，使得运行速度更快。
```Py

>>> arr
array([[ 0,  1,  2,  3],
       [ 4,  5,  6,  7],
       [ 8,  9, 10, 11]])
>>> arr1 = arr[:3, :]
>>> arr1
array([[ 0,  1,  2,  3],
       [ 4,  5,  6,  7],
       [ 8,  9, 10, 11]])
>>> arr1.flags
  C_CONTIGUOUS : True
  F_CONTIGUOUS : False
  OWNDATA : False
  WRITEABLE : True
  ALIGNED : True
  WRITEBACKIFCOPY : False
  UPDATEIFCOPY : False

>>> arr1 = arr[:, 1:3]
>>> arr1.flags
  C_CONTIGUOUS : False
  F_CONTIGUOUS : False
  OWNDATA : False
  WRITEABLE : True
  ALIGNED : True
  WRITEBACKIFCOPY : False
  UPDATEIFCOPY : False

>>> arr2 = np.ascontiguousarray(arr1)
>>> arr2.flags
  C_CONTIGUOUS : True
  F_CONTIGUOUS : False
  OWNDATA : True
  WRITEABLE : True
  ALIGNED : True
  WRITEBACKIFCOPY : False
  UPDATEIFCOPY : False
```


## itertools.count

产生无限序列
```py 
for t in count():
    ...
```
## torch.max(input, dim)

函数会返回两个tensor，第一个tensor是每行的最大值；第二个tensor是每行最大值的索引。

## glob.glob()
带通配符搜索文件返回路径列表
```py
import glob

#获取指定目录下的所有图片
print (glob.glob(r"/home/qiaoyunhao/*/*.png"))#加上r让字符串不转义

#获取上级目录的所有.py文件
print (glob.glob(r'../*.py')) #相对路径

```

## torch.stack()

堆叠默认沿着第一位堆叠
```py
>>> import torch
>>> a = torch.rand((2, 3))
>>> b = torch.rand((2, 3))
>>> c = torch.stack((a, b))
>>> a.size(), b.size(), c.size()
(torch.Size([2, 3]), torch.Size([2, 3]), torch.Size([2, 2, 3]))
```

## os.path.basename(path)

给路径，返回文件名
```py
path='D:\CSDN'
os.path.basename(path)=CSDN
```

## os.path.splitext(path)

分开文件名拓展名

```py
fname,fename=os.path.splitext('/home/ubuntu/python_coding/split_func/split_function.py')
# fname is:/home/ubuntu/python_coding/split_func/split_function
#fename is:.py
```

## torch.nn.functional.pad

dim : 从最后一维开始往回数，每两个数pad一个维度。

## os.path.join()
```py
print os.path.join('/111','/222','333') #/222/333
```
从倒数第一个，以‘/’开头的参数开始拼接，之前的参数全部丢弃。