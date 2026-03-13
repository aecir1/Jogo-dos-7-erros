# Jogo dos 7 Erros - Soluções

Abaixo estão listados os 7 erros plantados em cada folha de resposta (desafios).
Eles envolvem problemas de HTML, CSS e JavaScript que devem ser corrigidos através do DevTools (F12) para que as páginas fiquem idênticas ao gabarito.

---

## 🛑 Desafio 1 (Baseado no Gabarito 1 - Perfil)
1. **CSS (`body`)**: `justify-content` está como `flex-start` ao invés de `center`.
2. **CSS (`.avatar`)**: Perdeu o arredondamento por estar com `border-radius: 0` (ficou quadrado).
3. **CSS (`.bio`)**: A cor do texto (`#1e1e2f`) está quase igual ao fundo, deixando-o camuflado.
4. **HTML (`<button>`)**: O `id` está como `active-btn` e não `action-btn`, quebrando a referência do JavaScript.
5. **HTML (`<h1>`)**: A tag de nome perdeu a classe `name` e está usando `nome`, perdendo a estilização CSS.
6. **JS (`<script>`)**: Está chamando `document.getElementByName()` ao invés de `document.getElementById()`, gerando um erro no console.
7. **CSS (`.btn:hover`)**: A pseudo-classe de hover está com `opacity: 0`, fazendo o botão sumir quando o mouse passa por cima.

---

## 🛑 Desafio 2 (Baseado no Gabarito 2 - Login)
1. **CSS (`.login-box`)**: O `padding` está em `0px` ao invés de `40px`, deixando os elementos sufocados na borda.
2. **HTML (`<input> da senha`)**: O atributo `type` está como `text` ao invés de `password`, deixando a senha exposta.
3. **HTML (`<form>`)**: O `id` foi alterado para `auth-form-x`, quebrando o vínculo com o JavaScript que escuta o evento de submit de `auth-form`.
4. **CSS (`.input-group label`)**: O display mudou para `inline` (ao invés de `block`), quebrando a estrutura acima do campo de texto.
5. **CSS (`.submit-btn`)**: Tanto o fundo (`background`) quanto o texto (`color`) do botão estão configurados como `transparent`, deixando-o completamente invisível.
6. **JS (`<script>`)**: O método para impedir o recarregamento natural do form está escrito erroneamente como `e.prevent()` no lugar de `e.preventDefault()`.
7. **CSS (`body`)**: O flexbox foi desativado com `display: block` e a tela deixou de ter todos os elementos centralizados vertical e horizontalmente.


**Boa sorte aos participantes do grupo! 🚀**
