FROM mcr.microsoft.com/dotnet/core/sdk:6.0 as build-env
WORKDIR /app
COPY ../ .
RUN dotnet publish -c Release -o output

FROM nginx:alpine
WORKDIR /usr/share/nginx/html
COPY ..from=build-env /app/output/wwwroot .
