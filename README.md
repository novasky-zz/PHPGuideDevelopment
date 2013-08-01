PHPGuideDevelopment
===================

Um pequeno guia pessoal para padrões no desenvolvimento PHP.
Todo o conteúdo visa a escrita de um código mais limpo e organizado e não deve ser usado como única fonte de consulta.

Este guia, de maneira nenhuma, substitui quaisquer recomendações PSR propostos pelo [FIG-Standards](https://github.com/php-fig/fig-standards)

Sintaxe
------------
* Respeite a forma de indentação pré-estabelecida.
* Quebre linhas sempre que iniciar um novo comando.
* NUNCA utilize <? ?>. Prefira sempre <?php ... ?> para scripts completos ou includes/requires. Para disparos de strings, utilize a forma abreviada <?=$string?>.
* Arquivos de script PHP puros não precisam do ?> no final do arquivo. Isso evita que escape algum HTML indesejado.
* Utilize as palavras reservadas sempre em minúsculo: true, false, break, continue, if, foreach, etc.
* Utilize chaves {} ou : sempre na linha que se seguem comandos condicional ou laços de repetição.

```php
    if ( $um == 1 ) :
    
    // ou
    
    foreach ( $arr as $a ) :
    
```

* Utilize aspas duplas " " para strings que possam concatenar variáveis dentro delas. Para isto, utilize chaves {} para concatenar a variável sem precisar quebrar o fluxo das aspas duplas.

```php
    $world = 'world';
    echo "Hello, {$world}!";
```

* Deixe um espaço para cada definição de estrutura imposta por parênteses () e chaves {}. Esta diretriz não é válida para colchetes [].

```php
    // Espaços entre as declarações de cada parênteses ()
    if ( $um == 1 ) :
        echo "Isto é um.";
    else
        echo "Isto não é um.";
    endif;
    
    // A utilização dos colchetes deve vir seguida à palavra respectiva.
    $frutas[5] = "Laranja";
```

* Encadeie as declarações de atributos de métodos em um único escopo.

```html
NOTA: Evite utilizar essa forma de declaração de atributos.
Procure sempre criar atributos separados para facilitar os comentários de documentação.
```

```php
    class Classe_Teste {
        public $foo,
               $bar = 1,
               $trip = "test",
               $myArray = [];
    }
```


Nomenclaturas
------------
Guia para Nomenclaturas.


Indentação
------------
Guia para indentação


Comentários
------------
Guia para comentários
