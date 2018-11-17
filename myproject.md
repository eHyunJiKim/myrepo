
import requests
r=requests.get('https://news.joins.com/article/21615113')
r.encoding='utf8'
data=str(r.text)
begin=data.find('"당신에게 이 나라는 어떤 의미가 있나요."')
end=data.rfind('백수진 기자')
a=data[begin:end]
print(a)
a=a.replace('이',' ') ; a=a.replace('.',' ') ; a=a.replace(',',' ') ;a=a.replace('교수는',' ') ; a=a.replace('있는',' ') ; a=a.replace('없었다',' ') ; a=a.replace('&nbsp;<br/>','') ; a=a.replace(';<br/>','') ; a=a.replace('</a>  </strong>  </li> </ul> </div></div>','') ; a=a.replace('</strong> </div> <div class="bd"> <ul class="text_type">  <li>  <strong class="headline">   <a href="http://news.joins.com/article/21615137">','') ; a=a.replace('&nbsp;<br/><div class="ab_related_article"> <div class="hd"> <strong>','') 
a=a.replace('범죄를', ' ') ; a=a.replace('수',' ') ; a=a.replace('범죄로',' ') ; a=a.replace('적이',' ') ; a=a.replace('것으로',' ') ; a=a.replace('영향을',' ') ; a=a.replace('요인이',' ') ; a=a.replace('성향이',' '); a=a.replace('가정',' ') ; a=a.replace('같은', ' ') ; a=a.replace('본',' '); a=a.replace('한',' ') ; a=a.replace('그는',' '); a=a.replace('<br/>&nbsp;<br/>','') ; a=a.replace('"','') ; a=a.replace("'",'')
a=a.replace('&nbsp;<br/>&nbsp;<br/>','') ; a=a.replace('적',' ') ; a=a.replace('것다',' ') ; a=a.replace('다',' ') ; a=a.replace('사건',' ') ; a=a.replace('요인',' ') ;a=a.replace('성향',' ') ; a=a.replace('면담',' ') ; a=a.replace('때',' ') ; a=a.replace('후',' ') ;a=a.replace('거의',' '); a=a.replace('앓은',' ') ; a=a.replace('분석',' ') ; a=a.replace('지난해',' ') ; a=a.replace('런',' ') ; a=a.replace('범죄의',' ')
a=a.replace('<div',' ') ; a=a.replace('만', ' ') ; a=a.replace('그',' '); a=a.replace('범죄', ' '); a=a.replace('범죄에',' '); a=a.replace('상', ' ') ; a=a.replace('정신질환',' ') ; a=a.replace('하지만',' ') ; a=a.replace('미친', ' ') ; a=a.replace('나타났',' ') ; a=a.replace('등',' ') ; a=a.replace('중',' ') ; a=a.replace('사람은', ' ') ; a=a.replace('점', ' ')
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
        
k=requests.get('http://monthly.chosun.com/client/news/viw.asp?ctcd=C&nNewsNumb=200812100052&page=26')
k.encoding='utf8'
datak=str(k.text)
begin=datak.find("지난 10월 20일 아침 8시15분.")
end=datak.rfind("지뢰처럼 언제 터질지 모른다.⊙")
b=datak[begin:end]
print(b)

mydict={}
b=b.split()
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
