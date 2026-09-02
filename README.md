# Marketplace de plugins da Stallae

Um marketplace de plugins para o Claude Code. Hoje publica um plugin.

## Instalar

No Claude Code, `/plugin` → **Adicionar marketplace** → **Adicionar de um
repositório**, e cole:

```
https://github.com/stallae/sagarana-plugin.git
```

Ou pela linha de comando:

```
/plugin marketplace add stallae/sagarana-plugin
```

Depois `/plugin` e escolha `sagarana`.

## Plugins

| plugin | o que faz |
|---|---|
| [`sagarana`](plugins/sagarana) | leitura da sua conta Sagarana — catálogo, estante, feed e detalhe de livro |

## Por que este repositório é separado

O servidor MCP vive no backend do Sagarana, que é privado. Um marketplace é
clonado por quem instala, então os manifests precisam estar num repositório
alcançável. Aqui não há segredo: são quatro arquivos de configuração, e o
endereço do servidor MCP é público por natureza — quem o chama sem um token
autorizado recebe 401.
