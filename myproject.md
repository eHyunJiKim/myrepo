#묻지마 범죄 최근 증가
#살인범죄의 감소 추세에도 불구하고 묻지마 범죄는 최근 3년간 매년 54~55건이 지속적으로 발생하여 국민 불안을 야기

import PyPDF2
file=open('150828_보도자료(묻지마_범죄_대책_관련_유관기관_등_공동세미나_개최)-대검_강력부.pdf','rb')
fileReader=PyPDF2.PdfFileReader(file)
print()

#묻지마 범죄의 원인
#신문기사에서 많이 나오는 단어 찾기 
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



#묻지마 범죄자의 원인
#IMF  가정해체         

import requests
r=requests.get('http://news.chosun.com/site/data/html_dir/2009/07/25/2009072500040.html')
r.encoding='utf8'
data=str(r.text)

begin=data.find("IMF 경제위기 등을 겪으면서")
end=data.rfind("새로운 가족 형태가 늘어난 것이다.")
a=data[begin:end]
print(a)



