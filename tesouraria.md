# Tesouraria da tribo: instalação do servidor

A Tesouraria mostra o estoque de relíquias e bandeiras de todos os membros da tribo e permite empréstimos entre eles, com reserva de horário, devolução automática e caução opcional. Para funcionar, **uma pessoa da tribo** precisa rodar o servidor (o arquivo `server.py` desta pasta). Os outros membros só se cadastram.

## Segurança

- **Nada sai sem o dono aceitar.** Todo pedido espera o **Aceitar** dele, e antes aparece o resumo e o histórico de quem pede.
- Cada relíquia pode ser marcada como **🔒 não emprestar**.
- **Só entra quem tem a chave da tribo** e foi aprovado pelo admin. Se a chave vazar, o admin troca.
- Os dados ficam **só no servidor da tribo**: quem o roda é o responsável por eles.

## 1. Rodar o servidor (Windows, sem saber programar)

1. **Instale o Python**: [python.org/downloads](https://www.python.org/downloads/). Na 1ª tela do instalador, **marque "Add python.exe to PATH"** e clique em **Install Now**.
2. Crie uma pasta (ex.: `C:\tesouraria`) e coloque nela o arquivo `server.py`.
3. Abra a pasta no Explorador de Arquivos, clique na barra de endereço, apague, digite `cmd` e aperte Enter. Abre uma janela preta já nessa pasta.
4. Digite `set TRUST_PROXY=1` e Enter; depois `python server.py` e Enter. Aparece `Tesouraria em http://127.0.0.1:8787`. **Deixe a janela aberta.**
5. Teste no navegador: `http://127.0.0.1:8787/v1/health` deve mostrar `{"ok": true, ...}`.

Mac ou Linux: os mesmos passos, com `python3 server.py`.

## 2. Liberar para a tribo (endereço na internet, grátis)

O servidor no seu PC só você enxerga. Um túnel grátis da Cloudflare dá um endereço https para a tribo:

1. Baixe o `cloudflared-windows-amd64.exe` na [página de releases do cloudflared](https://github.com/cloudflare/cloudflared/releases), renomeie para `cloudflared.exe` e coloque na mesma pasta.
2. Abra **outra** janela `cmd` na pasta (passo 3 acima) e rode: `cloudflared tunnel --url http://127.0.0.1:8787`
3. Ele mostra um endereço `https://alguma-coisa.trycloudflare.com`. **Deixe essa janela aberta também.**

## 3. Cadastrar a tribo

1. No script: **⚙ Config → 🛠 Diagnóstico e Tesouraria**. Em **Servidor**, cole o endereço https; em **Chave da tribo**, invente uma senha (mín. 6 letras) e clique em **Cadastrar**. Você vira o admin.
2. Passe o endereço e a chave **só para a tribo**, em mensagem privada.
3. Cada membro faz o mesmo, com a mesma chave, e fica "aguardando". Você aprova em **👥 Membros**.

## Bom saber

- O PC precisa ficar **ligado com as duas janelas abertas**. Se desligar, a Tesouraria para; nada se perde e ela volta quando religar.
- O túnel grátis **muda de endereço** quando reinicia: todos trocam o Servidor e clicam em **Cadastrar** de novo, com a mesma chave.
- O servidor guarda uma cópia do banco a cada 6 h na pasta `backups`.
- Para um endereço fixo e sempre ligado (servidor alugado com HTTPS), veja [DEPLOY.md](DEPLOY.md).
- Detalhes técnicos e a API: [README.md](README.md) desta pasta.
