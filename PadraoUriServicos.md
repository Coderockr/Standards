###Regras gerais
 - Evitar artigos the, of, a, etc.
 - Evitar CamelCase
 - Evitar CAIXA ALTA
 - Abreviar quando não houver perda semântica
 - Os componentes da URI, quando compostos por mais de uma palavra, devem ser separados por underline ``_``

####Estrutura da URI:

```
modulo.verbo[-escopo][-entidade].formato
``` 

####Componentes da URI
1. modulo: o módulo do serviço (gerado automaticamente)
2. verbo: o que será feito; quando possível, utilizar verbos HTTP (put, delete, post, get)
3. escopo: (opcional), o que se pretende atingir com o verbo
4. entidade: (opcional), a entidade a qual o escopo pertence ou tem alguma espécie de dependência explícita
5. formato: json, xml (gerado automaticamente)
 

###Exemplos:

1.   ``aplication.authenticate.json`` : escopo e entidade foram omitidos por simplicidade; foi utilizando authenticate como verbo pois nenhum dos verbos HTTP se enquadra perfeitamente
2.   ``aplication.get-client.xml``: (retorna o cliente de um usuário) a entidade foi omitida por simplicidade - provavelmente não haverá um get-client para outra coisa senão retornar o cliente de um usuário. O modo extendido ficaria: ``get-client-user``
3.   ``aplication.get-menu_tree.json``: (retorna o grafo de menu de um usuário), vale notar o underline para separar as palavras com compõem o escopo, e a omissão da entidade por simplicidade
4.   ``application.put-user-client.xml``: (atualiza um usuário do cliente), utilização do componente entidade; é importante observar a ordem, basicamente, atualiza algo de alguém
5. ``application.post-user-client.json`` (cria um usuário para o cliente)