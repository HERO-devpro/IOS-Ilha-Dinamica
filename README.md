# IOS Ilha Dinâmica

Recriação em HTML e CSS de um iPhone com a Dynamic Island (ilha dinâmica) do iOS, feita à mão como projeto de estudo de animações e interfaces.

## Demonstração

Basta abrir o `index.html` no navegador. Não há dependências, build ou servidor.

## Funcionalidades

- Corpo do iPhone com bordas, botões laterais, câmera e indicador de home.
- Tela com gradientes coloridos em duas seções espelhadas.
- Ilha dinâmica que expande ao passar o mouse ou ao receber foco pelo teclado (`Tab`).
- Barra de reprodução com tempo atual, duração e progresso, exibida quando a ilha está expandida.
- Paleta com quatro temas de cor: Deep Purple, Gold, Space Black e Silver.

## Como usar

1. Abra o `index.html` no navegador.
2. Passe o mouse sobre a ilha, ou pressione `Tab` para focá-la, para expandi-la.
3. Clique em uma das bolinhas coloridas para trocar o tema do aparelho.

## Estrutura

```
index.html   Marcação do aparelho, da ilha e da paleta de cores
style.css    Estilos, variáveis de tema e animações
```

## Como funciona

- **Temas:** quatro `input type="radio"` no topo do `body` guardam o tema escolhido. As `label.swatch` da paleta acionam esses inputs, e os seletores `#id:checked ~ .phone .bg .tema` revelam a camada de fundo correspondente.
- **Cores:** as variáveis `--c-h`, `--c-s` e `--c-l` definem o matiz, a saturação e a luminosidade do aparelho. Cada tema sobrescreve esses valores.
- **Expansão da ilha:** `.notch-container:hover` e `.notch-container:focus-within` alteram `max-height`, `max-width` e `transform`, animados com `transition` e a curva `--ease-spring`.
- **Barra de reprodução:** a `.bar` é um item de `.content` com `flex-basis: 100%`, então ela quebra para uma linha própria abaixo do título. Sua altura e opacidade são controladas por `--bar-height` e `--bar-opacity`, definidas apenas no estado de foco.
- **Unidades:** o tamanho base vem de `--size: max(5px, 1vmin)`, e o restante do layout usa `em`, o que mantém o aparelho proporcional em telas diferentes.

## Tecnologias

- HTML5
- CSS3 (Flexbox, variáveis CSS, gradientes, `mask-image`, `backdrop-filter`, `transition` e `@keyframes`)
- Fonte Inter, carregada do Google Fonts
