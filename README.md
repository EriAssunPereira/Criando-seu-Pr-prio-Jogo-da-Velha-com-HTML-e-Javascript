# Criando-seu-Pr-prio-Jogo-da-Velha-com-HTML-e-Javascript

Criação de um Jogo da Velha utilizando HTML, CSS e JavaScript. Vamos dividir o projeto em módulos para facilitar o entendimento e a organização do código.

### Módulo 1: Estrutura HTML
Começaremos com a estrutura básica do HTML. Criaremos um arquivo `index.html` e dentro dele, definiremos uma tabela com 3 linhas e 3 colunas, que representarão o tabuleiro do jogo.

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <title>Jogo da Velha</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div id="jogoDaVelha">
        <table>
            <tr>
                <td id="célula-0"></td>
                <td id="célula-1"></td>
                <td id="célula-2"></td>
            </tr>
            <tr>
                <td id="célula-3"></td>
                <td id="célula-4"></td>
                <td id="célula-5"></td>
            </tr>
            <tr>
                <td id="célula-6"></td>
                <td id="célula-7"></td>
                <td id="célula-8"></td>
            </tr>
        </table>
    </div>
    <script src="script.js"></script>
</body>
</html>
```

### Módulo 2: Estilização CSS
No arquivo `styles.css`, vamos adicionar estilos para tornar o tabuleiro visualmente agradável.

```css
#jogoDaVelha {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

#jogoDaVelha table {
    border-collapse: collapse;
}

#jogoDaVelha td {
    width: 100px;
    height: 100px;
    border: 1px solid #000;
    text-align: center;
    vertical-align: middle;
    font-size: 36px;
    cursor: pointer;
}
```

### Módulo 3: Lógica JavaScript
Por fim, no arquivo `script.js`, implementaremos a lógica do jogo. Criaremos funções para controlar as jogadas, verificar o vencedor e alternar entre os jogadores.

```javascript
document.addEventListener('DOMContentLoaded', () => {
    const células = document.querySelectorAll('#jogoDaVelha td');
    let vezDoJogador = 'X';

    células.forEach(célula => {
        célula.addEventListener('click', (e) => {
            if (e.target.textContent === '') {
                e.target.textContent = vezDoJogador;
                vezDoJogador = vezDoJogador === 'X' ? 'O' : 'X';
                verificarVencedor();
            }
        });
    });

    function verificarVencedor() {
        // Aqui você adicionará a lógica para verificar o vencedor
    }
});
```

Esses são os passos básicos para criar um Jogo da Velha. Você pode expandir o projeto adicionando um placar, opções para reiniciar o jogo e até mesmo uma IA para jogar contra.
