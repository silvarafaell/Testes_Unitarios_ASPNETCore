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
