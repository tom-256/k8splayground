```
$kubectl rollout history deployment echo
$kubectl rollout history deployment echo --revision=1
$kubectl rollout undo deployment echo
#Podのログを見る
$kubectl log -f echo-summer-8z75d -c echo
#コンテナに入る
$kubectl get pod
$kubectl exec -it PODNAME bash
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

コンテキストの切り替え
```
$kubectl config get-contexts
$kubectl cofnig use-context <CONTEXT_NAME>
```

```
#ServiceAccountの作成
$kubectl create sa <USERNAME>
#secretの確認(secrets)
$kubectl get sa <USERNAME> -o yaml
#トークンの取り出し(data.token)
$kubectl get secret <USERNAME> -o yaml
#認証情報の設定
$kubectl config set-credentials <USERNAME> --token=XXX
```


- terminationGracePeriodSeconds
終了処理に時間のかかるアプリケーションは長めに取っておく
- lifecycle.preStop
シャットダウンコマンドがあるものは前処理で実行する
