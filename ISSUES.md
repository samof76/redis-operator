# Issue Found in Repo

1. As documented in the README the following command does not work.

    ```bash
    ❯ kustomize build "github.com/freshworks/redis-operator/manifests/kustomize/overlays/default?ref=v3.3.2"
    Error: accumulating resources: accumulateFile "accumulating resources from '../minimal/': '/tmp/kustomize-185940947/manifests/kustomize/overlays/minimal' must resolve to a file", accumulateDirector: "recursed accumulation of path '/tmp/kustomize-185940947/manifests/kustomize/overlays/minimal': accumulating components: accumulateDirectory: \"couldn't make target for path '/tmp/kustomize-185940947/manifests/kustomize/components/version': json: unknown field \\\"labels\\\"\""
    ```

2. Deploying redis-operator using the kubectl as mentions in README fails

    ```bash
    ❯ kubectl apply -f https://raw.githubusercontent.com/freshworks/redis-operator/v3.3.2/example/operator/all-redis-operator-resources.yaml
    deployment.apps/redisoperator created
    clusterrolebinding.rbac.authorization.k8s.io/redisoperator created
    clusterrole.rbac.authorization.k8s.io/redisoperator created
    serviceaccount/redisoperator created
    service/redisoperator created
    resource mapping not found for name: "redis-operator-metrics" namespace: "" from "https://raw.githubusercontent.com/freshworks/redis-operator/v3.3.2/example/operator/all-redis-operator-resources.yaml": no matches for kind "ServiceMonitor" in version "monitoring.coreos.com/v1"
    ensure CRDs are installed first
    resource mapping not found for name: "redisoperator" namespace: "" from "https://raw.githubusercontent.com/freshworks/redis-operator/v3.3.2/example/operator/all-redis-operator-resources.yaml": no matches for kind "PodMonitor" in version "monitoring.coreos.com/v1"
    ensure CRDs are installed first
    ```

