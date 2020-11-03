---
title: Управление доступом к данным защитника Microsoft 365 в центре безопасности Майкрософт 365
description: Сведения о том, как управлять разрешениями на доступ к данным в защитнике Microsoft 365
keywords: доступ, разрешения, MTP, Защита от угроз (Майкрософт), Microsoft 365, безопасность, MCAS, MDATP, Cloud App Security, Advanced Threat Protection в Microsoft Defender, область, определение области, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 55b7b8c5755b773a4d53c95017a0a17a85495dee
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847252"
---
# <a name="manage-access-to-microsoft-365-defender"></a>Управление доступом к защитнику Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Защитник Microsoft 365

Учетные записи, назначенные следующим ролям Azure Active Directory (AD), могут получать доступ к функциям и данным защитника Microsoft 365:
- Глобальный администратор
- Администратор безопасности
- Оператор безопасности
- Глобальный читатель
- Читатель сведений о безопасности

Чтобы просмотреть учетные записи с этими ролями, см. раздел [Разрешения в Центре безопасности Microsoft 365](https://security.microsoft.com/permissions).

## <a name="access-to-functionality"></a>Доступ к функциям
Доступ к определенным функциям зависит от [роли Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Обратитесь к глобальному администратору, если вам нужен доступ к определенным функциям, для которых вам или вашей группе пользователей требуется назначить новую роль.

### <a name="approve-pending-automated-tasks"></a>Утверждение ожидающих автоматизированных задач
[Автоматический анализ угроз и защита от атак](mtp-autoir-actions.md) может выполнять действия с сообщениями электронной почты, пересылая правила, файлы, механизмы сохраняемости и другие артефакты, обнаруженные во время анализа. Чтобы утвердить или отклонить ожидающие действия, требующие явного утверждения, вам необходимы определенные роли, назначенные в Microsoft 365. Дополнительные сведения см. в статье [Разрешения центра уведомлений](mtp-action-center.md#required-permissions-for-action-center-tasks).

## <a name="access-to-data"></a>Доступ к данным
Доступ к данным защитника Microsoft 365 можно контролировать с помощью области, назначенной группам пользователей в защитнике Майкрософт для управления доступом на основе ролей конечной точки (RBAC). Если доступ к определенному набору устройств в защитнике для конечной точки не был ограничен, у вас будет полный доступ к данным в защитнике Microsoft 365. Однако если область учетной записи задана, вам будут доступны только данные об устройствах в этой области.

Например, если вы принадлежите только одной группе пользователей с ролью Microsoft "защитник для конечной точки", и эта группа пользователей получает доступ только к торговым устройствам, вы увидите только данные о торговых устройствах в защитнике Microsoft 365. [Дополнительные сведения о параметрах RBAC в защитнике Майкрософт для конечной точки](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Элементы управления доступом в Microsoft Cloud App Security
Во время предварительной версии защитник Microsoft 365 не применяет элементы управления доступом на основе параметров безопасности облачных приложений. Доступ к данным защитника Microsoft 365 не зависит от этих параметров.

## <a name="related-topics"></a>См. также

- [Роли Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Защитник Майкрософт для конечной точки RBAC](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Роли Cloud App Security](https://docs.microsoft.com/cloud-app-security/manage-admins)
