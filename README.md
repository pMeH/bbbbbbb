# Userscript para TW

Agenda ataques, apoios, nobres e fakes com precisão de milissegundos, e automatiza recursos, academia, saque, coleta, treino de paladino, modo de férias, melhorias de mapa. Tudo pelo painel que abre dentro do jogo.

> **Projeto independente, gratuito e sem fins lucrativos**, sem qualquer ligação, parceria ou aprovação da desenvolvedora do jogo. Leia o [Aviso legal](#aviso-legal) antes de usar.

## Por que este projeto existe

Pela nossa experiência, a grande maioria de quem joga competitivamente já usa scripts. Quem joga sem eles pode receber milhares de comandos, e não há como uma pessoa defender isso na mão.

A ideia deste projeto é **deixar o jogo mais equilibrado**: que ninguém precise pagar por scripts ou manter multicontas para conseguir jogar de igual para igual. Por isso ele é gratuito e de código aberto.

O projeto é **aberto a contribuições**: correções, melhorias e novas funções são bem-vindas por pull request, assim como relatos de problemas nas issues.

## Como instalar

1. Instale a extensão **Tampermonkey** no seu navegador (Chrome, Edge ou Firefox): [tampermonkey.net](https://www.tampermonkey.net/).
2. Aqui no GitHub, abra o arquivo `agendador-tw.user.js` e clique em **Raw**.
3. O Tampermonkey abre a tela de instalação: clique em **Instalar**.
   - Se não abrir sozinho: copie todo o conteúdo do arquivo, clique no ícone do Tampermonkey → **Criar um novo script**, apague o que vier, cole e salve (Ctrl+S).
4. No Chrome/Edge: em `chrome://extensions`, ligue o **Modo do desenvolvedor** (nas versões mais novas: Tampermonkey → **Detalhes** → **Permitir scripts do usuário**). Sem isso o script não roda.
5. Entre no jogo e recarregue a página. O botão do Agendador aparece na tela (atalho **Alt+Q** abre e fecha o painel).

Para atualizar: repita os passos 2 e 3 com o arquivo novo.

## Observações

- **A precisão varia.** Nos nossos testes, o comando chega entre **0 e 350 ms** do horário pedido. Ainda não sabemos se isso vem do servidor do jogo ou se o script pode melhorar. Por isso, **sempre deixe um intervalo entre os envios** (ex.: limpeza e nobre com algumas centenas de ms de diferença), para a ordem de chegada não trocar.
- **Verificação do jogo (captcha):** o script **não resolve nem contorna** a verificação. Quando ela aparece, ele **para tudo** até você resolvê-la no jogo e clicar em Retomar.
- **Módulo de relíquias (Tesouraria da tribo):** precisa que uma pessoa da tribo rode o servidor da Tesouraria. Sem ele, o resto funciona normalmente. Veja abaixo.

## Servidor da Tesouraria (módulo de relíquias)

A Tesouraria deixa a tribo ver o estoque de relíquias e bandeiras de todos os membros e emprestar entre si, com reserva de horário, devolução automática e caução opcional. Nada sai sem o dono aceitar.

Ela precisa de um pequeno servidor (1 arquivo em Python, sem banco de dados para instalar), rodado por **uma pessoa da tribo** no próprio PC ou num servidor alugado. Os arquivos estão na pasta `modulo_reliquia`.

**Guia de instalação passo a passo:** [modulo_reliquia/tesouraria.md](modulo_reliquia/tesouraria.md)

## Aviso legal

- **Sem ligação com a desenvolvedora do jogo.** Este é um projeto independente de fãs, sem parceria, patrocínio ou aprovação de quem desenvolve ou publica o jogo. Nomes e marcas do jogo pertencem aos seus donos.
- **Risco para a conta.** O uso de scripts pode violar os termos de uso do jogo e levar à **punição ou ao banimento da conta**. Antes de usar, leia as regras do seu mundo. Quem instala e usa assume esse risco.
- **Sem garantia.** O software é fornecido **"como está"**, sem garantia de qualquer tipo. Os autores e contribuidores não se responsabilizam por banimentos, perdas no jogo, comandos que não saírem ou chegarem fora do horário, nem por qualquer outro dano decorrente do uso.
- **Gratuito.** O projeto não é vendido e não tem fins lucrativos. Desconfie de quem cobrar por ele.
- **Privacidade.** Os autores não recebem nenhum dado de quem usa. As configurações ficam no navegador de cada um. Os avisos opcionais (e-mail e notificação no celular) e a Tesouraria só enviam dados se você ligar essas funções. Quem roda o servidor da Tesouraria é o responsável pelos dados da sua tribo.
- **Conteúdo do jogo.** Este repositório não contém arquivos, imagens nem código do jogo.
