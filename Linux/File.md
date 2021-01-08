## linux文件操作  
### 处理目录常见命令  
1. ls 列出目录及文件名  
   选项与参数：  
 - -a：全部的文件，连同隐藏的文件（开头为.的文件）一起列出来  
 - -d：仅列出目录本身，而不是列出目录内的文件数据  
 - -l：长数据串列出，包含文件的属性与权限等数据。
2. cd 切换目录  
3. pwd 显示当前的目录  
   选项与参数： 
   * -P：显示出确实的路径，而非使用连结(link)路径
4. mkdir 创建新目录  
   ```shell
    mkdir [-mp] 目录名称 
    ```
  选项与参数：
  * -m： 配置文件的权限，直接配置，不需要看默认权限
  * -p： 帮助你直接将所要的目录（包含上一级目录）递归创建起来。
  ```shell
 mkdir -p test/test1/test2
 mkdir -m 711 test2  
 ```
5. rmdir 删除一个空目录  
   ```shell
   rmdir [-p] 目录名称
   ```
   选项与参数：  
   * -p：连同上一级空的目录一起删除
  ```powershell
  rmdir -p test1/test2/test3
  ```
6. cp 复制文件或目录  
   选项与参数：
   + -a：相当于-pdr的意思
   + -d：若来源档为连结档的属性，则复制连结档属性而非文件本身
   + -f： 为强制(force)的意思，若目标文件已经存在且无法开启，则移除后再尝试一次。
   + -i：若目标档已存在时，再覆盖时会先询问动作的进行。
   + -l：进行硬式连结档创建，而非文件本身
   + -p：连同文件的属性一起复制过去，而非使用默认属性（备份常用）
   + -r：递归持续复制，用于目录的复制
   + -s：复制成为符合连结档，即windows的快捷方式
   + -u：若目标文件比源文件旧才升级目标文件。
7. rm 删除文件或目录  
   ```powershell
   rm [-fir] 文件或目录
   ```
   选项与参数：
   * -f：就是force的意思，忽略不存在的文件，不会出现警告信息；
   * -i：互动模式，在删除前会询问使用者是否动作；
   * -r：递归删除，最常用在目录删除，是非常危险的选项。
8. mv 移动文件与目录，或修改文件与目录的名称  
   选项与参数：  
   * -f：强制的意思，如果目标文件已存在，不会询问而直接覆盖；
   * -i：若目标文件已经存在，就会询问是否覆盖；
   * -u：若目标文件已经存在，且源文件比较新，才会升级。
### Linux文件查看
1. cat 由第一行开始显示文件内容。
   ```powershell
   cat [-AbEnTv]
   ```
   选项和参数：  
   * -A:相当于-vET的整合选项，可列出一些特殊字符而不是空白而已；
   * -b：列出行号，仅针对非空白行做行号显示，空白行不标行号；
   * -E：将结尾的断行字节$显示出来；
   * -n：列印出行号，连同空白行也会有行号，与-b不同；
   * T：将tab键以^|显示出来；
   * -v:列出一些看不出来的特殊字符。
2. tac 与cat命令相反，文件内容从最后一行开始显示，可以看出tac是cat的倒着写  
3. nl 显示行号
4. more 一页一页翻动  
   在more运行中，有以下几个键可以操作：
   * 空格键 ：代表向下翻一页；
   * Enter：代表向下翻一行；
   * /字符串:代表在这个显示的内容当中，向下搜索“字符串”这个关键字；
   * :f :立刻显示出文档名以及目前显示的行数；
   * q：代表离开more，不再显示该文件内容；
   * b或者ctrl-b：代表往回翻页。
  5. Less 一页一页翻动  
   less运行时，可以输入以下命令：
   * 空格键：向下翻动；
   * pagedown：向下翻动一页；
   * pageup：向上翻动一页；
   * /字符串：向下搜索字符串；
   * ?字符串：向上搜索字符串
   * n：重复前一个搜索
   * N：反向重复前一个搜索；
   * q：离开less这个程序。
  6. head 取出前面几行     
     ```
     head [-n number] 文件  
     ```
    
   选项和参数：  
   * -n:后面接数字，代表显示几行的意思。
  7. tail 取出文件后面几行  
    ``` 
    tail [-n number] 文件
    ```  
  选项和参数：
   * -n：后面接数字，代表显示几行的意思；
   * -f：表示持续侦测后面所接的文档，要等到按下ctrl+c才会结束tail的侦测。


   


