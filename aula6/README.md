

# Exercício
### Desenvolva o Diagrama Entidade-Relacionamento para as seguintes situações:

> Continuação da aula 5

2. Um diretor dirige no máximo um departamento. Um
departamento tem no máximo um diretor.

![image](https://user-images.githubusercontent.com/93677384/149006779-369f32cb-5513-4ece-8411-9bc24837281f.png)


3. Um autor escreve vários livros. Um livro pode ser
escrito por vários autores.
4. Uma equipe é composta por vários jogadores. Um
jogador joga apenas em uma equipe.
5. Um cliente realiza várias encomendas. Uma
encomenda diz respeito apenas a um cliente.

## Normalização

### Aplicar as Formas Normais cabíveis, nas questões abaixo. Você deve transformar os esquemas abaixo em conjuntos de esquemas que estejam na 2NF, 3NF.

1. Empregado (Número Empregado, Nome do Empregado, Número do Departamento, Nome do Departamento, Número do Gerente, Nome do Gerente, Número do Projeto, Nome do Projeto, Data de Início do Projeto, Número de horas trabalhadas no projeto, valor-hora do Projeto).

```
Número Empregado -> Nome do Empregado
Número do Departamento -> Nome do Departamento
Número do Gerente -> Nome do Gerente
Número do Projeto -> Nome do Projeto
Número do Projeto, Número Empregado -> Número de horas trabalhadas no projeto, valor-hora do Projeto, Data de Início do Projeto
```
```
2FN
Empregado(NumeroEmp, NomeEmpregado,NumeroDepto)
Depto(NumeroDepto, NomeDepto, NumeroGerente)
Gerente(NumeroGerente, NomeGerente)
Projeto(NumeroProjeto, NomeProjeto)
TrabalhaProjeto(NumProjeto, NumEmpregado, dataInicio, NumeroHoras, ValorHoras)
```
2. OrdemCompra (codOrdem, dtEmissão, codFornecedor, nomeFornecedor, endereçoFornecedor, codMaterial (n vezes), descriçãoMaterial (n vezes), qtComprada (n vezes), valorUnitário (n vezes), valorTotalItem (n vezes), valorTotalOrdem).

```
CódOrdem, CódMaterial -> dtEmissão, qtComprada (n vezes), valorTotalItem (n vezes), valorTotalOrdem. 
CódFornecedor -> nomeFornecedor, endereçoFornecedor, 
CódMaterial -> descriçãoMaterial (n vezes),  valorUnitário (n vezes), 
```
2FN
Material (CódMaterial, descriçãoMaterial (n vezes),  valorUnitário (n vezes))
Fornecedor (codFornecedor, nomeFornecedor, endereçoFornecedor)
OrdemCOmpra (CódOrdem, CódMaterial, dtEmissão, qtComprada (n vezes), valorTotalItem (n vezes), valorTotalOrdem)
```


4. Tabela de Notas Fiscais (NumNF, Série, Data emissão, CodCliente, NomeCliente, EndereçoCliente, CGC cliente, Código Mercadoria, Descrição Mercadoria, Quantidade vendida, Preço de venda, Total da venda da Mercadoria e Total Geral da Nota).Cada nota pode ter mais de uma mercadoria. 
