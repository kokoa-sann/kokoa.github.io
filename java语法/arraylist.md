# 方法

## `arraylist.romove`

里面方法的参数可以是`object`对象，也可以是`integer`对象
当添加元素`arraylist.add(1)`的时候默认自动装箱，即将`1`装箱为`integer`对象

当我们想删除`Java` `List`对象中的某一个的时候，可以选择根据索引*index*删除，也可以根据对象删除，调用的方法都是`remove`。  

**问题** 
但是当我们对一个`List<integer>`对象删除某个元素的，`remove(i) `是删除索引为`i`的元素，还是删除值为`i`的元素？

**回答**
是删除索引为`i`的元素，因为`i`是`int`类型的值，而`List`对象中的是装箱后的`integer`对象，所以`i`(int)不是`List`中的值

``` java
class Solution {
    public static void main(String[] args) {
        List<Integer> ls = new ArrayList<>();
        ls.add(1);
        ls.add(2);
        ls.add(3);
        ls.add(4);
        System.out.println(ls);
        ls.remove(1);
        System.out.println(ls);
        ls.remove(Integer.valueOf(4));
        System.out.println(ls);
    }
}

/* 结果
[1, 2, 3, 4]
[1, 3, 4]
[1, 3]
*/
```

可以看出当直接传入一个`int`值时，它是默认删除索引对应的元素。
如果是传入一个`Integer`对象的时候，他是删除那个值的元素。
因为`List`中保存的是`Integer`类型的值，`int`类型找不到，所以认为是索引。

---

参考链接：

- [Java List的remove()方法，参数为数字时，需要注意][List的remove()方法]

  

---

[List的remove()方法]:https://blog.csdn.net/qq_42520962/article/details/109116356 "List的remove()方法，参数为数字时，需要注意"





