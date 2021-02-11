## Kubernetes Tips

- Ingress 외부 노출
- CRD 생성

### Ingress 외부 노출

- Ingress는 pod를 외부로 노출하기 위해 따로 TCP를 지원하지 않기 때문에, ingress-nginx 라는 Controller가 필요하다

  - 깃허브 (https://github.com/kubernetes/ingress-nginx)
  - 공식문서 (https://kubernetes.io/docs/concepts/services-networking/ingress/)

- Ingress Controller는 tcp-services 라는 ConfigMap을 수정해 `외부 노출할 포트`와 `서비스`를 설정할 수 있다.

- 수정 방법

  - ```
    > kubectl edit configmap tcp-services -n ingress-nginx
    ```

  - ```
    apiVersion: v1
    kind: ConfigMap
    metadata:
      name: tcp-services
      namespace: ingress-nginx
    data:
      5044: "default/test-svc:5044"
    ```

  - 아래 data: 영역 부분에 `<ingress_expose_port>: "<namespace>/<service_name>:<service_port>"` 를 기재한다.

  - 이후 Ingress Node로 5044 접근시 정상적으로 접근이 되는것을 볼수 있다.

### CRD 생성

- 참고링크 (https://blog.naver.com/alice_k106/221579974362)