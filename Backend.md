
### Geral

As regras são baseadas no PSR-2. Não havendo algo relacionado aqui deve-se respeitar o que consta na [PSR-2](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md)

- Arquivos DEVEM usar apenas <?php 

- Todos os arquivos devem ser salvos na codificação UTF-8. Configurar editores e IDEs usadas para salvar desta forma.

- Todos os arquivos PHP DEVEM terminar com uma linha em branco

- A tag de fechamento ?> DEVE ser omitida em arquivos que contém apenas código PHP

- Nomes de classes DEVEM ser declaradas no formato StudlyCaps.  Exemplo: RestController

- Cada classe DEVE estar em um arquivo separado e DEVE existir uma declaração de namespace

- Constantes de classe DEVEM ser declaradas em maiúsculas e com underscore como separador. Exemplo: PAYMENT_TYPE

- Nomes de métodos DEVEM ser declarados em camelCase. Exemplo: getPaymentMode

- Código DEVE usar 4 espaços para indentação e não tabs

- Linhas PREFERENCIALMENTE precisam ter 80 caracteres ou menos

- Em métodos onde o retorno é opcional (void)  PREFERENCIALMENTE  retornar o ponteiro do próprio objeto ($this)

- DEVE ter uma linha em branco depois da declaração do namespace e DEVE ter uma linha em branco depois do bloco de declaração dos uses

- PREFERENCIALMENTE optar por cláusulas feitas através do Query builder em detrimeto à DQL

- Nenhum arquivo PHP deve lançar exceções, warnings, strict standards ou notices

- DEVE existir apenas um use por declaração. Exemplo correto:

```php
use Core\Service\ParameterFactory;
use Core\Service\ParameterSet;
use Core\Service\Service;
```

Exemplo ERRADO:

```php
use Core\Service\ParameterFactory,
    Core\Service\ParameterSet,
	Core\Service\Service;
```

- As declarações de use DEVEM vir após a declaração da namespace
- Toda a lista com múltiplas entradas as quais a ordem não importa para o funcionamento deve ser ordenada alfabeticamente, inclusive namespaces.
- As chaves de abertura e fechamento da classe DEVEM ser em novas linhas. Exemplo:

```php
class Auth extends Service
{
	//código
}
```

- As chaves de abertura e fechamento de métodos DEVEM ser em novas linhas. Exemplo:

```php
public function authenticate(ParameterSet $params)
{   
	//código
}
```

- A visibilidade (public, private, protected) DEVE ser declarada em todos os métodos e propriedades. abstract e final DEVEM ser declaradas antes da visibilidade. static DEVE ser declarado depois da visibilidade.  Variáveis NÃO DEVEM iniciar com underscore como forma de definição de visibilidade.

- As chaves de abertura de estruturas de controle DEVEM ser na mesma linha, as de fechamento devem ser em nova linha. Parênteses de abertura de estruturas de controle NÃO DEVE ter espaços depois e o de fechamento NÃO DEVE ter espaços antes.  Exemplo:

```php
if (count($user)==0) {
	throw new Exception("Login ou senha inválidos");
}    
```

- Palavras chave do PHP DEVEM ser em minúsculas. O mesmo para true, false, null.

- As palavras chave extends e implements DEVEM ser declaradas na mesma linha do nome da classe. Exemplo:

```php
<?php
namespace Vendor\Package;

use FooClass;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

class ClassName extends ParentClass implements \ArrayAccess, \Countable
{
    // constants, properties, methods
}
```

- Nomes de variáveis devem conter somente caracteres alfanuméricos, não sendo underscores permitidos. Números são permitidos mas são desencorajados na maioria dos casos.

- Nomes de variáveis, métodos e classes devem ser em inglês. Exemplos:

```php
$filter = $this->getFilter();
$client = $this->getClient();
```

- A utilização de verbos é encorajada, ou seja, variáveis e métodos devem sempre ser tão verbais quanto prático para descrever os dados que o desenvolvedor pretende armazenar nelas. Nomes concisos de variáveis como "$i" e "$n" são desencorajados para todos os contextos de laço, exceto os menores. Se um loop contém mais de 20 linhas de código então as variáveis de índice devem ter nomes mais descritivos.

- Nomes de funções devem conter somente caracteres alfanuméricos, não sendo underscores permitidos. Números são permitidos mas desencorajados na maioria dos casos.

- A declaração de um método deve se parecer com o exemplo abaixo. Note a localização dos parênteses, espaços e chaves:

```php
<?php
namespace Vendor\Package;

class ClassName
{
    public function fooBarBaz($arg1, &$arg2, $arg3 = [])
    {
        // method body
    }
}
```

- Na lista de argumentos de um método NÃO DEVE existir espaços antes de cada vírgula e DEVE existir um espaço após cada vírgula.

# Estruturas de controle

Nos exemplos a seguir observar a posição de espaços, vírgulas e parênteses. 

## if, elseif, else

```php
<?php
if ($expr1) {
    // if body
} elseif ($expr2) {
    // elseif body
} else {
    // else body;
}
```

## switch, case

```php
<?php
switch ($expr) {
    case 0:
        echo 'First case, with a break';
        break;
    case 1:
        echo 'Second case, which falls through';
        // no break
    case 2:
    case 3:
    case 4:
        echo 'Third case, return instead of break';
        return;
    default:
        echo 'Default case';
        break;
}
```

## while, do while

```php
<?php
while ($expr) {
    // structure body
}

<?php
do {
    // structure body;
} while ($expr);
```

## for

```php
<?php
for ($i = 0; $i < 10; $i++) {
    // for body
}
```

## foreach

```php
<?php
foreach ($iterable as $key => $value) {
    // foreach body
}
```

## try, catch

```php
<?php
try {
    // try body
} catch (FirstExceptionType $e) {
    // catch body
} catch (OtherExceptionType $e) {
    // catch body
}
```

# Documentação e comentários

Todas as classes e métodos devem ser documentados de acordo com o padrão phpDocumentator. Dessa forma é possível gerar documentação de forma automática.

## Classes

```php
<?php
namespace Api\Model;

use Zend\InputFilter\Factory as InputFactory;
use Zend\InputFilter\InputFilter;
use Zend\InputFilter\InputFilterAwareInterface;
use Zend\InputFilter\InputFilterInterface;
use Core\Model\Entity;

/**
 * Entidade token
 *
 * @category Api
 * @package Model
 * @author  Elton Minetto<eminetto@coderockr.com>
 */
class Token extends Entity
{
```

Sendo:

	@author o nome e e-mail do author do código, separado por , caso tenha mais de um
	@category o nome do módulo
	@package o nome do namespace, podendo ter @subpackages para identificar namespaces complexas. 


Exemplo:

```php
namespace Core\Authentication\Adapter\Exception;

/**
 * Descrição da classe
 *
 * @category Core
 * @package Authentication
 * @subpackage Adapter\Exception
 * @author  Elton Minetto<eminetto@coderockr.com>
 */
```

## Variáveis

```php
/**
 * Table Gateway usado para manipular as entidades
 *
 * @var Core\Db\TableGateway
 */
protected $tableGateway;

```
Sempre colocar uma descrição do motivo da variável existir e o tipo da variável.

## Métodos

```php
/**
 * Atualiza uma entidade
 *
 * @param  int   $id   O código da entidade a ser atualizada
 * @param  array $data Os dados sendo alterados
 * @return array       Retorna a entidade atualizada
 */
public function update($id, $data) 
{
	$data = array_merge($this->get($id), $data);
 	$this->getTableObject()->setData($data);
 	return $this->getTableGateway()
               ->save($this->getTableObject())
               ->getData();
}
```

Descrever o que faz o método, seus parâmetros (com tipo e descrição)  e o retorno (com tipo e descrição).

## Comentários gerais

Trechos de código complexos devem ser documentados, podendo-se usar comentários de uma linha (``//``) ou de múltiplas linhas (``/*`` e ``*/``)

## PHP Code Sniffer

Para analisar o estilo de programação é possível usar o comando como no exemplo abaixo:

	./vendor/bin/phpcs --standard=PSR2 module/Api/src/

Também é possível configurar as IDEs de desenvolvimento para fazer isso automaticamente, como o Eclipse e o [PhpStorm](https://confluence.jetbrains.com/display/PhpStorm/PHP+Code+Sniffer+in+PhpStorm#PHPCodeSnifferinPhpStorm-InstallingviaComposer)

O phpcs pode ser incluído no processo de pre-commit, então ele será executado durante o fluxo normal de desenvolvimento. Quando for fazer um commit, caso ele falhe e você receba uma mensagem como: 

	Running Code Sniffer... E.
	FILE: ...jects/clipp/Backend/module/Application/src/Application/	Service/User.php
	FOUND 1 ERROR(S) AFFECTING 1 LINE(S)
	265 | ERROR | The closing brace for the class must go on the next line after | | the body

Você deverá seguir a instrução acima e corrigir o erro reportado. Depois que os erros reportados forem corrigidos você pode tentar o commit novamente e ele funcionará.

## Suporte ao PHP 7

Deve-se utilizar sempre que possível o support a type hinting e return types adicionado no PHP 7:

```php
public function getToken(): string
{
    return $this->token;
}

public function setToken(string $token)
{
    $this->token = $token;
}
```

### Referências

[Dicas do livro Clean Code: Handbook of Agile Software Craftmanship](http://www.jeancarlomachado.com.br/post/visualizar/00053/dicas-do-livro-clean-code-handbook-of-agile-software-craftmanship)

[PHP The Right Way](http://www.phptherightway.com/)
