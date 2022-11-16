# web/python_termproject
from google.colab import files
myfile = files.upload()
# PL_result.csv upload

import pandas as pd

data = pd.read_csv("PL_result.csv",encoding='windows-1254')

# 홈팀과 어웨이팀 이름 알려주는 것 (복사해서 붙여 넣어주세요)
a = 1
b = 0
Team_List = ["Liverpool","Arsenal","Coventry","Aston Villa","QPR","Chelsea","Blackburn","Sheffield Weds","Man City","Oldham","Sheffield United","Newcastle","Leeds","Southampton","Everton","West Ham","Wimbledon","Norwich","Man United","Tottenham","Ipswich","Swindon","Crystal Palace","Nott'm Forest","Leicester","Middlesbrough","Bolton","Derby","Sunderland","Barnsley","Charlton","Bradford","Watford","Fulham"]
for c in Team_List :
  print("(",a,")"," : ", Team_List[b])
  a = a+1
  b = b+1
  
# 홈팀과 어웨이팀의 승패 (*위의 팀 알림이에서 복사해서 붙여 넣어주세요*)
home_Team = input("Home Team : ")
away_Team = input("Away Team : ")
print("Selected team(Home : Away) : " + home_Team + " : " + away_Team)

preResult = pd.concat([data[data['HomeTeam']==home_Team], data[data['AwayTeam']==home_Team]]).sort_index()
result = pd.concat([preResult[preResult['AwayTeam']==away_Team]]).sort_index()
result
