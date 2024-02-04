# Readme.md

## Passos para criar um helm-chart público

- Criar repositório e fazer o clone
- Criar o arquivo robotx.txt para evitar bot no repositório
```bash
echo -e "User-Agent: *\nDisallow: /"> robots.txt
```
- Criar o chart
```bash
helm create flask-to-learn-containers
```
- Fazer o lint
```bash
helm lint flask-to-learn-containers 
```
- Criar seus templates e configurações do chart
- Criar pacote do helm chart
```bash
helm package flask-to-learn-containers
```
- Criar arquivo de index.yaml para listar todos os pacotes do repositório
```bash
helm repo index --url https://robertsilvatech.github.io/helm-charts
```

