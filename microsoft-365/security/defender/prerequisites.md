---
title: Предпосылки Microsoft 365 Defender
description: Узнайте о требованиях к лицензированию, оборудованию и программному обеспечению и других параметрах конфигурации для Microsoft 365 Defender
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: f9904ecb5b9ab0a0f634903a5dc0ee3049d06b38
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074782"
---
# <a name="microsoft-365-defender-prerequisites"></a>Предпосылки Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Узнайте о лицензировании и других требованиях к подготовкам и использованию [Microsoft 365 Defender.](microsoft-365-defender.md)

## <a name="licensing-requirements"></a>Требования к лицензированию
Любая из этих лицензий предоставляет доступ к функциям Microsoft 365 Defender в центре безопасности Microsoft 365 без дополнительных затрат:

- Microsoft 365 E5 или A5
- Microsoft 365 E5 Security или A5 Security
- Windows 10 Enterprise E5 или A5
- Корпоративная мобильность + безопасность (EMS) E5 или A5 
- Office 365 E5 или A5
- Microsoft Defender для конечной точки
- Microsoft Defender для удостоверений 
- Microsoft Cloud App Security
- Defender for Office 365 (Plan 2)

Дополнительные сведения можно [получить в планах корпоративных служб Microsoft 365.](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)

> У вас еще нет лицензии? [Пробное использование или приобретение подписки на Microsoft 365](../../commerce/try-or-buy-microsoft-365.md?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>Проверка существующих лицензий
Перейдите в центр администрирования Microsoft 365[(admin.microsoft.com),](https://admin.microsoft.com/)чтобы просмотреть существующие лицензии. В Центре администрирования выберите **Выставление счетов** > **Лицензии**.

>[!NOTE]
> Для получения сведений о  лицензии  вам необходимо на должность администратора биллинга или глобального читателя в [Azure AD.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) Если у вас возникли проблемы с доступом, обратитесь к глобальному администратору.

## <a name="required-permissions"></a>Необходимые разрешения
Вы должны быть глобальным **администратором** или **администратором** безопасности в Azure Active Directory, чтобы включить Microsoft 365 Defender. Список ролей, необходимых для использования защитника Microsoft 365, а также сведения о регулировании доступа к данным, читайте в материале Об управлении доступом к [Microsoft 365 Defender.](m365d-permissions.md)

## <a name="browser-requirements"></a>Требования к браузеру
Доступ к Microsoft 365 Defender в центре безопасности Microsoft 365 с помощью Microsoft Edge, Internet Explorer 11 или любого веб-браузера, совместимых с HTML 5.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>Доступность для GCC, GCC High и других государственных учреждений США
В настоящее время Защитник Microsoft 365 *не доступен* для:
- Облако сообщества правительства США (GCC)
- Облачное облако государственного сообщества США (GCC High)
- Министерство обороны США
- Все государственные учреждения США с коммерческими лицензиями

## <a name="related-topics"></a>Статьи по теме
- [Обзор Защитника Microsoft 365](microsoft-365-defender.md)
- [Включив защитник Microsoft 365](m365d-enable.md)
- [Управление доступом и разрешениями](m365d-permissions.md)
