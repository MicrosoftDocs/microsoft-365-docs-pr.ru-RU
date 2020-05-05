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
ms.openlocfilehash: 394fceffb96350b7702c5eef4a8138b3eb53f714
ms.sourcegitcommit: 997f6227f33c3683ade9672e881d09216df22ee9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2020
ms.locfileid: "44016078"
---
# <a name="turn-on-microsoft-threat-protection"></a>Включение Защиты от угроз (Майкрософт)

**Область применения:**
- Защита от угроз (Майкрософт)

Защита от угроз (Майкрософт) объединяет процесс реагирования на инциденты, интегрируя основные возможности Advanced Threat Protection (ATP) в Microsoft Defender, Office 365 ATP, Microsoft Cloud App Security и Azure ATP. В этом едином интерфейсе добавлены мощные функции, к которым можно получить доступ в Центре безопасности Майкрософт 365.

Чтобы получить лучшую защиту и оптимизировать защиту от угроз Майкрософт, мы рекомендуем развернуть все поддерживаемые службы в сети. Для получения дополнительных сведений [Ознакомьтесь с разворачиванием поддерживаемых служб](deploy-supported-services.md).

## <a name="check-license-eligibility-and-required-permissions"></a>Проверка допустимости лицензий и необходимых разрешений
Лицензия Microsoft 365, в том действиях безопасности, A5 или A5, а также действующая комбинация лицензий предоставляет доступ к поддерживаемым службам и предоставляет Вам возможность использовать защиту от угроз Майкрософт в центре безопасности Майкрософт 365 без дополнительной стоимости лицензирования.

Для получения подробных сведений о лицензировании [Прочтите требования к лицензированию](prerequisites.md#licensing-requirements).

### <a name="check-your-role"></a>Проверка роли
Чтобы включить защиту от угроз Майкрософт, необходимо быть **глобальным администратором** или **администратором безопасности** в Azure Active Directory. [Просмотр ролей в Azure AD](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a>Начало работы со службой

Защита от угроз Майкрософт собирает данные из различных интегрированных служб. Он будет обрабатывать и хранить данные централизованно, чтобы определять новые аналитики и создавать централизованные рабочие процессы ответа. Это происходит, не затрагивая существующие развертывания, параметры или данные, связанные со встроенными службами.

Перед включением службы центр безопасности Microsoft 365 ([Security.Microsoft.com](https://security.microsoft.com)) отображает страницу приветствия Microsoft Threat Protection, когда вы выбираете **инциденты**, **Центр уведомлений** **или поиск** в области навигации. Эти параметры навигации не отображаются, если вы не можете использовать защиту от угроз Майкрософт.

![Изображение страницы приветствия Microsoft Threat Protection, показанной в том случае, если защита от угроз](../../media/mtp-welcome.png)
Майкрософт не включена на*странице приветствия Microsoft Threat Protection в центре безопасности Microsoft 365*

Чтобы включить защиту от угроз Майкрософт, просто завершите процесс на странице приветствия. Вы также можете включить защиту от угроз Майкрософт, закрыв **Параметры** ([Security.Microsoft.com/Settings](https://security.microsoft.com/settings)) в области навигации и выбрав **защиту от угроз Майкрософт**.

>[!NOTE]
>Если вы не видите **Параметры** в области навигации или не смогли получить доступ к странице, проверьте свои разрешения и лицензии.       

### <a name="select-data-center-location"></a>Выбор расположения центра обработки данных
Если для вашей организации подготовлена служба ATP в Microsoft Defender, данные будут храниться и обрабатываться в том же расположении центра обработки данных, которое вы выбрали для [данных ATP в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy). В противном случае вам будет предложено выбрать новое расположение центра обработки данных для Защиты от угроз (Майкрософт). 
 
Необходимо предоставить согласие, прежде чем данные будут совместно использоваться службами и объединены.

### <a name="confirm-that-the-service-is-on"></a>Подтверждение включения службы
После подготовки службы в нее добавляются:

- [Управление инцидентами](incidents-overview.md)
- Центр уведомлений для управления службой [Автоматического анализа угроз и защиты от атак](mtp-autoir.md)
- [Расширенные](advanced-hunting-overview.md) возможности поисковых

![Изображение области навигации центра безопасности Microsoft 365 с помощью функций](../../media/mtp-on.png)
защиты от угроз Майкрософт*Центр безопасности Microsoft 365 с возможностью управления происшествиями и другими возможностями защиты от угроз Майкрософт*

### <a name="getting-azure-atp-data"></a>Получение данных Azure ATP
Чтобы предоставить доступ к данным Azure ATP службе Защиты от угроз (Майкрософт), убедитесь в том, что включена интеграция Microsoft Cloud App Security с Azure ATP. [Подробнее об этой интеграции](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a>Выключение Защиты от угроз (Майкрософт)
Чтобы прекратить использование службы Защиты от угроз (Майкрософт), в Центре безопасности Microsoft 365 выберите **Параметры** > **Защита от угроз (Майкрософт)** > **Согласиться или отказаться**. Снимите флажок **Включение Защиты от угроз (Майкрософт)** и сохраните изменения.

Соответствующие функции будут удалены из центра безопасности Microsoft 365.

## <a name="get-assistance"></a>Получение помощи

Сотрудники службы поддержки Майкрософт могут помочь подготовить или отменить подготовку службы и связанных ресурсов в клиенте. Для получения помощи выберите **нужна помощь?** в центре безопасности Майкрософт 365. При обращении в службу поддержки следует упомянуть о защите от угроз Майкрософт.

## <a name="related-topics"></a>См. также

- [Обзор Защиты от угроз (Майкрософт)](microsoft-threat-protection.md)
- [Требования к лицензированию и другие предварительные требования](prerequisites.md)
- [Развертывание поддерживаемых служб](deploy-supported-services.md)
- [Обзор ATP в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Обзор Office 365 ATP](../office-365-security/office-365-atp.md)
- [Обзор Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Обзор Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Хранение данных в службе ATP в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
