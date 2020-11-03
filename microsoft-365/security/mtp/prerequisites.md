---
title: Предварительные требования для защитника Microsoft 365
description: Сведения о лицензировании, требованиях к оборудованию и программному обеспечению, а также другие параметры конфигурации для защитника Microsoft 365
keywords: требования, предварительные требования, оборудование, программное обеспечение, браузер, MTP, M365, лицензия,, A5, A5, EMS, покупка
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 415cdb79a6aa9371ee2f07de579cfb2f873f1acb
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844780"
---
# <a name="microsoft-365-defender-prerequisites"></a>Предварительные требования для защитника Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Защитник Microsoft 365

Сведения о лицензировании и других требованиях для подготовки и использования [защитника Microsoft 365](microsoft-threat-protection.md).

## <a name="licensing-requirements"></a>Требования к лицензированию
Любая из этих лицензий предоставляет доступ к функциям защитника Microsoft 365 в центре безопасности Майкрософт 365 без дополнительных затрат:

- Microsoft 365 в ~ или A5
- Microsoft 365 и безопасность A5
- Windows 10 Корпоративная ячейка = или A5
- Enterprise Mobility + Security (EMS), а также A5 
- Office 365 в ~ или A5
- Microsoft Defender для конечной точки
- Microsoft Defender для удостоверений 
- Microsoft Cloud App Security
- Защитник для Office 365 (план 2)

> [!NOTE]
> Пробные лицензии для Office 365 в настоящее время не предоставляют доступ к защитнику Microsoft 365.

Дополнительные сведения см. [в планах корпоративных служб Microsoft 365](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).

> У вас еще нет лицензии? [Пробное использование или приобретение подписки на Microsoft 365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>Проверка существующих лицензий
Перейдите в центр администрирования Microsoft 365 ([Admin.Microsoft.com](https://admin.microsoft.com/)), чтобы просмотреть существующие лицензии. В Центре администрирования выберите **Выставление счетов** > **Лицензии**.

>[!NOTE]
> Для просмотра сведений о лицензии необходимо назначить роль **администратора выставления счетов** или роль **глобального читателя** [в Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) . Если у вас возникли проблемы с доступом, обратитесь к глобальному администратору.

## <a name="required-permissions"></a>Обязательные разрешения
Чтобы включить защитник Microsoft 365, необходимо быть **глобальным администратором** или **администратором безопасности** в Azure Active Directory. Список ролей, необходимых для использования защитника Microsoft 365, и сведения о контролируемом доступе к данным, читайте в статье [Управление доступом к защитнику microsoft 365](mtp-permissions.md).

## <a name="browser-requirements"></a>Требования к браузеру
Доступ к защитнику Microsoft 365 в центре безопасности Майкрософт 365 с помощью Microsoft EDGE, Internet Explorer 11 или любого совместимого с HTML 5 веб-браузера.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>Доступность для государственных учреждений США, а также других учреждений и других учреждений США
В настоящее время защитник Microsoft 365 *недоступен* для следующих компонентов:
- Облако сообщества для государственных организаций США (GCC)
- Высококачественное облако сообщества США (GCC High)
- Отдел обороны США
- Все правительственные учреждения США с коммерческими лицензиями

## <a name="related-topics"></a>Статьи по теме
- [Обзор защитника Microsoft 365](microsoft-threat-protection.md)
- [Включение защитника Microsoft 365](mtp-enable.md)
- [Управление доступом и разрешениями](mtp-permissions.md)
