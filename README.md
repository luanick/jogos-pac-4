# Jogos PAC 4

Repositório com os jogos desenvolvidos pelas equipes do PAC 4.

## Jogos
| Jogo | Pasta | Plataforma |
|---|---|---|
| Dimi's Ink Test | [`dimis-ink-test/`](dimis-ink-test/) | Windows |
| Efeito Dominó: Futuro em Jogo | [`efeito-domino/`](efeito-domino/) | Navegador |
| GeoMath | [`geomath/`](geomath/) | Windows |
| Léo na Amazônia | [`leo-na-amazonia/`](leo-na-amazonia/) | Windows |
| Profundo Abismo de Cálculo | [`profundo-abismo-de-calculo/`](profundo-abismo-de-calculo/) | Windows |
| Viagem Pelas Eras | [`viagem-pelas-eras/`](viagem-pelas-eras/) | Windows |
| Wizards of the Mathemagics | [`wizards-of-the-mathemagics/`](wizards-of-the-mathemagics/) | Navegador |

Abra a pasta do jogo e leia o `RESUMO_DO_JOGO.md`: ele explica o jogo, como baixar e jogar, e traz o link da pesquisa de opinião.

## Como o repositório é organizado
```
nome-do-jogo/
├── RESUMO_DO_JOGO.md   resumo do jogo, controles e link da pesquisa
├── executavel/         o jogo pronto para rodar (sem código-fonte)
├── documentacao/       GDD ou documento do jogo
└── video/              vídeo do jogo
```

## Sobre os executáveis
- Os jogos ficam compactados em `.zip`. **Extraia o zip antes de jogar**: alguns jogos precisam de outros arquivos na mesma pasta do `.exe`.
- O GitHub não aceita arquivos acima de 100 MB. Jogos maiores que isso ficam na aba **[Releases](https://github.com/luanick/jogos-pac-4/releases)**, uma por jogo, e a pasta `executavel/` do jogo leva até ela.
- Nos jogos para Windows, o aviso azul **"O Windows protegeu o computador"** é normal. Clique em **Mais informações** e depois em **Executar assim mesmo**.

## Adicionar um jogo novo
1. Crie uma pasta com o nome do jogo em letras minúsculas e com hífens (ex.: `meu-jogo`).
2. Dentro dela, crie `executavel/`, `documentacao/`, `video/` e um `RESUMO_DO_JOGO.md` (use outro jogo como modelo).
3. Se o executável passar de 100 MB, publique em **Releases** com a tag `nome-do-jogo-v1.0` e coloque o link em `executavel/`.
4. Acrescente o jogo na tabela acima.
