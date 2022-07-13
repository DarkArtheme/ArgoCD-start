# Как развернуть dev ArgoCD

1. Установка.
```
$ helm upgrade --install -n argocd argocd argo/argo-cd --set server.ingress.enabled=true
```

2. Добавляем флаг `--insecure` в раздел флагов сервера.
```
$ kubectl --namespace argocd edit deployment argocd-server
```

3. Прокидываем порт.
```
$ kubectl port-forward service/argocd-server -n argocd 8080:443
```

