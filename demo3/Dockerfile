FROM mcr.microsoft.com/dotnet/aspnet:2.1-alpine3.12
WORKDIR /app
COPY dist/ .
ENTRYPOINT [ "dotnet" ]
CMD ["/app/app1.dll"]

