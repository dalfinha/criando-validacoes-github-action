# Documentação do Fluxo de Trabalho - Verificação de Tags

Este fluxo de trabalho é projetado para verificar a presença de tags específicas nos arquivos do repositório após um evento de push.

## Descrição

Esse fluxo de trabalho é acionado sempre que ocorre um evento de push no repositório. Ele verifica a presença de tags específicas nos arquivos do código do repositório e gera mensagens de sucesso ou erro com base nos resultados da busca.

## Tags Verificadas

O fluxo de trabalho verifica as seguintes tags nos arquivos do código:

- **Tag Repositorio**: Verifica a presença da tag "repositorio" nos arquivos do repositório.

- **Tag Servico_Operacional**: Verifica a presença da tag "Servico_Operacional" nos arquivos do repositório.

- **Tag Tecnologia**: Verifica a presença da tag "Tecnologia" nos arquivos do repositório.

## Passos do Fluxo de Trabalho

1. **Checkout da última versão do código**: O repositório é clonado para o ambiente do fluxo de trabalho para análise.

2. **Verificação de Tags**:
   - Cada passo verifica a presença de uma tag específica usando o comando `grep`.
   - O comando `grep` procura pela tag nos arquivos do código, excluindo os diretórios `.github` e `.github/workflows`.
   - Se a tag for encontrada, uma mensagem de sucesso é exibida e os arquivos onde a tag foi encontrada são listados.
   - Se a tag não for encontrada, uma mensagem de erro é exibida com instruções para incluir a tag.

## Utilização

- Certifique-se de configurar as chaves de autenticação (se necessário) e definir o evento de push como acionador para esse fluxo de trabalho.

- Personalize as tags verificadas e as mensagens de sucesso/erro conforme necessário.

## Notas

- Esse fluxo de trabalho pode ser personalizado para verificar outras tags ou critérios específicos de acordo com as necessidades do projeto.

- O uso de tags ajuda a manter o código organizado e a fornecer informações adicionais sobre as partes do projeto.

- Certifique-se de manter esta documentação atualizada e vinculada ao fluxo de trabalho no repositório.
