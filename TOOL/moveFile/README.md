# 批量文件移动
![](http://img04.static.yohobuy.com/thumb/2012/04/19/10/01c705bab7702eafe10d50a92556c6ec55-0750x1500-1-product.jpg)
## 内容简介
> 通过逐行读取txt文件中的文件路径，移动到另外的文件夹，主要用于删除项目中无用的文件并备份

## 源码

	import os
	import shutil
	
	def moveFile(filelist,movePath):
	
	    feedlist = [line for line in file(filelist)]
	    
	    for loop in feedlist:
	    
	        loop = loop.replace('\r','').replace('\n','').replace('\t','')
	        print ('The value is:'+loop)
	        
	        if os.path.isfile(loop):
	            shutil.move(loop,movePath)
	        else:
	            print "is not file"+loop


