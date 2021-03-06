---
title: Configuración del correo electrónico en Microsoft Intune (Azure) | Microsoft Docs
titleSuffix: ''
description: Cree un perfil de correo electrónico en Microsoft Intune, impleméntelo en el administrador de dispositivos Android y dispositivos Android Enterprise, iOS, iPadOS y Windows. Use perfiles de correo electrónico para configurar los valores de correo electrónico comunes, incluidos un servidor de correo electrónico y un método de autenticación para conectarse al correo electrónico corporativo en los dispositivos que administra.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/15/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9657353dd877b380d506e588934e3f6fd29b51c1
ms.sourcegitcommit: b7e5b053dfa260e7383a9744558d50245f2bccdc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "82587039"
---
# <a name="add-email-settings-to-devices-using-intune"></a>Agregar la configuración de correo electrónico a dispositivos que usan Intune

Microsoft Intune incluye una configuración de correo electrónico diferente que puede implementar en los dispositivos de su organización. Un administrador de TI crea perfiles de correo electrónico con una configuración específica para conectarse a un servidor de correo, como Office 365 y Gmail. Los usuarios finales luego se conectarán a las cuentas de correo electrónico corporativas, las autenticarán y las sincronizarán en sus dispositivos móviles. Al crear e implementar un perfil de correo electrónico, puede confirmar que la configuración es estándar en varios dispositivos. Y ayudará a reducir las llamadas de soporte técnico de los usuarios finales que no conocen la configuración de correo electrónico correcta.

Puede usar perfiles de correo electrónico para configurar las opciones de correo electrónico integradas en los siguientes dispositivos:

- Administrador de dispositivos Android en Samsung Knox Standard 4.0 y versiones más recientes
- Android Enterprise
- iOS 8.0 y versiones posteriores
- IPadOS 13.0 y versiones más recientes
- Windows Phone 8.1 y versiones posteriores
- Windows 10 (escritorio) y Windows 10 Mobile

En este artículo se explica cómo crear un perfil de correo electrónico en Microsoft Intune. También incluye vínculos a las distintas plataformas para consultar configuraciones más específicas.

## <a name="create-the-profile"></a>Creación del perfil

1. Inicie sesión en el [Centro de administración del Administrador de puntos de conexión de Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Seleccione **Dispositivos** > **Perfiles de configuración** > **Crear perfil**.
3. Escriba las propiedades siguientes:

    - **Plataforma**: seleccione la plataforma de los dispositivos. Las opciones son:  

        - **Administrador de dispositivos Android** (solo en Samsung Android Knox Standard)
        - **Android Enterprise**
        - **iOS/iPadOS**
        - **Windows 10 y versiones posteriores**
        - **Windows Phone 8.1**

    - **Perfil**: Seleccione **Correo electrónico**.

4. Seleccione **Crear**.
5. En **Básico**, escriba las propiedades siguientes:

    - **Nombre**: escriba un nombre descriptivo para la directiva. Asígnele un nombre a las directivas para que pueda identificarlas de manera sencilla más adelante. Por ejemplo, un nombre de directiva válido es **Windows 10: Configuración del correo electrónico para dispositivos Windows 10**.
    - **Descripción**: escriba una descripción para la directiva. Esta configuración es opcional pero recomendada.

6. Seleccione **Siguiente**.

7. En **Opciones de configuración**, las opciones que puede configurar serán diferentes, según la plataforma que haya elegido. Elija la plataforma para la configuración detallada:

    - [Administrador de dispositivos Android (Samsung Knox Standard)](email-settings-android.md)
    - [Android Enterprise](email-settings-android-enterprise.md)
    - [iOS/iPadOS](email-settings-ios.md)
    - [Windows 10](email-settings-windows-10.md)
    - [Windows Phone 8.1](email-settings-windows-phone-8-1.md)

8. Seleccione **Siguiente**.
9. En **Etiquetas de ámbito** (opcional), asigne una etiqueta para filtrar el perfil por grupos de TI específicos, como `US-NC IT Team` o `JohnGlenn_ITDepartment`. Para obtener más información sobre las etiquetas de ámbito, vea [Usar control de acceso basado en rol (RBAC) y etiquetas de ámbito](../fundamentals/scope-tags.md).

    Seleccione **Siguiente**.

10. En **Asignaciones**, seleccione los usuarios o grupos que van a recibir el perfil. Para obtener más información sobre la asignación de perfiles, vea [Asignación de perfiles de usuario y dispositivo](device-profile-assign.md).

    Seleccione **Siguiente**.

11. En **Revisar y crear**, revise la configuración. Si selecciona **Crear**, se guardan los cambios y se asigna el perfil. La directiva también se muestra en la lista de perfiles.

## <a name="remove-an-email-profile"></a>Eliminación de un perfil de correo electrónico

Los perfiles de correo electrónico se asignan a grupos de dispositivos, no a grupos de usuarios. Hay varias maneras de eliminar un perfil de correo electrónico de un dispositivo, incluso cuando hay un solo perfil de este tipo en el dispositivo:

- **Opción 1**: abra el perfil de correo electrónico (**Dispositivos** > **Perfiles de configuración**, seleccione su perfil y elija **Asignaciones**. En la pestaña **Incluir** se muestran los grupos que están asignados al perfil. Haga clic con el botón derecho en el grupo > **Quitar**. Asegúrese de **Guardar** los cambios.

- **Opción 2**: [borre o retire el dispositivo](../remote-actions/devices-wipe.md). Puede usar estas acciones para quitar datos y configuraciones de forma selectiva o por completo.

## <a name="secure-email-access"></a>Protección del acceso al correo electrónico

Puede ayudar a proteger los perfiles de correo electrónico con las siguientes opciones:

- **Certificados**: cuando se crea el perfil de correo electrónico, puede elegir un perfil de certificado creado anteriormente en Intune. Este certificado se conoce como "certificado de identidad". Se autentica con un perfil de certificado de confianza o un certificado raíz para confirmar que el dispositivo de un usuario tiene permiso para conectarse. El certificado de confianza se asigna al equipo que autentica la conexión de correo electrónico. Suele ser el servidor de correo nativo.

  Si usa la autenticación basada en certificados para el perfil de correo electrónico, implemente el perfil de correo electrónico, el de certificado y el perfil raíz de confianza en los mismos grupos para asegurarse de que cada dispositivo pueda reconocer la legitimidad de la entidad de certificación.

  Para más información sobre cómo crear y usar perfiles de certificado en Intune, consulte [Secure resource access with certificate profiles](../protect/certificates-configure.md) (Protección del acceso a recursos con perfiles de certificado).

- **Nombre de usuario y contraseña**: el usuario final se autentica en el servidor de correo nativo al proporcionar su nombre de usuario y contraseña. La contraseña no existe en el perfil de correo electrónico. Por lo tanto, el usuario final escribe la contraseña al conectarse al correo electrónico.

## <a name="how-intune-handles-existing-email-accounts"></a>Cómo Intune administra las cuentas de correo electrónico existentes

Si el usuario ya ha configurado una cuenta de correo electrónico, el perfil de correo electrónico se asigna de forma diferente, dependiendo de la plataforma.

- **iOS/iPadOS**: Se detecta un perfil de correo electrónico existente duplicado en función del nombre de host y la dirección de correo electrónico. El perfil de correo electrónico duplicado bloquea la asignación de un perfil de Intune. En este caso, la aplicación de Portal de empresa informa al usuario final de que no es compatible y le pide que quite el perfil configurado manualmente. Para evitar este problema, indique a los usuarios finales que se inscriban *antes* de instalar un perfil de correo electrónico. Esto permite que Intune configure el perfil.

- **Windows:** Se detecta un perfil de correo electrónico existente duplicado en función del nombre de host y la dirección de correo electrónico. Intune sobrescribe el perfil de correo electrónico existente que ha creado el usuario final.

- **Android Samsung Knox Standard**: Se detecta un perfil de correo electrónico existente duplicado en función de la dirección de correo electrónico y se sobrescribe con el perfil de Intune. Android no usa el nombre de host para identificar el perfil. No cree varios perfiles de correo electrónico con la misma dirección de correo electrónico en diferentes hosts. Los perfiles se sobrescriben entre sí.

- **Perfiles de trabajo Android**: Intune proporciona dos perfiles de correo electrónico de trabajo Android, uno para la aplicación de Gmail y otro para la aplicación de Nine Work. Estas aplicaciones están disponibles en Google Play Store e instalan el perfil de trabajo del dispositivo. Estas aplicaciones no crean perfiles duplicados. Ambas aplicaciones admiten conexiones a Exchange. Para usar la conectividad de correo electrónico, implemente una de estas aplicaciones de correo electrónico en los dispositivos de los usuarios. A continuación, cree e implemente el perfil de correo electrónico adecuado. Puede usar perfiles de configuración de correo electrónico de Gmail y Nine que funcionarán con los tipos de inscripción de perfil de trabajo y de propietario del dispositivo, e incluirán el uso de perfiles de certificado en ambos tipos de configuración de correo electrónico. Todas las directivas de Gmail o Nine que haya creado en la configuración del dispositivo para perfiles de trabajo seguirán aplicándose al dispositivo, sin necesidad de trasladarlas a las directivas de configuración de aplicaciones. Puede que algunas aplicaciones de correo electrónico, como Nine Work, no sean gratuitas. Revise los detalles de la licencia de la aplicación o póngase en contacto con la empresa de la aplicación si tiene alguna pregunta. 

## <a name="changes-to-assigned-email-profiles"></a>Cambios realizados en los perfiles de correo electrónico asignados

Si hace cambios en el perfil de correo electrónico que asignó anteriormente, puede que los usuarios finales vean un mensaje que les pida aprobar la reconfiguración de los ajustes de correo electrónico.

## <a name="next-steps"></a>Pasos siguientes

Se crea el perfil, pero todavía no hace nada. Después, [asigne el perfil](device-profile-assign.md) y [supervise el estado](device-profile-monitor.md).
