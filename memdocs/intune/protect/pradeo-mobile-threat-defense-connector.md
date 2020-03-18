---
title: Conector Mobile Threat Defense de Pradeo con Intune
titleSuffix: Intune on Azure
description: Aprenda a integrar Intune con el conector Mobile Threat Defense de Pradeo para controlar el acceso de los dispositivos móviles a los recursos corporativos.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/09/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: cde4d389-1770-4226-85a3-a2f3b3fb92a3
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: a23155c31586992c82781998bb664bf2ce6a0889
ms.sourcegitcommit: 3d895be2844bda2177c2c85dc2f09612a1be5490
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2020
ms.locfileid: "79339181"
---
# <a name="pradeo-mobile-threat-defense-connector-with-intune"></a>Conector Mobile Threat Defense de Pradeo con Intune

Puede controlar el acceso desde dispositivos móviles a recursos corporativos mediante el acceso condicional basado en la evaluación de riesgos efectuada por Pradeo, una solución de defensa contra amenazas móviles (MTD) integrada en Microsoft Intune. El riesgo se evalúa en función de la telemetría recopilada de los dispositivos que ejecutan la aplicación Pradeo.

Se pueden configurar directivas de acceso condicional según la evaluación de riesgos de Pradeo habilitada mediante las directivas de cumplimiento de dispositivos de Intune. Puede usar dichas directivas para permitir o bloquear dispositivos que no cumplan los requisitos y, de este modo, evitar que estos accedan a recursos corporativos en función de las amenazas detectadas.

> [!NOTE]
> Este proveedor de Mobile Threat Defense no es compatible con dispositivos no inscritos.

## <a name="supported-platforms"></a>Plataformas compatibles

- **Android 4.0.3 y versiones posteriores**

- **iOS 7 y versiones posteriores**

## <a name="prerequisites"></a>Requisitos previos

- Azure Active Directory Premium

- Suscripción a Microsoft Intune

- Pradeo Security para la suscripción a Mobile Threat Defense

  - Para obtener más información, vea el [sitio web de Pradeo](https://www.pradeo.com/en-US/mobile-threat-protection).

## <a name="how-do-intune-and-pradeo-help-protect-your-company-resources"></a>¿Cómo ayudan Intune y Pradeo a proteger los recursos de la empresa?

La aplicación Pradeo para iOS/iPadOS y Android captura telemetría del sistema de archivos, la pila de red, el dispositivo y las aplicaciones cuando está disponible. Después, envía los datos de telemetría al servicio en la nube de Pradeo para evaluar el riesgo del dispositivo frente a las amenazas móviles.

La directiva de cumplimiento de dispositivos de Intune incluye una regla para Mobile Threat Defense de Pradeo que se basa en la evaluación del riesgo de Pradeo. Cuando esta regla está habilitada, Intune evalúa la conformidad del dispositivo con la directiva que habilitó. Si se detecta que el dispositivo no cumple con la directiva, se bloqueará el acceso de los usuarios a los recursos corporativos, como Exchange Online y SharePoint Online. Los usuarios también reciben los pasos de la aplicación Pradeo instalada en sus dispositivos para resolver el problema y volver a obtener acceso a los recursos corporativos.

## <a name="sample-scenarios"></a>Escenarios de ejemplo

Estos son algunos casos más frecuentes.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Control del acceso basado en amenazas de aplicaciones malintencionadas

Cuando se detectan aplicaciones malintencionadas, como el malware, en los dispositivos, puede bloquear las siguientes acciones hasta resolver la amenaza:

- Conectarse al correo electrónico corporativo

- Sincronizar los archivos corporativos mediante la aplicación OneDrive para el trabajo

- Acceder a las aplicaciones de empresa

*Bloquear cuando se detectan aplicaciones malintencionadas:*

![Imagen conceptual de aplicaciones malintencionadas detectadas](./media/pradeo-mobile-threat-defense-connector/pradeo-maliciousapps-blocked.png)

*Acceso concedido tras la corrección:*

![Aplicaciones malintencionadas detectadas y acceso concedido](./media/pradeo-mobile-threat-defense-connector/pradeo-maliciousapps-unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Controlar el acceso basándose en amenazas en la red

Detecte amenazas para la red, por ejemplo, ataques de tipo **Man in the middle**, y proteja el acceso a las redes Wi-Fi según el riesgo del dispositivo.

*Bloquear el acceso de red a través de Wi-Fi:*

![Bloquear el acceso de red a través de Wi-Fi](./media/pradeo-mobile-threat-defense-connector/pradeo-network-wifi-blocked.png)

*Acceso concedido tras la corrección:*

![Imagen conceptual de acceso concedido tras la corrección](./media/pradeo-mobile-threat-defense-connector/pradeo-network-wifi-unblocked.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Controlar el acceso a SharePoint Online basándose en amenazas en la red

Detecte amenazas para la red, por ejemplo, ataques de tipo **Man in the middle**, y evite la sincronización de archivos corporativos según el riesgo del dispositivo.

*Bloqueo de SharePoint Online cuando se detectan amenazas a la red:*

![Bloqueo de SharePoint Online cuando se detectan amenazas a la red](./media/pradeo-mobile-threat-defense-connector/pradeo-network-spo-blocked.png)

*Acceso concedido tras la corrección:*

![Imagen conceptual de acceso concedido tras la corrección para el ejemplo de SharePoint](./media/pradeo-mobile-threat-defense-connector/pradeo-network-spo-unblocked.png)

<!-- 
### Control access on unenrolled devices based on threats from malicious apps

When the Pradeo Mobile Threat Defense solution considers a device to be infected:

![App protection policy blocks due to detected malware](./media/pradeo-mobile-threat-defense-connector/pradeo-app-policy-block.png)

Access is granted on remediation:

![Access is granted on remediation for App protection policy](./media/pradeo-mobile-threat-defense-connector/pradeo-app-policy-remediated.png)
-->

## <a name="next-steps"></a>Pasos siguientes

- [Integración de Pradeo con Intune](pradeo-mtd-connector-integration.md)

- [Configuración de las aplicaciones de Pradeo](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Creación de una directiva de cumplimiento de dispositivos de Pradeo](mtd-device-compliance-policy-create.md)

- [Activación del conector MTD de Pradeo](mtd-connector-enable.md)