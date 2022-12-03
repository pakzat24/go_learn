

# Go语言学习笔记——包管理

## 初始化：

我们在终端用  go mod init  [自己随便起]
例如： go mod init pakzat

------

![go_1_1](https://github.com/pake0224/go_learn/blob/main/%E6%8B%89%E8%A5%BF%E5%A7%86/%E6%88%AA%E5%9B%BE%202022-12-03%2018-29-59.png)

## 同一个文件中访问不同函数的代码:



![go_1_2](https://github.com/pake0224/go_learn/blob/main/%E6%8B%89%E8%A5%BF%E5%A7%86/%E6%88%AA%E5%9B%BE%202022-12-03%2019-31-22.png)

### 

## 不同文件调用:

我在主目录有一个main.go文件和note目录，而notedm目录下有一个hello.go文件

![go_1_2](https://github.com/pake0224/go_learn/blob/main/%E6%8B%89%E8%A5%BF%E5%A7%86/%E6%88%AA%E5%9B%BE%202022-12-03%2019-53-44.png)

------

### 以上就是包管理教程

### 重点：

### 跨文件调用时，函数名开头必须是大写字母。
