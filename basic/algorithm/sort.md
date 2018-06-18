## 排序算法概要
![排序算法](../../images/sort.png)

排序算法是非常基础的算法之一，在我们生活中应用相当广泛，比如我们逛购物网站时，会按商品的销量去检索。上图列出了基本的排序的比较情况，根据各自的时间复杂度和空间复杂度，我们可以知道算法的好坏。

参考资料：
- [十大经典排序算法](https://github.com/hustcc/JS-Sorting-Algorithm)

## 常见排序算法

### 插入排序
插入排序是一种最简单直观的排序算法，它的工作原理是通过构建有序序列，对于未排序数据，在已排序序列中从后向前扫描，找到相应位置并插入。

```js
// 从小到大排序
function sort(arr) {
  var arrCopy = arr.concat();
  for (var i = 1; i < arrCopy.length; i++) {
    var prevIndex = i - 1;
    var currentValue = arrCopy[i];
    while (prevIndex >= 0 && currentValue < arrCopy[prevIndex]) {
      arrCopy[prevIndex + 1] = arrCopy[prevIndex];
      prevIndex--;
    }
    arrCopy[prevIndex + 1] = currentValue;
  }

  return arrCopy;
}
```

```php
// 从小到大排序
function sort($arr) {
    for ($i = 1; $i < count($arr); $i++) {
        $prevIndex = $i - 1;
        $currentValue = $arr[$i];
        while ($prevIndex >= 0 && $currentValue < $arr[$prevIndex]) {
            $arr[$prevIndex + 1] = $arr[$prevIndex];
            $prevIndex--;
        }
        $arr[$prevIndex + 1] = $currentValue;
    }

    return $arr;
}
```

### 选择排序

### 冒泡排序

### 快速排序

### 希尔排序

### 归并排序

### 堆排序
