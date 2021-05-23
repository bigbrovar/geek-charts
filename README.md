## Welcome to bigbrovar Lidarr  Helm Catalog

This Helm installs the latest lidarr service on an Arm64 based kubernetes cluster

- helm repo add  lidarr https://bigbrovar.github.io/lidarr-charts/



helmfile sample :

    repositories:
      - name: lidarr
        url:  https://bigbrovar.github.io/lidarr-charts/

    releases:
      - name: lidarr-charts 
        namespace: media
        chart: bigbrovar/lidarr-charts
        version: 0.1.0
        values:
             - image:
                 tag: arm64v8-latest
             - ingress:
                enabled: true
                hosts:
                  - lidarr.local
