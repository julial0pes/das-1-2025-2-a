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
O Princípio de Liskov é aplicado em contextos onde há herança entre classes. Ele define uma regra importante para a redefinição de métodos de uma classe base (superclasse) em suas 
classes filhas (subclasses).
A ideia central é:
"Se uma classe filha herda de uma classe base, ela deve ser capaz de substituí-la em qualquer lugar do código sem quebrar o comportamento esperado."
Ou seja, o código deve funcionar normalmente se você usar uma instância da classe filha no lugar da classe pai, sem causar erros, comportamentos inesperados ou violações de regras da classe base.

-----------01/09/2025

Características arquiteturais = requisitos não funcionais

É impossível que um sistema atenda 100% a todos os itens da arquitetura estrutural, que incluem:

disponibilidade
confiabilidade
integridade
escalabilidade
segurança
agilidade
tolerância a falhas
elasticidade
recuperabilidade
desempenho
implementabilidade
capacidade de aprendizado

Sempre precisamos abrir mão de algum aspecto; essa escolha representa uma característica arquitetural.

Decidimos por uma arquitetura que melhor atenda às características prioritárias para o sistema.

A decisão arquitetural é escolher como o sistema será organizado, ou seja, qual arquitetura será utilizada.


O que um arquiteto faz?

Toma decisões arquiteturais
-Deve ser uma pessoa que orienta a equipe, dando um norte sobre o que fazer, como fazer e por que fazer. Às vezes, ele toma uma decisão específica para preservar uma característica da arquitetura, como escalabilidade, desempenho ou disponibilidade.

Analisa continuamente a arquitetura
-Pode decidir reconstruir determinada parte do sistema, sempre mantendo a vitalidade da arquitetura.

Mantém a arquitetura atualizada com as últimas tendências
-Um arquiteto deve se atualizar constantemente com as últimas tendências técnicas do setor. As decisões arquiteturais tendem a ser de longo prazo e difíceis de mudar.

Assegura a conformidade com as decisões
-Verifica continuamente se as equipes de desenvolvimento seguem as decisões da arquitetura, assim como os princípios de design definidos, documentados e comunicados por ele.

Possui exposição e experiências diversificadas
-Deve ter passado por diversas experiências e se expor a tecnologias variadas.

Tem conhecimento sobre o domínio do negócio
-Deve ter certo nível de especialização no domínio do negócio para poder se comunicar de forma eficiente com o Product Owner (PO).

Possui habilidades interpessoais
-Precisa saber lidar com pessoas, sendo capaz de motivar, inspirar e liderar.

Entende e lida bem com questões políticas
-Deve compreender que existe uma estrutura hierárquica e, às vezes, negociar prazos com equipes e clientes para lidar bem com o clima político da empresa.


Operação DevOps

DevOps é uma maneira de entregar valor para o cliente mais rapidamente, entregando funcionalidades com mais agilidade. A contratação de Dev e Ops refere-se à substituição das operações e desenvolvimento em silos, ou seja, todos são responsáveis pelo sistema e participam da criação e manutenção de todas as partes do projeto.
Se o sistema cair, todos recebem a notificação e trabalham juntos para colocá-lo no ar novamente. É difícil encontrar profissionais DevOps, por isso normalmente são criadas equipes específicas de DevOps.

----------- 02/09

Nível de Abstração

Arquiteto de Software pensa em alto nível, estrutura do sistema, tecnologias envolvidas, decisões de arquitetura, trade-offs técnicos e requisitos não funcionais (como desempenho, escalabilidade, segurança, etc.).
Designer/Desenvolvedor lida com a implementação prática, criação de código, design de classes, interfaces de usuário, testes e entrega de funcionalidades específicas.

Responsabilidades

Arquiteto:
Traduz requisitos de negócio em atributos arquiteturais.
Escolhe padrões, estilos arquiteturais e tecnologias.
Cria componentes (blocos estruturais do sistema).
Avalia e gerencia trade-offs técnicos e comerciais.
Atua como mentor e facilitador técnico para os desenvolvedores.

Designer/Desenvolvedor:
Implementa os componentes definidos pelo arquiteto.
Cria diagrama de classes, interfaces, e o código-fonte.
Testa e garante que o software funcione como esperado.

Tipo de Conhecimento

Arquiteto:
Prioriza amplitude técnica: conhece uma grande variedade de tecnologias, mesmo que não profundamente.
Precisa saber o que existe, o que é possível, e o que considerar como solução.

Desenvolvedor:
Prioriza profundidade técnica: é especialista em poucas tecnologias e sabe aplicá-las com maestria no dia a dia.

Forma de Pensar (Pensamento Arquitetônico)

O arquiteto enxerga o sistema como um todo, conectando requisitos de negócio com decisões técnicas.
Já o desenvolvedor foca mais no nível da implementação concreta das decisões arquiteturais.

ou seja
O arquiteto pensa no sistema como um todo, com foco em decisões técnicas que impactam todo o projeto, equilibrando vários fatores, como tecnologia, negócio e restrições. Ele tem uma visão ampla e trabalha com muitos conhecimentos diferentes, mesmo que não seja especialista em todos.
O designer/desenvolvedor foca na implementação prática, construindo as partes específicas do sistema, detalhando o design das funcionalidades e escrevendo o código. Ele precisa ser especialista em algumas tecnologias para entregar um trabalho de qualidade.
