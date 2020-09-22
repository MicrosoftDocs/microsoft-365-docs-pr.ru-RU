---
title: Предварительные требования для Защиты от угроз (Майкрософт)
description: Сведения о лицензировании, требованиях к оборудованию и программному обеспечению, а также других параметрах конфигурации Защиты от угроз (Майкрософт)
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
ms.openlocfilehash: 50ca606a6bef9cec528b6b0ef78142f050e37c51
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195495"
---
# <a name="microsoft-threat-protection-prerequisites"></a>Предварительные требования для Защиты от угроз (Майкрософт)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Защита от угроз (Майкрософт)

Сведения о лицензировании и других требованиях для подготовки и использования [защиты от угроз Майкрософт](microsoft-threat-protection.md).

## <a name="licensing-requirements"></a>Требования к лицензированию
Любая из этих лицензий обеспечивает доступ к функциям защиты от угроз Майкрософт в центре безопасности Майкрософт 365, не требуя дополнительных затрат:

- Microsoft 365 в ~ или A5
- Microsoft 365 и безопасность A5
- Windows 10 Корпоративная ячейка = или A5
- Enterprise Mobility + Security (EMS), а также A5 
- Office 365 в ~ или A5
- Advanced Threat Protection в Microsoft Defender
- Расширенная защита от угроз Azure 
- Microsoft Cloud App Security
- Расширенная защита от угроз Office 365 (план 2)

> [!NOTE]
> Пробные лицензии для Office 365 в настоящее время не предоставляют доступ к защите от угроз Майкрософт.

Дополнительные сведения см. [в планах корпоративных служб Microsoft 365](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).

> У вас еще нет лицензии? [Пробное использование или приобретение подписки на Microsoft 365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>Проверка существующих лицензий
Перейдите в центр администрирования Microsoft 365 ([Admin.Microsoft.com](https://admin.microsoft.com/)), чтобы просмотреть существующие лицензии. В Центре администрирования выберите **Выставление счетов** > **Лицензии**.

>[!NOTE]
> Для просмотра сведений о лицензии необходимо назначить роль **администратора выставления счетов** или роль **глобального читателя** [в Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) . Если у вас возникли проблемы с доступом, обратитесь к глобальному администратору.

## <a name="required-permissions"></a>Обязательные разрешения
Чтобы включить защиту от угроз Майкрософт, необходимо быть **глобальным администратором** или **администратором безопасности** в Azure Active Directory. Список ролей, необходимых для использования защиты от угроз Майкрософт, и сведения о контролируемом доступе к данным, читайте в статье [Управление доступом к защите от угроз Майкрософт](mtp-permissions.md).

## <a name="browser-requirements"></a>Требования к браузеру
Доступ к защите от угроз Майкрософт в центре безопасности Microsoft 365 с помощью Microsoft EDGE, Internet Explorer 11 или любого совместимого с HTML 5 веб-браузера.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>Доступность для государственных учреждений США, а также других учреждений и других учреждений США
В настоящее время защита от угроз Майкрософт *недоступна* для:
- Облако сообщества для государственных организаций США (GCC)
- Высококачественное облако сообщества США (GCC High)
- Отдел обороны США
- Все правительственные учреждения США с коммерческими лицензиями

## <a name="related-topics"></a>См. также
- [Обзор Защиты от угроз (Майкрософт)](microsoft-threat-protection.md)
- [Включение Защиты от угроз (Майкрософт)](mtp-enable.md)
- [Управление доступом и разрешениями](mtp-permissions.md)
