---
title: 'Cambio de nombre de un dispositivo con Microsoft Intune: Azure | Microsoft Docs'
description: Cambie el nombre de un dispositivo mediante Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/27/2020
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8beb69178c6f845592caa9890bc8ed9759eb2e23
ms.sourcegitcommit: 302556d3b03f1a4eb9a5a9ce6138b8119d901575
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "83983045"
---
# <a name="rename-a-device-in-intune"></a>Cambio de nombre de un dispositivo en Intune

La acción **Cambiar el nombre del dispositivo** le permite cambiar el nombre de un dispositivo que está inscrito en Intune. El nombre del dispositivo se cambia en Intune y en el dispositivo.

Puede cambiar el nombre de los tipos de dispositivos siguientes:
- Windows de propiedad corporativa 
- iOS/iPadOS supervisado
- MacOS 10 de propiedad corporativa

Esta característica no es compatible actualmente con el cambio de nombre de dispositivos Windows híbridos con Azure AD.

## <a name="rename-a-device"></a>Cambiar el nombre de un dispositivo

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Elija **Dispositivos** > **Todos los dispositivos** > elija un dispositivo > **...**  > **Cambiar el nombre del dispositivo**.
4. En la hoja **Cambio de nombre de un dispositivo**, escriba el nombre nuevo en el cuadro de texto. Puede usar letras, números y guiones. El nombre debe incluir al menos una letra o guion.
5. Si quiere reiniciar el dispositivo después de cambiarle el nombre, elija **Sí** junto a **Restart after rename** (Reiniciar tras cambio de nombre).
6. Elija **Cambiar nombre**.

## <a name="windows-device-rename-rules"></a>Reglas para cambiar el nombre de un dispositivo Windows
Al cambiar el nombre de un dispositivo Windows, el nuevo nombre debe seguir estas reglas:
- 15 caracteres o menos (debe ser menor o igual que 63 bytes, sin incluir el valor NULL final).
- No puede ser una cadena nula o vacía.
- Caracteres ASCII permitidos: letras (a-z, A-Z), números (0-9) y guiones
- Caracteres Unicode permitidos: caracteres >=0x80, debe tener un formato UTF8 válido, debe ser asignable mediante IDN (es decir, el proceso RtlIdnToNameprepUnicode debe finalizar correctamente. Consulte el documento RFC 3492).
- El nombre no debe contener números exclusivamente.
- El nombre no debe contener espacios.
- Caracteres no permitidos: { | } ~ [ \ ] ^ ' : ; < = > ? & @ ! " # $ % ` ( ) + / , . _ *)


## <a name="next-steps"></a>Pasos siguientes

Para ver el estado de la acción **Cambiar nombre** del dispositivo, revise la página de **Información general** del dispositivo.
