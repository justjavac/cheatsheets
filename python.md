---
title: Python
---

### 列表

    list = []
    list[i:j]  # returns list subset
    list[-1]   # access last element
    list[:-1]  # return all but the last element
    
    list[i] = val
    list[i:j] = otherlist  # replace ith to jth element with otherlist
    del list[i:j]

    list.append(item)
    list.extend(list)
    list.insert(0, item)
    list.pop()
    list.remove(i)
    list1 + list2     # combine two list    
    set(list)         # remove duplicate elements from a list

    list.reverse()
    list.count(item)
    sum(list)

    list.sort()

    zip(list1, list2)
    sorted(list)
    ",".join(list)

### Dict

    dict.keys()
    dict.values()
    "key" in dict
    dict["key"]   # throws KeyError
    dict.get("key")
    dict.setdefault("key", 1)

### 迭代器

    for item in ["a", "b", "c"]:
    for i in range(4):     # 0 to 3
    for i in range(4, 8):  # 4 to 7
    for key, val in dict.items():

### [字符串](https://docs.python.org/2/library/stdtypes.html#string-methods)

    str[0:4]
    len(str)

    string.replace("-", " ")
    ",".join(list)
    "hi {0}".format('j')
    str.find(",")
    str.index(",")   # same, but raises IndexError
    str.count(",")
    str.split(",")

    str.lower()
    str.upper()
    str.title()

    str.lstrip()
    str.rstrip()
    str.strip()

    str.islower()

### 类型转换

    int(str)
    float(str)

### 列表解析

    [fn(i) for i in list]            # .map
    map(fn, list)                    # .map, returns iterator
    
    filter(fn, list)                 # .filter, returns iterator
    [fn(i) for i in list if i > 0]   # .filter.map

### 正则表达式

    import re

    re.match(r'^[aeiou]', str)
    re.sub(r'^[aeiou]', '?', str)
    re.sub(r'(xyz)', r'\1', str)

    expr = re.compile(r'^...$')
    expr.match(...)
    expr.sub(...)

