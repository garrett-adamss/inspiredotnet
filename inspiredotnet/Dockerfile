FROM mcr.microsoft.com/dotnet/sdk:6.0 AS base
WORKDIR /app
EXPOSE 80/tcp

FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /src
COPY ["inspiredotnet.csproj", "./"]
RUN dotnet restore "inspiredotnet.csproj"
COPY . .
WORKDIR "/src/."
RUN dotnet build "inspiredotnet.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "inspiredotnet.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "inspiredotnet.dll"]
