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

| plugin | aponta para | quando usar |
|---|---|---|
| [`sagarana`](plugins/sagarana) | produção (`api.sagarana.com.br`) | uso real |
| [`sagarana-dev`](plugins/sagarana-dev) | dev (`api.dev.sagarana.com.br`) | testar — banco e contas separados da produção |

## Por que este repositório é separado

O servidor MCP vive no backend do Sagarana, que é privado. Um marketplace é
clonado por quem instala, então os manifests precisam estar num repositório
alcançável. Aqui não há segredo: são quatro arquivos de configuração, e o
endereço do servidor MCP é público por natureza — quem o chama sem um token
autorizado recebe 401.
