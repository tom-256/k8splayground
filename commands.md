```
$kubectl rollout history deployment echo
$kubectl rollout history deployment echo --revision=1
$kubectl rollout undo deployment echo
#Podのログを見る
$kubectl log -f echo-summer-8z75d -c echo
```
