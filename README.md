## Laravel PHP Framework

[![Build Status](https://travis-ci.org/laravel/framework.svg)](https://travis-ci.org/laravel/framework)
[![Total Downloads](https://poser.pugx.org/laravel/framework/downloads.svg)](https://packagist.org/packages/laravel/framework)
[![Latest Stable Version](https://poser.pugx.org/laravel/framework/v/stable.svg)](https://packagist.org/packages/laravel/framework)
[![Latest Unstable Version](https://poser.pugx.org/laravel/framework/v/unstable.svg)](https://packagist.org/packages/laravel/framework)
[![License](https://poser.pugx.org/laravel/framework/license.svg)](https://packagist.org/packages/laravel/framework)

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable, creative experience to be truly fulfilling. Laravel attempts to take the pain out of development by easing common tasks used in the majority of web projects, such as authentication, routing, sessions, and caching.

Laravel aims to make the development process a pleasing one for the developer without sacrificing application functionality. Happy developers make the best code. To this end, we've attempted to combine the very best of what we have seen in other web frameworks, including frameworks implemented in other languages, such as Ruby on Rails, ASP.NET MVC, and Sinatra.

Laravel is accessible, yet powerful, providing powerful tools needed for large, robust applications. A superb inversion of control container, expressive migration system, and tightly integrated unit testing support give you the tools you need to build any application with which you are tasked.

## Official Documentation

Documentation for the entire framework can be found on the [Laravel website](http://laravel.com/docs).

### Contributing To Laravel

**All issues and pull requests should be filed on the [laravel/framework](http://github.com/laravel/framework) repository.**

### License

The Laravel framework is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT)


### Requisitos do Sistema
(adaptado de Java para PHP)

RQ001 Incluir Empresa 
    a. O sistema deverá disponibilizar interface de entrada de novos registros de empresa. 
    b. Uma empresa poderá ser do tipo matriz ou filial. Se uma empresa for filial, ela deverá ser aninhada a uma empresa matriz pré-cadastrada.
    c. O formulário de cadastramento de nova empresa deverá manter os seguintes campos:
        Razão Social (inputtext, até 100 caracteres), 
        Preenchimento Obrigatório
        CNPJ (utilizar máscara de validação), Preenchimento 
        Obrigatório
        Logradouro (inputtext, até 150 caracteres), 
        Preenchimento Obrigatório
        Número (inputtext, validação para números inteiros, até 10 caracteres), Preenchimento Obrigatório
        Complemento (inputtext, até 150 caracteres), 
        Preenchimento Opcional
        Município (inputtex, até 150 caracteres), Preenchimento Obrigatório
        UF (inputtex, até 2 caracteres), Preenchimento Obrigatório
        Matriz ou Filial (selectbox)
        Se Filial, apresentar campo de consulta para selecionar uma empresa matriz pré-cadastrada, com consulta por razão social ou CNPJ.
        Telefone de Contato 1 (máscara de telefone com DDI, DDD, Prefixo e Sufixo), Preenchimento Obrigatório
        Telefone de Contato 2 (máscara de telefone com DDI, DDD, Prefixo e Sufixo), Preenchimento Opcional
        Fax (máscara de telefone com DDI, DDD, Prefixo e Sufixo), Preenchimento Opcional
        E-mail (validação de máscara *@*.* ou *@*.*.*), 
        Preenchimento Opcional
        Anexar Imagem do Logotipo da Empresa (campo de upload, com validação de tipo de arquivo (jpg, png ou gif) através do Mimetype, e restrição de tamanho até 2MB, Preenchimento Opcional
        Anexar Contrato Social da Empresa (campo de upload, com validação de tipo de arquivo (DOC, DOCX, RTF, PDF) através do Mimetype, e restrição de tamanho até 10MB, Preenchimento Opcional
    d. As identificações de obrigatoriedade deverão ser sinalizadas na interface. Todas as exceções / validações deverão comunicar claramente ao usuário os erros detectados.
    e. O acesso à tela de inclusão se dará na interface da lista/consulta (RQ004)
    f. Após a inserção, os sistema deverá retornar à lista/consulta (RQ004) de registros, e apresentar mensagem de sucesso.
    
RQ002 Alterar Empresa 
    a. Permitir a alteração dos dados de um registro já inserido. Utilizar 

RQ003 Excluir Empresa 
    a. O sistema permitirá a exclusão de registros existentes.

RQ004 Listar Empresas 
    a. O sistema permitirá a consulta e listagem das empresas as mesmas regras de validação do formulário de inclusão, conforme RQ001.
    b. Campos devem vir preenchidos com os dados já inseridos.
    c. O CNPJ deverá ser somente leitura no modo de edição.
    d. Os campos de upload deverão disponibilizar link para consulta aos arquivos já carregados, e opção de remover os arquivos para inclusão de novos.
    e. A interface de seleção de empresas para alteração será a lista/consulta de empresas (RQ004)
    f. Após a alteração, o sistema deverá retornar à lista/consulta de registros, e apresentar mensagem de sucesso. A mensagem de sucesso de alteração deverá ser diferente da mensagem de sucesso de criação.
    b. Ao solicitar a exclusão, o sistema apresentará mensagem/diálogo de confirmação com o usuário.
    c. Se o registro excluído for uma matriz, o sistema deverá informar ao usuário que as filiais também serão excluídas. Após a confirmação, o sistema fará remoção em cascata da matriz e filiais.
    d. Se o registro excluído for uma filial, o sistema removerá apenas a filial,não afetando os registro de matriz.
    g. A interface de seleção de empresas para remoção será a lista/consulta de empresas (RQ004)
    e. Após a remoção, o sistema deverá retornar à lista/consulta de registros, e apresentar mensagem de sucesso cadastradas. 
    
RQ004 Listar Empresas 
    a. O sistema permitirá a consulta e listagem das empresas cadastradas. 
    b. A lista deverá ser paginada de 20 em 20 registros.
    c. A lista deverá disponibilizar em seu cabeçalho link para inclusão, e para cada registro, link para alteração e exclusão.
    d. O sistema deverá apresentar mensagem “Não há empresas cadastradas” na lista de consulta quando não houver registros na base de dados.
    e. O sistema deverá apresentar as empresas matrizes e filiais aninhadas hierarquicamente na consulta.
    f. O sistema deverá disponibilizar campos de busca por CNPJ, razão social, município e UF.
    g. A consulta por empresa apresentará as seguintes colunas:
        Logotipo (miniatura)
        CNPJ
        Razão Social
        UF
        Município
        Telefone 1