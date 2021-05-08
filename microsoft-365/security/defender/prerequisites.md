---
title: Microsoft 365 Предпосылки defender
description: Узнайте о требованиях к лицензированию, оборудованию и программному обеспечению и других параметрах конфигурации для Microsoft 365 Defender
keywords: требования, необходимые условия, оборудование, программное обеспечение, браузер, Microsoft 365 Defender, M365, лицензия, E5, A5, EMS, покупка
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
ms.openlocfilehash: 69345a0db42ec838dc0758cdb0e93a49a8ba6cfd
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259407"
---
# <a name="microsoft-365-defender-prerequisites"></a>Microsoft 365 Предпосылки defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Узнайте о лицензировании и других требованиях к подготовкам и использованию [Microsoft 365 Defender.](microsoft-365-defender.md)

## <a name="licensing-requirements"></a>Требования к лицензированию
Любая из этих лицензий предоставляет доступ к функциям Microsoft 365 Defender в центре Microsoft 365 безопасности без дополнительных затрат:

- Microsoft 365 E5 или A5
- Microsoft 365 E3 с Безопасность Microsoft 365 E5 надстройки
- Microsoft 365 A3 с надстройки Microsoft 365 A5 Security
- Windows 10 Корпоративная E5 или A5
- Enterprise Mobility + Security (EMS) E5 или A5 
- Office 365 E5 или A5
- Microsoft Defender для конечной точки
- Microsoft Defender для удостоверений 
- Microsoft Cloud App Security
- Defender для Office 365 (план 2)

Дополнительные сведения можно [получить в Microsoft 365 корпоративный планах службы.](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)

> У вас еще нет лицензии? [Пробное использование или приобретение подписки на Microsoft 365](../../commerce/try-or-buy-microsoft-365.md)

### <a name="check-your-existing--licenses"></a>Проверка существующих лицензий
Перейдите Microsoft 365 центр администрирования[(admin.microsoft.com)](https://admin.microsoft.com/)для просмотра существующих лицензий. В Центре администрирования выберите **Выставление счетов** > **Лицензии**.

>[!NOTE]
> Для получения сведений о  лицензии  вам необходимо на должность администратора биллинга или глобального читателя в [Azure AD.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) Если у вас возникли проблемы с доступом, обратитесь к глобальному администратору.

## <a name="required-permissions"></a>Обязательные разрешения
Вы должны быть глобальным **администратором** или **администратором** безопасности в Azure Active Directory, чтобы включить Microsoft 365 Defender. Список ролей, необходимых для использования Microsoft 365 Defender, а также сведения о регулировании доступа к данным, ознакомьтесь с управлением доступом к [Microsoft 365 Defender.](m365d-permissions.md)

## <a name="browser-requirements"></a>Требования к браузеру
Доступ Microsoft 365 Defender в центре Microsoft 365 с помощью Microsoft Edge, Internet Explorer 11 или любого веб-браузера, совместимых с HTML 5.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>Доступность для американских GCC, GCC и других государственных учреждений США
В настоящее время Microsoft 365 Defender *не доступен* для:
- Сша облако сообщества для государственных организаций (GCC)
- Высокая облако сообщества для государственных организаций (GCC high)
- Министерство обороны США
- Все государственные учреждения США с коммерческими лицензиями

## <a name="related-topics"></a>Статьи по теме
- [Microsoft 365 Обзор defender](microsoft-365-defender.md)
- [Включение Microsoft 365 Defender](m365d-enable.md)
- [Управление доступом и разрешениями](m365d-permissions.md)
