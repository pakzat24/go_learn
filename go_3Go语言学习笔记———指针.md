# Go语言学习笔记———指针

------

> ## 什么是指针？

> Go 语言中指针是很容易学习的，Go 语言中使用指针可以更简单的执行一些任务。
>
> 接下来让我们来一步步学习 Go 语言指针。
>
> 我们都知道，变量是一种使用方便的占位符，用于引用计算机内存地址。
>
> Go 语言的取地址符是 &，放到一个变量前使用就会返回相应变量的内存地址。

## 怎么获取指针？

```go
package main

import "fmt"

func main() {
   var a int = 10  

   fmt.Printf("变量的地址: %x\n", &a  )
}

//输出结果>>>0x50b230
//PS:这个输出的值每个人的都不相同

```

> ### 指针呢，也是一个类型，就像int，float，string一样，这个该怎么定义呢？

```go
var name *type
//例如：

var ca *int //指向整型
car cb *float //指向浮点型
//在指针类型前加*号是为了获取指针内容
```

> ## 怎么使用指针？

```go
package main

import "fmt"

func main(){
	var(
		ab int = 2
		bb *int
		cb *int
	)
		cb = &ab
		fmt.Printf("\nab的值=%v ab的内存地址是%v\nbb的值=%v bb的内存地址是%v\ncb的值=%v,cb的内存地址%v\n用*cb来读取ab的值%v\n\n",ab,&ab,bb,&bb,cb,&cb,*cb)
    
}
//输出结果
/*
ab的值=2 ab的内存地址是0xc0000c0008
bb的值=<nil> bb的内存地址是0xc0000b4028
cb的值=0xc0000c0008,cb的内存地址0xc0000b4030
用*cb来读取ab的值2
*/
```

> ## 用指针来完成计算小项目

### 我在note.go下创建一个函数Caa

```go
func Caa(cc *int){
	cj := cc
    c4 :=*cj+3
	fmt.Printf("cj的值=%v\ncj的内存地址=%v\ncj指向的内存的值%v\nc4的值是%v\n",cj,cj,*cj,c4)
}

```



### 我在main.go上创建一个变量

```go
var cc4 int = 2
```

### 然后对note.go上的Caa函数进行传值

```go
note.Caa(&cc4)
//输出结果
/*
cj的值=0x50b230
cj的内存地址=0x50b230
cj指向的内存的值2
c4的值是5
*/
```

> ### 整个过程呢就是：
>
> 在main.go创建值为cc4，然后把cc4的内存地址传给note.go文件下的Caa函数，Caa函数的cc变量负责接受这个值，并计算

![go_3](https://github.com/pake0224/go_learn/blob/main/%E6%8B%89%E8%A5%BF%E5%A7%86/%E6%88%AA%E5%9B%BE%202022-12-08%2023-54-56.png)