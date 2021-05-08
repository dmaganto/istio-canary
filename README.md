# istio-canary
istio-canary-deployment using custom helm chart

## Canary Deploy 
```
helm upgrade myapp ./ -f values.yaml --install --wait --atomic
helm upgrade myapp ./ -f values.yaml --install --wait --atomic --set Canary.enabled=true,Canary.tag=1.8
helm upgrade myapp ./ -f values.yaml --install --wait --atomic --set Canary.enabled=true,Canary.weight=10,Canary.tag=1.8,Production.weight=90
helm upgrade myapp ./ -f values.yaml --install --wait --atomic --set Canary.enabled=true,Canary.weight=40,Canary.tag=1.8,Production.weight=60
helm upgrade myapp ./ -f values.yaml --install --wait --atomic --set Canary.enabled=true,Canary.weight=70,Canary.tag=1.8,Production.weight=30
helm upgrade myapp ./ -f values.yaml --install --wait --atomic --set Canary.enabled=true,Canary.weight=100,Canary.tag=1.8,Production.weight=0
helm upgrade myapp ./ -f values.yaml --install --wait --atomic --set Canary.enabled=true,Canary.weight=100,Canary.tag=1.8,Production.tag=1.8,Production.weight=0
helm upgrade myapp ./ -f values.yaml --install --wait --atomic --set Production.tag=1.8
```

