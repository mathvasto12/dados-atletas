# Dados Atletas

Uma aplicação em JavaScript que utiliza a Programação Orientada a Objetos (POO) para receber informações de um atleta, determinar sua categoria por idade, calcular o Índice de Massa Corporal (IMC) e calcular a média válida de suas notas de acordo com os critérios das federações esportivas.

Este projeto faz parte do processo de certificação do **DEVstart**.

##  Índice

- [Resumo do Projeto](#-resumo-do-projeto)
- [Funcionalidades](#-funcionalidades)
- [Especificações Técnicas](#-especificações-técnicas)
  - [Atributos da Classe](#atributos-da-classe)
  - [Métodos da Classe](#métodos-da-classe)
- [Regras de Negócio](#-regras-de-negócio)
- [Exemplo de Uso](#-exemplo-de-uso)
- [Como Executar](#-como-executar)
- [Entrega](#-entrega)

---

##  Resumo do Projeto

O software foi desenvolvido com o objetivo de automatizar a consolidação de dados de atletas em competições. Ele é capaz de organizar as informações pessoais, enquadrar o atleta em uma categoria de idade específica, calcular o seu IMC e computar a média de notas descartando a maior e a menor pontuação recebida, garantindo uma avaliação justa.

##  Funcionalidades

- **Classificação por Categoria:** Define automaticamente a categoria do atleta com base na idade.
- **Cálculo de IMC:** Avalia o Índice de Massa Corporal a partir do peso e altura fornecidos.
- **Cálculo de Média Válida:** Aplica a metodologia de descartar os extremos (maior e menor nota) para obter uma média equilibrada e justa das notas dos juízes.

##  Especificações Técnicas

O projeto foi estruturado em uma classe JavaScript chamada `Atleta`.

### Atributos da Classe
A classe é inicializada recebendo os seguintes parâmetros no construtor:
- `nome`: Nome do atleta (String)
- `idade`: Idade do atleta (Number)
- `peso`: Peso em kg (Number)
- `altura`: Altura em metros (Number)
- `notas`: Um array contendo as notas atribuídas pelos juízes (Array de Numbers)

### Métodos da Classe
A classe possui métodos de processamento e métodos de acesso (getters simulados):

| Método | Descrição |
| :--- | :--- |
| `calculaCategoria()` | Executa a lógica para identificar a categoria baseada na idade. |
| `calculaIMC()` | Realiza o cálculo do IMC usando a fórmula matemática padrão. |
| `calculaMediaValida()` | Aplica o algoritmo de ordenação e descarte para obter a média correta. |
| `obtemNomeAtleta()` | Retorna o nome do atleta. |
| `obtemIdadeAtleta()` | Retorna a idade do atleta. |
| `obtemPesoAtleta()` | Retorna o peso do atleta. |
| `obtemNotasAtleta()` | Retorna o array de todas as notas do atleta. |
| `obtemCategoria()` | Retorna o resultado de `calculaCategoria()`. |
| `obtemIMC()` | Retorna o resultado de `calculaIMC()`. |
| `obtemMediaValida()` | Retorna o resultado de `calculaMediaValida()`. |

---

##  Regras de Negócio

### 1. Categorias por Idade
- **Infantil:** 9 a 11 anos
- **Juvenil:** 12 e 13 anos
- **Intermediário:** 14 e 15 anos
- **Adulto:** 16 a 30 anos
- **Sem categoria:** Demais idades

### 2. Cálculo do IMC
A fórmula utilizada para o cálculo do IMC é:
$$IMC = \frac{peso}{altura \times altura}$$

### 3. Cálculo da Média Válida
O cálculo utiliza a metodologia abordada no Projeto de Certificação 1:
1. Ordena o array de notas em ordem crescente.
2. Elimina a menor nota (primeira posição) e a maior nota (última posição).
3. Calcula a média aritmética simples das notas restantes.

---

##  Exemplo de Uso

```javascript
// Declaração do atleta
const atleta = new Atleta(
    "Cesar Abascal",
    30, 
    80, 
    1.70,
    [10, 9.34, 8.42, 10, 7.88]
);

// Exibição dos resultados no console
console.log(`Nome: ${atleta.obtemNomeAtleta()}`);
console.log(`Idade: ${atleta.obtemIdadeAtleta()}`);
console.log(`Peso: ${atleta.obtemPesoAtleta()}`);
console.log(`Altura: ${atleta.altura}`);
console.log(`Notas: ${atleta.obtemNotasAtleta().join(",")}`);
console.log(`Categoria: ${atleta.obtemCategoria()}`);
console.log(`IMC: ${atleta.obtemIMC()}`);
console.log(`Média válida: ${atleta.obtemMediaValida()}`);
