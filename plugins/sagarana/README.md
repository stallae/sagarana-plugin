# Sagarana · plugin do Claude Code

Dá ao Claude leitura da sua conta Sagarana: catálogo, estante, feed e detalhe
de livro.

## Instalar

```
/plugin marketplace add stallae/sagarana_backend
/plugin
```

Escolha `sagarana` na lista. No primeiro uso de uma ferramenta o navegador abre
para você autorizar com a sua conta Sagarana — não há chave de API para guardar,
e o acesso é revogável.

## Ferramentas

| ferramenta | o que faz |
|---|---|
| `buscar_livros` | busca no catálogo por título, autor ou editora |
| `livro` | detalhe de um livro pelo id, com médias e agregados |
| `minha_estante` | sua estante, com filtro por status e por texto |
| `meu_feed` | seu feed, no escopo `general` ou `following` |

## Somente leitura, e por quê isso é garantia

Não é porque a lista acima só tem leitura. É porque o token que o plugin recebe
não serve para mais nada:

- `withMcpAuth` valida por `getMcpSession`, que lê a tabela `oauth_access_token`;
- toda rota `/api/v1` valida por `getSession`, que lê a tabela `session`.

São credenciais de tabelas diferentes, e nenhum dos dois resolvedores enxerga a
do outro. Um token deste plugin recebe **401 em `POST /api/v1/posts`**. Publicar,
apagar, seguir e alterar configuração ficam inalcançáveis por construção — não
por promessa, e não por a lista de ferramentas ser curta.

## Apontar para o ambiente de desenvolvimento

`.mcp.json` aponta para produção. Para falar com o dev, troque a `url` para
`https://api.dev.sagarana.com.br/api/mcp`.
