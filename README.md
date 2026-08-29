# Controle de Validade — Loja

Protótipo web para controle de validade de produtos por corredor, com leitura via tag NFC. Feito para uso direto no celular, sem instalar nada.

## Como funciona

Cada corredor da loja recebe uma tag NFC. Ao encostar o celular na tag, o navegador abre direto a tela daquele corredor, mostrando todos os itens cadastrados com o status de validade:

- 🟢 **OK** — mais de 30 dias para vencer
- 🟡 **Atenção** — 30 dias ou menos (50% de desconto sugerido)
- 🔴 **Urgente** — 7 dias ou menos (80% de desconto sugerido)
- ⬛ **Retirar da prateleira** — já vencido

## Arquivos deste repositório

| Arquivo | Para que serve |
|---|---|
| `index.html` | O aplicativo inteiro (HTML + CSS + JavaScript, sem dependências externas de servidor) |
| `autozone-logo.png` | Logo usado na tela de login e no topo do app — **precisa estar na mesma pasta** que o `index.html`, senão some |

## Acesso

Existem dois níveis de acesso, cada um com sua senha:

| Perfil | Senha | Pode fazer |
|---|---|---|
| Colaborador | `7606` | Consultar corredores e itens |
| Gerente | `s7606` | Tudo do colaborador + adicionar/editar/excluir itens e corredores, renomear corredores, mover itens entre corredores |

## Link de cada corredor

Depois de publicar este repositório no GitHub Pages, o link de cada corredor é o endereço do site + `#/corredor/` + o número do corredor:

```
https://SEU-USUARIO.github.io/NOME-DO-REPOSITORIO/#/corredor/1
https://SEU-USUARIO.github.io/NOME-DO-REPOSITORIO/#/corredor/2
https://SEU-USUARIO.github.io/NOME-DO-REPOSITORIO/#/corredor/3
```

Corredores criados depois pelo gerente já funcionam automaticamente em `#/corredor/4`, `#/corredor/5` etc. — não é preciso subir nada de novo no GitHub quando um corredor novo é criado.

## Gravando as tags NFC

O app usa links (registro do tipo **URL/URI** em NDEF). Se a tag tiver pouca memória, encurte o link antes de gravar (ex: com [is.gd](https://is.gd) ou [tinyurl.com](https://tinyurl.com)) — o link encurtado redireciona sozinho para a tela certa.

## Limitações atuais (importante)

- **Os dados ficam salvos só no navegador de cada aparelho** (localStorage). Um celular não vê em tempo real o que outro celular cadastrou.
- **A senha não é segurança real.** Qualquer pessoa com acesso ao código-fonte do site consegue ver as senhas. Serve para organizar o uso do dia a dia, não para proteger dados sensíveis.

## Próximo passo (opcional)

Para sincronismo real entre aparelhos e login seguro de verdade, é necessário ligar o site a um banco de dados online (ex: Firebase, gratuito para este volume de uso). Isso substitui o armazenamento local por um banco compartilhado, mantendo o mesmo visual e funcionamento.
