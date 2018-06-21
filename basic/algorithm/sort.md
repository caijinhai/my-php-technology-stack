## 排序算法概要
![排序算法](../../images/sort.png)

排序算法是非常基础的算法之一，在我们生活中应用相当广泛，比如我们逛购物网站时，会按商品的销量去检索。上图列出了基本的排序的比较情况，根据各自的时间复杂度和空间复杂度，我们可以知道算法的好坏。

参考资料：
- [十大经典排序算法](https://github.com/hustcc/JS-Sorting-Algorithm)

## 常见排序算法

### 插入排序
插入排序是一种最简单直观的排序算法，它的工作原理是通过构建有序序列，对于未排序数据，在已排序序列中从后向前扫描，找到相应位置并插入。

JavaScript 版
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

PHP版
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
选择排序是一种简单直观的排序算法，无论什么数据进去都是 O(n²) 的时间复杂度。它的原理是首先在未排序序列中找到最小（大）元素，存放到排序序列的起始位置，再从剩余未排序元素中继续寻找最小（大）元素，然后放到已排序序列的末尾，重复上述步骤，直到所有元素均排序完毕。

JavaScript 版
```js
function selectionSort(arr) {
    var arrCopy = arr.concat();
    var length = arrCopy.length;
    var minIndex, temp;
    for(var i = 0; i < length - 1; i++) {
        minIndex = i;
        for(var j = i + 1; j < length; j++) {
            if (arrCopy[j] < arrCopy[minIndex]) {
                minIndex = j;
            }
        }
        temp = arrCopy[i];
        arrCopy[i] = arrCopy[minIndex];
        arrCopy[minIndex] = temp;
    }
    return arrCopy;
}
```

PHP 版
```php
function selectionSort($arr)
{
    $len = count($arr);
    for ($i = 0; $i < $len - 1; $i++) {
        $minIndex = $i;
        for ($j = $i + 1; $j < $len; $j++) {
            if ($arr[$j] < $arr[$minIndex]) {
                $minIndex = $j;
            }
        }
        $temp = $arr[$i];
        $arr[$i] = $arr[$minIndex];
        $arr[$minIndex] = $temp;
    }
    return $arr;
}
```

### 冒泡排序
冒泡排序（Bubble Sort）也是一种简单直观的排序算法。它重复地走访过要排序的数列，一次比较两个元素，如果他们的顺序错误就把他们交换过来。走访数列的工作是重复地进行直到没有再需要交换，也就是说该数列已经排序完成。这个算法的名字由来是因为越小的元素会经由交换慢慢“浮”到数列的顶端。

JavaScript 版
```js
function bubbleSort(arr) {
    var len = arr.length;
    for (var i = 0; i < len - 1; i++) {
        for (var j = 0; j < len - 1 - i; j++) {
            if (arr[j] > arr[j + 1]) {        // 相邻元素两两对比
                var temp = arr[j + 1];        // 元素交换
                arr[j + 1] = arr[j];
                arr[j] = temp;
            }
        }
    }

    return arr;
}
```

PHP 版
```php
function bubbleSort($arr)
{
    $len = count($arr);
    for ($i = 0; $i < $len - 1; $i++) {
        for ($j = 0; $j < $len - 1 - $i; $j++) {
            if ($arr[$j] > $arr[$j + 1]) {
                $tmp = $arr[$j];
                $arr[$j] = $arr[$j + 1];
                $arr[$j + 1] = $tmp;
            }
        }
    }

    return $arr;
}
```

### 快速排序
快速排序是由东尼·霍尔所发展的一种排序算法。在平均状况下，排序 n 个项目要 Ο(nlogn) 次比较。在最坏状况下则需要 Ο(n2) 次比较，但这种状况并不常见。事实上，快速排序通常明显比其他 Ο(nlogn) 算法更快，因为它的内部循环（inner loop）可以在大部分的架构上很有效率地被实现出来。

JavaScript 版
```js
function quickSort(left, right, arr) {
  if (left >= right || right > arr.length) {
    return;
  }

  var pivot = arr[left];
  var i = left;
  var j = right;
  while (i !== j) {
    while (arr[j] >= pivot && j > i) {
      j--;
    }

    while (arr[i] <= pivot && j > i) {
      i++;
    }

    if (j > i) {      
      var temp = arr[j];
      arr[j] = arr[i];
      arr[i] = temp;
    }
  }

  arr[left] = arr[i];
  arr[i] = pivot;

  quickSort(left, i - 1, arr);
  quickSort(i + 1, right, arr);
}
```

PHP 版
```php
function quickSort($arr)
{
    if (count($arr) <= 1) {
      return $arr;
    }
    $middle = $arr[0];
    $leftArray = array();
    $rightArray = array();

    for ($i = 1; $i < count($arr); $i++) {
        if ($arr[$i] > $middle) {
          $rightArray[] = $arr[$i];
        } else {
          $leftArray[] = $arr[$i];
        }
    }
    $leftArray = quickSort($leftArray);
    $leftArray[] = $middle;
    $rightArray = quickSort($rightArray);

    return array_merge($leftArray, $rightArray);
}
```

参考资料：
- [51CTO](http://developer.51cto.com/art/201403/430986.htm)

### 希尔排序

### 归并排序

JavaScript 版
```js
function mergeSort(arr) {  // 采用自上而下的递归方法
    var len = arr.length;
    if(len < 2) {
        return arr;
    }
    var middle = Math.floor(len / 2),
        left = arr.slice(0, middle),
        right = arr.slice(middle);
    return merge(mergeSort(left), mergeSort(right));
}

function merge(left, right)
{
    var result = [];

    while (left.length && right.length) {
        if (left[0] <= right[0]) {
            result.push(left.shift());
        } else {
            result.push(right.shift());
        }
    }

    while (left.length)
        result.push(left.shift());

    while (right.length)
        result.push(right.shift());

    return result;
}
```

PHP 版
```php
function mergeSort($arr)
{
    $len = count($arr);
    if ($len < 2) {
        return $arr;
    }
    $middle = floor($len / 2);
    $left = array_slice($arr, 0, $middle);
    $right = array_slice($arr, $middle);
    return merge(mergeSort($left), mergeSort($right));
}

function merge($left, $right)
{
    $result = [];

    while (count($left) > 0 && count($right) > 0) {
        if ($left[0] <= $right[0]) {
            $result[] = array_shift($left);
        } else {
            $result[] = array_shift($right);
        }
    }

    while (count($left))
        $result[] = array_shift($left);

    while (count($right))
        $result[] = array_shift($right);

    return $result;
}
```

参考资料：
- [博客园](https://www.cnblogs.com/chengxiao/p/6194356.html)

### 堆排序
