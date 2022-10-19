 ## 2 变量和简单数据类型
##### 2.3.1 使用方法修改字符串的大小写

 ```py
 name = "ada johN"
 print(name.title())
 >>> Ada JohN
 print(name.upper())
 >>> ADA JOHN
 print(name.lower())
 >>> ada john
 ```



##### 2.3.2 在字符串中使用变量

```py
first_name = "Ada"
last_name = "John"
full_name = f"{first_name} {last_name}"
print(full_name)
>>> Ada John
```



##### 2.3.4 删除空白

```py
language = "Python "
print(language)
>>> 'Python '
print(language.rstrip)
>>> 'Python'
```



## 3 列表简介

##### 3.2.2 在列表中插入元素

```py
list.insert(0, 'elem')
```



##### 3.2.3 从列表中删除元素

```py
del list[1]  			#根据索引删除元素
list.pop(1)  			#根据索引删除元素，还可以将被删除的元素赋给其他变量
list.remove('elem') 	#根据值删除元素
						#remove()一次只能删除一个元素
```



3.3 组织列表

```py
list.sort()				#对列表永久排序
print(sorted(list))		#对列表临时排序
list.reverse()			#永久颠倒列表
len(list)				#获取列表长度
```

