# 매니패스트 파일
매니페스트란 쿠버네티스의 오브젝트를 생성하기 위한 메타 정보를 YAML이나 JSON으로 기술한 파일이다. 실제 파드를 단독으로 기동하는 매니페스트를 작성하는 경우는 많지 않다. 보통 컨트롤러에 대한 매니페스트를 작성하는데 이때 파드에 대한 정보를 기술하는 부분이 포함된다.


## 대표적인 쿠버네티스의 오브젝트들의 마니패스트 파일

### 디플로이멘트
```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: <이름>
  namespace: <네임스페이스 이름>
spec:
  selector:
    matchLabels:
      <라벤>: <라벨>
  replicas: 2
  template:
    metadata:
      labels:
        <라벤>: <라벨>
    spec:
      containers:
      - name: <컨테이너 이름 주기>
        image: <컨테이너 ECR URL>
        ports:
        - containerPort: <포트번호>
        resources:
          limits:
            cpu: 500m
          requests:
            cpu: 200m
```

### 서비스
```
apiVersion: v1
kind: Service

metadata:
  name: <이름>
  namespace: <네임스페이스 이름>
spec:
  selector:
    <디플로이멘트 라벨>
  ports:
  - port: <ALB 포트>
    targetPort: <앱 포트>
    protocol: TCP
  type: NodePort
```

### 인그레스
```
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: <NAME>
  namespace: <NAMESPACE>
  annotations:
    alb.ingress.kubernetes.io/load-balancer-name: <LOADBALANCER-NAME>
    alb.ingress.kubernetes.io/scheme: # internet-facing // internal
    alb.ingress.kubernetes.io/target-type: # instance // ip
    alb.ingress.kubernetes.io/healthcheck-path: /health
    alb.ingress.kubernetes.io/target-node-labels: # node label
spec:
  ingressClassName: alb
  rules:
  - http:
      paths:
      - path: /
        pathType: Prefix
        backend:
          service:
            name: <SERVICE-NAME>
            port:
              number: 80
```