# 语言学习笔记———变量与常量

------

### [我的网站：sb110.icu](http://sb10.icu)

> ## 内容：

### 1.变量

### 2.常量

### 3.跨包调用变量与常量

------

> ## 变量

#### 比如我们定义一个变量有多种方法，例如：

```go
package main
import "fmt"
func main(){
    //在函数内部调用（只能在所在函数里使用）
	var a int = 1 //指定变量类型（我们指定了类型是int）
    var a1 = 11 //直接写值，它自己判断这个值是什么类型
	a2 := 111
	fmt.Println(a,a1,a2)
	a = 100
	fmt.Println("a是",a)
}
```

![go_2_1](https://github.com/pake0224/go_learn/blob/main/%E6%8B%89%E8%A5%BF%E5%A7%86/%E6%88%AA%E5%9B%BE%202022-12-04%2013-32-50.png)

------

> ## 常量

### 这个常量跟变量没什么区别，唯一有区别的地方是，变量可以用iota看行数，例如

`

```go
package main
import "fmt"

const(
	c=1
	c1=2
)
func main(){
    fmt.Println(c,c1) //输出结果为：c>>>1  ,c1>>>2
}
```

`

### 我们再来看iota

```go
package main
import "fmt"
const(
	t=iota
	t1=iota
    t2=iota
    t3
    t4
    t5
)
func main(){
    fmt.Println(t,t1,t2,t3,t4,t5)
}

输出结果为:
t>>>0
t1>>>1
t2>>>3
t4>>>4
t5>>>5

```

![go_2_2](https://github.com/pake0224/go_learn/blob/main/%E6%8B%89%E8%A5%BF%E5%A7%86/%E6%88%AA%E5%9B%BE%202022-12-04%2013-44-58.png)

------

> ## 跨包调用变量和常量

![go_2_3](https://github.com/pake0224/go_learn/blob/main/%E6%8B%89%E8%A5%BF%E5%A7%86/%E6%88%AA%E5%9B%BE%202022-12-04%2013-49-33.png)

### 注意：跨包调用时变量或常量名开头必须是大写字母
