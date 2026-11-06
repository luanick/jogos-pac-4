# Mini-games: auditoria e o que já foi refeito

Levantamento de tudo que existe, o que estava repetitivo e o que cada um
virou. Feito porque quase todos tinham caído no mesmo molde: **ponteiro
andando numa barra, aperte no verde**.

## A linguagem de controle (padronizada)

Um jogo de PC, sem analógico. Então:

```
WASD / setas  = direção e posição   (o "analógico")
Z             = AÇÃO 1   (principal: confirmar, arremessar, puxar)
X             = AÇÃO 2   (secundária: finta, respirar, levantar a mão)
C             = AÇÃO 3   (especial: pose)
TAB           = ficha do personagem   (era C — o C precisava ficar livre)
SHIFT         = arrancada no mapa     (o X também corria; não corre mais)
```

Nenhum mini-game inventa tecla própria. Se não couber em WASD + Z/X/C,
a mecânica está complicada demais.

## Estado de cada um

| Mini-game | Mecânica | Situação |
|---|---|---|
| Bolinha de papel (história) | esperar a professora virar e apertar | ok — leitura de situação |
| Passar cola (história) | segurar e soltar na hora certa | ok — risco contínuo |
| Simulador do laboratório | repetir sequência de setas | memória; genérico, mas cabe |
| Duelo de aura (Ruan) | quiz de humanas + coreografia | ok — o quiz não é barra |
| **Arremesso de papel** | **posição + força** | **REFEITO** |
| **"Ata" e sair andando** | **não reagir, andando** | **REFEITO** |
| **Treino do Téo** | **circuito de cones cronometrado** | **REFEITO** |
| Corrida contra o Téo | alternar ← → | mash; funciona, é a "prova" do circuito |
| **Discurso na assembleia** | **ritmo de tom, plateia visível** | **REFEITO** |
| **Chute na máquina** | **ler onde travou e acertar abaixo** | **REFEITO** |
| Reclamação na máquina | apertar ENTER seis vezes | trivial, mas a graça é a piada |

Eram **quatro** barras de timing. Agora são **zero**. A regra continua valendo:
uma barra pode existir em UMA atividade específica, nunca como molde do jogo.

---

## 1. Arremesso de papel — REFEITO

De barra para **posição + força**.

- o jogador **anda pela quadra** (WASD) e escolhe de onde arremessar;
- a distância é o problema: colado no aro **VALE 1**, lá do fundo **VALE 5**,
  e o número aparece em cima da cabeça dele enquanto ele escolhe;
- **segurar Z** carrega a força — o braço arma junto, e o medidor nasce do
  ombro dele, no mundo, não numa barra de tela;
- **soltar Z** arremessa com a força acumulada;
- passar da força é tão ruim quanto faltar: existe uma linha vermelha de
  "demais" e o corpo treme quando ele passa dela;
- a bolinha **cai onde a força mandou**: curta, dentro ou passando direto —
  é assim que se aprende a distância, sem número nenhum explicando;
- a tela diz depois: `CURTA POR POUCO`, `MUITO CURTA`, `PASSOU DIRETO`, `+5`;
- **X** finta: o braço vai e volta, a quadra reage, nada é gasto;
- **C** é a pose de convencido, liberada com 4 pontos na conta;
- **conhecimento ≥ 55** desenha a marca da força certa no medidor — o
  atributo faz alguma coisa de verdade;
- a câmera abre conforme ele recua, para o aro nunca sair do quadro.

A nota é por **pontos**, não por cestas: cinco cestas de perto (5) valem
menos que duas do fundo (10). Duas pessoas com a mesma pontaria podem
terminar com aura muito diferente, porque a decisão é **de onde**.

## 2. "Ata" e sair andando — REFEITO

De cutscene para **sair andando de verdade**.

- a abertura é a cena de sempre, cortada no instante em que ele diz "ata"
  e vira o corpo;
- daí o **controle volta para o jogador**, com uma regra só na tela:
  `NÃO OLHE PARA TRÁS`;
- é preciso caminhar até a **saída marcada no chão** (o vão do corredor;
  quando está fora da tela, o farol cola na borda como seta);
- **apertar para o lado do Ruan derruba tudo** — ele vira, o Ruan abre os
  braços e a quadra filma;
- **parar no meio também custa**: passou de uns segundos parado, vira piada
  sozinho (custa menos que olhar, mas custa);
- o Ruan não desiste: cinco provocações entram sozinhas, subindo de tom
  (`ata? ATA?!` → `volta aqui` → `OLHA PRA MIM` → `tô falando com você!`);
- **X** levanta a mão sem virar — só vale **durante** uma provocação, e
  rende 40 de aura a mais;
- a câmera segura os dois: o Ruan vai encolhendo no fundo do quadro
  enquanto o Lucas se afasta.

A piada virou a dificuldade: o difícil é **não reagir**.

## 3. Treino do Téo — REFEITO (circuito)

De barra para **percurso contra o relógio**.

- volta completa na pista, quatro marcas, bandeirinha verde na marca da vez;
- **oito cones** espalhados nas três raias: passar por cima, por baixo,
  ou atropelar e pagar o preço;
- **Z puxa** (arrancada) e gasta fôlego; **X para e respira**, recupera
  rápido mas o relógio não para;
- bater num cone derruba — e derruba **mais feio quem bate puxando**
  (52 quadros no chão contra 24);
- o fôlego fica preso ao Lucas, na lateral dele, não numa ficha;
- **o tempo é a nota**: abaixo de 5,5 s vale 8, acima de 13 s vale 1.

E é aqui que a progressão se sente: como o passo do jogo inteiro sai de
`passoPorQuadro()`, subir de VELOCIDADE derruba o tempo da volta sozinho.
Medido pelo teste, no mesmo percurso e com a mesma condução:

```
nível 0:  9,90 s   ->   nível 4:  6,48 s
```

## 4. Chute na máquina — REFEITO

De barra de força para **leitura**.

- a máquina abre num **close** da frente dela, com o mundo vivo atrás;
- o salgado está **travado numa mola visível**, com uma setinha piscando;
- WASD escolhe entre nove pontos: três colunas e três alturas;
- acertar é bater **logo abaixo de onde ele travou**, na mesma coluna;
- a faixa de cima é o **VIDRO** — chutar ali é o vexame, e a tela avisa;
- **X chacoalha** antes: o salgado desce uma mola (o chute fica fácil), mas
  alguém repara em você.

Não existe força: existe olhar para a máquina antes de chutar.

## 5. Discurso na assembleia — REFEITO

De barra de timing para **ritmo**, com a plateia como medidor.

- não há barra de atenção: há **32 pessoas desenhadas**. Elas vão virando de
  lado sozinhas, pegando o celular, se desligando — e você **conta cabeças**;
- a cada rodada você escolhe entre três falas, uma de cada tom:
  **FATO**, **PIADA**, **APELO**;
- ninguém aguarda dois argumentos do mesmo tom seguidos: o ritmo que funciona
  é **fato → piada → apelo → fato**. Repetir o tom esvazia o pátio;
- acertar o ritmo faz as cabeças voltarem, uma a uma, na tela;
- **X pede silêncio**, uma vez só: a plateia para de escorrer por uns segundos.

Três argumentos que peguem e a votação é sua.

## O que ainda é simples demais

- **Reclamação na máquina**: seis ENTERs. É de propósito — a piada é a
  burocracia —, mas não é jogo.
- **Simulador do laboratório**: repetir sequência de setas. Funciona, é
  genérico. Se um dia sobrar espaço, vira leitura de log.
- **Corrida contra o Téo**: alternar ← →. É a prova do circuito, e o mash
  combina com correr — fica.

## A régua

Antes de dar um mini-game por pronto:

1. estou controlando alguma coisa, ou só esperando o momento?
2. tenho decisões (onde ficar, quando ir, o que arriscar)?
3. existe habilidade que melhora com a prática?
4. é diferente dos outros mini-games do jogo?
5. eu jogaria isso sem a recompensa?

Se alguma resposta for não, refaz.

## Como conferir sem abrir o navegador

```
node testes/testar-extras.js      # arremesso, "ata" e a máquina
node testes/testar-desafios.js    # a assembleia e os desafios da história
node testes/testar-ginasio.js     # circuito, progressão e a prova do tempo
node testes/ver-minijogos.js      # arremesso, "ata" e circuito, em PNG
node testes/ver-minijogos2.js     # máquina e assembleia, em PNG
node testes/ver-arremesso.js      # só o arremesso, quadro a quadro
```
