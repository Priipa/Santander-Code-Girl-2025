# Arquitetura AWS - Blog com EC2, EBS, S3 e Load Balancer

Este repositório apresenta um exemplo de arquitetura em nuvem utilizando serviços da Amazon Web Services (AWS) para hospedar um blog simples, com suporte a armazenamento de mídia e escalabilidade.

## Caso de Uso
O objetivo é criar uma infraestrutura de baixo custo, segura e escalável para um blog (ex: WordPress, Ghost, etc.) que necessita:
- Servir conteúdo dinâmico (páginas HTML geradas pela aplicação).
- Permitir que autores façam upload de arquivos de mídia (imagens, vídeos, documentos).
- Garantir que os arquivos de mídia sejam armazenados de forma durável e entregues com eficiência aos usuários finais.

<img width="789" height="513" alt="Diagrama sem nome drawio" src="https://github.com/user-attachments/assets/54013967-5dc6-4ab3-af32-b5d34ecac33a" />

## Explicação
- **Usuários na Internet** → acessam o blog pelo navegador.
- **HTTPS Load Balancer** → distribui as requisições recebidas e garante maior disponibilidade.
- **Amazon EC2** → executa o servidor web e a aplicação do blog.
- **Amazon EBS** → volume de armazenamento usado pela instância EC2 para o sistema operacional e dados locais.
- **Amazon S3** → armazenamento de objetos para imagens e vídeos do blog, com entrega direta ao usuário.
- **AWS Cloud** → ambiente que concentra e organiza os recursos.

## Fluxo básico:
1. O usuário envia uma requisição HTTPS.
2. O Load Balancer recebe e encaminha para a instância EC2.
3. A aplicação no EC2 processa a requisição.
4. Caso haja mídias, elas são servidas diretamente do Amazon S3.
5. O Amazon EBS dá suporte ao EC2 como disco do sistema.

## Tecnologias Utilizadas
- [Amazon EC2](https://aws.amazon.com/ec2/) – Computação em nuvem para hospedar a aplicação.
- [Amazon EBS](https://aws.amazon.com/ebs/) – Armazenamento em blocos para a instância EC2.
- [Amazon S3](https://aws.amazon.com/s3/) – Armazenamento de objetos para mídias.
- [Elastic Load Balancing](https://aws.amazon.com/elasticloadbalancing/) – Distribuição de tráfego para maior disponibilidade.
