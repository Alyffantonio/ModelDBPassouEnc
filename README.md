# Modelagem de Dados PassouEncontrou

- Descrição do Projeto
Este projeto apresenta a modelagem de dados para um aplicativo de delivery, que permite que clientes façam pedidos diretamento ao vendedor ambulante. O diagrama representa as principais entidades e seus relacionamentos.

# Diagrama Entidade-Relacionamento (DER)
- status : *Em desenvolvimento*
- *podendo conter alguns erros!*

# users (Clientes):
- idusers (primary key) 
- first_name 
- last_name 
- phone 
- email 
- address 
- password 
- login 
- orders_id_orders (FK)

# sellers:
- idsellers (primary key) 
- name 
- email 
- password 
- rating 
- localization 
- name_establishment 
- orders_id_orders(FK) 
- product_idproduct(FK)


# orders:
- id_orders (chave primária) 
- date_time 
- status 
- total_value 
- product_idproduct(FK)
  
# product:
- idproduct(primary key)
- name
- description
- price

# comments:
- idcomments (Primary Key)
- users_idusers (FK)
- sellers_idsellers (FK)


# rating:
- idrating(Primary Key)
- rate
- users_idusers
- sellers_idsellers

# users_has_sellers:
- id (Primary Key)
- users_idusers (FK)
- sellers_idsellers (FK)

# Relacionamentos:
![image](https://github.com/user-attachments/assets/92bce1d4-e407-4dba-9e88-0ee9cabd82f1)


# Usuários (Clientes) e Pedidos:
- Relação 1:N (um para muitos).
- Um cliente pode fazer vários pedidos, mas cada pedido está associado a apenas um cliente.
- Chave estrangeira: orders_id_orders na tabela de usuários (Clientes) aponta para a tabela de pedidos (Orders).
# Vendedores e Pedidos:
- Relação 1:N (um para muitos).
- Um vendedor pode ter vários pedidos, mas cada pedido está associado a apenas um vendedor.
- Chave estrangeira: orders_id_orders na tabela de vendedores (Sellers) aponta para a tabela de pedidos (Orders).
# Pedidos e Produtos:
- Relação N:M (muitos para muitos).
- Um pedido pode conter vários produtos, e um produto pode estar em vários pedidos.
- Para representar essa relação, você precisará de uma tabela intermediária (tabela de junção) que relaciona pedidos e produtos.
# Comentários e Usuários/Vendedores:
- Relação 1:N (um para muitos).
- Tanto usuários quanto vendedores podem fazer comentários.
- Chave estrangeira: users_idusers e sellers_idsellers na tabela de comentários apontam para as tabelas de usuários e vendedores, respectivamente.
# Avaliações e Usuários/Vendedores:
- Relação 1:N (um para muitos).
- Tanto usuários quanto vendedores podem receber avaliações.
- Chave estrangeira: users_idusers e sellers_idsellers na tabela de avaliações apontam para as tabelas de usuários e vendedores, respectivamente.
# Relacionamento entre Usuários e Vendedores:
- Relação N:M (muitos para muitos).
- Um usuário pode seguir vários vendedores, e um vendedor pode ter vários seguidores.
- Para representar essa relação, você precisará de uma tabela intermediária (tabela de junção) que relaciona usuários e vendedores

# Instruções de Uso
Clone este repositório.
Importe o modelo de banco de dados para o seu sistema de gerenciamento de banco de dados (por exemplo, MySQL, PostgreSQL).
Execute consultas SQL para explorar os dados.

# Tecnologias Utilizadas
- MySQL
- Workbench
- Mermaid (para renderizar o diagrama no README)

  
