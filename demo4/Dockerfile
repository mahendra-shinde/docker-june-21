## Docker has no limit on how many STAGES you can have !!!
FROM mcr.microsoft.com/dotnet/sdk:2.1-alpine3.12 as build
COPY . . 
RUN ["dotnet","restore"]
RUN ["dotnet","publish","-o","dist"]

FROM mcr.microsoft.com/dotnet/aspnet:2.1-alpine3.12
WORKDIR /app
## Copy the published artifacts from previous stage "build"
COPY --from=build dist /app
CMD ["dotnet","/app/demo4.dll"]


