# README - CoDeLuri

## Sumário

1. [Introdução](#introdução)
2. [Estrutura do Projeto](#estrutura-do-projeto)
    - [HTML](#html)
    - [CSS](#css)
    - [JavaScript](#javascript)
3. [Instruções de Uso](#instruções-de-uso)
4. [Funcionalidades](#funcionalidades)
5. [Instalação](#instalação)
6. [Contato](#contato)

---

## Introdução

Bem-vindo ao CoDeLuri, um projeto desenvolvido pela DeveloperTinen, focado em criptografia e descriptografia de textos utilizando regras específicas de substituição de letras. Este documento fornece uma visão geral do projeto, incluindo sua estrutura, funcionalidades e instruções de uso.

---

## Estrutura do Projeto

### HTML

O arquivo `index.html` define a estrutura básica do site, incluindo o cabeçalho, corpo e rodapé. Ele também inclui links para o arquivo CSS e JavaScript, garantindo uma experiência de usuário fluida e estilizada.

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CoDeLuri</title>
    <link rel="stylesheet" href="styles.css">
    <link rel="shortcut icon" type="image/jpg" href="favicon.ico"/>
</head>
<body>
    <header>
        <h1>CoDeLuri</h1>
        <img src="teste2.png" alt="Logo" class="logo">
    </header>
    <div class="main-content">
        <div class="container">
            <div class="left-column">
                <img src="robocod.jpg" alt="Boneco">
            </div>
            <div class="right-column">
                <h2>Escreva e codifique:</h2>
                <strong><p>Utilize Somente letras minúsculas e sem acento!</p></strong>
                <textarea id="inputText" placeholder="Digite seu texto aqui..."></textarea>
                <div>
                    <button id="encryptButton">Criptografar</button>
                    <button id="decryptButton">Descriptografar</button>
                </div>
                <textarea id="outputText" placeholder="Resultado" readonly></textarea>
                <button id="copyButton">Copiar para área de transferência</button>
            </div>
        </div>
    </div>
    <footer>
    </footer>
</body>
</html>
```

### CSS

O arquivo `styles.css` estiliza os elementos HTML, proporcionando uma interface amigável e atraente. Ele define a aparência do cabeçalho, corpo e botões, além de garantir uma experiência visual consistente.

```css
body {
    font-family: 'Arial', sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f0f0f0;
}

header {
    background-color: #6a0dad; /* Roxo metálico */
    color: white;
    font-family: 'Arial Black', sans-serif;
    font-size: 20px;
    padding: 20px;
    text-align: center;
    position: relative;
}

header .logo {
    position: absolute;
    top: 20px;
    right: 100px;
    width: 100px; /* Tamanho pequeno */
}

footer {
    background-color: #6a0dad; /* Roxo metálico */
    color: white;
    text-align: center;
    padding: 0px 0;
    position: fixed;
    width: 100%;
    bottom: 0;
}

.main-content {
    display: flex;
    justify-content: center;
    align-items: center;
    height: calc(100vh - 100px);
}

.container {
    background: white;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    display: flex;
    align-items: center;
}

.left-column img {
    width: 100px; /* Tamanho pequeno para o boneco */
    display: block;
    margin:0 auto;
}

.right-column {
    text-align: center;
    max-width: 500px;
    margin: 0 auto;
}

.right-column textarea {
    width: 100%;
    height: 100px;
    margin: 10px 0;
    padding: 0px;
    border: 1px solid #ccc;
    border-radius: 4px;
    font-family: 'Arial', sans-serif; /* Fonte minimalista */
}

.right-column button {
    margin: 5px;
    padding: 10px 20px;
    border: none;
    border-radius: 4px;
    background-color: #007bff;
    color: white;
    cursor: pointer;
    font-family: 'Arial', sans-serif; /* Fonte minimalista */
}

.right-column button:hover {
    background-color: #0056b3;
}
```

### JavaScript

O arquivo `script.js` adiciona funcionalidades interativas ao site, como a criptografia e descriptografia de textos e a cópia do texto resultante para a área de transferência.

```javascript
document.getElementById('encryptButton').addEventListener('click', () => {
    const inputText = document.getElementById('inputText').value;
    const encryptedText = encryptText(inputText);
    document.getElementById('outputText').value = encryptedText;
});

document.getElementById('decryptButton').addEventListener('click', () => {
    const inputText = document.getElementById('inputText').value;
    const decryptedText = decryptText(inputText);
    document.getElementById('outputText').value = decryptedText;
});

document.getElementById('copyButton').addEventListener('click', () => {
    const outputText = document.getElementById('outputText');
    outputText.select();
    document.execCommand('copy');
    alert('Texto copiado para a área de transferência!');
});

function encryptText(text) {
    return text
        .replace(/e/g, 'enter')
        .replace(/i/g, 'imes')
        .replace(/a/g, 'ai')
        .replace(/o/g, 'ober')
        .replace(/u/g, 'ufat');
}

function decryptText(text) {
    return text
        .replace(/enter/g, 'e')
        .replace(/imes/g, 'i')
        .replace(/ai/g, 'a')
        .replace(/ober/g, 'o')
        .replace(/ufat/g, 'u');
}
```

---

## Instruções de Uso

1. Abra o arquivo `index.html` em seu navegador.
2. No campo "Digite seu texto aqui...", insira o texto que deseja criptografar ou descriptografar, utilizando apenas letras minúsculas e sem acento.
3. Clique no botão "Criptografar" para criptografar o texto ou "Descriptografar" para descriptografar.
4. O resultado aparecerá no campo "Resultado".
5. Para copiar o texto resultante para a área de transferência, clique no botão "Copiar para área de transferência".

---

## Funcionalidades

- **Criptografar Texto:** Substitui certas letras por sequências específicas.
- **Descriptografar Texto:** Reverte as substituições feitas na criptografia.
- **Copiar Texto:** Copia o texto resultante para a área de transferência.

---

## Instalação

1. Clone o repositório para sua máquina local.
2. Abra o arquivo `index.html` em seu navegador para visualizar e interagir com o site.

---

## Contato

Para mais informações ou suporte, entre em contato com nossa equipe através do e-mail: support@developertinen.com.

---

Obrigado por usar o CoDeLuri!