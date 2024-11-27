# Teste para Programador Python Júnior

## Etapa 1: Configuração Inicial e Modelos Básicos

<strong>Objetivo</strong>: Criar a estrutura inicial do projeto Django e definir os modelos principais.
<ol>
  <li><strong>Criação do projeto</strong>: O candidato deve iniciar um projeto Django chamado <strong>banco_app</strong>.</li>
  <li><strong>Criação do App</strong>: Cria um app dentro do projeto chamado <strong>clientes</strong>.</li>
  <li>
    <strong>Definir Modelos</strong>:
    <ul>
      <li>
        Criar um modelo <strong>Cliente</strong> com os seguintes campos:
        <ul>
          <li><strong>nome</strong> (CharField)</li>
          <li><strong>email</strong> (EmailField)</li>
          <li><strong>data_nascimento</strong> (DateField)</li>
          <li><strong>telefone</strong> (CharField)</li>
        </ul>
      </li>
      <li>
        Criar um modelo <strong>Conta</strong> com os seguintes campos:
        <ul>
          <li><strong>cliente</strong> (ForeignKey para o modelo <strong>Cliente</strong>)</li>
          <li><strong>numero_conta</strong> (CharField, único)</li>
          <li><strong>saldo</strong> (DecimalField com <strong>max_digits=10</strong> e <strong>decimal_places=2</strong>)</li>
        </ul>
      </li>
    </ul>
  </li>
  <li><strong>Migrações</strong>: Executar e confirmar as migrações para criar as tabelas.</li>
</ol>
<strong>Entrega esperada</strong>: Um projeto Django inicial com os modelos <strong>Cliente</strong> e <strong>Conta</strong> criados e migrados.

## Etapa 2: CRUD Básico para clientes e Contas

<strong>Objetivo</strong>: Implementar o CRUD básico para gerenciar clientes e contas.
<ol>
  <li>
    <strong>Views e Templates</strong>:
    <ul>
      <li>
        Criar views para <strong>Cliente</strong> e <strong>Conta</strong> com as seguintes operações:
        <ul>
          <li><strong>Criar</strong> Formulário para criar novos clientes e contas.</li>
          <li><strong>Listar</strong> Uma página que exiba todos os clientes e contas em listas separadas.</li>
          <li><strong>Editar</strong> Formulário para editar clientes e contas existentes.</li>
          <li><strong>Deletar</strong> Função para deletar clientes e contas.</li>
        </ul>
      </li>
    </ul>
  </li>
  <li><strong>URLs</strong>: Definir as URLs para as operações de CRUD.</li>
  <li>
    <strong>Forms</strong>: Usar <strong>ModelForm</strong> para criar formulários para <strong>Cliente</strong> e <strong>Conta</strong>,
    com templates básicos para adicionar, listar, editar e deletar registros.
  </li>
</ol>
<strong>Entrega esperada</strong>: Um CRUD completo e funcional para os modelos <strong>Cliente</strong> e <strong>Conta</strong>
com templates básicos para adicionar, listar, editar e deletar registros.

## Etapa 3: Validações e regras de Negócio
<strong>Objetivo</strong>: Implementar validações e regras para garantir a integridade dos dados.
<ol>
  <li>
    <strong>Validações no Modelo Conta</strong>:
    <ul>
      <li><strong>saldo</strong> deve ser inicializado com valor zero ao criar uma nova conta.</li>
      <li><strong>numero_conta</strong> deve ser único e composto por 10 dígitos (ex: 1234567890).</li>
    </ul>
  </li>
  <li>
    <strong>Validações no Modelo Cliente</strong>:
    <ul>
      <li><strong>telefone</strong> deve seguir um formato específico (ex: (99) 99999-9999).</li>
      <li><strong>data_nascimento</strong>deve ser uma data no passado.</li>
    </ul>
  </li>
  <li>
    <strong>Teste de Validação</strong>:
    <ul>
      <li>Criar testes unitários para validar o comportamento esperado.</li>
    </ul>
  </li>
</ol>
<strong>Entrega esperada</strong>: Sistema com regras de negócio implementadas e testes básicos para validações.

## Etapa 4: Operações de Transações Bancárias
<strong>Objetivo</strong>: Implementar funcionalidades básicas para depósitos, saques  transferências.
<ol>
  <li>
    <strong>Adicionar views para Transações</strong>
    <ul>
      <li><strong>Depositar</strong>: criar uma view onde é possível informar o <strong>numero_conta</strong> e o valor a ser depositado.</li>
      <li><strong>Sacar</strong>: Similar à de deposito, mas verificar se o saldo disponível é suficiente.</li>
      <li><strong>Transferir</strong>: Permitir transferências entre contas (selecionando <strong>numero_conta</strong> de origem e destino).</li>
    </ul>
  </li>
  <li>
    <strong>Regras de negócio para Transações</strong>
    <ul>
      <li>Saques e transferências só podem ocorrer se o saldo for suficiente.</li>
      <li>Limitar transferências a um valor máximo (ex: R$ 5000,00)</li>
    </ul>
  </li>
  <li>
    <strong>Histórico de Transações</strong>:
    <ul>
      <li>
        Criar um modelo <strong>Transacao</strong> que armazene a operação
        (<strong>saque</strong>, <strong>depósito</strong> ou <strong>transfêrencia</strong>), valor, data e conta
      </li>
    </ul>
  </li>
</ol>
<strong>Entrega esperada</strong>: Funcionalidade de transações bancárias com validações e registro de histórico.

## Etapa 5: API para Integração Externa (opcional)
<strong>Objetivo</strong>: Criar uma API para permitir o gerenciamento de clientes e contas através de requisições HTTP.
<ol>
  <li>
    <strong>Configuração do Django REST Framework</strong>:
    <ul>
      <li>Adicionar e configurar o <strong>djangorestframework no projeto</strong></li>
    </ul>
  </li>
  <li>
    <strong>Endpoints</strong>:
    <ul>
      <li>Criar endpoints para as operações CRUD de <strong>Cliente</strong> e <strong>Conta</strong>.</li>
      <li>Endpoints para realizar transações de depósito, saque e transfêrenci.</li>
    </ul>
  </li>
  <li>
    <strong>Autenticação Simples</strong>:
    <ul>
      <li>Implementar autenticação básica para proteger os endpoints.</li>
    </ul>
  </li>
</ol>
<strong>Entrega esperada</strong>: API REST para integração com operações CRUD e transações.

