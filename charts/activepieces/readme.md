## Install

### Add the helmchart repository

Add the helmchart repository with the following command:

```bash
helm repo add meyercharts https://mariomeyer.github.io/repo
```

### Customize the values you want for your helm install

Copy the following default values to a local `values.yaml` file:

```yaml
# Default values for activepieces.
# This is a YAML-formatted file.
# Declare variables to be passed into your templates.

replicaCount: 1

image:
  repository: docker.io/activepieces/activepieces
  pullPolicy: IfNotPresent
  # Overrides the image tag whose default is the chart appVersion.
  tag: 'latest'

imagePullSecrets: []
nameOverride: ''
fullnameOverride: ''

serviceAccount:
  # Specifies whether a service account should be created
  create: true
  # Automatically mount a ServiceAccount's API credentials?
  automount: true
  # Annotations to add to the service account
  annotations: {}
  # The name of the service account to use.
  # If not set and create is true, a name is generated using the fullname template
  name: ''

podAnnotations: {}
podLabels: {}

podSecurityContext:
  {}
  # fsGroup: 2000

securityContext:
  {}
  # capabilities:
  #   drop:
  #   - ALL
  # readOnlyRootFilesystem: true
  # runAsNonRoot: true
  # runAsUser: 1000

service:
  type: ClusterIP
  port: 80
  host: activepieces.local

queue:
  mode: MEMORY
  #mode: REDIS
  #url:
  #ui:
  #  enabled: true
  #  username:
  #  password:

# ngrok credentials
#ngrok:
#  domain:

db:
  type: SQLITE3
  #type: POSTGRES
  #host: <host>
  #port: 5432
  #username: <username>
  #password: <password>
  #database: <database>
  #ssl:
  #  enabled: true
  #  certificate:|
  #    -----BEGIN CERTIFICATE-----
  #    ...
  #    -----END CERTIFICATE-----

ingress:
  enabled: false
#  className: 'nginx'
#  annotations:
#    {}
    # kubernetes.io/ingress.class: nginx
    # kubernetes.io/tls-acme: "true"
#  hosts:
  #  - host:
  #    paths:
  #      - path: /
  #        pathType: Prefix
#  tls: []
  #  - secretName: chart-example-tls
  #    hosts:
  #      - chart-example.local

resources:
  {}
  # We usually recommend not to specify default resources and to leave this as a conscious
  # choice for the user. This also increases chances charts run on environments with little
  # resources, such as Minikube. If you do want to specify resources, uncomment the following
  # lines, adjust them as necessary, and remove the curly braces after 'resources:'.
  # limits:
  #   cpu: 100m
  #   memory: 128Mi
  # requests:
  #   cpu: 100m
  #   memory: 128Mi

autoscaling:
  enabled: false
  minReplicas: 1
  maxReplicas: 100
  targetCPUUtilizationPercentage: 80
  # targetMemoryUtilizationPercentage: 80

# Additional volumes on the output Deployment definition.
volumes: []
# - name: foo
#   secret:
#     secretName: mysecret
#     optional: false

# Additional volumeMounts on the output Deployment definition.
volumeMounts: []
# - name: foo
#   mountPath: "/etc/foo"
#   readOnly: true

nodeSelector: {}

tolerations: []

affinity: {}
```

### Apply the chart

Run the following command to apply the chart in your Kuberentes cluster:

```bash
helm install -f values.yaml activepieces meyercharts/activepieces
```

## Upgrade

Please follow the steps below:

### Reconfigure values.yaml

Do any changes on your `values.yaml` file with the desired configuration changes. You can also change the tag from `latest` to any version you'd like to upgrade to.

### Upgrade

```bash
helm upgrade -f values.yaml activepieces meyercharts/activepieces -n default
```

Congratulations! You have successfully upgraded your Activepieces helm deployment
