---
title: "Depuraci&#243;n de errores de autenticaci&#243;n de Windows | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF, autenticación"
  - "WCF, Autenticación de Windows"
ms.assetid: 181be4bd-79b1-4a66-aee2-931887a6d7cc
caps.latest.revision: 21
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 21
---
# Depuraci&#243;n de errores de autenticaci&#243;n de Windows
Cuando se utiliza la autenticación de Windows como un mecanismo de seguridad, la interfaz del proveedor de compatibilidad para seguridad \(SSPI\) controla los procesos de seguridad.Cuando los errores de seguridad se producen en el nivel de SSPI, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] los emerge.En este tema se proporciona un marco y conjunto de cuestiones que le ayudarán a diagnosticar los errores.  
  
 Para obtener una introducción al protocolo Kerberos, vea [Kerberos explicado](http://go.microsoft.com/fwlink/?LinkID=86946); para una introducción a SSPI, vea [SSPI](http://go.microsoft.com/fwlink/?LinkId=88941).  
  
 Para la autenticación de Windows, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza normalmente el proveedor de compatibilidad para seguridad \(SSP\) *Negotiate*, que realiza la autenticación mutua de Kerberos entre el cliente y el servicio.Si el protocolo Kerberos no está disponible, de forma predeterminada [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se retira a NT LAN Manager \(NTLM\).Sin embargo, puede configurar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para utilizar solo el protocolo Kerberos \(y para que se inicie una excepción si Kerberos no está disponible\).También puede configurar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para utilizar formularios restringidos del protocolo Kerberos.  
  
## Depuración de la metodología  
 El método básico es el siguiente:  
  
1.  Determine si está utilizando la autenticación de Windows.Si está utilizando cualquier otro esquema, no se aplicará este tema.  
  
2.  Si está seguro de que está utilizando la autenticación de Windows, determine si su configuración de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza Kerberos Direct o Negotiate.  
  
3.  Cuando haya determinado si su configuración está utilizando el protocolo Kerberos o NTLM, podrá entender los mensajes de error en el contexto correcto.  
  
### Disponibilidad del protocolo Kerberos y NTLM  
 SSP de Kerberos exige que un controlador de dominio actúe como el Centro de distribución de claves de Kerberos \(KDC\).El protocolo Kerberos solo está disponible cuando el cliente y el servicio están utilizando las identidades del dominio.En otras combinaciones de cuentas, se utiliza NTLM, tal y como se resume en la tabla siguiente.  
  
 Los encabezados de la tabla muestran posibles tipos de cuenta utilizados por el servidor.La columna izquierda muestra posibles tipos de cuenta utilizados por el cliente.  
  
||Usuario local|Sistema local|Usuario de dominio|Equipo del dominio|  
|-|-------------------|-------------------|------------------------|------------------------|  
|Usuario local|NTLM|NTLM|NTLM|NTLM|  
|Sistema local|NTLM anónimo|NTLM anónimo|NTLM anónimo|NTLM anónimo|  
|Usuario de dominio|NTLM|NTLM|Kerberos|Kerberos|  
|Equipo del dominio|NTLM|NTLM|Kerberos|Kerberos|  
  
 Específicamente, los cuatro tipos de cuenta incluyen:  
  
-   Usuario local: perfil de usuario de solo el equipo.Por ejemplo: `MachineName\Administrator` o `MachineName\ProfileName`.  
  
-   Sistema local: el SISTEMA de cuentas integrado en un equipo que no está unido a un dominio.  
  
-   Usuario del dominio: una cuenta de usuario en un dominio de Windows.Por ejemplo: `DomainName\ProfileName`.  
  
-   Equipo del dominio: un proceso con la identidad del equipo en ejecución en un equipo unido a un dominio de Windows.Por ejemplo: `MachineName\Network Service`.  
  
> [!NOTE]
>  Se captura la credencial de servicio cuando se llama al método <xref:System.ServiceModel.ICommunicationObject.Open%2A> de la clase <xref:System.ServiceModel.ServiceHost>.Se lee la credencial del cliente siempre que el cliente envíe un mensaje.  
  
## Problemas comunes de autenticación de Windows  
 En esta sección se tratan algunos problemas comunes de autenticación de Windows y las soluciones posibles.  
  
### Protocolo Kerberos  
  
#### Problemas de SPN\/UPN con el protocolo Kerberos  
 Cuando se utiliza la autenticación de Windows y se usa o se negocia el protocolo Kerberos mediante SSPI, la dirección URL que el extremo de cliente usa debe incluir el nombre de dominio completo del host de servicio dentro de la dirección URL del servicio.Esto supone que la cuenta con la que se ejecuta el servicio tiene acceso a la clave del nombre de entidad de seguridad de servicio \(SPN\) de equipo \(valor predeterminado\) que se crea cuando el equipo se agrega al dominio de Active Directory, que se hace por lo general ejecutando el servicio en la cuenta Servicio de red.Si el servicio no tiene acceso a la clave SPN del equipo, debe proporcionar el SPN correcto o el nombre principal del usuario \(UPN\) de la cuenta con la que se está ejecutando el servicio en la identidad del extremo del cliente.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] cómo funciona [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con SPN y UPN, vea [Identidad del servicio y autenticación](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
 En los escenarios de equilibrio de carga, como las granjas de servidores web o los conjuntos de procesos de aplicación web, una práctica común es definir una cuenta única para cada aplicación, asignar un SPN a esa cuenta y asegurarse de que todos los servicios de la aplicación se ejecutan con esa cuenta.  
  
 Para obtener un SPN para la cuenta de servicio, necesita ser un administrador de dominios de Active Directory.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Kerberos Technical Supplement for Windows](http://go.microsoft.com/fwlink/?LinkID=88330).  
  
#### El protocolo Kerberos Direct requiere que el servicio se ejecute en una cuenta de equipo de dominio  
 Esto se produce cuando la propiedad `ClientCredentialType` está establecida como `Windows` y la propiedad <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> está establecida como `false`, tal y como se muestra en el código siguiente.  
  
 [!code-csharp[C_DebuggingWindowsAuth#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#1)]
 [!code-vb[C_DebuggingWindowsAuth#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#1)]  
  
 Para solucionarlo, ejecute el servicio mediante una cuenta de equipo de dominio, como el servicio de red, en un equipo unido a un dominio.  
  
### La delegación requiere la negociación de la credencial  
 Para utilizar el protocolo de autenticación Kerberos con la delegación, debe implementar el protocolo Kerberos con negociación de la credencial \(a veces denominado Kerberos de "autenticación mutua" o "de varios pasos"\).Si implementa la autenticación de Kerberos sin la negociación de la credencial \(denominada en ocasiones Kerberos de "un disparo" o "fase única"\), se producirá una excepción.  
  
 Para implementar Kerberos con la negociación de credenciales, lleve a cabo los pasos siguientes:  
  
1.  Implemente la delegación estableciendo <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> como <xref:System.Security.Principal.TokenImpersonationLevel>.  
  
2.  Es necesaria la negociación de SSPI:  
  
    1.  Si está usando enlaces estándar, establezca la propiedad `NegotiateServiceCredential` como `true`.  
  
    2.  Si está utilizando los enlaces personalizados, establezca el atributo `AuthenticationMode` del elemento `Security` como `SspiNegotiated`.  
  
3.  Es necesaria la negociación de SSPI para utilizar Kerberos al no permitir el uso de NTLM:  
  
    1.  Realice esta acción en el código, con la siguiente instrucción: `ChannelFactory.Credentials.Windows.AllowNtlm = false`  
  
    2.  O bien puede hacerlo en el archivo de configuración estableciendo el atributo `allowNtlm` como `false`.Este atributo se incluye en [\<ventanas\>](../../../../docs/framework/configure-apps/file-schema/wcf/windows-of-clientcredentials-element.md).  
  
### Protocolo NTLM  
  
#### Negociar SSP retrocede hasta NTLM, pero NTLM está deshabilitado  
 La propiedad <xref:System.ServiceModel.Security.WindowsClientCredential.AllowNtlm%2A> se establece en `false`, que hace que [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] intente por todos los medios que se inicie una excepción si se utiliza NTLM.Tenga en cuenta que, aunque se establezca esta propiedad en `false`, es posible que se envíen igualmente las credenciales NTLM a través de la conexión.  
  
 A continuación, se muestra cómo deshabilitar el retroceso a NTLM.  
  
 [!code-csharp[C_DebuggingWindowsAuth#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#4)]
 [!code-vb[C_DebuggingWindowsAuth#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#4)]  
  
#### Error en el inicio de sesión de NTLM  
 Las credenciales del cliente no son válidas en el servicio.Compruebe que el nombre de usuario y la contraseña se hayan establecido correctamente y que se corresponde con una cuenta que es conocida en el equipo en el que se está ejecutando el servicio.NTLM utiliza las credenciales especificadas para iniciar sesión en el equipo del servicio.Mientras las credenciales pueden ser válidas en el equipo donde el cliente se está ejecutando, se producirá un error en este inicio de sesión si las credenciales no son válidas en el equipo del servicio.  
  
#### Se inicia la sesión anónima de NTLM, aunque los inicios de sesión anónimos se deshabilitan de manera predeterminada  
 Al crear un cliente, la propiedad <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> se establece como <xref:System.Security.Principal.TokenImpersonationLevel>, tal y como se muestra en el ejemplo siguiente, aunque de forma predeterminada el servidor no permite los inicio de sesión anónimos.Esto solo se produce cuando el valor predeterminado de la propiedad <xref:System.ServiceModel.Security.WindowsServiceCredential.AllowAnonymousLogons%2A> de la clase <xref:System.ServiceModel.Security.WindowsServiceCredential> sea `false`.  
  
 El código de cliente siguiente intenta habilitar los inicios de sesión anónimos \(observe que la propiedad predeterminada es `Identification`\).  
  
 [!code-csharp[C_DebuggingWindowsAuth#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#5)]
 [!code-vb[C_DebuggingWindowsAuth#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#5)]  
  
 El código del servicio siguiente cambia el valor predeterminado para habilitar los inicio de sesión anónimos por el servidor.  
  
 [!code-csharp[C_DebuggingWindowsAuth#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#6)]
 [!code-vb[C_DebuggingWindowsAuth#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#6)]  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] suplantación, vea [Delegación y suplantación](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
 Por otra parte, el cliente se está ejecutando como un servicio de Windows, utilizando el SISTEMA de cuentas integrado.  
  
### Otros problemas  
  
#### No se establecen las credenciales del cliente correctamente  
 La autenticación de Windows utiliza la instancia <xref:System.ServiceModel.Security.WindowsClientCredential> devuelta por la propiedad <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> de la clase <xref:System.ServiceModel.ClientBase%601>, no <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>.A continuación se muestra un ejemplo incorrecto.  
  
 [!code-csharp[C_DebuggingWindowsAuth#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#2)]
 [!code-vb[C_DebuggingWindowsAuth#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#2)]  
  
 En el ejemplo siguiente se muestra el ejemplo correcto.  
  
 [!code-csharp[C_DebuggingWindowsAuth#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#3)]
 [!code-vb[C_DebuggingWindowsAuth#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#3)]  
  
#### SSPI no está disponible  
 Los sistemas operativos siguientes no admiten la autenticación de Windows cuando se utilizó como un servidor: [!INCLUDE[wxp](../../../../includes/wxp-md.md)] Home Edition, [!INCLUDE[wxp](../../../../includes/wxp-md.md)] Media Center Edition y [!INCLUDE[wv](../../../../includes/wv-md.md)] Home Editions.  
  
#### Desarrollo e implementación con distintas identidades  
 Si desarrolla una aplicación en un equipo y la implementa en otro, y utiliza tipos de cuentas diferentes para autenticarse en cada equipo, el comportamiento puede ser diferente.Supongamos, por ejemplo, que desarrolla una aplicación en un equipo Windows XP Pro con el modo de autenticación `SSPI Negotiated`.Si utiliza una cuenta de usuario local para autenticarse, se utilizará el protocolo NTLM.Una vez desarrollada la aplicación, implementa el servicio en un equipo Windows Server 2003, donde se ejecuta bajo una cuenta de dominio.En este punto, el cliente no podrá autenticar el servicio, porque estará utilizando Kerberos y un controlador de dominio.  
  
## Vea también  
 <xref:System.ServiceModel.Security.WindowsClientCredential>   
 <xref:System.ServiceModel.Security.WindowsServiceCredential>   
 <xref:System.ServiceModel.Security.WindowsClientCredential>   
 <xref:System.ServiceModel.ClientBase%601>   
 [Delegación y suplantación](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)   
 [Escenarios no admitidos](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)