# Guia Passo a Passo: Resolvendo o Jogo dos 7 Erros

Este guia tem como objetivo te ensinar a encontrar, identificar e corrigir os 7 erros plantados nos dois desafios propostos utilizando o **DevTools (Aba F12)** do seu navegador (Google Chrome, Edge, etc.). 

## 🛠️ Como usar o F12
Quando você abre a página do desafio em seu navegador, você deve pressionar a tecla `F12` no teclado para abrir o **Painel de Desenvolvimento**. As duas abas que você mais usará são:

1. **Aba Elements (Elementos):** Ela exibe todo o código HTML (do lado esquerdo) e CSS (do lado direito). Você pode clicar com o direito num botão ou imagem da página e ir em **Inspecionar**, e a aba Elements pulará exatamente para esta linha de código. É nela que consertaremos classes, tags e estilos CSS.
2. **Aba Console:** Ela mostra todos os erros que ocorrem nos scripts (JavaScript). Toda vez que alguma lógica der errado, o console indicará o motivo em vermelho.

> Ponto importante: Tudo o que você altera pelo F12 só existe visualmente para testar. **Após descobrir onde está o erro, você precisa consertá-lo no seu arquivo original (ex:** `desafio1.html`**)** usando seu editor de código (VS Code ou Bloco de Notas).

---

## 🛑 Desafio 1: Perfil Profissional (desafio1.html)
Abra a página `desafio1.html`. O objetivo é que ela fique idêntica ao `gabarito1.html`.

### 1. Tudo alinhado para a esquerda ao invés de no centro
- **Como inspecionar:** Pressione F12 e clique na primeira tag de cima, a `<body>` na aba *Elements*.
- **Como resolver:** Olhe a janela "Styles" direita. A propriedade `justify-content` está como `flex-start`. Altere-a para `center`.
- **No arquivo:** Vá até a linha 14 do `desafio1.html` e altere o `flex-start` para `center`.

### 2. Imagem redonda virou um quadrado
- **Como inspecionar:** Clique com o botão direito sobre a foto quadrada e selecione "Inspecionar".
- **Como resolver:** O F12 focará na imagem `<img class="avatar">`. No lado direito, em "Styles", você verá que a regra `.avatar` possui um `border-radius: 0;`. Altere esse 0 para `50%` para a foto voltar a ser redonda.
- **No arquivo:** Linha 33, altere o valor do `border-radius` de `0` para `50%`.

### 3. A profissão e o texto "sumiram" contra o fundo escuro
- **Como inspecionar:** Inspecione a área vazia embaixo do título "Front-end Hacker". Você notará que o texto "soluções do dog." está lá, mas invisível.
- **Como resolver:** Ao clicar na tag `<p class="bio">`, olhe no "Styles" a propriedade `color: #1e1e2f;`. Essa cor é a mesma cor do fundo. Troque a cor por `#ccc` ou `#fff` para que o texto reapareça.
- **No arquivo:** Linha 40, altere o hexadecimal `#1e1e2f` para uma cor clara como `#ccc`.

### 4. Nome da pessoa com formatação errada
- **Como inspecionar:** Inspecione o título principal (`<h1>`).
- **Como resolver:** O `<h1 class="nome">Gaguinho Jr</h1>` está usando a classe `nome` ao invés de `name`. O CSS que cria as letras gordas está atrelado à classe com o nome em inglês.
- **No arquivo:** Linha 59, altere a classe de `nome` para `name`.

### 5. O botão "Conectar" desaparece ao passar o mouse
- **Como inspecionar:** Passe o mouse no botão. Ele ficará invisível.
- **Como resolver:** Inspecione o botão. Na aba "Styles", clique em ":hov" (para forçar o estado de Hover). Você verá que a classe `.btn:hover` tem a propriedade `opacity: 0`. Isso faz o botão sumir totalmente. Remova essa linha.
- **No arquivo:** Na linha 53, remova a instrução `opacity: 0;`.

### 6 e 7. O botão não emite aviso ao ser clicado (Erros de Lógica/JS)
- **Como inspecionar:** Abra a aba **Console** do DevTools (F12) e clique no botão "Conectar". Ele exibirá o erro: `Uncaught TypeError: document.getElementByName is not a function`.
- **Como resolver (Erro 6 - JS):**  Na linha 66, a função do script devia encontrar um elemento por ID, mas o comando está escrito errado. Mude `document.getElementByName('action-btn')` para `document.getElementById('action-btn')`.
- **Como resolver (Erro 7 - HTML):** Mesmo mudando isso, ainda dará erro porque o ID do botão (`<button id="active-btn">`) no HTML não bate com o que o script está procurando (ele procura `action-btn`). É necessário alinhar os dois. Mude o ID do botão de `active-btn` para `action-btn`.
- **No arquivo:** Linha 62, mude o id para `action-btn`. E na linha 66, altere a função inteira para `document.getElementById('action-btn')`.

---

## 🛑 Desafio 2: Portal de Autenticação (desafio2.html)
Abra a página `desafio2.html` e tente chegar ao mesmo visual e comportamento do `gabarito2.html`.

### 1. A página subiu para o topo da tela
- **Como inspecionar:** Abra o F12 e inspecione a tag `<body>`.
- **Como resolver:** Nos estilos, o Flexbox foi removido e substituído por `display: block`. A página não centraliza os itens sozinha. Modifique para `display: flex; justify-content: center; align-items: center;`.
- **No arquivo:** Substitua a linha 13 por `display: flex; justify-content: center; align-items: center;`.

### 2. O balão branco (Box) sufocou tudo. Sem respiros ao redor.
- **Como inspecionar:** Selecione a div inteira que acomoda o login (`<div class="login-box">`).
- **Como resolver:** Na janela de estilos da direita, localize a regra pad para `.login-box`. O `padding: 0px;` tirou todo o espaço interno de respiro. Altere-o para `padding: 40px;` e veja o respiro voltar.
- **No arquivo:** Altere a linha 19 e mude `padding: 0px` para `padding: 40px`.

### 3. Texto quebrando fora de ordem
- **Como inspecionar:** Inspecione a palavra "E-mail corporativo". 
- **Como resolver:** Na mesma aba lateral "Styles", a regra `.input-group label` está com `display: inline;`. O `inline` faz com que o texto não tenha sua própria linha e quebre o layout que o input precisa. Mude para `display: block;`.
- **No arquivo:** Linha 26, altere `display: inline` para `display: block`.

### 4. O botão "Entrar na Nave" está invisível.
- **Como inspecionar:** Use a setinha de inspeção do F12 pra tentar encontrar o botão dentro do balão ou localize no HTML o `<button>` e clique nele.
- **Como resolver:** Veja nas regras da direita que as propriedades de `.submit-btn` mudam tanto a imagem de fundo quanto a cor do texto para `transparent`. Remova ambas (`background: transparent;` e `color: transparent;`). O botão já possuía uma cor principal de transição. Defina `background: #333; color: #fff;` para restabelecer os valores base, ou copie as cores do gabarito.
- **No arquivo:** Linha 39 e 40, adicione cor. Mudar fundo `transparent` para `background: #333` e o texto para `color: #fff`. 

### 5. A senha está aparecendo como texto puro sem as estrelinhas.
- **Como inspecionar:** Inspecione a barra onde digita a string. 
- **Como resolver:** No próprio HTML, procure por `<input type="text" id="password"...>`. O fato dele ser tipo `text` anula a restrição visual da senha. É só dar dois cliques em cima do "text" e mudar para "password".
- **No arquivo:** Linha 69, mude `type="text"` para `type="password"`.

### 6. e 7. O erro no Envio do Form (Script não impede o recarregar da página)
- **Sintoma:** Ao clicar no botão "Entrar na Nave", tente perceber que se você piscar, a página recarregará em meio segundo sem validar nada, mesmo apertando nele sendo invisível.
- **Como descobrir:** O JavaScript está tentando prever o envio "nativo" e tratá-lo, mas não está conseguindo.
- **No arquivo (Erro 6 - HTML):** Vá na linha 62. O ID do forms é `auth-form-x`, enquanto no JavaScript (linha 76) o JS estuda monitorar `auth-form`. Remova o "-x" para alinhá-los. Mude `auth-form-x` para `auth-form`.
- **No arquivo (Erro 7 - JS):** A linha 77 tem o comando de JS falso: `e.prevent();`. O método da internet pra parar um "evento natural de recarregar" é escrito `e.preventDefault()`. Conserte no seu arquivo.
