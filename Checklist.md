# Code Review Checklist 

## Geral

- O código funciona? Ele desempenha o papel esperado, a lógica está correta, etc?
- O código é facilmente entendido?
- O código respeita as convenções de codificação [definidas para o projeto](https://bitbucket.org/compufour/clipp/wiki/PadraoCodificacao)?
- Existe algum código redundante ou duplicado?
- O código é o mais modular possível?
- Algum código de log ou debug pode ser removido?
- Se a tarefa exigir a inclusão de uma nova biblioteca/componente no composer.json ou no bower.json toda a equipe deve ser informada para evitar problemas de compatibilidade. O mesmo caso seja necessária uma atualização de versão de uma biblioteca/componente já existente
- Código comentado foi removido?

## Segurança

- Todos os inputs foram validados (tipo correto, tamanho, formato, valores válidos)?
- Os parâmetros inválidos foram tratados?

## Documentação

- Deve ser avisado na descrição do PR se for necessário executar o composer ou o bower para que o código funcione
- Garantir que todas as mensagens geradas tenham tradução
- O código possui documentação? Nos principais métodos e lógicas complexas?
- Todas as variáveis foram definidas com nomes significativos, consistentes e claros?

## Performance

- As consultas do Doctrine foram otimizadas pensando-se em melhoria de performance?
- Informações que podem ser armazenadas em cache estão sendo cacheadas?
- Processamentos redundantes ou lentos foram otimizados?
- Foi evitado o uso de construções IF-ELSE para diminuir a complexidade da execução?

## Testes

- Se a tarefa envolver apenas um módulo, executar os testes daquele módulo. Se envolver mais de um, rodar todos os testes do sistema. 
- Os testes unitários devem ser rodados com todos os erros do PHP habilitados de modo à garantir que nenhum notice,warning,deprecated entre na base.
- Se for uma tarefa que crie ou altere uma API devem ser criados/alterados os testes de Api referentes a tarefa
- Os testes unitários devem cobrir tanto dos casos de sucesso quanto dos casos de erro
- Testar a interface seguindo os requisitos mínimos de navegadores:

	Microsoft Internet Explorer 8.0
	Chrome 35.0
	Safari 8
	Firefox version 35

- Caso não consiga testar em todos os navegadores deve descrever na descrição do PR em quais navegadores realizou os testes




## Referências

[http://blog.fogcreek.com/increase-defect-detection-with-our-code-review-checklist-example/](http://blog.fogcreek.com/increase-defect-detection-with-our-code-review-checklist-example/)

[https://www.liberty.edu/media/1414/%5B6401%5Dcode_review_checklist.pdf](https://www.liberty.edu/media/1414/%5B6401%5Dcode_review_checklist.pdf)

[https://gist.github.com/bwest87/1004992](https://gist.github.com/bwest87/10049924)