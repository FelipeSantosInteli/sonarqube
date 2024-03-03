# Relatório sobre Análise de Código com SonarQube em Projetos .NET

https://developer.okta.com/blog/2021/09/08/sonar-qube-dotnet#analysis-results-in-sonarqube

O artigo publicado no blog da Okta se concentra no uso do SonarQube em projetos .NET, esse que é uma plataforma de código aberto usada para avaliar a qualidade do código fonte, sendo uma estrutura de desenvolvimento de software amplamente utilizada para construir aplicativos web e desktop usando linguagens como C# e VB.NET. O SonarQube é integrado ao processo de desenvolvimento .NET para fornecer análises detalhadas e relatórios sobre a qualidade do código, incluindo detecção de código duplicado, vulnerabilidades de segurança, bugs potenciais e conformidade com padrões de codificação.

## Conceitos Aprendidos

1. **Configuração do SonarQube em Projetos .NET**: O artigo orienta sobre como configurar o SonarQube para analisar projetos .NET, incluindo a instalação do SonarScanner e a configuração do arquivo de propriedades do projeto.

2. **Execução da Análise de Código**: São abordados também os passos necessários para executar uma análise de código usando o SonarScanner, tanto a geração de relatórios, quantp a visualização dos resultados no painel do SonarQube.

3. **Interpretação dos Resultados**: É explorado sobre como interpretar os resultados da análise de código no SonarQube, incluindo a identificação de áreas problemáticas, como código duplicado, vulnerabilidades de segurança e violações de padrões de codificação.

4. **Melhoria da Qualidade do Código**: O artigo indica também estratégias para melhorar a qualidade do código com base nos insights fornecidos pelo SonarQube, como refatoração de código, correção de bugs e adoção de melhores práticas de codificação.

<img alt="sonarqube" src="./assets/Captura de tela 1.png">


Essa imagem mostra o painel do SonarQube com informações gerais, como contadores de bugs, vulnerabilidades e problemas de código, ou o número de duplicações de código, em uma visualização mais simples com métricas diretas.

Também é possível ver métricas e análises mais detalhadas na aba "Measures"

<img alt="sonarqube" src="./assets/Captura de tela 2.png">

<img alt="sonarqube" src="./assets/Captura de tela 3.png">


A aba "Issues" permite se aprofundar melhor na análise do código-fonte. O SonarQube relata todos os possíveis problemas, desde questões menores até bugs críticos. É possível explorar cada problema no código a ser considerado, juntamente com uma explicação do problema e uma estimativa de tempo para resolvê-lo.

<img alt="sonarqube" src="./assets/Captura de tela 4.png">

# SampleApp-SonarQube

# Analyze Your Code Using SonarQube, Docker and .NET Core

This app is an example app for learning how to use SonarQube on your projects. For more details please read [Analyze Your Code Using SonarQube, Docker and .NET Core](link_to_replace) to see a detailed instruction on how to do that.

**Prerequisites:**

- [Java 11](https://adoptopenjdk.net/)+
- [Docker](https://docs.docker.com/get-docker/)
- [.NET Core](https://dotnet.microsoft.com/download)
- [SonarScanner for .NET Core](https://github.com/SonarSource/sonar-scanner-msbuild/releases/download/4.7.1.2311/sonar-scanner-msbuild-4.7.1.2311-netcoreapp2.0.zip)

**Table of Contents**

- [Getting Started](#getting-started)
- [Help](#help)
- [License](#license)

## Getting Started

Begin with running SonarQube on Docker:
```sh
docker run -d --name sonarqube -p 9000:9000 -p 9092:9092 sonarqube
```

**NOTE:** You'll be able to login with `admin/admin`. After first login, you will be promted to change the default credentials.

In order to run SonarScanner, run the following commands:

```sh
dotnet sonarscanner begin /k:"project-key" /d:sonar.login=admin /d:sonar.password=admin
dotnet build <path_to_solution.sln>
dotnet sonarscanner end /d:sonar.login=admin /d:sonar.password=admin
```

> **NOTE:** Remember to replace "path_to_solution" and "password" with correct ones for your example.

## Help

Please post any questions as comments on the [blog post](link_to_replace), or visit our [Okta Developer Forums](https://devforum.okta.com/). You can also ask them on [Stack Overflow with the `sonarqube` tag](https://stackoverflow.com/tags/sonarqube).

## License

Apache 2.0, see [LICENSE](LICENSE).
