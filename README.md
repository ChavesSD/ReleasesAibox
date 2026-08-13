# ReleasesAibox

Repositório de **releases** do Aibox: instalador do app e catálogo de APKs (Totem, Painel e Outros).

O código-fonte fica em [ChavesSD/Aibox](https://github.com/ChavesSD/Aibox).

## Como o app usa este repositório

| Arquivo | Função |
| --- | --- |
| `latest.json` | Versão do Aibox (atualização do programa) |
| `apks.json` | Catálogo de APKs (hash, tamanho e URL) |
| `apk_assets/` | Arquivos `.apk` baixados pelo Aibox após instalar |

O instalador (`Aibox-Setup.exe`) **não** inclui APKs. Depois de instalar, o app lê `apks.json` e baixa o que faltar ou estiver desatualizado.

## Atualizar os APKs

1. Substitua os arquivos em `apk_assets/` (mantenha o nome `Categoria-arquivo.apk`).
2. Regenere o catálogo no projeto Aibox:

```powershell
python publish_apks.py --version 1.0.1
```

3. Copie o novo `apks.json` para a raiz deste repositório e faça commit + push em `main`.

Os usuários só precisam clicar em **Baixar APKs** no Aibox (ou reabrir o app).
