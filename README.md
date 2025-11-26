# DAS-1-2025-3-A 

### Princípios Fundamentais de Projeto de Software

**Padronização de código:** Adotar um padrão de escrita de código para controlar a complexidade e facilitar o entendimento por toda a equipe. Exemplo:

- Nomes de classes devem começar com letra maiúscula.
- Variáveis e métodos devem utilizar o padrão camelCase.
  
Organização por Camadas:
- Controller = API Rest / HTML
- Entity = Dados
- Repository = con bd
- Service = Lógica
- Config = Centraliza as configurações das aplicações
  
**Reutilização de Frameworks:** Utilize frameworks consolidados ao invés de reinventar a roda. Isso economiza tempo e garante robustez.

**Orientação a Objetos:** Essencial para modularizar o sistema, permitindo que diferentes partes sejam desenvolvidas e mantidas por diferentes pessoas de forma eficiente.


### Ocultamento de Informação
Consiste em proteger os atributos internos de uma classe, permitindo o acesso e a modificação apenas por meio de métodos públicos:

Getters: para leitura dos dados.

Setters: para alteração dos dados.
Essa prática evita manipulação direta das variáveis, preservando a integridade dos dados.

### Código Coeso
Um código é considerado coeso quando realiza uma única tarefa de forma clara e eficiente. Quanto maior a coesão, mais simples se torna entender, manter e evoluir a classe.


### Abstração
Abstração é o processo de representar elementos do mundo real dentro do software, focando apenas nos detalhes essenciais para o funcionamento do sistema.

### Acoplamento
Acoplamento é o grau de dependência entre duas classes:

Acoplamento aceitável: quando as classes se relacionam de forma controlada.
Acoplamento ruim: quando mudanças em uma classe impactam diretamente outras.

### Relacionamentos em UML:

Herança: representada por uma seta vazada (exemplo: Gato e Cachorro herdam de Animal).

Implementação: seta vazada e pontilhada (uso em implementação de interfaces).

Associação: seta preenchida (indica ligação direta entre objetos).

### Dívida Técnica

Dívida técnica ocorre quando uma solução é implementada de maneira rápida ou incorreta, funcionando momentaneamente, mas dificultando manutenções futuras. Exemplo:

Código com baixo padrão de coesão e alto acoplamento.
Soluções que “funcionam”, mas não seguem boas práticas.

### Autoacoplamento
Ocorre quando alterações em uma parte do código impactam outras internamente. Embora natural em sistemas complexos, deve ser minimizado por meio de boas práticas.

### @Autowired
Anotação do Spring Framework utilizada para realizar injeção de dependência. O framework instancia e fornece automaticamente os objetos necessários para uma classe, eliminando a necessidade de criação manual.

---------------------------------------------------------------

### SOLID
Conjunto de cinco princípios para garantir código orientado a objetos limpo, flexível e de fácil manutenção. Criado por Robert C. Martin:

### **S** – Single Responsibility Principle (SRP):
Uma classe deve ter apenas um motivo para mudar, ou seja, uma única responsabilidade.

### Arquitetura MVC (Model-View-Controller)

A arquitetura MVC é um padrão de projeto amplamente utilizado para organizar aplicações web e desktop, promovendo a separação de responsabilidades:

- **Model:** Representa os dados da aplicação e as regras de negócio. É importante destacar que o Model não é a mesma coisa que a entidade (embora em muitos frameworks estejam relacionados).

- **View:** Responsável pela interface com o usuário (geralmente arquivos HTML, CSS, JS).

- **Controller:** Atua como intermediário entre a View e o Model. Recebe as requisições da interface, processa as informações (possivelmente consultando ou manipulando o Model) e retorna uma resposta para a View.


### **I** — Interface Segregation Principle (Princípio da Segregação de Interfaces)

O Princípio da Segregação de Interfaces estabelece que uma classe não deve ser obrigada a implementar métodos que não utiliza. Em outras palavras, é melhor criar interfaces menores e especializadas, em vez de agrupar tudo em uma única interface ampla e genérica.

Esse princípio favorece um baixo nível de acoplamento entre as classes, reduzindo dependências diretas entre os módulos do sistema. Assim, a comunicação entre os componentes ocorre por meio de interfaces bem estruturadas, que funcionam como acordos claros entre as diferentes partes da aplicação.

Exemplo: Interfaces no Java com Swing
- A biblioteca Swing é usada para construir interfaces gráficas em Java, e é um ótimo exemplo de aplicação do princípio de segregação de interfaces.
```
package br.univille;

import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JOptionPane;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class Janelinha extends JFrame {

    private JButton botaozinho;
    private Controlador controlador;

    public Janelinha() {
        setTitle("Eu não acredito");
        setSize(500, 500);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        botaozinho = new JButton("ME CLICA");
        controlador = new Controlador();
        botaozinho.addActionListener(controlador);

        /* Exemplo alternativo:
        botaozinho.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                JOptionPane.showMessageDialog(null, "oi");
            }
        });
        */

        add(botaozinho);
        setVisible(true);
    }

    public static void main(String[] args) {
        new Janelinha();
    }
}
```
------------------------------------------
### Princípio da Inversão de Dependência

Esse princípio recomenda que classes clientes dependam de abstrações (interfaces ou classes abstratas), e não de implementações concretas. Abstrações são mais adaptáveis e flexíveis, enquanto implementações concretas limitam mudanças e dificultam manutenção.
Prefira composição a herança

Herança de classes: exemplo class A extends B, permite reuso de código, porém cria acoplamento entre classes.
Herança de interfaces: exemplo interface I extends J, impõe obrigação de implementar métodos, sem reuso de código.

Recomenda-se usar composição em vez de herança para maior flexibilidade.

### Prefira composição a herança

Significa que é melhor construir funcionalidades combinando objetos (composição) do que depender fortemente de heranças de classes. A herança pode criar estruturas rígidas e difíceis de manter, enquanto a composição permite maior reutilização de código e flexibilidade para montar comportamentos diferentes.

### Princípio de Demeter

Um método deve invocar apenas métodos de:
- Sua própria classe.
- Objetos recebidos como parâmetro.
- Objetos criados dentro do método.
- Atributos da classe.

### Classe Abstrata

É uma classe parcialmente implementada, servindo como base para subclasses.


### Open/Closed Principle (Princípio Aberto/Fechado)
Uma classe deve estar:

- Fechada para modificação (evitar alterações diretas que podem gerar novos bugs).
- Aberta para extensão (permitir novos comportamentos sem mexer no código já testado).
- 
-------------------------------------------

### Princípio de Liskov

Em contextos de herança, o princípio estabelece que uma classe filha deve poder substituir a classe base sem alterar o comportamento esperado. Ou seja, usar uma instância da classe filha onde a classe pai é esperada não deve causar erros nem comportamentos inesperados.
Características arquiteturais = requisitos não funcionais

Um sistema dificilmente atenderá 100% dos requisitos arquiteturais, tais como:

- Disponibilidade
- Confiabilidade
- Integridade
- Escalabilidade
- Segurança
- Agilidade
- Tolerância a falhas
- Elasticidade
- Recuperabilidade
- Desempenho
- Implementabilidade
- Capacidade de aprendizado

É necessário abrir mão de alguns aspectos, escolhendo características prioritárias para a arquitetura do sistema.

------------------------------

### Expectativas de um arquiteto

- Toma decisões arquiteturais: orienta a equipe, definindo o que fazer, como e por quê, preservando características como escalabilidade e desempenho.
- Analisa continuamente a arquitetura: pode reconstruir partes do sistema para manter a vitalidade da arquitetura.
- Mantém-se atualizado: acompanha as últimas tendências técnicas do setor.
- Assegura conformidade: verifica se a equipe segue as decisões arquiteturais e princípios de design.
- Possui experiência diversificada: exposto a tecnologias variadas.
- Conhece o domínio do negócio: para comunicação eficaz com Product Owner (PO).
- Habilidades interpessoais: motiva, inspira e lidera pessoas.
- Lida com questões políticas: compreende hierarquias e negocia prazos.

### Decisões de arquitetura

- Define como o sistema será organizado, ou seja, qual arquitetura será adotada para atender melhor às necessidades. Também garante que as decisões preservem a escalabilidade, desempenho e alinhamento com os objetivos do negócio.
- Analisar continuamente a arquitetura
- Analisa constantemente a arquitetura, podendo reconstruir partes do sistema para manter sua vitalidade, adaptando-se a novas necessidades e corrigindo possíveis dívidas técnicas.

### Manter-se atualizado

- Está sempre acompanhando as últimas tendências técnicas do setor, novas ferramentas, padrões arquiteturais e boas práticas que possam ser aplicadas ao sistema.

### Domínio do negócio
- Conhece o domínio do negócio para se comunicar de forma eficaz com o Product Owner (PO), entender prioridades e garantir que a arquitetura atenda às necessidades reais da empresa.

### DevOps

DevOps é uma abordagem que integra as equipes de Desenvolvimento (Dev) e Operações (Ops) para melhorar a colaboração e a produtividade. Em vez de trabalhar em silos, as equipes compartilham práticas e ferramentas para planejar, desenvolver, testar, implantar e monitorar aplicativos de forma contínua e eficiente.

Por que utilizar DevOps
- Redução do tempo de ciclo: Ao trabalhar em lotes menores e automatizar processos, é possível entregar software mais rapidamente.
- Melhoria contínua: Com feedback constante, as equipes podem aprender e melhorar seus processos.
- Maior colaboração: A integração entre desenvolvimento e operações promove uma comunicação mais eficaz.
- Maior estabilidade: A automação e o monitoramento constante ajudam a identificar e corrigir problemas rapidamente.

---------------------------------------

### Diferença entre: Arquitetura e Design

**Arquiteto:** 

- Traduz requisitos de negócio em atributos arquiteturais.
- Escolhe padrões, estilos e tecnologias.
- Cria componentes estruturais.
- Avalia trade-offs técnicos e comerciais.
- Atua como mentor técnico.

**Designer/Desenvolvedor:**
- Implementa componentes definidos.
- Cria diagramas, interfaces e código.
- Testa e valida o software.

**Tipo de Conhecimento** 
Arquiteto:	
- Amplitude técnica: conhece várias tecnologias, mesmo que não profundamente.
Desenvolvedor
- Profundidade técnica: especialista em poucas tecnologias.
  
-------------------------------------------

### Design Patterns

Soluções reutilizáveis para problemas recorrentes em desenvolvimento de software, popularizados pelos "Gang of Four" (Erich Gamma, Richard Helm, Ralph Johnson e John Vlissides) em 1994.

Categorias:

Criacionais: focam na criação de objetos. Ex.: Abstract Factory, Factory Method, Singleton, Builder, Prototype.
Estruturais: tratam da composição de classes e objetos. Ex.: Proxy, Adapter, Facade, Decorator, Bridge, Composite, Flyweight.
Comportamentais: lidam com interação e divisão de responsabilidades. Ex.: Strategy, Observer, Template Method, Visitor, Chain of Responsibility, Command, Interpreter, Iterator, Mediator, Memento, State.

### Categorias de Padrões

- Criacionais: soluções para criação de objetos.
Exemplos: Abstract Factory, Factory Method, Singleton, Builder, Prototype.

- Estruturais: soluções para composição de classes e objetos.
Exemplos: Proxy, Adapter, Facade, Decorator, Bridge, Composite, Flyweight.

- Comportamentais: soluções para interação e divisão de responsabilidades.
Exemplos: Strategy, Observer, Template Method, Visitor, Chain of Responsibility,
Command, Interpreter, Iterator, Mediator, Memento, State.


### Factory Method
Suponha um sistema distribuído baseado em TCP/IP. Três funções (f, g, h) criam objetos TCPChannel para comunicação:
```
void f() {
  TCPChannel c = new TCPChannel();
  ...
}

void g() {
  TCPChannel c = new TCPChannel();
  ...
}

void h() {
  TCPChannel c = new TCPChannel();
  ...
}
```
Problema
Se for necessário usar UDP, o sistema quebra o Princípio Aberto/Fechado.
O código não está preparado para extensões sem modificações.

Solução
Criar um método fábrica estático que centralize a criação dos objetos:
```
class ChannelFactory {
  public static Channel create() { // método fábrica estático
    return new TCPChannel();
  }
}

void f() {
  Channel c = ChannelFactory.create();
  ...
}

void g() {
  Channel c = ChannelFactory.create();
  ...
}

void h() {
  Channel c = ChannelFactory.create();
  ...
}
```

### Fábrica Abstrata
Uma variação utiliza uma classe abstrata para definir vários métodos fábrica:
```
abstract class ProtocolFactory { // Fábrica Abstrata
  abstract Channel createChannel();
  abstract Port createPort();
  ...
}

void f(ProtocolFactory pf) {
  Channel c = pf.createChannel();
  Port p = pf.createPort();
  ...
}
```
### Singleton
Suponha uma classe Logger usada para registrar operações do sistema:
```
void f() {
  Logger log = new Logger();
  log.println("Executando f");
}

void g() {
  Logger log = new Logger();
  log.println("Executando g");
}

void h() {
  Logger log = new Logger();
  log.println("Executando h");
}
```
O problema é que criamos múltiplas instâncias do Logger, o que não é eficiente nem desejável.

Solução
Aplicar o padrão Singleton, garantindo que a classe possua apenas uma única instância global:
```
public class Logger {
    private static Logger instance;

    private Logger() {}

    public static Logger getInstance() {
        if (instance == null) {
            instance = new Logger();
        }
        return instance;
    }

    public void println(String msg) {
        System.out.println(msg);
    }
}
```

### Observer

O Observer define uma relação de dependência um-para-muitos entre objetos.

Quando um objeto muda de estado, todos os dependentes são notificados automaticamente.


Exemplo prático: sistemas de eventos e notificações.

Estrutura
Subject → objeto observado.
Observer → interessados que “escutam” mudanças no subject.
Exemplo em Java
```
// Interface Observer
public interface Observer {
    void update(String message);
}

// Subject
import java.util.ArrayList;
import java.util.List;

public class Publisher {
    private List<Observer> observers = new ArrayList<>();

    public void addObserver(Observer o) {
        observers.add(o);
    }

    public void notifyObservers(String message) {
        for (Observer o : observers) {
            o.update(message);
        }
    }
}

// Concrete Observer
public class Subscriber implements Observer {
    private String name;

    public Subscriber(String name) {
        this.name = name;
    }

    public void update(String message) {
        System.out.println(name + " recebeu: " + message);
    }
}

// Uso
public class Main {
    public static void main(String[] args) {
        Publisher publisher = new Publisher();

        Subscriber s1 = new Subscriber("Alice");
        Subscriber s2 = new Subscriber("Bob");

        publisher.addObserver(s1);
        publisher.addObserver(s2);

        publisher.notifyObservers("Novo artigo publicado!");
    }
}
```


### Trade-offs em Arquitetura

Nenhuma arquitetura atende perfeitamente a todos os requisitos. Trade-offs são escolhas que priorizam certos aspectos em detrimento de outros. Por exemplo, a arquitetura ideal para um sistema de leilão não serve para um marketplace com milhões de requisições por segundo.

Entre as arquiteturas para alta escala, destacam-se os modelos baseados em tópicos (Publish/Subscribe) e em filas. Na arquitetura baseada em tópicos, que segue o modelo 1 para muitos, uma mensagem é publicada e todos os assinantes a recebem. Esse modelo promove baixo acoplamento entre emissor e receptor, sendo similar ao padrão Observer, com notificações assíncronas. Já na arquitetura baseada em filas, que segue o modelo 1 para 1, as mensagens são enfileiradas e consumidas em ordem, garantindo entrega ordenada e armazenamento até o consumo. Essa abordagem costuma ser mais resiliente e oferece melhor observabilidade que tópicos.

Em termos de extensibilidade arquitetural, filas garantem a entrega da mensagem e mantêm histórico, mas exigem mudanças para acomodar novos consumidores. Por outro lado, tópicos permitem adicionar consumidores sem a necessidade de alterações no emissor.


-----------------------------------
# SEGUNDO SEMESTRE

**Circuit Breaker (Disjuntor)**

O Circuit Breaker é um padrão que protege sistemas distribuídos contra falhas repetidas.
Ele interrompe a comunicação com um serviço instável e só volta a liberar chamadas quando entende que ele se recuperou. Assim, evita sobrecarga, timeout e efeito cascata.

Estados principais
Closed → Tudo ok. As requisições fluem. Se o número de erros ultrapassar um limite, o estado muda.
Open → As chamadas são bloqueadas imediatamente. Nenhuma tentativa é feita. O sistema retorna erro de forma rápida.
Half-Open → Após um tempo, libera algumas requisições de teste. Se forem bem-sucedidas, volta para Closed; se falhar, volta para Open.

Por que é útil?
Em sistemas que dependem de múltiplos serviços, uma falha simples pode derrubar tudo.
O Circuit Breaker evita “flood” de requisições e melhora resiliência.

**Implementação de Filas: Producer / Consumer**

Esse padrão separa quem gera tarefas de quem processa essas tarefas.
O producer envia mensagens para uma fila; o consumer retira cada mensagem e executa o trabalho.

Elementos
Producer → Só cria tarefas e coloca na fila.
Fila → Armazena mensagens de forma confiável.
Consumer → Processa as mensagens uma por vez.

Vantagens
Processamento assíncrono
Escalabilidade: vários consumers processando em paralelo
Resiliência: se um consumer falha, outro pode assumir
Evita travar o sistema quando há picos de carga
Use em: envio de emails, pagamentos, uploads, geração de relatórios.

Definições das Características Arquiteturais

Características arquiteturais definem qualidade e comportamento do sistema, não o que ele faz.
Elas falam sobre desempenho, confiabilidade, manutenção, acessibilidade e segurança.

**Critérios para ser uma característica arquitetural**

Não descreve uma funcionalidade direta (ex.: “cadastrar usuário”).
Afeta estrutura do sistema (ex.: necessidade de cache, distribuição, particionamento).
Impacta sucesso do projeto (ex.: alto uptime, performance mínima).

Tipos
Operacionais: desempenho, disponibilidade, escalabilidade, recuperação.
Estruturais: modularidade, extensibilidade, testabilidade, manutenção.
Transversais: segurança, conformidade legal (LGPD), acessibilidade, usabilidade.

Essas características devem ser discutidas e priorizadas desde o início — ignorá-las gera sistemas frágeis.

**CQRS (Command Query Responsibility Segregation)**

CQRS separa escrita e leitura em modelos diferentes, otimizando cada lado.

Escritas (Commands)
Representam intenções do negócio
Alteram estado
Podem gerar eventos
Não retornam dados complexos
Leituras (Queries)
Retornam dados já formatados
Sem regras de negócio
Podem usar bancos otimizados para leitura

Benefícios
Escalabilidade separada
Melhoria de performance
Código mais claro

Mais segurança (quem lê ≠ quem modifica)

Cuidados
Adiciona complexidade
Pode gerar inconsistência eventual
Use CQRS quando há muito volume de leitura, regras de negócio complexas ou UI com muitos relatórios/consultas.

**Retry Pattern (Padrão de Retentativa)**

O Retry tenta repetir operações que falham temporariamente — comum em sistemas distribuídos.

Quando falhas ocorrem
Timeout
Falha de rede momentânea
Serviço sobrecarregado
Limite de requisições

Estratégias
Retry imediato
Retry com atraso
Exponential backoff (demora crescente)
Exponential + Jitter (evita “tsunami” de requisições simultâneas)
Retry inteligente evita frustração do usuário e reduz instabilidade geral.

**Fundamentos dos Padrões de Arquitetura**

Padrões de arquitetura descrevem como organizar componentes, responsabilidades e fluxo de dados.

**Anti-padrão – Big Ball of Mud**

Código sem organização, altamente acoplado, difícil de manter.

Arquitetura unitária
Tudo em um único executável. Simples, mas limitada para sistemas que crescem.

Cliente/Servidor
UI local → servidor central. Base de aplicações desktop e web antigas.

**Estilo de Arquitetura em Camadas**

A estrutura clássica: separação por responsabilidade.

Camadas típicas
Apresentação
Regras de negócio
Persistência
Banco de dados
Vantagens
Fácil de aprender
Separação de responsabilidades
Desenvolvimento rápido

Desvantagens
Deploy monolítico
Difícil escalar partes específicas
Alta acoplamento

**Estilo de Arquitetura Pipeline**
Fluxo unidirecional de transformação de dados: cada etapa faz uma tarefa específica.

Ideal para:
ETL
Processamento de arquivos
Stream de dados
Cada estágio é independente e reaproveitável.

**Arquitetura Microkernel**

Núcleo pequeno + plugins.

Core
Funcionalidades essenciais
Plugins
Funcionalidades extras sob demanda

Uso comum:
IDEs (VS Code, Eclipse)
Sistemas com personalização por cliente

**Arquitetura de Microsserviços**

Divide sistemas em serviços menores e independentes, cada um com seu domínio.

Características
Desacoplamento alto
Banco isolado por serviço
APIs para comunicação

Benefícios
Escalabilidade
Deploy independente
Time-to-market

Desafios
Latência
Monitoramento
Consistência eventual

Anti-Patterns Comuns
1. Granularidade Muito Fina: Serviços minúsculos que só fazem CRUD 
2. Transações Distribuídas: Tenta fazer ACID entre serviços
3. Shared Database: Múltiplos serviços acessando mesmo banco
4. ESB Disfarçado: API Gateway com lógica de negócio
5. Acoplamento Chatty: Serviço A chama B chama C chama D...

Orquestração de chamadas
