---
title: Включение Защиты от угроз (Майкрософт) в Центре безопасности Microsoft 365
description: Узнайте, как включить Защиту от угроз (Майкрософт) и начать интеграцию инцидентов безопасности и реагирования на них.
keywords: Начало работы, включение MTP, защита от угроз Майкрософт, M365, безопасность, расположение данных, необходимые разрешения, права на лицензирование, страница параметров
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
ms.openlocfilehash: 8f966060ebc9a30166647b397b93f2b45356df74
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083736"
---
# <a name="turn-on-microsoft-threat-protection"></a>Включение Защиты от угроз (Майкрософт)

**Область применения:**
- Защита от угроз (Майкрософт)

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Защита от угроз (Майкрософт) объединяет процесс реагирования на инциденты, интегрируя основные возможности Advanced Threat Protection (ATP) в Microsoft Defender, Office 365 ATP, Microsoft Cloud App Security и Azure ATP. В этом едином интерфейсе добавлены мощные функции, к которым можно получить доступ в Центре безопасности Майкрософт 365.

## <a name="check-license-eligibility-and-required-permissions"></a>Проверка допустимости лицензий и необходимых разрешений
Клиенты, имеющие Microsoft 365 365, а также эквивалентное сочетание лицензий, могут использовать защиту от угроз Майкрософт. Дополнительные сведения см. в статье [Требования к лицензированию](prerequisites.md#licensing-requirements).

Чтобы включить защиту от угроз Майкрософт, необходимо быть **глобальным администратором** или **администратором безопасности** в [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) .

## <a name="start-using-the-service"></a>Начало работы со службой
Защита от угроз Майкрософт собирает данные из различных интегрированных служб. Он будет обрабатывать и хранить данные централизованно, чтобы определять новые аналитики и создавать централизованные рабочие процессы ответа.

Перед включением службы центр безопасности Microsoft 365 ([Security.Microsoft.com](https://security.microsoft.com)) не отображает **инциденты** и параметры **центра уведомлений** в области навигации.

![Изображение области навигации центра безопасности Microsoft 365 без функций](../../media/mtp-off.png)
защиты от угроз Майкрософт*Центр безопасности Майкрософт 365 с отключенной функцией защиты от угроз Майкрософт*

Чтобы включить защиту от угроз Майкрософт, выберите **Параметры** в области навигации. На **[странице Параметры](https://security.microsoft.com/settings)** перейдите к разделу **Защита от угроз Майкрософт** > /отказ от участия **/отказ**.

>[!NOTE]
>Если вы не видите **Параметры** в области навигации или не смогли получить доступ к странице, проверьте свои разрешения и лицензии.

### <a name="select-data-center-location"></a>Выбор расположения центра обработки данных
Если для вашей организации подготовлена служба ATP в Microsoft Defender, данные будут храниться и обрабатываться в том же расположении центра обработки данных, которое вы выбрали для [данных ATP в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy). В противном случае вам будет предложено выбрать новое расположение центра обработки данных для Защиты от угроз (Майкрософт). 

Необходимо предоставить согласие, прежде чем данные будут совместно использоваться службами и объединены.

### <a name="confirm-that-the-service-is-on"></a>Подтверждение включения службы
После подготовки службы в нее добавляются:

- [Управление инцидентами](incidents-overview.md)
- Центр уведомлений для управления службой [Автоматического анализа угроз и защиты от атак](mtp-autoir.md)
- Возможности [расширенного поиска](advanced-hunting-overview.md) на существующей странице **Поиск**

![Изображение области навигации центра безопасности Microsoft 365 с помощью функций](../../media/mtp-on.png)
защиты от угроз Майкрософт*Центр безопасности Microsoft 365 с возможностью управления происшествиями и другими возможностями защиты от угроз Майкрософт*

### <a name="getting-azure-atp-data"></a>Получение данных Azure ATP
Чтобы предоставить доступ к данным Azure ATP службе Защиты от угроз (Майкрософт), убедитесь в том, что включена интеграция Microsoft Cloud App Security с Azure ATP. [Подробнее об этой интеграции](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a>Выключение Защиты от угроз (Майкрософт)
Чтобы прекратить использование службы Защиты от угроз (Майкрософт), в Центре безопасности Microsoft 365 выберите **Параметры** > **Защита от угроз (Майкрософт)** > **Согласиться или отказаться**. Снимите флажок **Включение Защиты от угроз (Майкрософт)** и сохраните изменения.

Данные будут удалены без возможности восстановления, а соответствующие функции будут удалены из центра безопасности Microsoft 365.

## <a name="get-assistance"></a>Получение помощи

Сотрудники службы поддержки Майкрософт могут помочь подготовить или отменить подготовку службы и связанных ресурсов в клиенте. Для получения помощи выберите **нужна помощь?** в центре безопасности Майкрософт 365. При обращении в службу поддержки следует упомянуть о защите от угроз Майкрософт.

## <a name="related-topics"></a>См. также

- [Обзор Защиты от угроз (Майкрософт)](microsoft-threat-protection.md)
- [Требования к лицензированию и другие предварительные требования](prerequisites.md)
- [Обзор ATP в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Обзор Office 365 ATP](../office-365-security/office-365-atp.md)
- [Обзор Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Обзор Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Хранение данных в службе ATP в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
