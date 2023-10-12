# 💡 Usando o GitHub Actions para facilitar o dia-a-dia

Pensando em automatizar pushs do Github, o script em .YAML e BASH verifica a presença de tags/termos específicas nos arquivos do repositório. Não incluíndo o actions presente no .github\workflows\.

O arquivo presente no diretório .github/workflows/ é a base para o Github Actions procurar a palavra "Repositorio", "Servico_Operacional" e "Tecnologia", gerando mensagem de sucesso ou erro com base na busca.  A mensagem de sucesso inclui em qual arquivo as palavras se encontram. 

Nessa nova versão, mesclei o workflow de validação das palavras com um init e validate de um código terraform, se existente no seu repositório.

## Como o fluxo funciona? ⭐

### step> valida-variaveis-obrigatorias

1. **Checkout da última versão do código**: O repositório é clonado para o ambiente do fluxo de trabalho para análise.

2. **Verificação de Tags**:
   - Cada passo verifica a presença de uma tag específica usando o comando `grep`.
   - O comando `grep` procura pela palavra nos arquivos do código, excluindo o diretório `.github`.
   - Se a palavra for encontrada, uma mensagem de sucesso é exibida e os arquivos onde a tag foi encontrada são listados.
   - Se a palavra não for encontrada, uma mensagem de erro é exibida com instruções para incluir a tag.

### step> terraform-validate

1. **Instala dependências do Terraform**

2. **Terraform Init && Terraform Validate**:
   - Após instalar as dependências, o terraform inicia e cria uma validação na mesma action. Para que ocorra sem falhas, a validação roda direto no repositório.