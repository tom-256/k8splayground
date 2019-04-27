```
$kubectl rollout history deployment echo
$kubectl rollout history deployment echo --revision=1
$kubectl rollout undo deployment echo
#Podのログを見る
$kubectl log -f echo-summer-8z75d -c echo
```

k8sクラスタ内のDNSではService.Namespace.svc.localで名前解決する
```
#省略なし
$curl http://echo.default.svc.local
#異なるNamespace
$curl http://echo.default
#同一Namespace
$curl http://echo
```