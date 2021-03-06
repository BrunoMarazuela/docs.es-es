---
title: "Protocolo de Internet versión 6"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IPv6, improvements
- IPv4
- IPv6
- Internet Protocol version 6, improvements
- Internet Protocol version 6
ms.assetid: e6fa8ebd-010a-4c48-a5ec-a5102c53c06f
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 333fbb452cb1f24b5e62d1106eff4560b26267b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="internet-protocol-version-6"></a>Protocolo de Internet versión 6
El protocolo de Internet versión 6 (IPv6) es un nuevo conjunto de protocolos estándar para la capa de red de Internet. IPv6 está diseñado para resolver muchos de los problemas que se producen en la versión actual del conjunto de protocolo de Internet (conocido como IPv4) en relación con el agotamiento de direcciones, la seguridad, la configuración automática, la extensibilidad, etc. IPv6 amplía las funciones de Internet para habilitar nuevos tipos de aplicaciones, incluidas las aplicaciones móviles y de punto a punto. A continuación se indican los principales problemas del protocolo IPv4 actual:  
  
-   Rápido agotamiento del espacio de direcciones.  
  
     Esto ha llevado al uso de traductores de direcciones de red (NAT) que asignan varias direcciones privadas a una sola dirección IP pública. Los principales problemas causados por este mecanismo son la sobrecarga de procesamiento y la falta de conectividad de extremo a extremo.  
  
-   Falta de compatibilidad jerárquica.  
  
     Debido a su organización inherente de clases predefinidas, IPv4 carece de verdadera compatibilidad jerárquica. Es imposible estructurar las direcciones IP de forma que se asigne realmente la topología de red. Este error de diseño fundamental crea la necesidad de grandes tablas de enrutamiento para entregar paquetes de IPv4 en cualquier ubicación en Internet.  
  
-   Configuración de red compleja.  
  
     Con IPv4, las direcciones deben asignarse de forma estática o mediante un protocolo de configuración como DHCP. En una situación ideal, los hosts no deberían tener que confiar en la administración de una infraestructura DHCP. En su lugar, deberían poder realizar la configuración por sí mismos en función del segmento de red en el que se encuentran.  
  
-   Falta de autenticación y confidencialidad integradas.  
  
     IPv4 no requiere compatibilidad con ningún mecanismo que proporcione la autenticación o el cifrado de los datos intercambiados. Esto cambia con IPv6. El protocolo de seguridad de Internet (IPSec) es un requisito de compatibilidad con IPv6.  
  
 Un nuevo conjunto de protocolos debe cumplir los siguientes requisitos básicos:  
  
-   Enrutamiento a gran escala y direccionamiento con poca sobrecarga.  
  
-   Configuración automática para varias situaciones de conexión.  
  
-   Autenticación y confidencialidad integradas.  
  
 Para obtener más información, vea [IPv6 Addressing](../../../docs/framework/network-programming/ipv6-addressing.md) (Direccionamiento IPv6), [IPv6 Routing](../../../docs/framework/network-programming/ipv6-routing.md) (Enrutamiento de IPv6), [IPv6 Auto-Configuration](../../../docs/framework/network-programming/ipv6-auto-configuration.md) (Configuración automática de IPv6), [Enabling and Disabling IPv6](../../../docs/framework/network-programming/enabling-and-disabling-ipv6.md) (Habilitar y deshabilitar IPv6) y [How to: Modify the Computer Configuration File to Enable IPv6 Support](../../../docs/framework/network-programming/how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md) (Cómo: Modificar el archivo de configuración de equipo para habilitar la compatibilidad con IPv6).  
  
## <a name="references"></a>Referencias  
 A continuación se indica una selección de documentos RFC que se pueden encontrar en el sitio de Internet Engineering Task Force ([http://www.ietf.org](http://www.ietf.org/)):  
  
-   RFC 1287, Towards the Future Internet Architecture (Hacia la arquitectura de Internet del futuro).  
  
-   RFC 1454, Comparison of Proposals for Next Version of IP (Comparación de propuestas para una próxima versión de IP).  
  
-   RFC 2373, IP Version 6 Addressing Architecture (Arquitectura de direccionamiento de IP versión 6).  
  
-   RFC 2374, An IPv6 Aggregatable Global Unicast Address Format (Formato de dirección de unidifusión global agregable de IPv6).  
  
 También encontrará información relacionada con IPv6 en el [área de IPv6 en Technet](http://go.microsoft.com/fwlink/?LinkID=179658).  
  
## <a name="see-also"></a>Vea también  
 [Ejemplo de sockets IPv6](http://go.microsoft.com/fwlink/?LinkID=179568)  
 [Network Programming Samples (Ejemplos de programación de red)](../../../docs/framework/network-programming/network-programming-samples.md)  
 [Sockets](../../../docs/framework/network-programming/sockets.md)
