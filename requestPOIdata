from urllib.parse import quote
import urllib.request
import json
import string


Universities=['北京交通大学','北京邮电大学','北京大学','清华大学','北京理工大学','北京航空航天大学','中国人民大学','中国政法大学']

datas=Universities
print(len(datas))
for data in datas:
	#print(x)
	weburl="http://map.baidu.com/su?wd="+urllib.parse.quote(data)+"&cid=289&type=0&pc_ver=2"
	response = urllib.request.urlopen(weburl)
	hjson=json.loads(response.read().decode('utf-8'))
	str1=''.join(hjson['s'])
	index1=str1.find('$131')
	uid=str1[index1+5:index1+29]
	#print(index1)
	print(data+":"+uid)
	dataurl="http://map.baidu.com/?pcevaname=pc4.1&qt=ext&uid="+uid+"&ext_ver=new&l=12"
	response2=urllib.request.urlopen(dataurl)
	djson=json.loads(response2.read().decode('utf-8'))
	str2=''.join(djson['content']['geo'])
	index2=str2.find('|1-')
	str2=str2[index2+3:len(str2)]
	strlist=str2.split(',')
	cnt=0
	for points in strlist:
		if cnt%2==0:
			x=points
			cnt+=1
		else:
			y=points
			print(x+','+y)
			cnt+=1



