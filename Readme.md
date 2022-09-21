# Jogo_Mem-ria
# Jogo de Memória 
Esse projeto é um jogo de mémoria sobre gatinhos, Cada participante deve ou apenas um jogador, na sua vez,virar duas peças. Caso as figuras sejam iguais, as duas cartas permanecem viradas. Se forem peças diferentes, são viradas novamente, e sendo passada a vez ao participante seguinte.

## Tecnologias utilizadas
1. **HTML**: O HTML é o componente básico da web, ele permite inserir o conteúdo e estabelecer a estrutura básica de um website. Portanto, ele serve para dar significado e organizar as informações de uma página na web. Sem isso, o navegador não saberia exibir textos como elementos ou carregar imagens e outros conteúdos.
2.**CSS**: CSS é chamado de linguagem Cascading Style Sheet e é usado para estilizar elementos escritos em uma linguagem de marcação como HTML. O CSS separa o conteúdo da representação visual do site.
3. **JS**: é uma linguagem de programação que permite a você criar conteúdo que se atualiza dinamicamente, controlar múltimídias, imagens animadas, e tudo o mais que há de intessante.

## Funções Principais

### Embaralha as Cartas
'''
const loadGame = () => {
    const duplicateCharacters = [ ...characters, ...characters ];

    const shuffledArray = duplicateCharacters.sort(() => Math.random() - 0.5);

    shuffledArray.forEach((character) => {
      const card = createCard(character);
      grid.appendChild(card);
    });
  }
'''  

  ### Criar as Cartas
'''
  const createCard = (character) => {

    const card = createElement('div', 'card');
    const front = createElement('div', 'face front');
    const back = createElement('div', 'face back');

    front.style.backgroundImage = `url('../images/${character}.jpg')`;
    // ../images/${character}.jpg

    card.appendChild(front);
    card.appendChild(back);

    card.addEventListener('click', revealCard);
    card.setAttribute('data-character', character)

    return card;
  }
'''

  ## Verificar o acerto
  ...
  const checkCards = () => {
    const firstCharacter = firstCard.getAttribute('data-character');
    const secondCharacter = secondCard.getAttribute('data-character');

    if (firstCharacter === secondCharacter) {

      firstCard.firstChild.classList.add('disabled-card');
      secondCard.firstChild.classList.add('disabled-card');

      firstCard = '';
      secondCard = '';

      checkEndGame();

    } else {
      setTimeout(() => {

        firstCard.classList.remove('reveal-card');
        secondCard.classList.remove('reveal-card');

        firstCard = '';
        secondCard = '';

      }, 500);
    }

  }
  ...

  ## Como Rodar o Código
  Baixe o código e abra o arquivo **_index.html_** no seu navegador 

  ## Imagens da Tela
tela 1
![tela 1](/images/tela1.png)



  ## Referências
  * JS: [MDN](https://developer.mozilla.org/pt-BR/docs/Learn/JavaScript/First_steps/What_is_JavaScript)
  * HTML: [Homehost](https://www.homehost.com.br/blog/tutoriais/o-que-e-html/)
  * CSS: [Hostinger](https://www.hostinger.com.br/tutoriais/o-que-e-css-guia-basico-de-css)