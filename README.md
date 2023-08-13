# 💡 Verificação de Tags/Palavras chaves em um código

Pensando em automatizar pushs do Github, o script em .YAML e BASH verifica a presença de tags/termos específicas nos arquivos do repositório. Não incluíndo o actions presente no .github\workflows\.

## O que é?

O arquivo presente no diretório .github/workflows/ é a base para o Github Actions procurar a palavra "Repositorio", "Servico_Operacional" e "Tecnologia", gerando mensagem de sucesso ou erro com base na busca.  A mensagem de sucesso inclui em qual arquivo as palavras se encontram. 

## Como o fluxo funciona? ⭐

### valida-pre-requisitos-infra.yml

1. **Checkout da última versão do código**: O repositório é clonado para o ambiente do fluxo de trabalho para análise.

2. **Verificação de Tags**:
   - Cada passo verifica a presença de uma tag específica usando o comando `grep`.
   - O comando `grep` procura pela palavra nos arquivos do código, excluindo os diretórios `.github` e `.github/workflows`.
   - Se a palavra for encontrada, uma mensagem de sucesso é exibida e os arquivos onde a tag foi encontrada são listados.
   - Se a palavra não for encontrada, uma mensagem de erro é exibida com instruções para incluir a tag.

## Utilização

- Personalize as tags verificadas e as mensagens de sucesso/erro conforme necessário.
