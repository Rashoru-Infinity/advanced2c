# advanced2c
pNNx(感情の快不快を表す)の値をInfluxDBに集めてGrafanaでグラフを表示します。  
GrafanaではpNNxの低下を検知したときと低下した状態から回復したときにSlackへの通知を行います  
通知は数分の時差が生じることがあります  

# 実行/停止
実行
```
docker-compose up -d
```
停止
```
docker-compose down
```

# Grafana
![localhost_3000_d_gE74tRAnz_pnn-monitor_orgId=1 from=now-5m to=now](https://user-images.githubusercontent.com/49583698/147467214-ca92d463-23b0-431d-85a2-7270a9699833.png)
![localhost_3000_d_gE74tRAnz_pnn-monitor_orgId=1 from=now-5m to=now (1)](https://user-images.githubusercontent.com/49583698/147468305-9fd84240-b48f-4742-b742-b44e4ee6d47f.png)
pNNの値の推移をGrafanaで確認することができます  
pNNの値が閾値をしばらく下回るとグラフのタイトル付近のハートの色が緑から赤に変わり、Slackに通知が飛びます  
タイトル付近のハートが赤の状態から緑に戻ると数分後に再度Slackに通知が飛びます  

# Slack
![image](https://user-images.githubusercontent.com/49583698/147468376-5e2c90e7-851f-4bf5-94ee-673d3ba2faab.png)
デフォルトのデータベースを使用するとRashoru-InfinityのSlackのワークスペースのgeneralに通知が飛ぶので注意してください  
GrafanaにログインしてContact pointsの項目を修正することでSlackのワークスペースとチャンネルを変更できます  
