---
title: Borrar el contenido de un dispositivo macOS
titleSuffix: Microsoft Intune
description: Obtenga información sobre cómo borrar todos los datos, incluido el sistema operativo, de un dispositivo macOS.
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
ms.assetid: ab396092-907a-44b7-a157-aabee62176a9
ms.reviewer: coferro
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 50575b1a4b19a6fbebb3fd904a471e19b070860e
ms.sourcegitcommit: 302556d3b03f1a4eb9a5a9ce6138b8119d901575
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "83989962"
---
# <a name="erase-all-data-from-a-macos-device"></a>Borrar todos los datos de un dispositivo macOS

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Puede borrar todos los datos de un dispositivo macOS, incluido el sistema operativo. El dispositivo también se eliminará de la administración de Intune. No se proporcionará ninguna advertencia al usuario final.

1. En el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), elija **Dispositivos** > **Todos los dispositivos** > elija el dispositivo que quiera borrar.
2. Haga clic en **Más** > **Borrar** > proporcione un número de 6 dígitos para el **PIN de recuperación**. Este es el PIN que debe proporcionar al usuario para que pueda volver a instalar el sistema operativo en su dispositivo. No olvide anotar este PIN porque no podrá verlo una vez completada la acción de borrado.
![Captura de pantalla](./media/device-erase/providepin.png)
3. Haga clic en **Aceptar** para borrar el dispositivo.
