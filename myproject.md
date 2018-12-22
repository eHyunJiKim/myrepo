##매년 강력범죄가 증가하는 추세인데, 증가하는 강력범죄와 관련하여 최근 사회적으로 이슈가 되고 있는 소년강력범죄와 정신감정의 관계, 강력범죄의 특성을 가진 묻지마 범죄의 특성과 원인에 대해 알아보았다. 
#강력범죄의 증가 
print("<강력범죄 발생 현황>")
import pandas as pd
data=pd.read_excel('복사본Report.xls')
print(data.loc[[1,2,3,4,5,6,7,8,9,10,11],['기간','강력범']]
print("분석 : 매년 강력범죄가 증가하는 추세이다.")

#소년 범죄자들이 최근 정신감정을 통해 심신미약을 주장하려는 사례가 늘어가고 있다. 
#소년범죄자 범행시 정신상태
import openpyxl
data=openpyxl.load_workbook('data.xlsx')
sheet=data['데이터']
cells=sheet['J14': 'J18']
disorder_total=dict()
for row in cells:
    for cell in row:
        discorder_total[sheet.cell(cell.row,3).value]=cell.value
print("강력범죄(흉악) 범죄 시 정신장애")
print(disorder_total)

print("분석 : 강력범죄를 저지르는 소년범죄자들이 정신장애와 연관이 많은 것으로 보아, 소년범죄자들이 범행 당시 정신장애가 있었음을 주장하며 정신감정을 요구하는 경우가 많이 발생하고 있다는 사실을 알 수 있다.")


#정신감정의 의뢰 : 문제점
import requests
r=requests.get("http://news.heraldcorp.com/view.php?ud=20181128000429")
r.encoding='utf8'
data=str(r.text)
begin=data.find("실제로 현행 형법에 따르면")
end=data.rfind('이에 대한 반대 여론이 최근 거세진 것으로 보인다."고 설명했다.')
a=data[begin:end+1]
print(a)



#최근 지속적으로 발생하고 있는 묻지마 범죄의 특성
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
    print("사회 : 묻지마 범죄는 범죄자의 은둔형 성향과 그의 사회적 환경과 연관이 깊다.") 
if "관계" in mydict:
    print("관계: 묻지마 범죄는 범죄자의 은둔형 성향과 그의 사회적 환경과 연관이 깊다.")
if "환경" in mydict:
    print("환경 :  묻지마 범죄는 범죄자의 은둔형 성향과 그의 사회적 환경과 연관이 깊다.")
if "외톨" in mydict:
    print("외톨 : 묻지마 범죄는 범죄자의 은둔형 성향과 그의 사회적 환경과 연관이 깊다.")
if "성향" in mydict:
    print("성향: 묻지마 범죄는 범죄자의 은둔형 성향과 그의 사회적 환경과 연관이 깊다.")
    
if"사회" in mydict:
    print("사회: 묻지마 범죄는 범죄자의 은둔형 성향과 그의 사회적 환경과 연관이 깊다.") 
if "관계" in mydict:
    print("관계 :  묻지마 범죄는 범죄자의 은둔형 성향과 그의 사회적 환경과 연관이 깊다.")
if "환경" in mydict:
    print("환경 :  묻지마 범죄는 범죄자의 은둔형 성향과 그의 사회적 환경과 연관이 깊다.")
if "외톨" in mydict:
    print("외톨 :  묻지마 범죄는 범죄자의 은둔형 성향과 그의 사회적 환경과 연관이 깊다.")
if "성향" in mydict:
    print("성향 :  묻지마 범죄는 범죄자의 은둔형 성향과 그의 사회적 환경과 연관이 깊다.")
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

if "흉기를" in mydict:
    print("흉기 : 묻지마 범죄는 강력 범죄와 연관이 깊다.")
if "‘은둔형" in mydict:
    print("은둔형: 묻지마 범죄자는 은둔형 성향을 가지고 있으며 이로 부터 느낀 고립감을 사회에 분노로  표출하려고 하는 경향이 있다.")
if "고립" in mydict:
    
    print("고립 : 묻지마 범죄자는 은둔형 성향을 가지고 있으며 이로 부터 느낀 고립감을 사회에 분노로  표출하려고 하는 경향이 있다.")
if "분노" in mydict:
    print("분노: 묻지마 범죄자는 은둔형 성향을 가지고 있으며 이로 부터 느낀 고립감을 사회에 분노로  표출하려고 하는 경향이 있다.")

          
#묻지마 범죄자의 원인
#IMF  가정해체
import requests
r=requests.get('http://news.chosun.com/site/data/html_dir/2009/07/25/2009072500040.html')
r.encoding='utf8'
data=str(r.text)
print("(원인)")
begin=data.find("IMF 경제위기 등을 겪으면서")
end=data.rfind("새로운 가족 형태가 늘어난 것이다.")
a=data[begin:end+27]
print(a)

