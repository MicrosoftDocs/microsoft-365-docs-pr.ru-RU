---
title: Управление доступом к данным Защиты от угроз (Майкрософт) в Центре безопасности Microsoft 365
description: Сведения об управлении разрешениями для данных Защиты от угроз (Майкрософт)
keywords: доступ, разрешения, MTP, Защита от угроз (Майкрософт), Microsoft 365, безопасность, MCAS, MDATP, Cloud App Security, Advanced Threat Protection в Microsoft Defender, область, определение области, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
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
ms.openlocfilehash: ca9d6320d7ba13b2af4200e5f270c9480d8336fd
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808574"
---
# <a name="manage-access-to-microsoft-threat-protection"></a>Управление доступом к службе Защиты от угроз (Майкрософт)

**Область применения:**
- Защита от угроз (Майкрософт)

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Доступ к данным и функциям Защиты от угроз (Майкрософт) имеют учетные записи, которым назначены следующие роли Azure Active Directory (AD):
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
Управлять доступом к данным Защиты от угроз (Майкрософт) можно с помощью области, назначаемой группам пользователей в средстве управления доступом на основе ролей (RBAC) ATP в Microsoft Defender. Если область доступа не была задана как определенный набор устройств в службе ATP в Microsoft Defender, вы получите полный доступ к данным Защиты от угроз (Майкрософт). Однако если область учетной записи задана, вам будут доступны только данные об устройствах в этой области.

Например, если вы принадлежите только к одной группе пользователей с ролью ATP в Microsoft Defender и эта группа пользователей имеет доступ только к торговым устройствам, вы увидите только данные о торговых устройствах в службе Защиты от угроз (Майкрософт). [Подробнее о параметрах RBAC в службе ATP в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Элементы управления доступом в Microsoft Cloud App Security
В режиме предварительного просмотра Защита от угроз (Майкрософт) не применяет элементы управления доступом на основе параметров Cloud App Security. Эти параметры не влияют на доступ к данным Защиты от угроз (Майкрософт).

## <a name="related-topics"></a>См. также

- [Роли Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [RBAC ATP в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Роли Cloud App Security](https://docs.microsoft.com/cloud-app-security/manage-admins)