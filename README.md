# .Net Core GitVersion on Docker Container

GitVersion Dockerfile for .Net Core Projects

[![Docker Pulls](https://img.shields.io/docker/pulls/elioseverojunior/docker-dotnet-gitversion.svg)](https://hub.docker.com/r/elioseverojunior/docker-dotnet-gitversion/) [![Docker Automated build](https://img.shields.io/docker/automated/elioseverojunior/docker-dotnet-gitversion.svg)](https://hub.docker.com/r/elioseverojunior/docker-dotnet-gitversion/) [![Docker Build Status](https://img.shields.io/docker/build/elioseverojunior/docker-dotnet-gitversion.svg)](https://hub.docker.com/r/elioseverojunior/docker-dotnet-gitversion/)

## This Image Using

|                                  | Name          | Version       |
| --------------------------------- |:-------------:| -------------:|
| OS                               | Debian        |   Stretch (9) |
| .NET SDK                         | .NET Core SDK | 2.2 (2.2.401) |
| Git Version   (DotNet Core Tool) | CLI           |         5.0.1 |

Please check [Releases Page](https://github.com/elioseverojunior/docker-dotnet-gitversion/releases) for details.

## Latest Versions

[Latest Debian](https://www.debian.org/releases/stable/)
[Latest .Net SDK](https://www.microsoft.com/net/download/all)
[Latest Git Version](https://www.nuget.org/packages/dotnet-gitversion)

## Using Example


And then you need .Net Core project. If you haven't one, run this codes;

```
mkdir ConsoleApplication1
cd ConsoleApplication1

dotnet new console
dotnet new sln
dotnet sln ConsoleApplication1.sln add ConsoleApplication1.csproj
git init
```

Take login token from sonarqube server, change working directory to project directory and run this code;

```
docker run --name dotnet-gitversion -it --rm -v $(pwd):/pre-build \
  -e JENKINS_BUILD_NUMBER=1 \
  elioseverojunior/docker-dotnet-gitversion
```
