`上大学期间第一次接触排序算法就是＇冒泡排序发＇   `

记得我第一次接触c语言的时候，完全不懂（似乎那时候代码都是'记下来的'）．   
那时候觉得满足了功能实现就足够了，根本没有考虑效率［时间复杂度.空间复杂度］   


来吧，我们的高级攻城师们一起来进入大学时代，呵呵：  

下面是最常用的冒泡排序算法：    
```c
void Swap(int &a, int &b)  //c++的写法
{
        a^=b;
        b^=a;
        a^=b;
        return;
}


void BubleSort(int *a, int len)
{　　
        int i = 0;
    　  int j = 0;　　　　

	for(i=0;i<len-1;++i)
	{
		for(j=0;j<len-i-1;++j)
		{
			if(a[j] > a[j+1])
			{
				Swap(a[j], a[j+1]);

			}

		}

	}
}
```



稍微有想法的就不会这么写了：  

```c
void BubleSort(int *a, int len)
{　　　　　　　
　　    int flag = 0;　　
        int i = 0;
        int j = 0;　　　　　

	for(i = 0; i < len-1; ++i)
	{       
                flag =1;
		for(j = 0; j < len-i-1; ++j)
		{
			if(a[j] > a[j+1])
			{
				Swap(a[j],　a[j+1]);
　　　　　　　　                 flag = 0;
			}
		}

　　　　        if(flag) return;
	}
}
```

这样加一个标志为flag,如果在一轮排序中任何相邻的两个数都没有进行交换，  
则说明该数组已经是有序的了,所以直接提前终止排序．这样的话是不是就可以   
减少排序的次数了恩，尤其是对一个已经有序的进行顺序的排序．　　   

上面这个是在学习汇编的时候觉悟的，当时用汇编练习冒泡排序．   
还有一种写法，其实我感觉就是上面的一种再次升级的写法吧：    

```c
void BubleSort(int *a, int len)
{　　　　　　　
　　　　 int k = 0;　　
        int i = 0;
        int j = 0;　　　　　

	for(i = len; i > 0; i = k)
	{       
            
		for(j=0, k = 0; j < i-1; ++j)
		{
			if(a[j] > a[j+1])
			{
				Swap(a[j],　a[j+1]);
                                k = j;
			}
		}

        }

}
```

上面的排序每次都把其尾部的位置给记录下来，后面有序的就不用再次去比较了．　　 












欢迎一起交流学习 
====
 
在使用中有任何问题，欢迎反馈给我，可以用以下联系方式跟我交流

* 邮件(1031379296#qq.com, 把#换成@)
* QQ: 1031379296
* weibo: [@王发康](http://weibo.com/u/2786211992/home)


Thx
====

* chunshengsterATgmail.com


Author
====
* Linux\nginx\golang\c\c++爱好者
* 欢迎一起交流  一起学习# 
* Others say good and Others good


