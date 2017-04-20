# 本的化数据存储

 
![](http://img04.static.yohobuy.com/thumb/2012/04/19/10/01c705bab7702eafe10d50a92556c6ec55-0750x1500-1-product.jpg)
## 内容简介
> 功能类似与html的Cookie，将系统临时数据保存为json格式的文件，通过key进行增删查改

## 源码

	# encoding:utf-8
	'''
	Created on 2017年4月15日
	
	@author: UbunGit
	'''
	
	import json
	
	cookiedata = {}
	／**
	 * 存储，修改
	 *／    
	def setCookie(key,value):
	
	    cookiedata[key] = value;
	    with open('Cookie.json', 'wb+') as json_file:
	        json_file.write(json.dumps(cookiedata))
	    json_file.close() 
	／**
	 * 查看
	 *／
	def getCookie(key):
	
	    if key in cookiedata.keys():
	        return cookiedata[key]
	        
	／**
	 * 移除
	 *／	    
	def removeCooKie(key):
	
	    cookiedata.pop(key, None)
	    with open('Cookie.json', 'wb+') as json_file:
	        json_file.write(json.dumps(cookiedata))
	    json_file.close()
	    
	
	def main():
	    with open("Cookie.json") as json_file:
	        jsondata  = str(json_file.read())
	        if (len(jsondata)==0):
	            data = {}
	        else:
	            data = json.loads(jsondata)
	    json_file.close()   
	    return data;
	    
	if __name__ == '__main__':
	    main()


