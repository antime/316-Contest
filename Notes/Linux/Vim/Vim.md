# Vim 的一些使用技巧

- 在 Vim 下批量每行开头添加字符串

`:起始行号,结束行号s/^/注释符/`

- 在 Vim 下批量每行末尾添加字符串

`:起始行号，结束行号s/$/字符串/`

- 在 Vim 下批量所有行末尾添加字符串

```
:%s/$/字符串/
:%s/$/\//                   #在所有行末尾添加 '/'
```

- 批量清楚注释

`:起始行号,结束行号s/^注释符//`

- vim 下删除全部

`:%d`

- 替换第n行开始到最后一行中所有的str1 为str2

`:n,$s/str1/str2/g`

- 把一个很长的一行按空格分为多行

`:%s/ +/\r/g`

> 但是Vim会提示无效的选项“+”，直接输入`:%s/ /\r/g`，则替换成功<br>
> `%s`:在整个文件范围查找替换<br>
> `/`:分隔符<br>
> `\r`:换行符<br>
> `/g`:全局替换<br>

- 将文本中的空行删除

`:g/^s*$/d`

> `g`：全局<br>
> `/`：分隔符<br>
> `^s*$`：匹配空行，其中`^`代表行首，`s`代表空字符，包括空格和制表福，`*`重复0到n个前面的字符，`$`表示行尾。连起来就是匹配只有空字符的行，也就是空行。<br>
> `/d`：删除该行<br>

- 删除文本内的重复行

`:g/^\(.*\)$\n\1$/d`

> 在删除重复行之前需要先排序`:sort`

- 分屏同步移动

> 在两个屏中分别输入
> `:set scb`<br>
> 解除同步移动
> `:set scb!`<br>

- 取消之前的搜索

`:nohl`

- 编辑无权限文件时提示无法保存时，可以使用

`:w !sudo tee %`

- vim 复制内容到系统剪贴板

> `:"+y`<br>
> 按 `Shift + v` 选中要复制的区域，在当前模式输入 `"` `+` `y`
