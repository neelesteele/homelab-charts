## Welcome to Neele Steele's Super Awesome Helm Catalog

- helm repo add neelesteele https://neelesteele.github.io/homelab-charts

helmfile sample :

    repositories:
      - name: neelesteele
        url: https://neelesteele.github.io/geek-charts

    releases:
      - name: radarr
        namespace: media
        chart: neelesteele/radarr
        version: 6.6.6
        values:
             - image:
                 tag: latest
             - ingress:
                enabled: true
                hosts:
                  - radarr.bangyour.mom
                tls:
                  - hosts:
                      - radar.bangyour.mom
                    secretName: radarr-bangedyour.mom
