## 🔌 RabbitMQprodutor
Exemplo de API Comunicação por Mensageria com RabbitMQ em C# ASP.NET Core 10 com banco de dados SQLite.

#### 🔄 Executar a aplicação 

VSCode Terminal [1]
```bash 
docker-compose up --build 
```

VSCode Terminal [2]
```bash 
cd RabbitMQprodutor
dotnet run 
```

| Host | URL |
|-----------|-----------|
| **API**      | http://localhost:5010/swagger/index.html  |
| **RabbitMQ** | http://localhost:15672/ |

#### ⚙️ RabbitMQ -> Queues and Streams
- Em Queues , existe uma tabela Overview na coluna name , clique em **(fila)**
Desça até o botão Get Message(s) , voçê encontrará o Json enviado.

## 🔌 RabbitMQconsumir

#### 🔄 Executar a aplicação 

VSCode Terminal [3]
```bash 
cd RabbitMQconsumir
dotnet add RabbitMQconsumir.csproj package Microsoft.EntityFrameworkCore.Design
dotnet ef migrations add CriarBancoInicial
dotnet ef database update
dotnet run 
```
Os dados do arquivo **Json** serão gravados no SQLite. O consumer e a tabela somente são atualizados, se estiver em funcionamento, caso contrário, fica na fila de espera dentro do RabbitMQ.
