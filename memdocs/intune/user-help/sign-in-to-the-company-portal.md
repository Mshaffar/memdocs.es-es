---
title: Cómo iniciar sesión en la aplicación de portal de empresa | Microsoft Docs
description: Obtenga información sobre cómo iniciar sesión en la aplicación Portal de empresa en distintas plataformas.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 12/31/2019
ms.topic: end-user-help
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: cfd214bc-f072-4808-af2e-a3cbf7af9bca
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.collection: ''
ms.openlocfilehash: 59555c8bb9a35d5b70b46836f2298bf3ed342b2d
ms.sourcegitcommit: a77ba49424803fddcaf23326f1befbc004e48ac9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "83881830"
---
# <a name="sign-in-to-company-portal"></a>Inicio de sesión en el Portal de empresa  

Hay tres formas de iniciar sesión en la aplicación Portal de empresa:

* Inicie sesión con su dirección de correo electrónico profesional y la contraseña.  
* Inicio de sesión con autenticación basada en certificado.  
* Inicie sesión desde otro dispositivo.    


## <a name="sign-in-with-your-email-address-and-password"></a>Inicio de sesión con la dirección de correo electrónico y la contraseña
En los pasos siguientes se muestran capturas de pantallas del Portal de empresa para iOS.  

1. Abra la aplicación Portal de empresa en el dispositivo y pulse **Iniciar sesión**.  

   ![Captura de pantalla de ejemplo de la página de inicio de sesión de Portal de empresa.](./media/intune-ios-cp-signin-1908.png)


2. Especifique su **cuenta profesional o educativa** y pulse **Siguiente**.

   ![Se solicita al usuario que proporcione solamente su dirección de correo electrónico en lugar de la dirección de correo electrónico y la contraseña en la misma pantalla.](./media/cp_ios_aad_signin_after_1804_002.png)

3. Escriba la contraseña y pulse **Iniciar sesión**.

   ![El usuario deberá escribir la contraseña una vez que se acepte la dirección de correo electrónico.](./media/cp_ios_aad_signin_after_1804_003.png)

4. La aplicación comprobará sus credenciales. Cuando haya terminado, podrá acceder a los recursos de su organización e instalar las aplicaciones disponibles.  

   ![Después del proceso de autenticación, la aplicación Portal de empresa inicia sesión, lo que se indica con una barra de carga.](./media/cp_ios_aad_signin_after_1804_004.png)

## <a name="sign-in-with-certificate-based-authentication"></a>Inicio de sesión con autenticación basada en certificado
Solo verá esta opción de inicio de sesión si su organización permite la autenticación basada en certificados y usted tiene un certificado disponible para su uso.  

1. Abra la aplicación Portal de empresa en el dispositivo.  

2. Seleccione la **cuenta profesional o educativa**.  

3. Toque el vínculo **Iniciar sesión con un certificado**.  

4. Toque **Continuar** para usar el certificado.  

## <a name="sign-in-from-another-device"></a>Inicio de sesión desde otro dispositivo

Si la empresa usa tarjetas inteligentes para acceder a los equipos, es probable que tenga que autenticarse iniciando sesión en otro dispositivo.  

1. Abra la aplicación Portal de empresa en el dispositivo. Asegúrese de que es el dispositivo que va a usar para acceder a los recursos de trabajo.       

1. Seleccione **Iniciar sesión desde otro dispositivo**.  

   ![La página de inicio de sesión de Portal de empresa le pide la dirección de correo electrónico al usuario.  Se muestra el botón "Siguiente" y un vínculo "Iniciar sesión desde otro dispositivo". También incluye un vínculo a "¿No se puede acceder a su cuenta?". Un vínculo en la parte inferior lleva a información de Privacidad y cookies de Microsoft.](./media/cp_ios_aad_signin_after_1804_005.png)

2. Recibe un único código de un solo uso para iniciar sesión en el portal de empresa. Copie el código.

   ![Se proporcionan instrucciones para ir a la página https://microsoft.com/devicelogin con un código de acceso único desde el equipo de trabajo; luego se usa el código para iniciar sesión.](./media/cp_ios_aad_signin_after_1804_006.png)

3. En el otro dispositivo (el que está usando para la autenticación), abra el explorador y vaya a [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin). Escriba o pegue el código.  

   ![Imagen del explorador del usuario en su equipo de trabajo en lugar de su aplicación Portal de empresa. La página "Inicio de sesión del dispositivo" que aparece solicita al usuario el código que recibió en la aplicación Portal de empresa.](../fundamentals/media/whats-new-app-ui/cp_ios_aad_signin_from_another_device_after_1704_004.png)

4. Seleccione __Continuar__ para permitir que Portal de empresa inicie sesión en el dispositivo de trabajo.   

   ![El usuario ingresó su código único en el campo y el sitio "Inicio de sesión del dispositivo" solicitó la confirmación con respecto a que Portal de empresa de Intune era la aplicación correcta para recibir autorización para iniciar sesión.](../fundamentals/media/whats-new-app-ui/cp_ios_aad_signin_from_another_device_after_1704_005.png) 

5. Una vez que se comprueba el código, puede cerrar la ventana.  

   ![Una página de confirmación que establece que el usuario inició sesión en la aplicación Portal de empresa en el dispositivo y que se puede cerrar esta página.](../fundamentals/media/whats-new-app-ui/cp_ios_aad_signin_from_another_device_after_1704_006.png)

6. La aplicación Portal de empresa inicia sesión en el dispositivo de trabajo.  

   ![Después del proceso de autenticación, la aplicación de portal de empresa inicia sesión e indica su proceso con una barra de carga.](./media/cp_ios_aad_signin_after_1804_007.png)

¿Aún necesita ayuda? Póngase en contacto con el departamento de soporte técnico de la empresa. Para averiguar su información de contacto, vaya al [sitio web del portal de empresa](https://go.microsoft.com/fwlink/?linkid=2010980).  
