### Olá! eu sou o Jefson Oliveira ✋

[![Linkedin](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/jefson-oliveira-a92a62206/)
[![Instagran](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://www.instagram.com/jefson_k_oliveira/)
[![Whatsapp](https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white)](https://api.whatsapp.com/send/?phone=%2B5592982933346&text&type=phone_number&app_absent=0)

##

<div>
 <a href="https://github.com/formandodev">
  <img height="170em" src="https://github-readme-stats.vercel.app/api?username=JefsonOliveira&show_icons=true&theme=dracula&include_all_commits=true&count_private=true"/>
<img height="170em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=JefsonOliveira&layout=compact&langs_count=7&theme=dracula"/>
</div> 

##

 ### Tecnologias que eu uso no meu dia
<div style="display: inline_block"><br/>
  <img aling="center" alt="html5" src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" />
  <img aling="center" alt="html5" src="https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white" />
  <img aling="center" alt="html5" src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" />
  <img aling="center" alt="html5" src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" />
  <img aling="center" alt="html5" src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" />
  <img aling="center" alt="html5" src="https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white" />
  <img aling="center" alt="html5" src="https://img.shields.io/badge/MySQL-00000F?style=for-the-badge&logo=mysql&logoColor=white" />
    <img align="right" alt="Rafa-pic" height="150" style="border-radius:50px;" src="https://i.im.ge/2023/02/11/aChXK0.picwish.png">
</div>

 ### “Qualquer pessoa pode escrever um código que um computador possa entender. Bons programadores escrevem códigos que humanos possam entender.”
 ### Martin Fowler

<p align="center">   <img alingn="center" src="https://profile-counter.glitch.me/JefsonOliveira/count.svg" /></p>


<html>
  <head>
    <title>GitHub Contribution Grid Snake</title>
  </head>
  <body>
   
   const GitHub = require('github-api');
const blessed = require('blessed');

const github = new GitHub();
const user = 'SEU_USUARIO_GITHUB';
const repo = 'SEU_REPOSITORIO_GITHUB';

// Cria a tela do jogo usando a biblioteca "blessed"
const screen = blessed.screen({
  smartCSR: true,
  title: 'Cobrinha de Commit no GitHub',
});

// Cria o campo onde a cobrinha irá se movimentar
const field = blessed.box({
  top: 'center',
  left: 'center',
  width: '50%',
  height: '50%',
  content: '',
  tags: true,
  border: {
    type: 'line',
  },
  style: {
    fg: 'white',
    bg: 'black',
    border: {
      fg: '#f0f0f0',
    },
  },
});

// Adiciona o campo na tela do jogo
screen.append(field);

// Define o tamanho da cobrinha
const snakeSize = 5;

// Define a posição inicial da cobrinha
let snake = [
  [10, 10],
  [9, 10],
  [8, 10],
  [7, 10],
  [6, 10],
];

// Define a direção inicial da cobrinha
let direction = 'right';

// Função para obter os commits mais recentes do repositório
async function getCommits() {
  const repository = github.getRepo(user, repo);
  const { data } = await repository.getCommits();
  return data;
}

// Função para atualizar o campo com os commits
async function updateField() {
  const commits = await getCommits();
  const fieldContent = [];
  for (let i = 0; i < field.height - 2; i++) {
    const row = [];
    for (let j = 0; j < field.width - 2; j++) {
      row.push(' ');
    }
    fieldContent.push(row.join(''));
  }
  for (let i = 0; i < commits.length; i++) {
    const commit = commits[i];
    const x = Math.floor((commit.commit.committer.date - Date.now()) / (1000 * 60 * 60 * 24)) + Math.floor(field.width / 2);
    const y = Math.floor(field.height / 2) + i;
    if (x >= 0 && x < field.width - 2 && y >= 0 && y < field.height - 2) {
      fieldContent[y] = fieldContent[y].substr(0, x) + '#' + fieldContent[y].substr(x + 1);
    }
  }
  field.setContent(fieldContent.join('\n'));
  screen.render();
}

// Função para atualizar a posição da cobrinha
function updateSnake() {
  const head = snake[0];
  let newHead;
  switch (direction) {
    case 'right':
      newHead = [head[0] + 1, head[1]];
      break;
    case 'left':
      newHead = [head[

