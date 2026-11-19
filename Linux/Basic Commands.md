

更改文件属组:
chown [–R] 所有者 文件名
chown [-R] 所有者:属组名 文件名
更改文件所有者：
chown [–R] 所有者 文件名
chown [-R] 所有者:属组名 文件名
更改文件属性:
chmod [-R] xyz 文件/目录
r=4,w=2,x=1
chmod u=,g=,o= 文件名

绝对路径:从根目录/写起
i.e.  /usr/share/doc
相对路径:由 /usr/share/doc 要到 /usr/share/man 底下时，可以写成： cd ../man

**ls**(list files)
**cd**(change directory)
**pwd**(print work directory)
**mkdir**(make directory)
**rmdir**(remove directory)
**cp**(copy file)
**rm**(remove)
**mv**(move file)
获取命令使用文档: man command

上一级目录: cd ..
i.e.  当前在/home/user
打开上一级目录中的某个文件/文件夹: cd ../lib64


# cp
cp [options] source 1 source2 source3 .... directory
#### options:-a  -i -p -r 


