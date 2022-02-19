# www.camel-k.com



### Install Camel-K
See the Apache Camel K installation page for details: (https://camel.apache.org/camel-k/next/installation/installation.html).

```shell
minikube start
minikube addons enable registry
minikube start --addons registry
kamel install
```

### Install Karavan
```shell
kubectl apply -k karavan -n default
```

### Open Karavan
Get Karavan URL
```shell
minikube service karavan --url
```
Result should be like
```shell
Tunnel for service camel-karavan:
|-----------|---------------|-------------|------------------------|
| NAMESPACE |     NAME      | TARGET PORT |          URL           |
|-----------|---------------|-------------|------------------------|
| default   | camel-karavan |             | http://127.0.0.1:60708 |
|-----------|---------------|-------------|------------------------|
```
Open url `http://127.0.0.1:60708` in browser


## Security

[4ndersonLin/awesome-cloud-security: 🛡️ Awesome Cloud Security Resources ⚔️](https://github.com/4ndersonLin/awesome-cloud-security)

> # [](https://github.com/4ndersonLin/awesome-cloud-security#contents)Contents
> 
> -   [Standards](https://github.com/4ndersonLin/awesome-cloud-security#standards)
> -   [Tools](https://github.com/4ndersonLin/awesome-cloud-security#tools)
> -   [Reading materials](https://github.com/4ndersonLin/awesome-cloud-security#reading-materials)
> -   [Resource](https://github.com/4ndersonLin/awesome-cloud-security#resource)
> -   [Contributing](https://github.com/4ndersonLin/awesome-cloud-security#contributing)
> 
> # Standards
> 
> -   [Compliances](https://github.com/4ndersonLin/awesome-cloud-security#compliances)
> -   [Benchmarks](https://github.com/4ndersonLin/awesome-cloud-security#benchmarks)
> 
> ## Compliances
> 
> -   [CSA STAR](https://cloudsecurityalliance.org/star/)
> -   [ISO/IEC 27017:2015](https://www.iso.org/standard/43757.html)
> -   [ISO/IEC 27018:2019](https://www.iso.org/standard/76559.html)
> -   [MTCS SS 584](https://www.imda.gov.sg/regulations-and-licensing-listing/ict-standards-and-quality-of-service/IT-Standards-and-Frameworks/ComplianceAndCertification)
> 
> ## Benchmarks
> 
> -   [CIS Benchmark](https://www.cisecurity.org/cis-benchmarks/)
> 
> # Tools
> 
> -   [Infrastrcture](https://github.com/4ndersonLin/awesome-cloud-security#infrastrcture)
> -   [Container](https://github.com/4ndersonLin/awesome-cloud-security#container)
> -   [SaaS](https://github.com/4ndersonLin/awesome-cloud-security#saas)
> -   [Penetration testing/leaerning](https://github.com/4ndersonLin/awesome-cloud-security#penetration-testingleaerning)
> -   [Native tools](https://github.com/4ndersonLin/awesome-cloud-security#nativetools)
