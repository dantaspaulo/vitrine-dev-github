# Política de privacidade do Vitrine Dev para GitHub

Última atualização: 16 de outubro de 2026.

O Vitrine Dev para GitHub é um plugin gratuito e de código aberto (licença MIT) para o Claude. Ele é
feito de instruções em texto e de um script em Python que rodam no ambiente de quem usa. **O plugin
não tem servidor, não coleta dados e não envia nada ao autor.** O autor não recebe, não vê e não
guarda nenhum dado de quem usa o plugin.

## Que dados o plugin lê

- **Dados públicos do perfil do GitHub** que você indicar: nome, bio, empresa, site, localização,
  repositórios públicos, repositórios fixados e contagem de contribuições. A leitura é feita pelo
  GitHub CLI (`gh`) instalado na sua máquina, com a sua própria sessão do GitHub.
- **Os textos que você mesmo fornece** durante a conversa: posicionamento, cases, números, contatos
  (por exemplo, o seu e-mail) e a lista de nomes que não podem aparecer (`nao-citar.txt`).
- **Páginas que você indicar**, como o seu site ou o seu LinkedIn, lidas pelo Claude com as
  ferramentas dele, como em qualquer conversa.

## Para onde os dados vão

- **GitHub.** Na prévia, o texto do README gerado vai para a API de Markdown do GitHub
  (`gh api markdown`), só para mostrar como o GitHub vai exibir a página. Sem o `gh` instalado, nada é
  enviado. A publicação (commit e push no seu repositório `USUARIO/USUARIO`) só acontece quando você
  manda, e o que for publicado ali fica público, como todo repositório público do GitHub.
- **Serviços públicos de imagem usados no README gerado:** capsule-render.vercel.app,
  readme-typing-svg.demolab.com, img.shields.io e skillicons.dev. O seu nome, a frase do topo, os
  nomes da sua stack e os rótulos dos botões de contato vão no endereço dessas imagens, e quem visita
  o seu perfil carrega as imagens desses serviços. Cada serviço segue a própria política.
- **Claude.** O plugin roda dentro das suas conversas com o Claude, que seguem a
  [política de privacidade da Anthropic](https://www.anthropic.com/legal/privacy).

Os dados não vão para nenhum outro lugar.

## O que fica guardado

O plugin não guarda nada por conta própria. Os arquivos de trabalho (`perfil.json`, `nao-citar.txt`
e a prévia) ficam numa pasta da sua máquina, fora do repositório público, e você pode apagá-los
quando quiser. O README e os cartões ficam no seu repositório do GitHub, se você decidir publicar.

## Público

O plugin não é destinado a menores de 18 anos.

## Contato

Paulo Sérgio Dantas, autor do plugin: contato@paulosdantas.adv.br. Dúvidas e problemas também podem
ser abertos em [github.com/dantaspaulo/vitrine-dev-github/issues](https://github.com/dantaspaulo/vitrine-dev-github/issues).

## In English

Vitrine Dev for GitHub has no server, collects no data and sends nothing to its author. It reads
public GitHub profile data through your own `gh` session and the texts you provide; it sends the
generated README to GitHub's Markdown API for the preview and pushes to your profile repository only
when you say so. The generated README loads images from capsule-render.vercel.app,
readme-typing-svg.demolab.com, img.shields.io and skillicons.dev, with your name and labels in the
image URLs. Working files stay in a folder on your machine. Your conversations with Claude follow
Anthropic's privacy policy. Contact: contato@paulosdantas.adv.br.
