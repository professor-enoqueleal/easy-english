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

Agora que o projeto React já foi criado, quero que você implemente a página principal.

Requisitos da interface:
- A página deve ser limpa e minimalista.
- O conteúdo padrão do `App.jsx` deve ser substituído, mantendo a estrutura base do projeto padrão. O CSS deve ser mantido, e usar a mesmo cor de background.
- A página deve ter um `<h1>` com o texto "Easy English - Prática de Listening".
- No centro da página, adicione um reprodutor de vídeo utilizando iframe_api para simplicidade. O vídeo padrão deve ser o seguinte: https://www.youtube.com/watch?v=Yp0kth7-zsM&t e o timer padrão de reprodução deve ser de 15 segundos. A cada 15 segundos o vídeo repete
- Abaixo do reprodutor de vídeo, adicione dois botões, sem texto, usando ícones da biblioteca `react-icons`:
    - Um botão de configuração (ícone de engrenagem).
    - Um botão de concluir (ícone de check).
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
