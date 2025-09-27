# Easy English

# Prompt 1

Eu sou um desenvolvedor Java, e quero criar um aplicativo para me ajudar a estudar inglês. 

O aplicativo deve ser um site simples, com o objetivo de praticar a repetição. 

Requisitos do projeto: 
- O aplicativo deve ter uma página web com um reprodutor de vídeo. 
- O usuário deve ser capaz de definir o tempo de início e fim para repetir uma seção específica do vídeo. Por padrão, se o usuário não definir um tempo de início customizado, o vídeo deve repetir, a reprodução de 15 segundos.
- Se o usuário recarregar a tela, o tempo já assistido não deve mudar.
- A interface deve ser minimalista e focar na funcionalidade principal.
- Se o usuário alterar o tempo de repetição, por exemplo de 15 segundos para 30, o tempo que ele já assitiu não pode ser zerado. 
- O aplicativo precisa ser responsivo para funcionar bem em dispositivos móveis. 
- O aplicativo deve ser uma PWA (Progressive Web App) para que possa ser instalado no celular. 

Restrições de tecnologia: 
- Não usarei Java para este projeto. 
- Eu quero utilizar JavaScript. Estou em dúvida entre JavaScript vanilla, ou frameworks como React, Angular ou Vue.js. 

Qual framework seria a melhor escolha para este projeto, considerando a premissa de  simplicidade e velocidade de construção para entregar um MVP rapidamente? Justifique sua resposta e responda em português.

---

# Prompt 2

Levando em consideração que irei utilizar o framework react para desenvolver esse aplicativo, que deve respeitar os rquisitos a seguir: 

Requisitos do projeto: 
- O aplicativo deve ter uma página web com um reprodutor de vídeo. 
- O usuário deve ser capaz de definir o tempo de início e fim para repetir uma seção específica do vídeo. Por padrão, se o usuário não definir um tempo de início customizado, o vídeo deve repetir, a reprodução de 15 segundos.
- Se o usuário recarregar a tela, o tempo já assistido não deve mudar.
- A interface deve ser minimalista e focar na funcionalidade principal.
- Se o usuário alterar o tempo de repetição, por exemplo de 15 segundos para 30, o tempo que ele já assitiu não pode ser zerado. 
- O aplicativo precisa ser responsivo para funcionar bem em dispositivos móveis. 
- O aplicativo deve ser uma PWA (Progressive Web App) para que possa ser instalado no celular. 

liste e execute os comandos para criar a estrutura do projeto e liste também os passos necessários para executar o projeto.

---

# Prompt 3

Agora, no projeto React já foi criado, você deve implementar a página principal. 

Requisitos da interface:
- A página deve ser limpa e minimalista.
- O conteúdo padrão do `App.jsx` deve ser substituído, mantendo a estrutura base do projeto padrão. O CSS deve ser mantido, e usar a mesmo cor de background.
- A página deve ter um `<h1>` com o texto "Easy English - Prática de Listening".
- No centro da página, adicione um reprodutor de vídeo utilizando a iframe_api para simplicidade. O vídeo padrão deve ser o seguinte: https://www.youtube.com/watch?v=Yp0kth7-zsM&t
- O timer padrão de reprodução do vídeo deve ser de 15 segundos. A cada 15 segundos o vídeo repete.
- Abaixo do reprodutor de vídeo, adicione dois botões. Os botões não devem conter texto, devem apenas usar ícones da biblioteca `react-icons`:
    - Um botão será de configuração e deve utilizar o ícone de engrenagem.
    - Um botão será de concluir e deve utilizar o ícone de check.
- Abaixo do vídeo, adicione um parágrafo (`<p>`) com o texto: "O vídeo irá repetir até você clicar em Concluir."
- Abaixo do parágrafo, anterior, adicione outro paragrafo que será um contador que mostra o tempo restante para a repetição de acordo com a parametrização. Esse contador deve ser atualizado conforme o vídeo é produzido, até zerar.

Lógica de interação:
- Quando o usuário clicar no botão de concluir, o vídeo deve ser pausado e reiniciado para o tempo 0 e permanecer pausado. 
- Quando o usuário clicar no botão de configuração, um campo de entrada de texto (`<input>`) com um botão "Salvar" devem ser exibitos.
- Os campos de input e salvar deve ficar hidden e devem aparecer apenas quando o usuário clicar no botão de engrenagem / configuração.
- O usuário pode digitar um novo tempo de repetição (em segundos) no campo.
- Ao clicar em "Salvar", o vídeo deve usar esse novo tempo de repetição e reiniciar o loop. O reprodutor de vídeo deve acatar as configurações feitas pelo usuário.
- O estado de repetição deve ser gerenciado usando hooks do React (`useState` e `useEffect`).
- A página completa não pode ser recarregada, levando em consideração que trata-se de um projeto SPA.
- O reprodutor de vídeo deve ter o máximo de tamanho possível, considerando o navegador que está sendo utlizado e o conceito de responsividade.

---

# Prompt 4

Agora que o componente principal App.jsx está funcional, o próximo passo é habilitar o aplicativo como um Progressive Web App (PWA).

Tarefa 1: Criar o Conteúdo do Manifest

Crie o conteúdo completo do arquivo manifest.json, definindo:

name: "Easy English"
short_name: "EE Listen"
start_url: "/index.html"
display: "standalone"
background_color: "#f0f4f8" (cor do background atual)
theme_color: "#2563eb" (cor azul primária do design)
icons: Inclua uma array de ícones com tamanhos de 192x192 e 512x512, usando URLs placeholder (ex: '/icon-192.png').

Tarefa 2: Criar o Conteúdo do Service Worker

Crie o conteúdo do arquivo service-worker.js para caching de ativos essenciais (caching estático) e funcionalidade offline básica. O Service Worker deve cachear a página raiz ('/') e os principais arquivos de assets. Use uma estratégia de cache-first.

Tarefa 3: Registrar o Service Worker

Atualize o arquivo App.jsx para:

Incluir uma função de utilidade para o registro do service worker (ServiceWorkerRegistration).

Chamar essa função dentro de um useEffect para registrar o service worker apenas uma vez, após o componente montar.

Adicionar uma tag <link rel="manifest" href="/manifest.json"> no <head> da página usando o hook useEffect e document.createElement.

---

# Prompt 5

Build Final e Guia de Deploy no Amazon S3

Agora eu quero que você prepare a aplicação para a produção e consolidar o guia de deploy.

Tarefa 1. Build da Aplicação
- Executar o comando de compilação (Build) da aplicação React para gerar a pasta de saída contendo todos os arquivos estáticos prontos para produção (HTML, JS, CSS, manifest.json, service-worker.js).
- Liste e execute o comando exato que deve ser executado na raiz do projeto (assumindo o setup padrão do create-react-app).

Tarefa 2. Instruções Detalhadas para deploy no Deploy (Amazon S3)
Liste o passo a passo completo, detalhado e sequencial para realizar o deploy do conteúdo gerado pelo build (a pasta estática) em um bucket do Amazon S3.

O passo a passo deve incluir, obrigatoriamente, as seguintes seções e ações:

Tarefa 2.1 Configuração do BucketCriação do Bucket (incluindo a necessidade de desmarcar a opção "Block all public access").

- Configuração da hospedagem de site estático, especificando index.html como documento de índice e documento de erro (para suportar rotas SPA).
- Definição da Política do Bucket (Bucket Policy) para permitir o acesso de leitura pública (s3:GetObject). O JSON da política deve ser listado.

