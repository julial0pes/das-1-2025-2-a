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
