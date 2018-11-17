
import requests
r=requests.get('https://news.joins.com/article/21615113')
r.encoding='utf8'
data=str(r.text)
begin=data.find('"당신에게 이 나라는 어떤 의미가 있나요."')
end=data.rfind('백수진 기자')
a=data[begin:end]
print(a)
mydict={}
a=a.split()
for w in a:
    if w in mydict:
        mydict[w]+=1
    else:
        mydict[w]=1
i=0
for k in sorted(mydict, key=mydict.__getitem__, reverse=True):
        print('%s: %s'%(k,mydict[k]))
        i+=1
        if i>19:
            break
        
import requests
q=requests.get('http://monthly.chosun.com/client/news/viw.asp?ctcd=C&nNewsNumb=200812100052&page=26')
q.encoding='utf8'
dataq=str(q.text)
beginq=dataq.find("지난 10월 20일 아침 8시15분.")
endq=dataq.rfind("언제 터질지 모른다.⊙")
b=dataq[beginq:endq]
print(b)

mydicta={}
b=b.split()
for wa in b:
    if wa in mydicta:
        mydicta[wa]+=1
    else:
        mydicta[wa]=1
i=0
for k in sorted(mydicta, key=mydicta.__getitem__, reverse=True):
        print('%s: %s'%(k,mydicta[k]))
        i+=1
        if i>19:
            break




