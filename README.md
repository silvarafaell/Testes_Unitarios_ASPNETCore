Curso Testes Unitários com ASP.NET Core no nextwave(LuisDEV)

### Apresentação do Curso
 - Testes Unitários têm sido cada vez mais cobrados em vagas de diversos niveis, tanto nacionais quanto internacionais
 - Não somente isso, mas a sua adoção em projetos de diversos portes traz inúmeros benefícios, como melhor manutenibilidade e assertividade no código escrito.
 - Por conta disso, aprender testes unitários já virou algo essencial na carreira de desenvolvedores(as) .NET
 - Neste curso veremos:
   - O que são Testes Unitários
   - Desafios na implementação
   - Como testar código ruim
   - Dummies, Mocks, Stubs
   - Padrão de Escrita
   - Fundamentos de xUnit
   - Criando seus primeiros testes com o xUnit
   - Fundamentos de NSubstitute com  Prática
   - Fundamentos de Moq com Prática Validação com Fluent Assertions com Pratica
   - Geração de Dados com Bogus com Prática

### O que são Testes Unitários
 - Testes Unitários são métodos que verificam o funcionamento de unidades de código, vulgo métodos, e seus objetos associados.
   - Validação de caminhos (caminhos feliz) principais, alternativos, e de exceção ( de erros).
 - O grande objetivo, por incrivel que pareça, não é ter uma grande cobertura, e sim resultar em uma arquitetura melhor, menos acoplada, e de melhor manutenção.
 - Classes com muitas dependências são muito dificeis de testar
 - Métrica utilizada: Cobertura de Código.
 - Benefícios
   - Cobertura de caminhos principais, alternativos e de exceção.
   - Detecção de regressão de erros
   - Documentação de regras de negócio.
   - Melhor desenho de código.
   - Teste Fraco é valida as regras de negocio, valida apenas o caminho feliz.

### Desafios na Implementação
 - Códigos defíceis de se testar
 - Falta de automação (SonarQube, Jenkins, Azure DevOps, AWS CodePipeline)
 - Limitação técnica
 - Ego e sabotagem dos desenvolvedores (fator humano)
 - Falta de clareza no processo de desenvolvimento
 - Prazos curtos
 - Cultura da empresa

 ### Como testar código ruim ?
  - Antes de se testar código ruim, precisamos realizar uma refatoração, afinal, é comum encontrar código fortemente acoplado a implementações de componentes externos, como:
    - Banco de dados
    - APIs externas
    - Serviços de nuvem
  - O ideal é aplicar técnicas de refatoração!
  - Uma técnica bem simples mas muito eficiente é:
    - Extrair métodos
    - Extrair classe
    - Extrair Interface
    - Substituir no código cliente pelo uso da interface via injeção de dependência
      - Em muitas situações, será necessário utilizar o container IOC do framework

### Dummies, Mocks, Stubs
 - Dummies: dados fakes, geralmente criados para apenas serem passados em alguma chamada do método de interesse.
 - Mocks: objeto pré-programado em que são definidas expectativas nas chamadas e respostas que ele possa tratar, com possibilidade de verificação nas chamadas feitas.
 - Stubs: definem respostas "chumbadas" em métodos para simplificar os testes, sobreescrevendo as reais implementações, por exemplo
   - Exemplo: seu método espera um INotificationService, e você cria um FakeNotificationService que implementa essa interface, para substituri na hora de passar para a classe a ser testada

### Padrão de Escrita
 - AAA: Arrange, Act, Assert
   - Arrange: preparação para o teste, criação e configuração de mocks
   - Act: ação a ser testada
   - Assert: checagem do estado pós-ação
 - Given_When_Then
   - Uma classe de teste por caso de uso
   - Uma classe de teste por classe testada

### Fundamentos de xUnit
 - xUnit é uma framework de teste unitário para .NET, projetado para ser simples e extensível
 - Historico:
   - Criado por Brad Wilson e Jim Newkirk, que também contribuíram para NUnit.
 - Objetivo:
   - Promover práticas de teste modernas e padrões de código limpo.
 - Componentes:
   - Classe de Teste: Contém métodos de teste.
   - Método de Teste: Um método que verifica uma funcionalidade específica.
 - Atributos principais:
   - Fact: Usado para indicar que um método é um teste de unidade.
   - Theory, InlineData e MemberData: Usados para testes parametrizados.
 - Assertivas:
   - Principais Métodos:
     - Assert.Equal(expected, actual): Verifica se dois valores são iguais.
     - Assert.NotEqual(notExpected, actual): Verifica se dois valores não são iguais.
     - Assert.True(condition): Verifica se confição é verdadeira.
     - Assert.False(condition): Verifica se a confição é falsa.

### Fundamentos de NSubstitute
 - NSubstitute é uma biblioteca para criação de objetos substitutos (mocks) usados em testes unitários.
 - Objetivo: Facilitar a substituição de dependências em testes unitários, permitindo a simulação de comportamentos e verificação de interações
 - Características
   - Sintaxe Simples e Intuitiva: Uso de expressões lambda para configuração e verificação
   - Suporte para Proxies Dinâmicos: Criação de objetos substitutos sem a necessidade de configuração explícita.
   - Interação com Diversos Frameworks de Teste: Compativel com xUnit, NUnit, MSTest, entre outros
 - Principais usos:
   - Substituição de Dependências: Substituição de dependencias para isolar a unidade sendo testada.
   - Simulação de Comportamento Complexos: Quanto métodos têm comportamentos complexos ou dependem de serviços externos
   - Verificação de Interações: Verificar se métodos são chamados corretamente surante a execução do teste

### Fundamentos de Moq
 - Moq é uma biblioteca amplamente utilizada para criação de mocks, stubs e fakes em testes unitários no ecossistema .NET
 - Objetivo: Facilitar a substituição de dependências em testes de unidade, permitindo a simulação de comportamentos, a verificação de interações e a criação de testes mais isolados e confiáveis
 - Características:
   - Sintaxe Simples e Intuitiva: Uso de expressões lambda para configuração e verificação.
   - Mocks Fortemente Tipados: Permite criar objettos substitutos fortemente tipados, garantindo maiss segurança e fluidez ao escrever testes.
   - Configuração Dinâmica de Retornos: Possibilidade de configurar facilmente comportamentos como retornos condicionais, exceções lançadas, ou execução de callbacks.
   - Integração com Diversos Frameworks de Teste: Compatível com xUnit, NUnit, MSTest, entre outros.
 - Principais usos:
   - Substituição de Dependências: Substituição de dependências para isolar a unidade sendo testada
   - Simulação de Comportamentos Complexos: Quando métodos têm comportamentos complexos ou dependem de serviços externos
   - Verificação de interações: Verificar se métodos são chamados corretamente durante a execução do teste

### Validações com Fluent Assertions
 - Fluent Assertions é uma biblioteca .NET para escrever assertivas de testes de forma fluida, legível e descritiva.
 - Objetivo:
   - Melhorar a clareza e a precisão na verificaçaõ de resultados esperados em testes unitários e de integração.
 - Características:
   - Sintaxe fluida e human-readable
   - Suporte a diferentes tipos de objetos e cenários de teste
   - Compativel com xUnit, UUnit, MSTest, entre outros.
   - Possibibilidade de validações customizadas.
 - Principais Métodos
   - .Should().Be() - verifica se valores são iguais
   - .Should().BeNull() / .Should().NotBeNull() - Verifica se valores são ou não nulos
   - .Should().BeEmpty() / Should().NotBeEmpty() / .Should().Contain() - Verifica se uma coleção contém está ou não vazia, se contém um item, respectivamente.
   - .Should().Throw<Exception>() - Verifica se uma exceção especifica foi lançada
   - .Should().BeEquivalentTo() - Verifica equivalencia profunda de ojbetos. 
