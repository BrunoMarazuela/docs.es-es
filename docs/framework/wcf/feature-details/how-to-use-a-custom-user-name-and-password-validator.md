---
title: "Cómo utilizar un nombre de usuario personalizado y un validador de contraseñas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, username and password
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ee138c52c8cdd63137bf3c468ebbdd064d60d443
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-custom-user-name-and-password-validator"></a>Cómo utilizar un nombre de usuario personalizado y un validador de contraseñas
De forma predeterminada, cuando un nombre de usuario y la contraseña se utilizan para la autenticación, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] utiliza Windows para validar el nombre de usuario y la contraseña. Sin embargo, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] permite esquemas de autenticación de nombre y contraseña de usuario personalizada, también conocido como *validadores*. Para incorporar un nombre de usuario personalizado y un validador de contraseña, cree una clase que derive de <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> y, a continuación, configúrela.  
  
 Para una aplicación de ejemplo, vea [validador de contraseña de nombre de usuario](../../../../docs/framework/wcf/samples/user-name-password-validator.md).  
  
### <a name="to-create-a-custom-user-name-and-password-validator"></a>Para crear un nombre de usuario personalizado y un validador de contraseñas  
  
1.  Cree una clase que derive de <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]  
  
2.  Implemente el esquema personalizado de autenticación invalidando el método <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.  
  
     No utilice el código en el ejemplo siguiente que invalida el método <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> en un entorno de producción. Reemplace el código con su nombre de usuario personalizado y esquema de validación de contraseña, que podrían implicar la recuperación de los pares de nombre de usuario y contraseña de una base de datos.  
  
     Para devolver errores de autenticación al cliente, genere una <xref:System.ServiceModel.FaultException> en el método <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]  
  
### <a name="to-configure-a-service-to-use-a-custom-user-name-and-password-validator"></a>Para configurar un servicio con el fin de utilizar un nombre de usuario personalizado y un validador de contraseñas  
  
1.  Configure un enlace que utilice la seguridad de mensaje sobre cualquier transporte o la seguridad del nivel de transporte sobre HTTP(S).  
  
     Al utilizar la seguridad de los mensajes, agregar uno de los enlaces proporcionados por el sistema, como un [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), o un [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) que admite seguridad de mensajes y la `UserName` tipo de credencial.  
  
     Al usar la seguridad de nivel de transporte sobre HTTP (S), agregue el [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) o [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), [ \< netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) o un [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) que utilice HTTP (S) y el `Basic` esquema de autenticación.  
  
    > [!NOTE]
    >  Si se utiliza [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] o una versión posterior, puede usarse un validador de nombre de usuario y de contraseña personalizado con la seguridad de mensaje y de transporte. Con [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], solo puede utilizarse un validador de nombre de usuario y de contraseña con la seguridad de mensaje.  
  
    > [!TIP]
    >  Para obtener más información sobre el uso de \<netTcpBinding > en este contexto, vea [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)  
  
    1.  En el archivo de configuración, en la [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) elemento, agregue un [ \<enlaces >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) elemento.  
  
    2.  Agregar un [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) o [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) elemento a la sección de enlaces. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]crear un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] enlace elemento, vea [Cómo: especificar un enlace de servicio en la configuración](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
    3.  Establecer el `mode` atributo de la [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) o [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) a `Message`, `Transport`, `or``TransportWithMessageCredential`.  
  
    4.  Establecer el `clientCredentialType` atributo de la [ \<mensaje >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) o [ \<transporte >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).  
  
         Al utilizar la seguridad de los mensajes, establezca la `clientCredentialType` atributo de la [ \<mensaje >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) a `UserName`.  
  
         Al usar la seguridad de nivel de transporte sobre HTTP (S), establezca el `clientCredentialType` atributo de la [ \<transporte >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) o [ \<transporte >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) a `Basic`.  
  
        > [!NOTE]
        >  Cuando un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se hospeda en Internet Information Services (IIS) mediante la seguridad del nivel de transporte, y se establece la propiedad <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> como <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>, el esquema de autenticación personalizado utiliza un subconjunto de autenticación de Windows. Esto se debe a que en este escenario, IIS realiza la autenticación de Windows antes de que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] invoque al autenticador personalizado.  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]crear un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] enlace elemento, vea [Cómo: especificar un enlace de servicio en la configuración](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
     El siguiente ejemplo muestra el código de configuración para el enlace.  
  
    ```xml  
    <system.serviceModel>   
      <bindings>  
      <wsHttpBinding>  
          <binding name="Binding1">  
            <security mode="Message">  
              <message clientCredentialType="UserName" />  
            </security>  
          </binding>          
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
2.  Configure un comportamiento que especifique que un nombre de usuario personalizado y el validador de contraseñas se utilizan para validar los pares de nombre de usuario y para los tokens de seguridad <xref:System.IdentityModel.Tokens.UserNameSecurityToken> entrantes.  
  
    1.  Como elemento secundario de la [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) elemento, agregue un [ \<comportamientos >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento.  
  
    2.  Agregar un [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) a la [ \<comportamientos >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento.  
  
    3.  Agregar un [ \<comportamiento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) y establezca el `name` de atributo en un valor adecuado.  
  
    4.  Agregar un [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) a la [ \<comportamiento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) elemento.  
  
    5.  Agregar un [ \<userNameAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) a la [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).  
  
    6.  Establezca `userNamePasswordValidationMode` en `Custom`.  
  
        > [!IMPORTANT]
        >  Si no se establece el valor `userNamePasswordValidationMode`, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza la autenticación de Windows en lugar del nombre de usuario personalizado y validador de la contraseña.  
  
    7.  Establezca `customUserNamePasswordValidatorType` en el tipo que representa su nombre de usuario personalizado y el validador de la contraseña.  
  
     El ejemplo siguiente muestra el fragmento `<serviceCredentials>` en este punto.  
  
    ```xml  
    <serviceCredentials>  
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />  
    </serviceCredentials>  
    ```  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente muestra cómo crear un nombre de usuario personalizado y el validador de la contraseña. No utilice el código que invalida el método <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> en un entorno de producción. Reemplace el código con su nombre de usuario personalizado y esquema de validación de contraseña, que podrían implicar la recuperación de los pares de nombre de usuario y contraseña de una base de datos.  
  
 [!code-csharp[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
 [!code-vb[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]  
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>  
 [Uso del proveedor de pertenencia de ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)  
 [Autenticación](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)
