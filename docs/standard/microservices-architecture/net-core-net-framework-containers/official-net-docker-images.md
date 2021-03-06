---
title: "Imágenes oficiales de Docker de .NET"
description: "Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Imágenes de Docker de .NET oficiales"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 42872caa1a9306187daeefd35feb9bec3fae60af
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="official-net-docker-images"></a>Imágenes oficiales de Docker de .NET

Las imágenes oficiales de Docker de .NET son imágenes de Docker que Microsoft ha creado y optimizado. Están disponibles públicamente en los repositorios de Microsoft en [Docker Hub](https://hub.docker.com/u/microsoft/). Cada repositorio puede contener varias imágenes, según las versiones de .NET y según el sistema operativo y las versiones (Linux Debian, Linux Alpine, Windows Nano Server, Windows Server Core, etcétera).

Lo que pretende Microsoft con los repositorios de .NET es disponer de repositorios orientados y detallados que representen un escenario o una carga de trabajo específicos. Por ejemplo, las imágenes [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) se deben emplear al usar ASP.NET Core en Docker, porque esas imágenes de ASP.NET Core proporcionan optimizaciones adicionales para que los contenedores se puedan iniciar más rápidamente.

Por otro lado, las imágenes de .NET Core (microsoft/dotnet) están diseñadas para las aplicaciones de consola basadas en .NET Core. Por ejemplo, los procesos por lotes, Azure WebJobs y otros escenarios de consola deben usar .NET Core. Estas imágenes no incluyen la pila de ASP.NET Core, lo que produce una imagen de contenedor más pequeña.

La mayoría de los repositorios de imágenes ofrece un etiquetado exhaustivo con el que es más fácil elegir no solo la versión de un marco concreto, sino también un sistema operativo (distribución de Linux o versión de Windows).

Para más información sobre las imágenes oficiales de Docker de .NET que proporciona Microsoft, vea el [resumen de imágenes de Docker de .NET](https://aka.ms/dotnetdockerimages).

## <a name="net-core-and-docker-image-optimizations-for-development-versus-production"></a>Optimizaciones de imágenes de .NET Core y Docker para desarrollo y para producción

Al compilar imágenes de Docker para desarrolladores, Microsoft se centró en los siguientes escenarios principales:

-   Imágenes que se usan para *desarrollar* y compilar aplicaciones de .NET Core.

-   Imágenes que se usan para *ejecutar* aplicaciones de .NET Core.

¿Por qué varias imágenes? Al desarrollar, compilar y ejecutar aplicaciones en contenedor, normalmente hay prioridades diferentes. Al proporcionar diferentes imágenes para estas tareas independientes, con Microsoft es más fácil optimizar los procesos independientes de desarrollo, creación e implementación de aplicaciones.

### <a name="during-development-and-build"></a>Durante el desarrollo y la compilación

Durante el desarrollo, lo importante es la velocidad con que se pueden iterar los cambios y la capacidad para depurar los cambios. El tamaño de la imagen no es tan importante como la capacidad de realizar cambios en el código y ver rápidamente los cambios. Algunas herramientas y "contenedores de agente de compilación" usan la imagen de ASP.NET Core de desarrollo (microsoft/aspnetcore-build) durante el proceso de desarrollo y compilación. Al compilar dentro de un contenedor de Docker, los aspectos importantes son los elementos necesarios para compilar la aplicación. Esto incluye el compilador y cualquier otra dependencia de .NET, así como las dependencias de desarrollo web como npm, Gulp y Bower.

¿Por qué es importante este tipo de imagen de compilación? Esta imagen no se implementa para producción, sino que es una imagen que se usa para compilar el contenido que se coloca en una imagen de producción. Esta imagen se usaría en el entorno de integración continua (CI) o el entorno de compilación. Por ejemplo, en lugar de instalar de forma manual todas las dependencias de la aplicación directamente en un host de agente de compilación (una máquina virtual, por ejemplo), el agente de compilación crearía una instancia de una imagen de compilación de .NET Core con todas las dependencias necesarias para compilar la aplicación. El agente de compilación solo necesita saber cómo ejecutar la imagen de Docker. Esto simplifica el entorno de integración continua, que resulta mucho más predecible.

### <a name="in-production"></a>En producción

Lo importante en producción es la rapidez con que se pueden implementar e iniciar los contenedores según una imagen de .NET Core de producción. Por tanto, la imagen solo en tiempo de ejecución basada en [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) es pequeña, por lo que puede desplazarse rápidamente a través de la red desde el Registro de Docker hasta los hosts de Docker. El contenido está listo para ejecutarse, lo que agiliza el proceso que va desde iniciar el contenedor hasta procesar los resultados. En el modelo de Docker, no es necesario compilar desde el código C\#, como cuando se ejecuta dotnet build o dotnet publish al usar el contenedor de compilación.

En esta imagen optimizada solo se colocan los archivos binarios y otros contenidos necesarios para ejecutar la aplicación. Por ejemplo, el contenido que crea dotnet publish solo contiene los archivos binarios de .NET compilados, las imágenes y los archivos .js y .css. Con el tiempo, verá imágenes que contienen paquetes anteriores a la compilación JIT.

Aunque hay varias versiones de las imágenes de .NET Core y ASP.NET Core, todas ellas comparten una o más capas, incluida la capa base. Por tanto, la cantidad de espacio en disco necesaria para almacenar una imagen es pequeña; consiste únicamente en las diferencias entre la imagen personalizada y su imagen base. El resultado es que es rápido extraer la imagen desde el registro.

Al explorar los repositorios de imágenes de .NET en Docker Hub, encontrará varias versiones de imágenes clasificadas o marcadas con etiquetas. Estas etiquetas ayudan a decidir cuál usar, según la versión que necesite, como las de la tabla siguiente:

-   microsoft/**aspnetcore:2.0**

        ASP.NET Core, with runtime only and ASP.NET Core optimizations, on Linux and Windows (multi-arch)

-   microsoft/**aspnetcore-build:2.0**

        ASP.NET Core, with SDKs included, on Linux and Windows (multi-arch)


>[!div class="step-by-step"]
[Previous] (net-container-os-targets.md) [Next] (../architect-microservice-container-applications/index.md)
