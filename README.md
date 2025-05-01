# 🍽️ Restaurante Base

Este projeto é uma aplicação Java voltada para o **gerenciamento completo de um restaurante**, com foco em **modularidade**, **escalabilidade** e **clareza estrutural**. Ele oferece uma base sólida e extensível para sistemas que envolvam controle de pedidos, cardápio, clientes e funcionários.

## 🎯 Propósito

O projeto foi criado como uma **solução base para restaurantes**, com o objetivo de:

- Automatizar e organizar a operação de restaurantes de pequeno e médio porte.
- Servir como referência para arquiteturas em camadas orientadas a serviços (SOA).
- Ser um ponto de partida para projetos maiores, que demandem funcionalidades como APIs RESTful, relatórios e integrações externas.

---

## 🧩 Principais Funcionalidades

- **📦 Gestão de Pedidos**  
  Criação e acompanhamento de pedidos com itens do cardápio, valores e status.

- **📋 Gerenciamento de Cardápios**  
  Cadastro, edição e exclusão de pratos, bebidas e combos, com preços e descrições.

- **👤 Controle de Clientes**  
  Registro de dados de clientes para histórico de consumo e ações de fidelização.

- **👨‍🍳 Administração de Funcionários**  
  Gestão de usuários internos, com suas permissões e dados funcionais.

- **🔍 Consulta de Itens**  
  Busca por código ou nome de produtos, funcionários e clientes.

---

## 🌐 APIs RESTful Expostas

A aplicação já disponibiliza boa parte de suas funcionalidades por meio de **endpoints RESTful** organizados por recurso. Isso permite fácil integração com front-ends, sistemas externos ou aplicativos móveis. Exemplos de endpoints:

### 🔸 Cardápio (`/cardapio`)
| Método | Endpoint                     | Descrição                        |
|--------|------------------------------|----------------------------------|
| POST   | /cardapio                    | Adiciona um novo cardápio        |
| PUT    | /cardapio                    | Altera um cardápio existente     |
| DELETE | /cardapio/{codigo}           | Remove um cardápio pelo código   |
| GET    | /cardapio/codigo/{codigo}    | Busca um cardápio pelo código    |
| GET    | /cardapio/nome/{nome}        | Busca um cardápio pelo nome      |

### 🔸 Cliente (`/cliente`)
| Método | Endpoint                     | Descrição                         |
|--------|------------------------------|-----------------------------------|
| POST   | /cliente                     | Adiciona um novo cliente          |
| PUT    | /cliente                     | Altera um cliente existente       |
| DELETE | /cliente/{codigo}            | Remove um cliente pelo código     |
| GET    | /cliente/codigo/{codigo}     | Busca um cliente pelo código      |
| GET    | /cliente/nome/{nome}         | Busca clientes pelo nome          |

### 🔸 Entregador (`/entregador`)
| Método | Endpoint                     | Descrição                           |
|--------|------------------------------|-------------------------------------|
| POST   | /entregador                  | Adiciona um novo entregador         |
| PUT    | /entregador                  | Altera um entregador existente      |
| DELETE | /entregador/{codigo}         | Remove um entregador pelo código    |
| GET    | /entregador/codigo/{codigo}  | Busca um entregador pelo código     |


<br/>

> Todos os endpoints são implementados usando **Jakarta JAX-RS**.

---

## 🏗️ Estrutura do Projeto

A aplicação segue uma **arquitetura em camadas**, baseada em **separação de responsabilidades**. Isso facilita testes, manutenção e expansão do sistema.
```plaintext
src/
└── main/
    ├── java/
    │   └── ifmt/cba/
    │       ├── dto/          # Objetos de transferência de dados (DTOs)
    │       ├── entity/       # Entidades mapeadas para o banco de dados (JPA)
    │       ├── negocio/      # Regras de negócio e lógica principal
    │       ├── persistencia/ # Acesso ao banco de dados (DAO e repositórios)
    │       ├── servico/      # APIs RESTful e integração com a camada de negócio
    │       ├── util/         # Utilitários (validações, formatações, helpers)
    │       └── execucao/     # Classe principal e ponto de entrada do sistema
    └── resources/
        └── META-INF/
            └── persistence.xml  # Configuração da persistência JPA
```

## 🚧 Possíveis Expansões Futuras

- Integração com gateways de pagamento (ex: MercadoPago, Stripe).
- Emissão de relatórios gerenciais (faturamento, estoque, pedidos).
- Sistema de reservas de mesas.
- Interface mobile para clientes realizarem pedidos.
- Painel administrativo com dashboards.
