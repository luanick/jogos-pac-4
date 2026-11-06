# Efeito Dominó: Futuro em Jogo

Protótipo jogável — **trabalho de faculdade**. Não tem relação com o sistema de
chamados; é um projeto separado, que vive só nesta pasta.

Jogo narrativo 2D no **Colégio Nova Aurora**. Cada escolha vira registro, e
registro volta — é o efeito dominó.

## A história

Lucas está no terceiro ano. A escola acabou de lançar o **Projeto Horizonte**,
um programa que promete ajudar cada aluno a descobrir seus talentos e seu
caminho depois do ensino médio. Para isso instalaram uma inteligência artificial
chamada **ORION**.

No começo a ORION parece — e é — útil. Ela acompanha desempenho, identifica
dificuldade, sugere caminho. O que os alunos não sabem é que ela não analisa só
notas. Analisa escolhas: quem você ajuda, em quem confia, quando você mente,
quando evita o conflito, o que faz primeiro.

O jogo não começa com "a IA é má". Começa com uma aula chata sobre futuro, um
amigo empolgado e uma colega desconfiada. A pergunta cresce devagar:

> Se alguém consegue prever a sua decisão, você ainda está escolhendo?

### Quem é quem

| | |
|---|---|
| **Lucas** | quem você controla. A personalidade dele é montada pelas suas escolhas |
| **Gabriel** | amigo, espontâneo, impulsivo. Acha o Projeto Horizonte sensacional |
| **Marina** | observadora. Não é contra a tecnologia — ela quer saber quem controla os dados |
| **ORION** | a inteligência artificial do Projeto Horizonte. Não odeia ninguém. Ela otimiza |
| **Prof. Reis** | professor de Projeto de Vida |
| **Profa. Duarte** · **Coordenadora** · **Ruan** · **aluno novo** | a escola em volta |

## Como jogar

Dois cliques em **`index.html`**. Abre em qualquer navegador, não instala nada,
não precisa de internet.

Os controles são os mesmos em todo lugar: **WASD anda, Z/X/C são as três
ações**. Nenhum mini-game inventa tecla própria.

| Tecla | O que faz |
|---|---|
| ↑ ↓ ← → ou W A S D | andar, e mirar dentro dos mini-games |
| ENTER / Z / clique | **ação 1**: falar, confirmar, armar o arremesso, puxar na pista |
| X | **ação 2**: finta no arremesso, tchau de costas no "ata", respirar no circuito |
| C | **ação 3**: pose |
| segurar ENTER / Z | passar a cola, carregar a força do arremesso |
| TAB ou botão STATUS | abrir a ficha do personagem |
| SHIFT | arrancada no mapa (depois que o Téo te der fôlego) |
| M | ligar/desligar o som |

Chegue perto de quem tem o **!** amarelo em cima. Quando aparecer **ENTER** com o
que ele faz (`ENTER Falar com Gabriel`), é só apertar — de frente, de lado ou na diagonal.
O mapinha no canto mostra onde você está e onde é o objetivo; o **✦** verde marca
as atividades de aura, que são livres e repetíveis.

## O campus

O jogo tem dois lugares: o **quarto do Lucas** (a introdução) e o **Colégio Nova
Aurora**. Trocar de lugar redesenha mapa, gente, objetos e iluminação —
`carregarCenario()`.

O colégio é um campus, não um corredor com salas:

```
  BLOCO NORTE   biblioteca · laboratório de tecnologia · cantina
  CORREDOR      armários, murais, bebedouros, lixeiras
  BLOCO SUL     sala 101 · sala 102 · sala dos professores · banheiros
  PÁTIO         área coberta de convivência, com o painel da ORION
  FACHADA       porta principal de três folhas
  ÁREA EXTERNA  jardim, praça e entrada · GINÁSIO (quadra, arquibancada,
                placar, pista de corrida e vestiário)
```

A área externa é parte do colégio: uma calçada liga o portão do campus à porta
principal, com gramado, árvores, bancos, poste, bicicletário e uma grade com
portãozinho separando o jardim da quadra.

O estilo é **escola de verdade com tecnologia um pouco à frente**: tem quadro,
carteira, armário e mural; e também porta de vidro, placa digital ao lado de
cada sala, parede de telas no laboratório e o painel do pátio. Nada de virar
boate ou nave espacial.

## As fases

- **Prólogo — o quarto do Lucas.** Curto. Serve para aprender a andar, conversar
  com as coisas e sair pela porta. Já guarda a primeira escolha.
- **Fase 1 — primeiro dia.** Chegar na sala, a aula de Projeto de Vida (duas
  perguntas que voltam depois), o intervalo com exploração livre — Gabriel na
  cantina, Marina na biblioteca, um aluno novo perdido no pátio — e a seleção
  para o Projeto Horizonte que ninguém pediu.
- **Fase 2 — ORION.** O laboratório, a primeira aparição dela, a prova, a cola.
- **Fases 3 a 6.** Consequências, conflito, escalada e ruptura, com **8 finais**
  (3 secretos) decididos por atributos, relacionamentos e flags.

### O efeito dominó é real

O momento em que o jogo mostra a mão é a cena `orion_perfil`, no capítulo 3: a
ORION devolve o perfil dela sobre você e **cita textualmente** a sua resposta da
aula do primeiro dia, além do que você fez (ou não fez) com o aluno novo no
pátio. Fora isso, vários personagens ganham falas extras só porque você escolheu
uma coisa específica lá atrás — inclusive a Marina lembrando de como você a
cumprimentou no primeiro dia.

## O ginásio: a área modelo

Toda área importante do colégio tem que responder três perguntas. O ginásio é
a primeira que responde bem, e serve de molde para as outras:

| | |
|---|---|
| **por que eu iria até lá?** | tem o Téo, treino, corrida, loja e uma missão |
| **o que eu faço lá?** | dois mini-games, compras com créditos e a seletiva do revezamento |
| **o que muda depois?** | o Lucas anda mais rápido — no mapa inteiro, o jogo todo |

O ginásio tem arquibancada com corrimão, placar, relógio, tabela desenhada
com aro e rede, banco de reservas, armário de equipamento aberto, carrinho
de bolas, cones, garrafas e toalhas largadas, banners de campeonato e a
quadra pintada (garrafão, linha de fundo, laterais) — com a área de jogo
**livre**, que é onde o arremesso acontece.

### Téo

Ele **não é um menu de upgrade parado na pista**. Corre a raia, alonga,
bebe água, guarda material, senta no banco e volta para a quadra. Quando o
Lucas encosta, ele interrompe o que estava fazendo e vira — dá para sentir
que ele estava ali antes de alguém chegar.

É treinador, adversário, lojista e dono de uma missão.

- **Circuito de cones** — uma volta completa na pista contra o relógio, com
  quatro marcas e oito cones nas três raias. **Z puxa** (gasta fôlego), **X
  para e respira** (recupera rápido, mas o relógio continua). Bater num cone
  derruba, e derruba mais feio quem bate puxando. **O tempo é a nota**: abaixo
  de 5,5 s vale 8 pontos de treino, acima de 13 s vale 1. Cada cinco pontos
  sobem **um nível de velocidade**; a cada doze sobe o **fôlego**.
- **Correr contra o Téo** — largada por reação (queimar custa caro) e depois
  alternar ← → sem parar. Ele corre sempre um degrau acima do seu nível: dá
  para ganhar, mas nunca de graça.
- **A mochila dele** — tênis de treino, tênis de competição, munhequeira e
  energético, comprados com créditos.
- **"Preciso de um quarto homem"** — a seletiva do revezamento. Aparece quando
  o Lucas já corre e exige o cronômetro abaixo de 4,8 s.

### A progressão se SENTE

Velocidade e fôlego entram num lugar só do código — `passoPorQuadro()` — e por
isso mudam o jogo inteiro, não uma barra numa ficha:

- cada nível de velocidade acelera o passo em ~22%, do jardim à biblioteca;
- o tênis soma por cima do treino **e muda a cor do tênis do boneco**;
- com fôlego, segurar **SHIFT** dá arrancada, com poeira e rastro; o fôlego
  acaba, o Lucas fica sem ar e precisa recuperar antes de puxar de novo;
- e o **mesmo circuito**, corrido do mesmo jeito, fecha em **9,90 s no nível 0
  e 6,48 s no nível 4** — o teste mede isso a cada vez.

### A economia fecha

```
treinar (de graça, custa energia) -> velocidade 1 -> libera a corrida
   -> ganhar rende 60 créditos -> tênis de treino (45)
   -> tempos melhores -> seletiva (120) -> tênis de competição (140)
```

Nada é comprado com aura. A aura é medida social: ela **destrava** coisas (a
munhequeira do time só aparece com 250 de aura), e reputação e amizade com o
Téo viram **desconto** na mochila dele.

### E a ORION está vendo

As passadas contam. No capítulo 3, no perfil que ela monta, a ORION cita
quantas você treinou — e se você começou e parou.

## Como funcionam as atividades de aura

A regra é sempre a mesma, e nessa ordem:

```
AÇÃO ESCOLHIDA → PREPARAÇÃO → MINI-GAME → EXECUÇÃO VISUAL
              → REAÇÃO DO MUNDO → CONSEQUÊNCIA → RECOMPENSA
```

Nunca se escolhe uma opção e recebe "+150 aura". Primeiro é preciso **conseguir**,
depois se **vê** o Lucas fazendo, depois as pessoas em volta **reagem**, e só no
fim o número sobe. Se falhar, a falha também é uma cena — porque ninguém perde
aura em silêncio.

Tudo isso acontece **no mapa**: a câmera fecha em cima dos personagens, a escola
continua desenhada atrás e a plateia está ali de verdade.

### O duelo de aura com o Ruan (quadra)

Sete golpes, do mais barato ao mais caro. Quanto mais aura o golpe vale, mais
perguntas de humanas ele exige antes de sair. Cada golpe tem **coreografia
própria** de sucesso e de fracasso:

| Golpe | Aura | O que acontece na tela |
|---|---|---|
| Fazer o 67 | +150 | agacha, explode para cima, o 6 numa mão e o 7 na outra, vaivém, pose final |
| Responder só "ata" e sair andando | +90 | silêncio, a câmera fecha, "ata.", vira o corpo e começa a sair |
| Ajeitar a gola bem devagar | +110 | abaixa a cabeça, ajeita um lado, ajeita o outro, encara, sai |
| Invocar o Tung Tung Tung Sahur | +140 | três batidas no ar, cada uma mais forte, e o SAHUR |
| Sorrir de lado e sair andando | +170 | encara, sorriso de canto, pausa, vira e sai |
| Citar Sócrates no meio da treta | +210 | dedo em riste, a frase, e um único aplauso da plateia |
| Fazer o 67 de costas | +300 | vira de costas primeiro e faz sem olhar |

As falhas têm cena própria: o braço que trava no meio, o tropeço na hora de sair
andando, a mão que prende na gola e o branco de sete segundos.

### As outras três

- **Arremesso de papel** (quadra): cinco arremessos até o aro de verdade. Com
  três acertos na conta, a última bolinha sai **de costas**.
- **Máquina de lanche** (cantina): chutar exige dosar a força — fraco não derruba
  nada, forte demais quase derruba a máquina na frente de todo mundo. Abrir
  reclamação exige preencher os seis campos obrigatórios para receber "prazo
  estimado: 15 dias úteis".
- **Simulador do laboratório**: repetir a sequência. O terminal responde — pisca
  verde quando aceita, dá glitch vermelho quando recusa.

As atividades paralelas **não gastam eventos da história** e podem ser repetidas,
mas deixam flags pequenas (`fez_o_67`, `humilhou_ruan`, `vexame_na_quadra`,
`chutou_maquina`, `quase_derrubou_maquina`, `papel_na_cesta`) que mudam falas
depois.

## Como o código desenha gente

Existem dois desenhos do mesmo personagem, e é de propósito:

- **SPRITES** — o bonequinho pronto do mapa (16×17, 4 direções, 3 quadros). Anda
  e vira, e é o que aparece 99% do tempo.
- **Boneco articulado** (`desenharBoneco`) — o mesmo personagem montado por
  partes na hora: cabeça com expressão, tronco que inclina, dois braços com
  cotovelo, pernas que esticam num chute. Tem exatamente o tamanho do sprite,
  então entra no lugar dele dentro do mapa sem ninguém encolher ou flutuar.

Uma **coreografia** (`NUMEROS`) é uma função do tempo que posa cada ator quadro a
quadro, mais uma lista de **marcas** — coisas que acontecem num instante só (um
som, um NPC que ri, a tela que treme, a aura que sobe).

Os **figurantes** são alunos de fundo. Não falam, não entram na história e — de
propósito — **não bloqueiam a passagem** (se bloqueassem, um deles parado numa
porta poderia fechar o caminho até um objetivo). Eles respiram, viram a cabeça,
olham para quem passa perto, mexem no celular e reagem ao que acontece por perto.

## Os mini-games refeitos

Quase todos tinham virado a mesma coisa: ponteiro andando numa barra, aperte
no verde. Três foram reconstruídos com mecânicas de verdade — o detalhamento
completo está em [MINI-GAMES.md](MINI-GAMES.md).

| | Antes | Agora |
|---|---|---|
| **Arremesso de papel** | barra de timing | **posição + força**: você anda pela quadra e escolhe de onde atirar. Perto vale 1, do fundo vale 5. Segurar Z arma (o braço arma junto), soltar arremessa, e a bolinha cai onde a força mandou — curta, dentro ou passando direto. X finta. |
| **"Ata" e sair andando** | cutscene | **não reagir**: o controle volta para você e a regra é andar até a saída sem olhar para trás. O Ruan provoca cinco vezes, subindo o tom; apertar para o lado dele derruba tudo, e travar no meio também. X levanta a mão sem virar. |
| **Treino do Téo** | barra de timing | **circuito de cones** cronometrado (acima). |

Ainda são barras: o **discurso na assembleia** e o **chute na máquina**. Estão
na fila.

## A escola funcionando

O colégio não espera o Lucas. Se ele ficar parado meio minuto, alguma coisa
acontece — e não necessariamente perto dele.

São três camadas, da menor para a maior:

**1. Atividade** — o que UM aluno está fazendo agora. Onze rotinas curtas
(parar, mexer no celular, sentar, estudar, comer, encostar na parede, olhar
alguém, dar uma volta, mudar de ambiente) escolhidas pelo **lugar** e pelo
**jeito** de cada um: o estudioso estuda, o zoeiro vagueia, o quieto encosta
na parede. Quem lê aparece com livro na mão; quem come aparece mastigando.

**2. Convívio** — uma cena curta entre dois ou três alunos, com papéis:

| | |
|---|---|
| **a conversa** | um fala, o outro ri; se um terceiro passa, os dois olham e depois voltam ao assunto |
| **os livros** | um derruba tudo, o outro atravessa a cena para ajudar |
| **a bola** | dois batendo bola, e a bola cruza o quadro de verdade |
| **o carregador** | um atravessa o corredor para pedir, o outro nega com a cabeça |
| **a zoeira** | três rindo. O professor aparece e o silêncio é instantâneo. Ele passa, e eles voltam |

**3. Período** — o dia tem ANTES DA AULA → AULA → INTERVALO → SAÍDA, e o
**sinal não é um texto na tela**: ele para a escola inteira, todo mundo levanta
a cabeça, e só então cada um sai andando — um de cada vez, não em bloco. O
resultado é medido pelo teste `testar-vida.js`:

```
aula       -> SALA 102:13  CORREDOR:11  PROFESSORES:7  SALA 101:5  LABORATÓRIO:5
intervalo  -> CORREDOR:17  JARDIM:9  CANTINA:8  GINÁSIO:7
saída      -> JARDIM:18  PÁTIO:11  CORREDOR:8  GINÁSIO:6
```

Os **NPCs da história também têm agenda**: no intervalo o Gabriel está na
cantina de verdade e a Marina na biblioteca de verdade — e se o Lucas estiver
perto quando o sinal bate, ele vê os dois saírem da sala andando. E a relação
aparece no corpo: quem gosta de você cumprimenta de longe, quem não gosta vira
o rosto quando você chega perto.

## Como o mapa se explica sozinho

A pergunta que manda no cenário é uma só: **batendo o olho, dá para saber
onde eu estou?** Quatro coisas respondem isso.

### 1. A escada de valor do chão

Cada ambiente tem chão próprio, e eles formam uma escala do fechado para o
aberto. Você nunca precisa ler o nome do lugar para saber onde está:

| | |
|---|---|
| **sala de aula** | linóleo escuro e fosco, xadrez discreto, junta funda |
| **biblioteca** | carpete roxo de trama grossa — abafa som e abafa luz |
| **laboratório** | piso técnico, placa quadrada, junta acesa em ciano |
| **cantina** | ladrilho claro quadriculado, de lugar que se lava todo dia |
| **banheiro** | azulejo pequeno branco, frio |
| **corredor** | granilite claro e polido, o mais claro de dentro do prédio |
| **pátio coberto** | laje de concreto crua, junta larga, pilares |
| **calçada** | um degrau mais clara que o pátio, com meio-fio |
| **jardim** | grama |

Quanto mais claro o chão, mais "de passagem" é o lugar. Sala escura →
corredor claro → pátio mais claro → rua. A transição de dentro para fora
acontece sozinha, sem texto explicando.

### 2. A passada de acabamento

O mapa é um grid de 16px, mas a **leitura** não é. Depois de pintar os
tiles, uma passada percorre o mapa olhando cada vizinho e desenha o
acabamento em 2 a 6 pixels: sombra projetada embaixo de tudo que tem
altura, rodapé na base de cada parede, meio-fio onde a grama encontra a
calçada, degrau onde um piso vira outro, batente aceso e soleira em cada
porta, faixa de circulação no corredor, junta nas paredes longas e marca
de uso nos chãos grandes.

É o que dá a **resolução extra**: cada quadrado do mapa passa a ter borda,
canto e miolo próprios — o efeito de subdividir o bloco em quatro, sem
aumentar o corredor e sem mexer numa única coordenada do jogo. Roda uma
vez por cenário: custo zero por quadro.

### 3. As portas se anunciam

Toda porta tem batente aceso dos dois lados e joga luz no chão de quem
chega. Bate o olho e você sabe o que é passagem e para onde ela vai. O
corredor tem ainda **janelas altas** para as salas, que quebram o paredão
e deixam a luz de dentro vazar.

### 4. Foco por ambiente, e o Lucas achável

O ambiente onde o Lucas está fica com presença e o resto pesa — oito
camadas finas, borda macia, sem zoom e sem buraco negro: arquitetura,
gente e espaço continuam visíveis lá fora. E o Lucas tem contorno próprio
no sprite, poça de luz e sombra funda, para não sumir no chão claro do
corredor.

### As pessoas compõem, não entulham

Ninguém para em vão de porta (os tiles de passagem são proibidos), quem
está parado **encosta** — perto de parede, armário, banco ou mesa — e cada
ambiente tem **lotação**: quando enche, o próximo vai para o mais vazio.
É o que evita dezoito pessoas numa sala e a cantina vazia do lado.

## A interface não interrompe

A regra: **se não precisa parar o jogador, não para.**

Antes, toda atividade paralela terminava abrindo um painel no meio da tela
e exigia um ENTER para voltar a andar. Agora o desfecho de uma atividade é:

1. os números sobem **do próprio Lucas**, no mundo;
2. um aviso pequeno aparece no canto de baixo à direita —
   `ORION · Mandou bem no arremesso · TAB detalhes`;
3. ele some sozinho depois de alguns segundos;
4. o jogador nunca parou de andar.

Painel grande continua existindo **só para os desfechos da história** — ali
a interrupção é o ponto.

### Resumo agora, detalhe quando quiser

O texto inteiro de cada coisa que aconteceu fica guardado nos **REGISTROS**,
dentro do **TAB**. A ficha virou a central de informação, em duas colunas:

| | |
|---|---|
| **esquerda** | atributos, relacionamentos, velocidade, fôlego, recordes, itens |
| **direita** | a missão por extenso e os últimos registros da ORION, com os efeitos de cada um |

### A barra de cima só tem o que muda a decisão agora

Sobraram **dia, lugar e missão em uma linha**. Atributo, relação e aura
moravam lá chamando atenção o tempo inteiro sem nunca mudar nada — foram
para o TAB, e **aparecem sozinhos quando mudam**.

## Interação, portas e objetivos

A regra: **se o Lucas está claramente no lugar certo, o ENTER funciona.**

**Um sistema só** (`interacaoProxima()`) para gente, portas, máquinas, carteiras
e objetos de missão:

- alcança 1,5 tile em qualquer direção (diagonal incluída) e 2,2 tiles na
  direção em que o Lucas olha — dá para falar por cima de uma mesa, nunca
  através de parede;
- usa a posição real em pixels: NPC andando continua ao alcance no meio do passo;
- com mais de uma coisa perto, ganha a que a missão pede, depois a que ele
  olha, depois a mais perto;
- só entra quem tem algo a fazer — coisa decorativa não mostra ENTER;
- ao apertar, os dois se viram um para o outro.

O **prompt** é um só, pequeno: `ENTER` + verbo, em cima da coisa — ou embaixo,
se ela estiver abaixo do Lucas, para nunca cobrir o personagem. No NPC ele toma
o lugar da plaquinha do nome. O evento pode trocar o verbo com `verbo:`.

**Objetivo de lugar** (`zona:'SALA 102'`): chegar já dispara o evento. Resolveu
"Ir para a Sala 102" (antes era preciso achar o Gabriel e ficar de frente) e
"Voltar para a Sala 102" (antes acontecia sozinho, onde você estivesse).

**Coisa igual funciona igual**: as três fileiras de bancadas do laboratório, os
três murais, as quatro pias e todas as carteiras da Sala 102 respondem.

**Portas**: todas têm batente, luz no chão e placa, e a folha conta o que tem
do outro lado — número na sala de aula, bonequinhos no banheiro, livro na
biblioteca, vidro de correr no laboratório, vaivém na cantina, moldura dourada
com xícara na sala dos professores, porta dupla laranja no ginásio. Porta
**aberta** mostra a folha encostada e o chão no vão; porta **fechada** tampa a
passagem: o depósito do corredor (trancado, luz vermelha) e o portão do campus.
As duas explicam com ENTER por que não abrem.

**Orientação pelo cenário**: as placas do jardim, do corredor e do ginásio dizem
onde fica cada coisa. A ajuda de direção (três pontinhos e o nome do lugar) só
aparece quando o jogador para e hesita, e nunca dentro do ambiente certo.

## Um lugar usado por pessoas

A régua do acabamento visual: *isso parece um lugar construído e usado, ou um
conjunto de tiles colocado para cumprir função?* Três ferramentas fazem o
trabalho, e servem para qualquer ambiente novo:

- **Variação por lugar** (`DETALHES`): o mesmo objeto muda um pouco conforme a
  posição — outra planta no vaso, outra cor de pufe, um copo esquecido no banco,
  a cadeira que ninguém alinhou, a lixeira mais cheia. A variação sai de um
  número fixo por posição, então o colégio não muda sozinho de um dia para o outro.
- **Camada da frente** (`montarFrente`): o que é mais alto que um tile — o topo
  dos pilares do pátio, a copa das árvores — é desenhado depois das pessoas. Quem
  passa atrás some atrás do concreto; a copa que cobre o Lucas fica transparente.
- **Pátina** (`decorarFundo`, 5a): chão usado tem marca. Mancha, trinca, risco de
  sapato, grama brotando na junta — pouco, e só no chão de circulação.

O que cada ambiente ganhou:

| | |
|---|---|
| **pátio** | navegação primeiro: entre a primeira e a última porta nada sólido no chão, só o painel da ORION. A estrutura está nas paredes — pilastras de concreto em par (parede das salas e fachada), emoldurando a porta principal, o ginásio e o painel, com a sombra da viga cruzando o chão e a claridade da claraboia em cada vão. Vasos só nos quatro cantos; bancos, mesas, pufes, lixeiras e bebedouro nos dois extremos |
| **jardim** | árvores com copa e sombra (dois ipês, um amarelo e um roxo), mosaico do sol nascente no meio da praça, trilha gasta até as bicicletas |
| **corredor** | piso tátil amarelo, faixa de cor por bloco (terracota A, ocre B) com a letra, extintor, relógio, cartazes |
| **salas** | cadeira em cada carteira (verde na 101, azul na 102), coisas em cima, quadro com restos de aula, calendário e trabalhos |
| **laboratório** | bancadas montadas em postos (monitor, osciloscópio, kit de robótica), banquinhos, armários de componentes, caixas de tomada |
| **biblioteca** | estantes variadas com etiqueta de categoria, mesas de leitura com luminária, canto de leitura com tapete, balcão da bibliotecária |
| **banheiros** | bancada com cuba, torneira e espelho, cabines com trinco livre/ocupado, uma entreaberta |
| **cantina** | balcão em partes (vitrine de salgados, caixa, bandejas, geladeira), mesas de refeitório com bancos, marcação da fila |
| **professores** | mesa de reunião contínua, cantinho do café, mural de cortiça |
| **quarto** | pôster, mural, mochila, tênis, blusa no chão, luminária |

Cor: tecnologia aparece onde faz sentido (laboratório, ORION, telas). Banco,
vaso, lixeira, pilar e flor não brilham.

## Arquivos

| Arquivo | O que é |
|---|---|
| `index.html` | **o jogo** (HTML + CSS + JavaScript num arquivo só) |
| `versao-texto.html` | primeira versão, só texto — funciona sozinha |
| `mapa-do-campus.png` | o colégio inteiro numa imagem só |
| `quarto-do-lucas.png` | o quarto da introdução |
| `personagens.png` | retratos e bonequinhos de mapa de todo mundo |
| `bonecos.png` | o boneco articulado em várias poses e caras |
| `telas-do-jogo.png` | prints das telas do jogo |
| `animacao-67.png` | a coreografia do 67, quadro a quadro |
| `testes/` | scripts que jogam o jogo sozinhos para conferir se nada quebrou |

## Testes

Rodam com Node.js, dentro da pasta `testes`:

```bash
node testar-jogo-2d.js
```

- `testar-jogo-2d.js` — joga 6 partidas inteiras, do quarto até o final, andando
  pelo mapa de verdade
- `testar-desafios.js` — confere os desfechos dos desafios da história
- `testar-extras.js` — confere as atividades de aura (ganhar, perder e repetir)
- `testar-vida.js` — a escola continua existindo sozinha: mede quantas rotinas
  diferentes acontecem, quantas cenas entre alunos começam sem o jogador, o que
  o sinal faz com o colégio e se dá para andar até todos os ambientes
- `testar-ginasio.js` — a progressão de velocidade se sente no passo, a arrancada
  acaba e volta, a loja respeita requisitos e desconto, a corrida é vencível e
  perdível, e a missão do revezamento fecha
- `testar-cenas.js` — roda **todas** as coreografias quadro a quadro e confere que
  nenhum boneco sai voando, que o número de aura entra uma vez só, que a câmera
  volta para o jogador e que os figurantes não fecham caminho
- `testar-interacao.js` — ENTER funciona perto (de qualquer lado) e não de longe
  nem através de parede, toda porta funciona nos dois sentidos, ninguém nasce em
  parede, o mais relevante ganha, o prompt some ao afastar, objetivo de lugar
  avança ao chegar, NPC andando continua falável, porta trancada segue trancada
  e objeto igual responde igual; que a decoração não fechou caminho nenhum; e que
  no pátio nenhum móvel obriga a contornar (28 rotas entre portas, saídas e
  pontos de parada comparadas com o pátio vazio)
- `testar-mouse.js` — confere o jogo no mouse e mede a velocidade do passo
- `testar-baloes.js` / `testar-diagramacao.js` — nada estoura caixa nem sai da tela
- `testar-versao-texto.js` — a primeira versão, só texto, continua jogável

Conferência visual (geram PNG, sem abrir navegador):

- `ver-mapa.js [escala] [quarto] [--limpo] [--saida=arquivo.png]` — o cenário
  inteiro numa folha só. Sem `--limpo` marca NPCs, figurantes e objetos com
  cruzinhas; com `--limpo` sai só o cenário. É assim que se regeneram as imagens
  da pasta:
  `node testes/ver-mapa.js 2 --limpo --saida=mapa-do-campus.png` e
  `node testes/ver-mapa.js 3 quarto --limpo --saida=quarto-do-lucas.png`
- `ver-ambientes.js [nomes...]` — cada ambiente na câmera real do jogo, com a
  escola funcionando (pátio, jardim, salas, biblioteca, cantina, banheiros...)
- `ver-telas.js` — 21 telas do jogo
- `ver-atores.js` — o boneco articulado em várias poses
- `ver-duelo.js [golpe] [falha]` — a coreografia de um golpe, quadro a quadro
- `ver-cena.js [cesta|maquina|...]` — as outras cenas de ação
- `ver-minijogos.js` — folha de contato dos três mini-games refeitos
- `ver-arremesso.js` — o arremesso quadro a quadro (armar, soltar, curta, longa)
- `ver-foco.js` — o foco de ambiente: a zona do Lucas clara, o resto pesado
- `ver-escola.js` — a escola funcionando: oito lugares em momentos diferentes do dia
- `ver-dia1.js` — o Dia 1: a chegada, o sinal, o professor entrando, o intervalo
- `ver-minijogos2.js` — o chute na máquina e a assembleia
- `ver-ginasio.js` — o ginásio de quatro ângulos
- `ver-interface.js` — barra de cima, aviso da ORION e a ficha do TAB
- `ver-personagens.js` — retratos e sprites

Para olhar no navegador com ferramenta de automação (para jogar não precisa —
dois cliques no `index.html` bastam):

```bash
node testes/servidor-local.js
```

Onde o código está organizado (dentro de `index.html`, na ordem): mapa do
colégio, motor de cenários, sons, sprites e retratos, tiles, estado da história,
eventos, finais, jogador e câmera, boneco articulado, figurantes e reações,
motor de coreografia, coreografias do duelo, desafios, movimento e desenho.
