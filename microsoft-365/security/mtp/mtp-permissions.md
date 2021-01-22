---
title: Управление доступом к данным Защитника Microsoft 365 в Центре безопасности Microsoft 365
description: Узнайте, как управлять разрешениями на доступ к данным в Microsoft 365 Defender
keywords: доступ, разрешения, MTP, Защита от угроз (Майкрософт), Microsoft 365, безопасность, MCAS, MDATP, Cloud App Security, Advanced Threat Protection в Microsoft Defender, область, определение области, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 6f042b0c6314e8e5f80d40d76159712bc817a01c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930142"
---
# <a name="manage-access-to-microsoft-365-defender"></a>Управление доступом к Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Учетные записи с следующими ролями Azure Active Directory (AD) могут получать доступ к функциям и данным Защитника Microsoft 365:
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
Доступ к данным Защитника Microsoft 365 можно контролировать с помощью области, назначенной группам пользователей в Microsoft Defender для управления доступом на основе ролей (RBAC) конечной точки. Если область вашего доступа не была областью действия определенного набора устройств в Защитнике для конечной точки, вы будете иметь полный доступ к данным в Microsoft 365 Defender. Однако если область учетной записи задана, вам будут доступны только данные об устройствах в этой области.

Например, если вы принадлежите только к одной группе пользователей с ролью Microsoft Defender for Endpoint и этой группе пользователей предоставлен доступ только к устройствам продаж, вы увидите только данные об устройствах продаж в Microsoft 365 Defender. [Узнайте больше о параметрах RBAC в Microsoft Defender для конечной точки](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Элементы управления доступом в Microsoft Cloud App Security
Во время предварительной версии Защитник Microsoft 365 не применяет элементы управления доступом на основе параметров Cloud App Security. Эти параметры не влияют на доступ к данным Защитника Microsoft 365.

## <a name="related-topics"></a>См. также

- [Роли Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Microsoft Defender for Endpoint RBAC](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Роли Cloud App Security](https://docs.microsoft.com/cloud-app-security/manage-admins)
