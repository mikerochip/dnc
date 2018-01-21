# Mostly got this from these 2 pages:
# https://stormpath.com/blog/tutorial-deploy-asp-net-core-on-linux-with-docker
# https://docs.docker.com/engine/examples/dotnetcore/#create-a-dockerfile-for-an-aspnet-core-application

FROM microsoft/dotnet:2.0-sdk
COPY . /app
WORKDIR /app

RUN dotnet restore
RUN dotnet publish -c Release -o out

EXPOSE 5001/tcp
ENV ASPNETCORE_URLS http://*:5001
 
ENTRYPOINT ["dotnet", "run"]
