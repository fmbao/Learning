## git 学习

```python

git cat-file -t  -p (t 代表类型， p代表文件内容)
git object  （git 的数据单元）
git obj ->sha1哈希算法->加密文件

```

git  object几个类型：

- blob:文件内容
- tree：目录结构，文件权限，文件名
- commit：上一个commit，对应快照，作者，提交信息
- refs:HEAD、分支 、Tag

 ##    git小技巧

1. 误操作导致分支部件了，如何恢复？

   >比如操作`git reset --hard` 或者 `git rebase` 
   >
   >可以采用`git reflog`时光机

2. 如何获得一个干净的工作空间
   >现在的工作空间太乱了，工作到一半，临时插需求
   >
   >可以采用`git stash push -u --include-untracked`

3.  从Git历史中删除一个文件
    >比如删除敏感信息（私钥，内网IP等），不需要版本控制的超大文件
    >采用`git filte=-branch --tree-filter 'rm -f password.txt' HEAD`
   
 4.  commit之后想要撤回
    > `git reset --soft HEAD^`

