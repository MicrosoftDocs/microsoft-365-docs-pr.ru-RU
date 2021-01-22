---
title: Необходимые условия для Microsoft 365 Defender
description: Узнайте о лицензировании, требованиях к оборудованию и программному обеспечению, а также о других параметрах конфигурации Для Microsoft 365 Defender
keywords: требования, необходимые условия, оборудование, программное обеспечение, браузер, MTP, M365, лицензия, E5, A5, EMS, покупка
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ee1777debdb91a6ac73737db2db48e434ed3e2e2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930094"
---
# <a name="microsoft-365-defender-prerequisites"></a>Необходимые условия для Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Узнайте о лицензировании и других требованиях для предоставления и использования [Microsoft 365 Defender.](microsoft-threat-protection.md)

## <a name="licensing-requirements"></a>Требования к лицензированию
Любая из этих лицензий предоставляет доступ к функциям Защитника Microsoft 365 в Центре безопасности Microsoft 365 без дополнительных затрат:

- Microsoft 365 E5 или A5
- Безопасность Microsoft 365 E5 или A5
- Windows 10 Корпоративная E5 или A5
- Enterprise Mobility + Security (EMS) E5 или A5 
- Office 365 E5 или A5
- Microsoft Defender для конечной точки
- Microsoft Defender для удостоверений 
- Microsoft Cloud App Security
- Защитник для Office 365 (план 2)

> [!NOTE]
> Пробные лицензии для Office 365 в настоящее время не предоставляют доступ к Microsoft 365 Defender.

Дополнительные сведения можно [получить в планах обслуживания Microsoft 365 корпоративный.](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)

> У вас еще нет лицензии? [Пробное использование или приобретение подписки на Microsoft 365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>Проверка существующих лицензий
Чтобы просмотреть существующие лицензии, перейдите в Центр администрирования Microsoft 365[(admin.microsoft.com).](https://admin.microsoft.com/) В Центре администрирования выберите **Выставление счетов** > **Лицензии**.

>[!NOTE]
> Для получения сведений о  лицензии  вам должна быть назначена роль администратора вы выставления счета или роль глобального читателя в [Azure AD.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) Если у вас возникли проблемы с доступом, обратитесь к глобальному администратору.

## <a name="required-permissions"></a>Обязательные разрешения
Чтобы включить Microsoft 365 **Defender,** необходимо быть глобальным администратором или администратором безопасности в Azure Active Directory.  Список ролей, необходимых для использования Защитника Microsoft 365, и сведения об управлении доступом к данным, прочитайте об управлении доступом к [Microsoft 365 Defender.](mtp-permissions.md)

## <a name="browser-requirements"></a>Требования к браузеру
Доступ к Защитнику Microsoft 365 в Центре безопасности Microsoft 365 с помощью Microsoft Edge, Internet Explorer 11 или любого веб-браузера, совместимого с HTML 5.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>Доступность для us GCC, GCC High и других правительственных учреждений США
В настоящее время Защитник Microsoft 365 *не доступен для:*
- Облако сообщества государственных организаций США (GCC)
- Облако сообщества государственных организаций США High (GCC High)
- Министерства обороны США
- Все государственные учреждения США с коммерческими лицензиями

## <a name="related-topics"></a>Статьи по теме
- [Обзор Защитника Microsoft 365](microsoft-threat-protection.md)
- [Включить Microsoft 365 Defender](mtp-enable.md)
- [Управление доступом и разрешениями](mtp-permissions.md)
