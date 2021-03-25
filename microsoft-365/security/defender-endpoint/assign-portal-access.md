---
title: Назначение доступа пользователей к Центру безопасности Защитника Майкрософт
description: Назначить для чтения и записи или чтения только доступ к порталу Microsoft Defender для конечной точки.
keywords: назначение ролей пользователей, назначение доступа к чтением и записи, назначение доступа только для чтения, пользователя, ролей пользователей, ролей
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/28/2018
ms.technology: mde
ms.openlocfilehash: 71215c4988351644cfa4d79503c097c932caf9d6
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164781"
---
# <a name="assign-user-access-to-microsoft-defender-security-center"></a>Назначение доступа пользователей к Центру безопасности Защитника Майкрософт

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- Azure Active Directory.
- Office 365:
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Defender for Endpoint поддерживает два способа управления разрешениями:

- **Управление базовыми разрешениями.** Установите разрешения для полного доступа или только для чтения.
- Управление доступом на основе ролей **(RBAC)**: Установите гранулярные разрешения путем определения ролей, назначения групп пользователей Azure AD к ролям и предоставления группам пользователей доступа к группам устройств. Дополнительные сведения о RBAC см. в ссылке Управление доступом к порталу с помощью управления доступом на основе [ролей.](rbac.md)

> [!NOTE]
> Если вам уже назначены основные разрешения, вы можете перейти на RBAC в любое время. Перед переходом рассмотрите следующие вопросы:
> 
> - Пользователям с полным доступом (пользователям, которым назначена роль глобального администратора или администратора безопасности в Azure AD), автоматически назначена роль администратора Defender для конечной точки, которая также имеет полный доступ. Дополнительные группы пользователей Azure AD могут быть назначены роли администратора Defender для конечной точки после перехода на RBAC.  Управлять разрешениями с помощью RBAC могут только пользователи, назначенные роли администратора Defender для конечной точки. 
> - Пользователи с доступом только для чтения (читатели безопасности) будут терять доступ к порталу до тех пор, пока им не будет назначена роль. Обратите внимание, что роль в RBAC может быть назначена только группам пользователей Azure AD.
> - После перехода на RBAC вы не сможете вернуться к использованию базового управления разрешениями.

## <a name="related-topics"></a>Статьи по теме

- [Использование базовых разрешений для доступа к порталу](basic-permissions.md)
- [Управление доступом к порталу с помощью RBAC](rbac.md)
