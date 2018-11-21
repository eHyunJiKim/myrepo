#묻지마 범죄 최근 증가
#살인범죄의 감소 추세에도 불구하고 묻지마 범죄는 최근 3년간 매년 54~55건이 지속적으로 발생하여 국민 불안을 야기
import PyPDF2
pdfFile0bj=open('150828_보도자료(묻지마_범죄_대책_관련_유관기관_등_공동세미나_개최)-대검_강력부.pdf', 'rb')
pdfReader=PyPDF2.PdfFileReader(pdfFile0bj)
print(pdfReader.numPages)
page0bj=pdfReader.getPage(3)
print(page0bj.extractText())
pdfFile0bj.close()



v=convert_pdf_to_txt()
print(v)	
#묻지마 범죄의 원인
#신문기사에서 많이 나오는 단어 찾기 
import requests
r=requests.get('https://news.joins.com/article/21615113')
r.encoding='utf8'
data=str(r.text)
begin=data.find('"당신에게 이 나라는 어떤 의미가 있나요."')
end=data.rfind('백수진 기자')
a=data[begin:end]
a=a.replace('이',' ');a=a.replace('교수는',' ') ; a=a.replace('있는',' ')
a=a.replace('없었다',' ') ; a=a.replace('.',' ') ; a=a.replace('수',' ')
a=a.replace('범죄를',' ') ; a=a.replace('범죄로',' ') ; a=a.replace('적이',' ')
a=a.replace('것으로', ' ') ; a=a.replace('요인이',' ') ; a=a.replace('영향을',' ')
a=a.replace('성향이', ' ') ; a=a.replace('같은',' ') ; a=a.replace('본',' ')
a=a.replace('한',' ') ;a=a.replace('그는', ' ') 
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
        if i>30:
            break

        
        
import requests
r=requests.get('http://monthly.chosun.com/client/news/viw.asp?ctcd=C&nNewsNumb=200812100052&page=26')
data=str(r.text)
begin=data.find("지난 10월 20일 아침 8시15분.")
end=data.rfind("언제 터질지 모른다.⊙")
b=data[begin:end]

mydict={}
b=b.split()
for w in b:
    if w in mydict:
        mydict[w]+=1
    else:
        mydict[w]=1
i=0
for k in sorted(mydict, key=mydict.__getitem__, reverse=True):
        print('%s: %s'%(k,mydict[k]))
        i+=1
        if i>30:
            break



#묻지마 범죄자의 원인
#IMF  가정해체         

import requests
r=requests.get('http://news.chosun.com/site/data/html_dir/2009/07/25/2009072500040.html')
r.encoding='utf8'
data=str(r.text)

begin=data.find("IMF 경제위기 등을 겪으면서")
end=data.rfind("새로운 가족 형태가 늘어난 것이다.")
a=data[begin:end+10]
print(a)

