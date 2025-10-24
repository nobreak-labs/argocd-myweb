# Kustomize MyWeb

Kustomize를 사용하여 myweb 애플리케이션을 Kubernetes에 배포하기 위한 매니페스트입니다.

## 애플리케이션 정보

- **컨테이너 이미지**: ghcr.io/nobreak-labs/go-myweb
- **사용 가능한 태그**: v1.0, v2.0, v3.0, v4.0
- **레플리카 수**: 3
- **서비스 포트**: 80 → 8080

## 배포 방법

### Kustomize로 직접 배포
```bash
kubectl apply -k .
```

### ArgoCD를 통한 배포
```bash
argocd app create myweb \
  --repo https://github.com/nobreak-labs/argocd-myweb.git \
  --path kustomize-myweb \
  --dest-server https://kubernetes.default.svc \
  --dest-namespace default
```
