来源：https://yq.aliyun.com/video/play/1359?utm_content=m_45830<br>

* Python能做什么？
	* 1.简单脚本编程
	* 2.系统编程
	* 3.开发网络爬虫(类似：数据采集)	
	* 4.开发Web	
	* 5.进行自动化运维(类似：服务器集群管理脚本)	
	* 6.网络编程
	* 7.数据挖掘，机器学习等大数据与人工智能领域方向开发	


* 数据类型：type()--->查看数据类型
	* 1.数：a=1	type(a) 查看a的数据类型为：int
	* 2.字符串：'a1'  "a2gd /n gdg"  '''abcd'''	
	* 3.列表：[a1,"a2",a3]		存储多个元素的东西，元组里面的元素是可以重新赋值的
	* 4.元组：(1,"c",3)		存储多个元素的东西，元组里面的元素是不可以重新赋值的
	* 5.集合：去重		e=set("aaaabbvddfg")	去重字符串赋值给e	
	* 6.字典：{"a":"123","b":"456"}		关联数组(键值对)类似map

* 运算符:+ - * / 
	* +：字符串连接符
	* %：求余运算


* 控制结构：
	* 例：
	* 1.a=100	b=1
	'''
	if(a>19 and a<30):
	print(a)
	if(b<9):
		print(b)
	elif(a>9 and a<=19):
		print("a>9 and a<=19")
	elif(a<9):
		print("a<9")
	else:
		print("a<9")
	'''


	
	* 2.a=0
	'''
	while(a<10)	
	print("123456789")
	a+=1
	一直执行到a>10才不再执行
	'''



	* 3.a1=["a","b",2]
	'''
	for i in a1
	if(i=="b")
	break

	for i in rang(1,20)
		print("123456789")
		continue
	'''
	
	* break:全部直接退出,整个循环都中断
	* continue:中断一次循环，继续下次循环

<br>
函数与模块:

函数：作用域：变量作用范围

i=10		#定义局部变量
def abcd():	#定义函数
	j=20
	i+=30	#错误书写，不能在函数中修改变量		想要修改,声明变量为全局变量(global i-->代表i为全局变量)
	print(j)
	print(i)
abcd()		#调用函数
print(j)	#报错(在函数中声明就只能够在函数中作用,j只能在func()函数中使用)
print(i)

参数：与外界沟通的接口,分为：形参和实参
一般在函数定义的时候使用的参数是形参，在函数调用的时候使用的参数是实参

def kkk(a,b):
	if(a>b):
		print(str(a)+"比"+str(b)+"大")
	else:
		print(str(a)+"比"+str(b)+"小或相等")


模块：模块的导入
import random			#导入random模块(用于随机数的处理)
from time import sleep	#导入time模块的sleep方法(时间处理)
from time import *		#导入time模块的所有方法

a=["中奖","不中","不中"]
print(random.choice(a))



文件的操作：打开 open(文件地址，操作形式)	w:写入	r:读取	b:二进制	a:追加
举例：
x=0
yy=open("D:/AA/文本.txt","r",encoding="gbk")
data=yy.read()		#读全部
while True:
	line=yy.readline()	#一行行读
	if(len(line)==0):
		break			#全部直接退出,整个循环都中断
	print(line)
	x+=1				#统计读了多少行
yy.close()	#关闭文件

文件写入：
aa=open("D:/AA/文本.txt","a")
data="12345678"
aa.write(data)	#写入文件
aa.close()	#关闭文件




操作数据库先安装pymysql：pip install pymysql
查看是否安装python
查看是否安装pip

防止数据库乱码：修改python\Lib\site-packages\pymysql\connections.py\charset='utf8'

#数据库连接：
import pymsql		#导入模块
conn=pymysql.connect(host="127.0.0.1",user="root",passwd="root",db="mysql")	#连接数据库
#执行sql语句：无返回
conn.query("INSERT INTO mytab(titlemkeywd) VALUES('new title','123456')")	#添加数据
conn.commit()	#提交

#执行sql语句：有返回
cs=conn.cursor()		#使用游标
cs.execute("select = from mytab")	#查询
for i in cs:			#遍历游标
	print(Str(cs.rownumber))
	print(i[0])
	print(i[1])
conn.close


异常：(异常处理细化：监控for循环中是否存在异常)
for i in range(0,10):
	try:
		print(i)
		if(i==4):
			print(jkj)
	except Exception as err
		print(err)
print("123")



面向对象：类和对象

创建一个类
class person:
	passwd
实列化一个类
a=person()


构造函数(构造方法)
self:在类中的方法必须加上self参数
__init__(self,参数)
构造函数实际意义：初始化

举例：
class a:
	#无参构造方法
	def __init__(self):
		print("自动触发执行构造方法")
	#带参构造方法
	def __init__(self,name):
		print("自动触发执行构造方法"+name)

属性：类中变量：self.属性名

class b:
	def __init__(self,name,job):
		self.myname=name
		self.myjob=job
		
		
继承：单继承，多继承

父类(基类)
class father():
	def speak(self):
		print("会说")
单继承
class son(father)
	pass

第二个父类(基类)
class mother():
	def while(self):
		print("会写")
多继承
class daughter(father,mother):
	除了继承的方法外还有自己的方法
	def listen(self):
		print("能听")

重写(重载)
class son1(father):
	def speak(self):
		print("很会说")