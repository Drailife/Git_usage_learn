**git --version 查看git 版本信息**

**设置对应的用户名与邮箱地址。**
```
 git config --global user.name "your_username"

 git config --global user.email your_email@domain.com

 git config --list 查看所有配置
 ```
 
```
git init  #初始化库
git status 命令用于显示工作目录和暂存区的状态。使用此命令能看到那些修改被暂存到 了, 哪些没有, 哪些文件没有被Git tracked到
```

# 提交
```python
 # 添加所有文件到暂存区
git add *  
#提交暂存区中的内容到本地仓库 -m 提交信息             
git commit -m "消息内容"    
#提交到远程库
git push 
```

# 删除库中文件
```
从repo中删除该文件，但也从本地文件系统中删除它
git rm file.txt
要从repo中删除文件而不从本地文件系统中删除它，请使用：  
git rm --cached file.tx
 
git add .
git commit -m 'remove file'
git push
```
# 忽略文件
有些时候我们不想把某些文件纳入版本控制中，比如数据库文件，临时文件，设计文件等
在主目录下建立".gitignore"文件，此文件有如下规则：
忽略文件中的空行或以井号（#）开始的行将会被忽略。
可以使用Linux通配符。例如：星号（\*）代表任意多个字符，问号（？）代表一个字符，方括号（[abc]）代表可选字符范围，大括号（{string1,string2,…}）代表可选的字符串等。
如果名称的最前面有一个感叹号（!），表示例外规则，将不被忽略。
如果名称的最前面是一个路径分隔符（/），表示要忽略的文件在此目录下，而子目录中的文件不忽略。
如果名称的最后面是一个路径分隔符（/），表示要忽略的是此目录下该名称的子目录，而非文件（默认文件或目录都忽略）

```python
#为注释
*.txt        #忽略所有 .txt结尾的文件,这样的话上传就不会被选中！
!lib.txt     #但lib.txt除外
/temp        #仅忽略项目根目录下的TODO文件,不包括其它目录temp
build/       #忽略build/目录下的所有文件
doc/*.txt    #会忽略 doc/notes.txt 但不包括 doc/server/arch.txt
```
