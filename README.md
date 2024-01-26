# K8s 공부 로드맵
``` json
{
  "KubernetesRoadmap": [
    {
      "Phase": "기초 이해",
      "Topics": [
        "컨테이너 기술",
        "도커(Docker) 기초",
        "쿠버네티스 소개",
        "쿠버네티스 아키텍처"
      ],
      "Resources": [
        {"Type": "Book", "Title": "Kubernetes in Action", "Author": "Marko Luksa"},
        {"Type": "Online Course", "Title": "Getting Started with Kubernetes", "Platform": "Pluralsight"}
      ]
    },
    {
      "Phase": "기본 사용법",
      "Topics": [
        "kubectl 명령어 사용법",
        "Pod, ReplicaSet, Deployment 이해",
        "Service 및 Ingress 설정",
        "ConfigMap 및 Secret 활용"
      ],
      "Resources": [
        {"Type": "Documentation", "Title": "Kubernetes Official Documentation", "URL": "https://kubernetes.io/docs/"},
        {"Type": "Online Course", "Title": "Kubernetes Basics", "Platform": "Coursera"}
      ]
    },
    {
      "Phase": "고급 주제",
      "Topics": [
        "StatefulSet 및 DaemonSet",
        "쿠버네티스 네트워킹",
        "헬름 차트(Helm Charts)",
        "오토스케일링 및 HPA"
      ],
      "Resources": [
        {"Type": "Blog", "Title": "Kubernetes Best Practices", "Author": "Kelsey Hightower"},
        {"Type": "Online Course", "Title": "Advanced Kubernetes Concepts", "Platform": "Udacity"}
      ]
    },
    {
      "Phase": "운영 및 관리",
      "Topics": [
        "로그 및 모니터링",
        "보안 및 RBAC",
        "클러스터 업그레이드",
        "CI/CD 파이프라인 통합"
      ],
      "Resources": [
        {"Type": "Book", "Title": "The Kubernetes Book", "Author": "Nigel Poulton"},
        {"Type": "Documentation", "Title": "Kubernetes Operations", "URL": "https://github.com/tonybai-com/k8s-ops"}
      ]
    }
  ]
}
```