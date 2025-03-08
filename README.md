# Megaman Boss API

## Contexto
Este projeto é uma API desenvolvida em **.NET Core 3.1**, cujo objetivo principal é listar os dados dos bosses da franquia **Megaman**. O backend fornece respostas em JSON no seguinte formato:

```json
{
  "Id": 1,
  "Code": "DLN/DRN-003",
  "Name": "Cutman",
  "HP": 150,
  "Picture": "https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png"
}
```

## Tecnologias Utilizadas
O projeto utiliza as seguintes tecnologias:
- **[ASP.NET Core 3.1](https://dotnet.microsoft.com/en-us/download/dotnet/3.1)**
- **[Entity Framework Core](https://docs.microsoft.com/pt-br/ef/core/)**
- **[SQL Server](https://www.microsoft.com/pt-br/sql-server/sql-server-downloads)**
- **[Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/)**

## Estrutura do Projeto
A organização das pastas do projeto segue a estrutura abaixo:
```
.vs/
.vscode/
bin/
Controllers/
Database/
middlewares/
Models/
obj/
Properties/
Services/
appsettings.Development.json
appsettings.json  
global.json
MegamanApi.csproj  
MegamanApi.sln
Program.cs
Startup.cs
```
### Técnicas Utilizadas
- **Arquitetura MVC (Model-View-Controller)**: Para organização e separação de responsabilidades.
- **Entity Framework Core**: Para a persistência e manipulação do banco de dados.
- **Injeção de Dependência**: Implementada para facilitar a escalabilidade e manutenção do código.
- **Serialização JSON com Newtonsoft.Json**: Para manipulação de respostas JSON de forma otimizada.
- **Configuração via `appsettings.json`**: Para definir conexões e parâmetros do projeto.

## Dependências
| Dependência | Versão | Descrição |
|------------|--------|------------|
| [Microsoft.EntityFrameworkCore](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore/) | 3.1.8 | ORM para manipulação do banco de dados |
| [Microsoft.EntityFrameworkCore.Design](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore.Design/) | 3.1.8 | Ferramentas para design e migrações no Entity Framework Core |
| [Microsoft.EntityFrameworkCore.SqlServer](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore.SqlServer/) | 3.1.8 | Provedor do SQL Server para Entity Framework Core |
| [Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/) | 12.0.2 | Biblioteca para manipulação de JSON |

## Endpoints da API
### `GET /api/v1/robots`
Lista todos os robôs disponíveis.
#### Exemplo de Resposta:
```json
[
  {
    "Id": 1,
    "Code": "DLN/DRN-003",
    "Name": "Cutman",
    "HP": 150,
    "Picture": "https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png"
  }
]
```

---
### `GET /api/v1/robots/{id}`
Busca um robô pelo seu identificador único.
#### Exemplo de Resposta (Sucesso):
```json
{
  "Id": 1,
  "Code": "DLN/DRN-003",
  "Name": "Cutman",
  "HP": 150,
  "Picture": "https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png"
}
```
#### Exemplo de Resposta (Erro):
```json
{
  "message": "Nenhum robo encontrado"
}
```

---
### `POST /api/v1/robots`
Cria um novo robô.
#### Exemplo de Resposta:
```json
{
  "message": "Robô criado com sucesso"
}
```

## Configuração e Execução
1. **Clone o repositório:**
   ```sh
   git clone https://github.com/seu-usuario/megaman-api.git
   ```
2. **Acesse o diretório do projeto:**
   ```sh
   cd megaman-api
   ```
3. **Instale as dependências:**
   ```sh
   dotnet restore
   ```
4. **Execute a API:**
   ```sh
   dotnet run
   ```
5. **Acesse a API em:**
   ```
   http://localhost:5000/api/v1/robots
   ```
