# Validador de CPF e CNPJ 


Classe em PHP para validação de CPF e CNPJ.


## Instalação
Via [Composer](http://getcomposer.org)

```
composer config repositories.magecommerce/validador-cpf-cnpj github https://github.com/R-DIGITAL/validador-cpf-cnpj.git
```

```bash
composer require magecommerce/validador-cpf-cnpj:dev-main
```


## Como utilizar

Exemplo de uso para validação e formatação de CPF:
```php
// Não importa se já vem formatado ou não
$document = new \Bissolli\ValidadorCpfCnpj\CPF('123.456.789.00');

// Verifica se é um número válido de CPF
// Retorna true/false
$document->isValid();

// Retorna o número de CPF formatado (###.###.###-##)
// ou false caso não seja um número válido
$document->format();

// Retorna o número de sem formatação alguma
// ou false caso não seja um número válido
$document->getValue();
```


Exemplo de uso para validação e formatação de CNPJ:
```php
// Não importa se já vem formatado ou não
$document = new \Bissolli\ValidadorCpfCnpj\CNPJ('12.345.678/0001-90');

// Verifica se é um número válido de CNPJ
// Retorna true/false
$document->isValid();

// Retorna o número de CNPJ formatado (##.###.###/####-##)
// ou false caso não seja um número válido
$document->format();

// Retorna o número de sem formatação alguma
// ou false caso não seja um número válido
$document->getValue();
```


Exemplo de uso para validação e formatação de CNPJ ou CPF, já reconhecendo o tipo de documento baseado na quantidade de números:
```php
// Não importa se é CPF ou CNPJ e se já vem formatado
$document = new \Bissolli\ValidadorCpfCnpj\Documento('...');

// Retorna se é CPF ou CNPJ 
// Retorna se for um número inválido retorna false
$document->getType();

// Verifica se é um número válido de CNPJ ou CPF
// Retorna true/false
$document->isValid();

// Retorna o número de formatado de acordo com tipo de documento informado
// ou false caso não seja um número válido
$document->format();

// Retorna o número de sem formatação alguma
// ou false caso não seja um número válido
$document->getValue();
```

Simples assim!

## Contribuição

- Qualquer contribuição será bem vinda através de Pull Request;
- Usamos [Conventional Commits](https://www.conventionalcommits.org/) para manter o projeto organizado;
- [Aqui vai um artigo simples](https://medium.com/@klauskpm/how-to-create-good-commit-messages-67943d30cced) explicando como utilizar commitizen para gerar suas mensagens de commit de forma correta e simplificada;
