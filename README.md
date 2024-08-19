# bdrelacional_oficina_mecanica


+----------------+        +------------------+        +------------------+
|    Clientes    |<-----1-|     Veículos     |1-----> | Ordens de Serviço|
+----------------+        +------------------+        +------------------+
| ClienteID (PK) |        | VeiculoID (PK)   |        | OSID (PK)        |
| Nome           |        | Placa            |        | Numero           |
| Endereço       |        | Modelo           |        | DataEmissao      |
| Telefone       |        | Ano              |        | ValorTotal       |
| Email          |        | ClienteID (FK)   |        | Status           |
+----------------+        +------------------+        | DataConclusao    |
                                                    | VeiculoID (FK)    |
                                                    | EquipeID (FK)     |
                                                    +------------------+
                                                              |
                                                              |1
                                                              |
                                                         +----v----+
                                                         | Equipes |
                                                         +---------+
                                                         | EquipeID|
                                                         | NomeEquipe|
                                                         +---------+
                                                              1|
                                                              |
                                                         +----v-----+
                                                         | Mecânicos |
                                                         +-----------+
                                                         | MecanicoID|
                                                         | Nome      |
                                                         | Endereço  |
                                                         | Especialidade |
                                                         +-----------+

+-------------+        +-----------+        +-------------+       +-----------+
|  Serviços   |<-1---->| OS_Servicos|---n-> | Ordens de Serviço |--n>|OS_Pecas  |
+-------------+        +-----------+        +-------------+       +-----------+
| ServicoID   |        | OSID (FK)  |       | OSID (FK)   |       |PecaID (FK)|
| Descricao   |        | ServicoID (FK) |   | ServicoID   |       |Quantidade |
| ValorMaoDeObra |     | Quantidade |       +-------------+       +-----------+
+-------------+        +-----------+                                 
                                                                    |
                                                                    n|
                                                                     |
                                                                +---v--+
                                                                | Peças|
                                                                +------+
                                                                | PecaID|
                                                                | Descricao|
                                                                | Valor   |
                                                                +------+

