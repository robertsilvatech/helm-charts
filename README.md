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
helm repo index --url https://robertsilvatech.github.io/helm-charts .
```
- Enviar alterações pro repositório remoto
- Configurar GitHub Pages
    - Acesso o repositório > Settings > Source: Escolha a branch
    - O endereço vai ser:
      - https://robertsilvatech.github.io/helm-charts/

## Trabalhando com seu repositório público


Adicionando o repositório
```bash
helm repo add robertsilvatech https://robertsilvatech.github.io/helm-charts
```

Buscando charts
```bash
helm search repo flask-to-learn
```
Output
```bash
NAME                                            CHART VERSION   APP VERSION     DESCRIPTION                               
robertsilvatech/flask-to-learn-containers       0.1.0           1.0.0           A Helm chart for Learn Kubernetes and Helm
```

## Adicionando novos charts

Para adicionar novos charts no repositório existente use
```bash
helm repo index --url https://robertsilvatech.github.io/helm-charts --merge index.yaml .
```
