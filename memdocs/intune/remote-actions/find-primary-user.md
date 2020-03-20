---
title: Busque el usuario primario de un dispositivo de Microsoft Intune.
titleSuffix: ''
description: Busque el usuario primario (o la afinidad entre usuario y dispositivo) de un dispositivo de Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/27/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c30cc122931588149120efa10710627826c50e2c
ms.sourcegitcommit: 3d895be2844bda2177c2c85dc2f09612a1be5490
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2020
ms.locfileid: "79337972"
---
# <a name="find-the-primary-user-of-an-intune-device"></a>Búsqueda del usuario primario de un dispositivo de Intune

El usuario primario, también conocido como Afinidad entre usuario y dispositivo, es una propiedad de cada dispositivo de Intune. Un dispositivo de Intune puede tener un usuario primario asignado o no tener ninguno. Si no hay ningún usuario primario asignado, el dispositivo se denomina "dispositivo compartido".

## <a name="find-a-devices-primary-user"></a>Búsqueda del usuario primario de un dispositivo

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Elija **Dispositivos** > y elija un dispositivo.
3. En la página **Información general**, puede ver el usuario principal en la lista.

## <a name="change-a-devices-primary-user"></a>Búsqueda del usuario primario de un dispositivo

El usuario primario de un dispositivo se puede actualizar para dispositivos Windows 10 que están unidos a Azure AD o unidos a Azure AD híbrido.

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Seleccione **Dispositivos** > **Todos los dispositivos** > elija un dispositivo > **Propiedades** > **Change primary user** (Cambiar usuario primario).
3. Seleccione un nuevo usuario y elija **Seleccionar**.

Una vez actualizado el usuario primario, también se actualizará las hojas de dispositivos de Intune y Azure AD.

No se puede cambiar el usuario primario en dispositivos Windows 10 administrados conjuntamente.


## <a name="what-is-the-primary-user"></a>¿Qué es el usuario primario?
La propiedad del usuario primario se usa para asignar un usuario de Intune con licencia con sus dispositivos en:
- La aplicación Portal de empresa.
- El sitio web del usuario final.
- Experiencias de los profesionales de TI, como las páginas de solución de problemas en Azure Portal. Estas páginas usan el usuario primario para asignar las cuentas de usuario a los dispositivos. 

### <a name="company-portal-app"></a>Aplicación de portal de empresa
La aplicación Portal de empresa espera que la cuenta de usuario que inició sesión en Portal de empresa sea el usuario primario de dicho dispositivo. Si se asignó otro usuario como el usuario primario, la aplicación Portal de empresa muestra una advertencia:

"Este dispositivo ya está asignado a un usuario de la organización. Póngase en contacto con el soporte técnico de la empresa para convertirse en el usuario primario del dispositivo. Puede seguir usando la aplicación Portal de empresa, pero con una funcionalidad limitada".

Si un dispositivo de Intune no tiene asignado ningún usuario primario, la aplicación Portal de empresa lo detectará como dispositivo compartido. Los dispositivos compartidos se identifican de manera visual con una etiqueta de "compartido" que aparece en el icono del dispositivo. En este modo, la aplicación Portal de empresa todavía se puede usar para solicitar e instalar aplicaciones disponibles. Sin embargo, las acciones de autoservicio (restablecer, cambiar nombre, retirar) no están disponibles.  

Para aparecer en la aplicación Portal de empresa de los dispositivos compatibles, las aplicaciones disponibles deben estar asignadas a un grupo de usuarios. Se instalarán en el contexto del sistema o en el contexto del usuario, en función de cómo el administrador de TI configuró la aplicación. Para más información sobre el contexto de la aplicación, consulte [Instalación de aplicaciones en dispositivos Windows 10](../apps/apps-windows-10-app-deploy.md). Para usar esta característica, se requiere la versión 10.3.4651.0 o posterior de la aplicación Portal de empresa.


## <a name="who-is-assigned-as-the-primary-user"></a>¿Quién está asignado como el usuario primario?
Intune agrega automáticamente el usuario primario a los dispositivos durante la inscripción o poco después de ella. El método de inscripción determina cuándo se agrega el usuario primario a un dispositivo.

| Plataforma | Método de inscripción | El usuario primario asignado | El usuario primario se asigna |
| ---- | ---- | ---- | ---- |
| Windows | Incorporación de trabajo o escuela (controlado por el usuario) | El usuario de la inscripción | Durante la inscripción |   
| Windows | Inicio de sesión de aplicación moderna (controlado por el usuario) | El usuario de la inscripción | Durante la inscripción | 
| Windows | Inscripción solo en MDM (controlado por el usuario) | El usuario de la inscripción | Durante la inscripción | 
| Windows | Unión a Azure AD (configuración rápida) | El usuario de la inscripción | Durante la inscripción | 
| Windows | Unión a Azure AD (configuración rápida de AutoPilot) | El usuario de la inscripción | Durante la inscripción | 
| Windows | Inscripción solo en MDM | El usuario de la inscripción | Durante la inscripción | 
| Windows | Unión a AAD híbrida + GPO de inscripción automática | El primer usuario que inicia sesión en Windows | Cuando el primer usuario inicia sesión en Windows| 
| Windows | Administración conjunta | El primer usuario que inicia sesión en Windows | Cuando el primer usuario inicia sesión en Windows | 
| Windows | Unión a Azure AD (token de inscripción masiva) | Ninguno | No disponible | 
| Windows | Unión a Azure AD (modo de implementación automática de AutoPilot) | Ninguno | No disponible | 
| Multiplataforma | Inscripción controlada por el usuario con la aplicación Portal de empresa | El usuario de la inscripción | Durante la inscripción |
| Multiplataforma | Administrador de inscripción de dispositivos (DEM) | El usuario de DEM de la inscripción | Durante la inscripción |
| iOS/iPadOS y macOS | Inscripción de dispositivos automatizada de Apple (DEP con afinidad entre usuario y dispositivo) | El usuario de la inscripción | Durante la inscripción |
| iOS/iPadOS y macOS | Inscripción de dispositivos automatizada de Apple (DEP sin afinidad entre usuario y dispositivo) | Ninguno | No disponible |
| Android | Dispositivos Android dedicados de propiedad corporativa | Ninguno | No disponible |

## <a name="primary-user-and-azure-ad-device-owner"></a>Usuario primario y propietario del dispositivo de Azure AD
En algunos casos, el usuario primario de Intune puede ser distinto de la propiedad **Owner** (Propietario) del dispositivo de Azure AD (que puede ver en **Dispositivos** > **Dispositivos de Azure AD**). El propietario del dispositivo de Azure AD se agrega durante el registro de un dispositivo en Azure Active Directory.

## <a name="next-steps"></a>Pasos siguientes
[Administre sus dispositivos de Intune.](device-management.md)