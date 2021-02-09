# Helm

- Helm은 Helm Chart를 쿠버네티스에 배포를 관리하기 위한 프로그램

  

### Helm Chart란?

- Helm Chart는 쿠버네티스 소프트웨어의 패키지이다.
  - Chart 내 쿠버네티스 서비스 들이 저장된다. (인그레스, 서비스, 디폴로이먼트, 레플리카 셋 등)
  - 위 서비스들을 Helm Chart로 만들어 쿠버네티스에 배포 / 관리할수 있다.

- 튜토리얼 
  
  - Helm 공식문서 (https://helm.sh/docs/intro/quickstart/)
    - Helm을 간단하게 따라해볼수 있다.
  - Katacoda (https://www.katacoda.com/courses/kubernetes/helm-package-manager)
    - 기본 실습을 해볼수 있다.
  - 참고링크
    - https://tech.osci.kr/2019/11/23/86027123/ (헬름 차트를 이용한 쿠버네티스 배포/관리)
    - https://spoqa.github.io/2020/03/30/k8s-with-helm-chart.html (스포카에서 Helm을 도입하는 이야기)
  
- 주요 명령어

  - helm list (릴리즈된 차트들 조회)
  - helm install (차트를 쿠버네티스에 설치)
  - helm upgrade (쿠버테니스에 설치된 차트를 업데이트하기 위함)
  - helm uninstall (차트를 쿠버네티스에서 삭제)
  - helm template (환경별로 달리 설정하고 싶을때)
    - 환경별로 분리하고 싶은 값들은 {{ .. }} 형태로 들어가 있음
      - 여러 종류의 value.yaml을 관리하여 환경별로 분리할수 있다.
    - 아니면, 이는 `helm template --set key=value` 로 값을 바꾸어 배포할수도 있다.
  - helm rollback (기존 버전으로 돌아갈때)
  - helm history (지금까지 버전 기록들)

  

