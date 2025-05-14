### Olá! Sou o João Vitor 👋

[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://www.instagram.com/joao.vitorandrade_/)
[![Linkedin](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/joão-vitor-macieira-de-andrade-733252249/)
<hr/>
<div>
  <img height="195em" src="https://github-readme-stats.vercel.app/api?username=joaoandradedev&show_icons=true&theme=dracula&include_all_commits=true&count_private=true"/>
  <img height="195em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=joaoandradedev&layout=compact&langs_count=16&theme=dracula"/>
</div>
<hr/>

### Tecnologias🚀
<div style="display: inline_block"><br/>
  <img align="center" alt="html5" src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white"/>
  
  <img align="center" alt="css3" src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white"/>
  
  <img align="center" alt="js" src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black"/>
  
  <img align="center" alt="native" src="https://img.shields.io/badge/React_Native-20232A?style=for-the-badge&logo=react&logoColor=61DAFB"/>
  
  <img align="center" alt="node.js" src="https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white"/>
  
</div><br/>



LISTA DE TAREFAS:

document.addEventListener('DOMContentLoaded', () => {
    const inputNovaTarefa = document.getElementById('nova-tarefa');
    const btnAdicionarTarefa = document.getElementById('btn-adicionar');
    const listaTarefas = document.getElementById('tarefas');
    const erroDiv = document.getElementById('erro-input');

    btnAdicionarTarefa.addEventListener('click', adicionarTarefa);

    inputNovaTarefa.addEventListener('keypress', (event) => {
        if (event.key === 'Enter') {
            adicionarTarefa();
        }
    });

    function adicionarTarefa() {
        const textoTarefa = inputNovaTarefa.value.trim();

        // Limpa mensagens de erro
        erroDiv.textContent = '';

        if (textoTarefa === '') {
            erroDiv.textContent = 'Digite uma tarefa antes de adicionar.';
            return;
        }

        // Criação do elemento <li>
        const novaLi = document.createElement('li');

        novaLi.innerHTML = `
            <span class="tarefa-texto">${textoTarefa}</span>
            <div class="acoes">
                <button class="btn-concluir">Concluir</button>
                <button class="btn-remover">Remover</button>
            </div>
        `;

        // Botões dentro da nova tarefa
        const btnConcluir = novaLi.querySelector('.btn-concluir');
        const btnRemover = novaLi.querySelector('.btn-remover');
        const tarefaTextoSpan = novaLi.querySelector('.tarefa-texto');

        btnConcluir.addEventListener('click', () => {
            tarefaTextoSpan.classList.toggle('concluida');
        });

        btnRemover.addEventListener('click', () => {
            listaTarefas.removeChild(novaLi);
        });

        // Adiciona o <li> na lista
        listaTarefas.appendChild(novaLi);

        // Limpa o campo
        inputNovaTarefa.value = '';
    }
});
