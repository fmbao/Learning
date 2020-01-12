#### yied 总结

- yield 实现多任务并发

  >```python
  >import time
  >def tast1():
  >    while True:
  >        print("1")
  >        time.sleep(0.1)
  >        yield 
  > def tast2():
  >    while True:
  >        print("2")
  >        time.sleep(0.1)
  >        yield 
  >def main():
  >    t1 = task1()
  >    t2 = task2()
  >    while True:
  >        next(t1)
  >        next(t2)
  >if __name__ == "__main__":
  >    main()
  >        
  >```
  >
  >
  >
  >

#### 进程、线程、协程之间的对比

- 进程是资源分配的单位

- 线程是操作系统调度的单位

- 进程切换需要的资源最大，效率最低

- 线程切换需要的资源一个班，效率一般

- 协程切换任务资源很小，效率很高

- 多进程、多线程根据CPU核数不一样可能是并行，但是协程是在一个线程中，所以是并发的（并发就是将一个CPU资源充分利用起来的技术，伪并行技术）

  

#### 多值参数

定义支持多值参数的函数

- 有时可能需要**一个函数**能够处理的参数个数时不确定的，这个时候，就可以使用**多值参数**
- python中有两种多值参数：
  - 参数名前增加一个`*` 可以接收**元祖**
  - 参数名前增加两个`**`可以接收**字典**

- 一般在给多值参数命名时，习惯使用以下两个名字
  - `*args` --存放元组参数，前面有一个`*`
  - `**kwargs*`--存放字典参数，前面有两个`**`

- `args`是`arguments`的缩写，有变量的含义
- `kw`是`keyword`的缩写，`kwargs`可以记忆键值对参数

- 元组和字典的拆包

  - 在调用带有多值参数的函数时，如果希望：
    - 将一个元组变量，直接传递给`args`
    - 将一个字典变量，直接传递给`kwargs`

  - 就可以使用**拆包**，简化参数的传递，拆包的方式是：
    - 在元组变量前，增加一个`*`
    - 在字典变量前，增加两个`**`

  ```pyt
  def demo(*args, **kwargs):
  	print(args)
  	print(kwargs)
  	
  ### 需要将一个元组变量/字典变量传递给函数对应的参数
  gl_nums = (1,2,3)
  gl_xiaoming = {"name":"小明"，"age":18}
  demo(*gl_nums, **gl_xiaoming)
  ```

  

#### python中 _insert 以及 _author_ 设置

