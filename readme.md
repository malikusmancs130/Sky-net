Setup project
dotnet new list -> for check what type of project .net have
dotnet new sln  -> create solution for project
dotnet new webapi -o API -controllers -> create project with controller tempelate 
dotnet new classlibb -o Core
dotnet new classlibb -o Infrastructre

Now our solution project is contrainer for .net project we need to add diff project init.
dotnet sln add API Core Infrastructure 

to confirm all project include in solution : dotnet sln list

now API depends on -> infra and infra depends on -> core 
dotnet add reference ../Infrastructure
dotnet add reference ../Core

to check everything is fine : dotnet restore and then dotnet build
dotnet run . dotnet watch
---------------------------------------------------------------------------------------------------------------------------------------------
dotnet ef migrations add InitialCreate -s API -p Infrastructure
dotnet ef migrations remove -s API -p Infrastructure

dotnet ef database update -s API -p Infrastructure
