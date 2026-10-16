# Vitrine Dev para GitHub

O Claude transforma o seu perfil do GitHub numa vitrine que se lê em 20 segundos: quem você é, o
que você entrega e a prova disso. O resultado é o `README.md` do repositório especial
`USUARIO/USUARIO` e uma pasta `assets/` com cartões SVG animados: cases com problema, solução e
resultado, números, papéis atuais, método de trabalho, projetos abertos e stack. Cada bloco sai
também numa versão própria para celular.

## Instalar

No Claude Code (versão 2.1.275 ou mais nova), em um passo:

```
/plugin install vitrine-dev-github --marketplace dantaspaulo/vitrine-dev-github
```

Em versões anteriores, em dois passos:

```
/plugin marketplace add dantaspaulo/vitrine-dev-github
/plugin install vitrine-dev-github@dantaspaulo
```

## Como usar

Peça com as suas palavras, por exemplo:

- "deixa meu perfil do GitHub com cara de portfólio, meu usuário é fulano"
- "quero colocar meus cases no GitHub sem citar os clientes"
- "alinha meu GitHub com o meu site novo"

Ou chame a skill direto: `/vitrine-dev-github:perfil-github`.

O Claude então:

1. lê o que já é público: o seu perfil, o README atual e o site ou LinkedIn que você indicar;
2. pergunta só o que falta, em até três rodadas curtas, sempre com um rascunho para você aprovar;
3. guarda os seus textos num `perfil.json` fora do repositório público e gera o README e os cartões;
4. confere tudo: recusa publicar se um nome da sua lista `nao-citar.txt` aparecer, se um texto não
   couber no cartão ou se algo parecer senha, IP ou rascunho;
5. mostra uma prévia de computador e de celular lado a lado, e só publica com o seu ok.

Cliente que não autorizou o nome entra pelo setor e pelo porte. Número só entra com fonte e data.

## O que precisa ter

- `python3` e `git`.
- Opcional: o GitHub CLI (`gh`) logado, para o diagnóstico do perfil e a prévia igual à do GitHub.
- Opcional: Playwright, para capturar a prévia nos tamanhos de computador e de celular.

Pensado para o Claude Code, onde o Claude usa o `gh` e o `git` da sua máquina. Sem o `gh`, o
script continua montando e conferindo os arquivos, e o diagnóstico e a publicação ficam com você.

## O que o plugin roda, envia e busca

- **Roda** só o `scripts/perfil.py` (Python padrão, código aberto e legível, sem dependências) e,
  se estiverem instalados, o `gh` e o `git` da sua máquina. Não tem hook, servidor MCP nem
  instalação de pacote.
- **Lê do GitHub**, pelo `gh` e com a sua própria sessão, dados públicos do perfil que você indicar:
  nome, bio, empresa, site, repositórios, fixados e contagem de contribuições.
- **Na prévia, envia** o texto do README gerado para a API de Markdown do GitHub (`gh api markdown`),
  só para ver como o GitHub vai mostrar. Sem o `gh`, nada é enviado e a prévia mostra só os cartões.
- **O README gerado usa imagens de serviços públicos:** capsule-render.vercel.app (faixa do topo e
  do rodapé), readme-typing-svg.demolab.com (frases que se digitam), img.shields.io (botões de
  contato e de stack) e skillicons.dev (ícones da stack). O seu nome, a frase do topo e os nomes da
  stack vão no endereço dessas imagens, e quem visita o seu perfil as carrega desses serviços.
- **Publica** (commit e push no seu repositório `USUARIO/USUARIO`) só quando você manda.
- **Não guarda nada.** O `perfil.json` e o `nao-citar.txt` ficam numa pasta sua, fora do
  repositório público, e não vão para lugar nenhum.

Se você indicar um site ou um LinkedIn, o Claude lê essas páginas com as ferramentas dele, como em
qualquer conversa.

## Licença

MIT. Feito por [Paulo Sérgio Dantas](https://github.com/dantaspaulo). Código e exemplos em
[dantaspaulo/vitrine-dev-github](https://github.com/dantaspaulo/vitrine-dev-github).

## In English

Vitrine Dev turns your GitHub profile README into a portfolio that reads in 20 seconds: animated
SVG case cards (problem, solution, result), numbers with a source and a date, a mobile version of
every block, a side-by-side preview before anything is published, and a guard that refuses to
publish any client name on your do-not-cite list. The skill speaks Brazilian Portuguese. It runs
only a readable standard-library Python script plus your own `gh` and `git`, reads public profile
data from GitHub, sends the generated README to GitHub's Markdown API for the preview, and pushes
only when you say so.
