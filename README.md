# das-1-2025-2-a

---------- ANOTAÇÕES 04/08/2025

Abstração
Abstração é o ato de representar elementos do mundo real no software, focando apenas nos detalhes essenciais para o funcionamento do sistema.

Ocultamento de Informação
Consiste em proteger os atributos internos de uma classe, permitindo seu acesso e modificação apenas por meio de métodos públicos:
Getters: para leitura dos dados.
Setters: para alteração dos dados.
Isso evita a manipulação direta das variáveis e mantém a integridade dos dados.

Código Coeso
Um código coeso é aquele que executa uma única tarefa de forma clara e eficiente. Quanto maior a coesão, mais simples é entender, manter e evoluir a classe.

Acoplamento
É o grau de dependência entre duas classes.
Acoplamento aceitável: classes se relacionam de forma controlada.
Acoplamento ruim: mudanças em uma classe afetam diretamente outras.

Relacionamentos em UML:
Herança: seta vazada (ex: Gato e Cachorro herdam de Animal).
Implementação: seta vazada e pontilhada (implementação de interfaces).
Associação: seta preenchida (indica ligação direta entre objetos).

Autoacoplamento
Ocorre quando a alteração em uma parte do código impacta outras internamente. É natural em sistemas complexos, mas deve ser minimizado com boas práticas.

@Autowired
Anotação do Spring Framework usada para realizar injeção de dependência, ou seja, o próprio framework instancia e fornece os objetos que uma classe precisa, sem a necessidade de criá-los manualmente.

---------- ANOTAÇÕES 05/08/2025

SOLID
Conjunto de cinco princípios para um código orientado a objetos mais limpo, flexível e de fácil manutenção. Criado por Robert C. Martin, um dos principas nomes da engenharia de software:

S – Responsabilidade Única - Single Responsibility Principle:
Uma classe deve ter apenas um motivo para mudar, ou seja, deve ter uma única responsabilidade.

I – Segregação de Interfaces - Interface Segregation Principle:
Nenhuma classe deve ser forçada a implementar métodos que não utiliza. Prefira interfaces específicas em vez de genéricas.


MVC (Model-View-Controller)
Padrão de arquitetura que separa a aplicação em três camadas:
- Model: Dados e regras de negócio.
- View: Interface com o usuário (HTML, por exemplo).
- Controller: Intermedia a comunicação entre Model e View, controlando a lógica da aplicação.


------------- ANOTAÇÕES 11/08/2025

Princípio da Inversão de Dependência
Esse princípio recomenda que uma classe cliente crie dependências preferencialmente com abstrações, e não com implementações concretas. Isso porque as abstrações são mais adaptáveis e flexíveis, enquanto as implementações concretas tendem a limitar as mudanças e dificultar a manutenção no futuro.

Prefira composição a herança
Herança de classes: exemplo class A extends B, envolve reuso de código, mas cria acoplamento entre as classes.
Herança de interfaces: exemplo interface I extends J, não envolve reuso de código, apenas a obrigação de implementar os métodos definidos.

ou seja, usamos com composição do que herança 


Princípio de Demeter
Defende que a implementação de um método deve invocar apenas métodos de:

-A própria classe onde o método está.
-Objetos recebidos como parâmetro.
-Objetos criados dentro do próprio método.
-Atributos da classe onde o método está.

Principio do aberto fechado
Uma classe deve estar fechada para modificações e aberta para exenções.

classe abstrata 
classe abstrata é uma classe meio pronta

----------- 12/08/2025
principio de liskov
O Princípio de Liskov é aplicado em contextos onde há herança entre classes. Ele define uma regra importante para a redefinição de métodos de uma classe base (superclasse) em suas classes filhas (subclasses).

A ideia central é:
"Se uma classe filha herda de uma classe base, ela deve ser capaz de substituí-la em qualquer lugar do código sem quebrar o comportamento esperado."
Ou seja, o código deve funcionar normalmente se você usar uma instância da classe filha no lugar da classe pai, sem causar erros, comportamentos inesperados ou violações de regras da classe base.
