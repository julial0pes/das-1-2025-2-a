# DAS-1-2025-3-A 

### Abstração
Abstração é o processo de representar elementos do mundo real dentro do software, focando apenas nos detalhes essenciais para o funcionamento do sistema.

### Ocultamento de Informação
Consiste em proteger os atributos internos de uma classe, permitindo o acesso e a modificação apenas por meio de métodos públicos:

Getters: para leitura dos dados.

Setters: para alteração dos dados.
Essa prática evita manipulação direta das variáveis, preservando a integridade dos dados.

### Código Coeso
Um código é considerado coeso quando realiza uma única tarefa de forma clara e eficiente. Quanto maior a coesão, mais simples se torna entender, manter e evoluir a classe.

### Acoplamento
Acoplamento é o grau de dependência entre duas classes:

Acoplamento aceitável: quando as classes se relacionam de forma controlada.
Acoplamento ruim: quando mudanças em uma classe impactam diretamente outras.

### Relacionamentos em UML:

Herança: representada por uma seta vazada (exemplo: Gato e Cachorro herdam de Animal).

Implementação: seta vazada e pontilhada (uso em implementação de interfaces).

Associação: seta preenchida (indica ligação direta entre objetos).

### Autoacoplamento
Ocorre quando alterações em uma parte do código impactam outras internamente. Embora natural em sistemas complexos, deve ser minimizado por meio de boas práticas.

### @Autowired
Anotação do Spring Framework utilizada para realizar injeção de dependência. O framework instancia e fornece automaticamente os objetos necessários para uma classe, eliminando a necessidade de criação manual.

### Princípios de Projeto de Código
São boas práticas que orientam o desenvolvimento de software:

Componente	Função
Controller	API REST / HTML
Entity	Representa dados
Repository	Comunicação com banco de dados
Service	Contém a lógica de negócio
Config	Centraliza configurações da aplicação
SOLID

Conjunto de cinco princípios para garantir código orientado a objetos limpo, flexível e de fácil manutenção. Criado por Robert C. Martin:

S – Single Responsibility Principle (SRP):
Uma classe deve ter apenas um motivo para mudar, ou seja, uma única responsabilidade.

I – Interface Segregation Principle (ISP):
Nenhuma classe deve ser forçada a implementar métodos que não utiliza. Prefira interfaces específicas ao invés de genéricas.

MVC (Model-View-Controller)

Padrão arquitetural que separa a aplicação em três camadas:

Model: Dados e regras de negócio.

View: Interface com o usuário (ex.: HTML).

Controller: Intermedia a comunicação entre Model e View, controlando a lógica da aplicação.

Swing - Janela em Java
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

### Princípio da Inversão de Dependência

Esse princípio recomenda que classes clientes dependam de abstrações (interfaces ou classes abstratas), e não de implementações concretas. Abstrações são mais adaptáveis e flexíveis, enquanto implementações concretas limitam mudanças e dificultam manutenção.
Prefira composição a herança

Herança de classes: exemplo class A extends B, permite reuso de código, porém cria acoplamento entre classes.
Herança de interfaces: exemplo interface I extends J, impõe obrigação de implementar métodos, sem reuso de código.

Recomenda-se usar composição em vez de herança para maior flexibilidade.

### Princípio de Demeter

Um método deve invocar apenas métodos de:
Sua própria classe.
Objetos recebidos como parâmetro.
Objetos criados dentro do método.
Atributos da classe.
Princípio Aberto-Fechado
Uma classe deve estar aberta para extensões, mas fechada para modificações.

### Classe Abstrata

É uma classe parcialmente implementada, servindo como base para subclasses.

### Princípio de Liskov

Em contextos de herança, o princípio estabelece que uma classe filha deve poder substituir a classe base sem alterar o comportamento esperado. Ou seja, usar uma instância da classe filha onde a classe pai é esperada não deve causar erros nem comportamentos inesperados.
Características arquiteturais = requisitos não funcionais

Um sistema dificilmente atenderá 100% dos requisitos arquiteturais, tais como:

Disponibilidade
Confiabilidade
Integridade
Escalabilidade
Segurança
Agilidade
Tolerância a falhas
Elasticidade
Recuperabilidade
Desempenho
Implementabilidade
Capacidade de aprendizado

É necessário abrir mão de alguns aspectos, escolhendo características prioritárias para a arquitetura do sistema.

### Decisão arquitetural

Define como o sistema será organizado, ou seja, qual arquitetura será adotada para atender melhor às necessidades.

### O que faz um arquiteto de software?

Toma decisões arquiteturais: orienta a equipe, definindo o que fazer, como e por quê, preservando características como escalabilidade e desempenho.
Analisa continuamente a arquitetura: pode reconstruir partes do sistema para manter a vitalidade da arquitetura.
Mantém-se atualizado: acompanha as últimas tendências técnicas do setor.
Assegura conformidade: verifica se a equipe segue as decisões arquiteturais e princípios de design.
Possui experiência diversificada: exposto a tecnologias variadas.
Conhece o domínio do negócio: para comunicação eficaz com Product Owner (PO).
Habilidades interpessoais: motiva, inspira e lidera pessoas.
Lida com questões políticas: compreende hierarquias e negocia prazos.

### Design Patterns

Soluções reutilizáveis para problemas recorrentes em desenvolvimento de software, popularizados pelos "Gang of Four" (Erich Gamma, Richard Helm, Ralph Johnson e John Vlissides) em 1994.

Categorias:

Criacionais: focam na criação de objetos. Ex.: Abstract Factory, Factory Method, Singleton, Builder, Prototype.
Estruturais: tratam da composição de classes e objetos. Ex.: Proxy, Adapter, Facade, Decorator, Bridge, Composite, Flyweight.
Comportamentais: lidam com interação e divisão de responsabilidades. Ex.: Strategy, Observer, Template Method, Visitor, Chain of Responsibility, Command, Interpreter, Iterator, Mediator, Memento, State.

### Factory Method

Exemplo: sistema distribuído com objetos TCPChannel criados em três funções (f, g, h).
Problema: mudar para UDP quebra o Princípio Aberto/Fechado, pois o código precisa ser modificado em vários pontos.

Solução: centralizar a criação dos objetos em um método fábrica estático:

class ChannelFactory {
  public static Channel create() {
    return new TCPChannel();
  }
}

void f() {
  Channel c = ChannelFactory.create();
  ...
}


Se mudar para UDP, altera-se apenas o método create() na fábrica.

### Fábrica Abstrata:
Define vários métodos fábrica por meio de uma classe abstrata.

Singleton
Evita múltiplas instâncias de uma classe (ex.: Logger).

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


Uso:

Logger log = Logger.getInstance();
log.println("Executando f");

### Observer

Define uma relação de dependência um-para-muitos entre objetos, notificando automaticamente todos os interessados quando um objeto muda de estado.

Exemplo em Java:

public interface Observer {
    void update(String message);
}

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

public class Subscriber implements Observer {
    private String name;

    public Subscriber(String name) {
        this.name = name;
    }

    public void update(String message) {
        System.out.println(name + " recebeu: " + message);
    }
}

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

### Operação DevOps

DevOps visa entregar valor ao cliente de forma rápida e ágil, integrando desenvolvimento e operações. Todos são responsáveis pelo sistema, colaborando na criação e manutenção. Notificações de falhas são compartilhadas e resolvidas em equipe. Profissionais DevOps são raros, levando à criação de equipes especializadas.

Nível de Abstração
Papel	Foco Principal
Arquiteto	Alto nível: estrutura do sistema, tecnologias, decisões arquiteturais, requisitos não funcionais.
Designer/Desenvolvedor	Implementação prática: criação de código, design de classes, interfaces, testes e entrega.
Responsabilidades

Arquiteto:

Traduz requisitos de negócio em atributos arquiteturais.
Escolhe padrões, estilos e tecnologias.
Cria componentes estruturais.
Avalia trade-offs técnicos e comerciais.
Atua como mentor técnico.

Designer/Desenvolvedor:
Implementa componentes definidos.
Cria diagramas, interfaces e código.
Testa e valida o software.

Tipo de Conhecimento
Papel	Prioridade de Conhecimento
Arquiteto	Amplitude técnica: conhece várias tecnologias, mesmo que não profundamente.
Desenvolvedor	Profundidade técnica: especialista em poucas tecnologias.
Forma de Pensar

Arquiteto: visão ampla do sistema, conecta requisitos de negócio às decisões técnicas, equilibrando tecnologia, negócio e restrições.
Desenvolvedor: foco na implementação prática e detalhada das decisões arquiteturais.

### Trade-offs em Arquitetura

Nenhuma arquitetura atende perfeitamente todos os requisitos. Trade-offs são escolhas que priorizam certos aspectos em detrimento de outros.

Exemplo: arquitetura ideal para sistema de leilão não serve para marketplace com milhões de requisições por segundo.

Arquiteturas para alta escala

1. Arquitetura baseada em tópicos (Publish/Subscribe):
Modelo 1 para muitos: uma mensagem é publicada e todos os assinantes a recebem.
Baixo acoplamento entre emissor e receptor.
Similar ao padrão Observer, com notificações assíncronas.

2. Arquitetura baseada em filas:

Modelo 1 para 1: mensagens são enfileiradas e consumidas em ordem.
Garante entrega ordenada e armazenamento até o consumo.
Mais resiliente e com melhor observabilidade que tópicos.

Extensibilidade arquitetural

Filas garantem entrega e mantém histórico, porém exigem mudanças para novos consumidores.
Tópicos permitem adicionar consumidores sem alteração no emissor.
