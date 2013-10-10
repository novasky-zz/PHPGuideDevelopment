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
Preserve as seguintes diretrizes para nomeação de variáveis, constantes, atributos, métodos e classes:
* Utilize nomes sucintos e diretos referente à que se refere a variável, constante, atributo, método ou classe.
* Evite nomes muito extensos.

```php
    // nomes extensos confundem na hora de fazer a leitura da classe/método/variável
    function methodToDoWhateverThingThatYouWant();
     
    class ClassToDoWhateverThingThatYouWant()
```


* Prefira nomes em inglês. Desse modo, palavras que na grafia em português exigem acentuação não ficarão difíceis de ler/compreender.

```php
    function doAnything();
    function writeSomething();
```


* Utilize UpperCamelCase para definições de classes.

```php
    class FoolAround();
```


* Utilize lowerCamelCase para definições de variáveis, atributos e métodos.

```php
    $indexPosition = 1;
    function doAnything();
    function writeSomething();
```


* Utilize maiúsculas e palavras separadas por underline (_) para definição de constantes.

```php
    // MAIÚSCULAS e separadas por ''underline'' "_" para constantes
    define ("INDEX_POSITION" , 1);
```


* Prefira variáveis no SINGULAR e arrays no PLURAL. Isso auxiliará a compreensão de conjuntos ou strings.

```php
    // No singular, para demonstrar um elemento string
    $fruta = "Maçã";
     
    // No plural, para demonstrar conjunto de elementos
    $frutas = [
        1 => "Maçã" ,
        2 => "Laranja"
    ];
```


Indentação
------------
Indentação nunca é perda de tempo. Ela torna o código muito mais agradável de ler e compreender. 

* Configure seu editor para utilizar a indentação de 1 TAB (4 espaços).
* Prefira estruturas de condições e repetições utilizando seu inicalizador na mesma linha da definição do comando.
* Obedeça a hierarquia dos elementos encadeados. Utilize 1 TAB para cada novo elemento filho.

```php
    if ( $personagem === 'Goku' ) :
        echo "Oi, eu sou o Goku!";
    else :
        echo "Cacaroto, seu verme imundo!";
    endif;
```

* Utilize identação em elementos separados por vírgula, concatenação (.) e/ou arrays.

```php
    $frutas = [
        1 => "Maçã" ,
        2 => "Laranja"
    ];
    
    public $foo,
           $bar = 1,
           $trip = "test",
           $myArray = [];
```


Comentários
------------
```html
    Antes de deixar um comentário, releia seu código e reescreva-o de uma maneira que ele não precise de comentário :)
```

* Comentários só devem ser usados quando realmente necessário.
* Para comentários de 01 linha, utilize //
* Para comentários que exigem múltiplas linhas, utilize o formato phpDocumentor /** */

```php
    // Diretório principal do projeto
    $dirProject = "pasta/www/";
    
    /**
      * Diretório principal do projeto
      * Precisa utilizar caminho completo (ROOT)
      */
    $dirProject = "pasta/www/";
```
