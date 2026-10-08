# 🔮 Meus Consulentes

CRM simples para cartomante. Funciona direto no navegador e pode ser instalado no celular como um app (PWA), sem servidor, sem cadastro e sem mensalidade.

## O que ele faz

- **Consulentes:** cadastro com nome, WhatsApp, nascimento, observações e data de retorno.
- **Atendimentos:** histórico de cada pessoa com data, tiragem, valor e anotações.
- **Catálogo de tiragens:** ao escolher a tiragem, o valor é preenchido sozinho.
- **Agenda:** leituras marcadas por dia (Hoje, Amanhã, Atrasado), com controle de Pix confirmado. O botão **✓ Feita** envia o atendimento direto para o histórico da pessoa.
- **Chamar de volta:** filtro de quem está sem atendimento há 30 dias ou mais e filtro de retornos marcados.
- **Promoção mensal e Tiragens:** mensagens prontas com `{nome}`. O botão **Copiar e abrir** copia o texto com o nome da pessoa e abre a conversa no WhatsApp.
- **Importar conversa:** lê o arquivo `.txt` exportado do WhatsApp e registra os atendimentos (veja abaixo).
- **Backup:** copia, baixa e restaura todos os dados.

## Instalar no celular

1. Abra o endereço do app no navegador do celular.
2. **Android (Chrome):** menu ⋮ → **Instalar app** (ou **Adicionar à tela inicial**).
3. **iPhone (Safari):** botão **Compartilhar** → **Adicionar à Tela de Início**.

Depois de instalado, ele abre como um app normal e funciona também sem internet.

## Publicar no GitHub Pages

1. Crie um repositório **público** no GitHub (no plano gratuito, o Pages só publica repositórios públicos).
2. Envie todos os arquivos desta pasta para a raiz do repositório.
3. Em **Settings → Pages**, escolha **Deploy from a branch**, branch **main**, pasta **/ (root)**, e salve.
4. Em cerca de um minuto o app fica em `https://SEU-USUARIO.github.io/NOME-DO-REPOSITORIO/`.

## Seus dados

- Os dados dos consulentes ficam **somente no aparelho** (armazenamento do navegador). Nada é enviado ao GitHub nem a nenhum servidor.
- Cada aparelho tem os seus próprios dados. **Não há sincronização** entre celular e computador.
- Se você limpar os dados do navegador ou desinstalar o app, os dados são perdidos. Por isso, faça **💾 Backup** de vez em quando.

### Backup e troca de aparelho

- **Copiar backup:** copia tudo como texto. Cole em um lugar seguro (por exemplo, uma conversa com você mesma).
- **Baixar arquivo:** salva um arquivo `.json`.
- **Restaurar:** cole o texto ou escolha o arquivo e toque em **Restaurar**. Cadastros iguais são substituídos pelos do backup.

## Importar conversa do WhatsApp

1. No WhatsApp Business, abra a conversa → menu → **Exportar conversa** → **Sem mídia**.
2. No app, toque em **📥 Importar conversa** e escolha o arquivo `.txt` (pode escolher vários).
3. Confira a prévia (nome, telefone e tiragens encontradas), marque o que quer importar e toque em **Importar**.

Para a tiragem ser reconhecida sozinha, escreva nas leituras uma linha como:

```
Tiragem: Flecha do Cupido
```

Sem essa linha, o app oferece registrar um atendimento na data da última mensagem, desmarcado por padrão. Cadastros existentes são encontrados pelo telefone ou pelo nome, e atendimentos repetidos não são duplicados.

## Personalizar

Tudo está no arquivo `index.html`:

- **Catálogo e preços:** lista `CAT` (nome, valor e palavras-chave usadas na importação).
- **Texto da promoção:** `DEFAULT_PROMO`.
- **Textos das tiragens:** lista `TIR`.

Os textos também podem ser editados dentro do app, no botão **✏️ Editar texto**. Nos textos, `{nome}` vira o primeiro nome de cada pessoa.

## Atualizar o app

Substitua o `index.html` no repositório pelo novo e salve (commit). O app busca a versão nova quando há internet. Se o celular continuar mostrando a versão antiga, feche e abra o app novamente.

## Arquivos

| Arquivo | Para que serve |
| --- | --- |
| `index.html` | O app inteiro (telas, regras e estilos) |
| `manifest.json` | Nome, cores e ícones para instalar no celular |
| `sw.js` | Faz o app funcionar sem internet |
| `icon-192.png`, `icon-512.png`, `apple-touch-icon.png` | Ícones do app |

## Tecnologia

HTML, CSS e JavaScript puros, sem dependências e sem etapa de build. Dados no `localStorage` do navegador.
