#주로 강려범죄와 연관성이 깊은 묻지마 범죄는 최근 3년간 매년 54~55건이 지속적으로 발생하여 국민 불안을 야기 
print("<강력범죄 발생 현황>")
import pandas as pd
new_df2= pd.read_excel('복사본Report.xlsx')
print(type(new_df2))
print(new_df2.head())





print("<묻지마 범죄와 연관된 단어>")
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
a=a.replace('한',' ') ;a=a.replace('그는', ' ') ; a=a.replace('&nbsp;<br/>',' ') ;a=a.replace('<div',' ')
a=a.replace('<br/>', ' ') ; a=a.replace("다",' ') ; a=a.replace("교", ' ') ; a=a.replace("것",' ') ; a=a.replace("묻지마",' ') ; a=a.replace("적", ' ') ; a=a.replace("런", ' ') ; a=a.replace("고", ' ')  
a=a.replace('"', ' ') ; a=a.replace('는', ' ') ; a=a.replace('있',' ')
a=a.replace('인',' ') ; a=a.replace('그',' ') ; a=a.replace('&nbsp;',' ')
a=a.replace('나',' ') ; a=a.replace('class=',' ') ; a=a.replace('요',' ') ; a=a.replace('>',' ') ; a=a.replace('살',' ') ; a=a.replace('보',' ') ; a=a.replace('없',' ') ; a=a.replace("'",' ') ; a=a.replace('를',' ')
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
        if i>20:
            break

print("(분석)")        
if "조현병" in mydict:
    print("조현병: 묻지마 범죄는 조현병이라는 정신병과 연관이 깊다.")
if "사회""관계" "환경""외톨""성향" in mydict:
    print("사회, 관계, 환경, 외톨이, 성향: 묻지마 범죄는 범죄자의 은둔형 성향과 그의 사회적 환경과 연관이 깊다.") 
        
print("----------------")
        
        
import requests
r=requests.get('http://monthly.chosun.com/client/news/viw.asp?ctcd=C&nNewsNumb=200812100052&page=26')
data=str(r.text)
begin=data.find("지난 10월 20일 아침 8시15분.")
end=data.rfind("언제 터질지 모른다.⊙")
b=data[begin:end]
b=b.replace("<br>&nbsp;",' ') ; b=b.replace("<b><font",' ') ;b=b.replace("세",' ')
b=b.replace("살인",' ') ;b=b.replace("‘묻지마",' ')
b=b.replace("'", ' ') ; b=b.replace("한", ' ' ) ;b=b.replace("뒤",' ') ; b=b.replace("한다.",' ') ;b=b.replace("있다.",' ') ; b=b.replace("그",' ') ; b=b.replace("피의자",' ') ; b=b.replace("고시원",' ') ; b=b.replace("있는", ' ') ;b=b.replace("지난", ' ') ; b=b.replace("자신의",' ') ; b=b.replace("사건",' ') ;b=b.replace("사건의", ' ') ; b=b.replace("없는", ' ') ; b=b.replace("범행을", ' ') ; b=b.replace("따르면", ' ') ;b=b.replace("이렇게",' ') ;b=b.replace("뒤",' ')
b=b.replace("이런",' ') ; b=b.replace("저지른", ' ') ; b=b.replace("것으로", ' ') ; b=b.replace("대한", ' ') ; b=b.replace("범행", ' ') ; b=b.replace("묻지마", ' ') ; b=b.replace("범죄를", ' ') ; b=b.replace('묻지마',' ') ; b=b.replace("일본의", ' ') ; b=b.replace("논현동", ' ')
b=b.replace("<br><table",' ') ; b=b.replace('border="0"',' ') ; b=b.replace('cellspacing="0"',' ')
b=b.replace('cellpadding="0"',' ') ; b=b.replace('style="margin-top:3px;margin-bottom:23px;',' ')
b=b.replace('class="border"></td></tr><tr><td',' ')
b=b.replace('style="padding-top:5px;',' ')
b=b.replace("padding-left:5px;", ' ')
b=b.replace('padding-right:5px;"><font',' ')
b=b.replace('color="#2F73BA"',' ')

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
print("(분석)")
if "사이코" in mydict:
    print("사이코 : 묻지마 범죄는 정신적인 문제와 연관이 깊다.")

if "흉기를, 흉기에"  in mydict:
    print("흉기 : 묻지마 범죄는 강력 범죄와 연관이 깊다.")
if "‘은둔형, 고립된, 분노를" in mydict:
    print("은둔형, 고립, 분노 : 묻지마 범죄자는 은둔형 성향을 가지고 있으며 이로 부터 느낀 고립감을 사회에 분노로  표출하려고 하는 경향이 있다.")

#묻지마 범죄자의 원인
#IMF  가정해체
import requests
r=requests.get('http://news.chosun.com/site/data/html_dir/2009/07/25/2009072500040.html')
r.encoding='utf8'
data=str(r.text)
print("(원인)")
begin=data.find("IMF 경제위기 등을 겪으면서")
end=data.rfind("새로운 가족 형태가 늘어난 것이다.")
a=data[begin:end+30]
print(a)

