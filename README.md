## Welcome to bigbrovar Lidarr  Helm Catalog

This Helm installs the latest Ladarr service on an Arm64 based kubernetes cluster

- helm repo add  ladarr https://bigbrovar.github.io/ladarr-charts/



helmfile sample :

    repositories:
      - name: ladarr
        url:  https://bigbrovar.github.io/ladarr-charts/

    releases:
      - name: ladarr-charts 
        namespace: media
        chart: bigbrovar/ladarr-charts
        version: 0.1.0
        values:
             - image:
                 tag: arm64v8-latest
             - ingress:
                enabled: true
                hosts:
                  - ladarr.local
