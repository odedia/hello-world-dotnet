
# hello-world-dotnet
a dotnet example

##docker run -it --rm -p 3000:80 --name hello-world-dotnet hello-world-dotnet

https://dotnet.microsoft.com/learn/aspnet/microservice-tutorial/install

Step 2: 
dotnet new webapi -o hello-world --no-https
cd hello-worldhttps://dotnet.microsoft.com/learn/aspnet/microservice-tutorial/install

Step 2: 
dotnet new webapi -o hello-world-dotnet --no-https
cd hello-world 

Dockerfile
FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build
WORKDIR /src
COPY hello-world-dotnet.csproj .
RUN dotnet restore
COPY . .
RUN dotnet publish -c release -o /app
https://dotnet.microsoft.com/learn/aspnet/microservice-tutorial/install

Step 2: 
dotnet new webapi -o hello-world-dotnet --no-https
cd hello-world 

Dockerfile
FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build
WORKDIR /src
COPY hello-world-dotnet.csproj .
RUN dotnet restore
COPY . .
RUN dotnet publish -c release -o /app

FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
WORKDIR /app
COPY --from=build /app .
ENTRYPOINT ["dotnet", "hello-world-dotnet.dll"]

.dockerignore
Copy
Dockerfile
[b|B]in
[O|o]bjFROM mcr.microsoft.com/dotnet/core/aspnet:3.1
WORKDIR /app
COPY --from=build /app .
ENTRYPOINT ["dotnet", "hello-world-dotnet.dll"]

.dockerignore
Copy
Dockerfile
[b|B]in
[O|o]bj
