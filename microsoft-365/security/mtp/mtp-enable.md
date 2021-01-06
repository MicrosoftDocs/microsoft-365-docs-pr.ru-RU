---
title: Включить Защитник Microsoft 365 в Центре безопасности Microsoft 365
description: Узнайте, как включить Microsoft 365 Defender и начать интеграцию инцидентов безопасности и реагирования на них.
keywords: начало работы, включить MTP, Защиту от угроз (Майкрософт), M365, безопасность, расположение данных, необходимые разрешения, право на лицензию, страница параметров
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
ms.openlocfilehash: b052f70c1b618adef12c4f70c2b3fe55741697d5
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760510"
---
# <a name="turn-on-microsoft-365-defender"></a>Включить Защитник Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-threat-protection.md) объединяет процесс реагирования на инциденты, интегрируя ключевые возможности в Microsoft Defender для endpoint, Microsoft Defender для Office 365, Microsoft Cloud App Security и Microsoft Defender для удостоверений. В этом едином интерфейсе добавлены мощные функции, к которым можно получить доступ в Центре безопасности Майкрософт 365.

Защитник Microsoft 365 автоматически включается, когда подходящие клиенты с требуемой разрешением могут посетить Центр безопасности Microsoft 365. Ознакомьтесь с этой статьей, чтобы ознакомиться с различными предварительными условиями и тем, как работает Защитник Microsoft 365.

## <a name="check-license-eligibility-and-required-permissions"></a>Проверка прав на получение лицензии и необходимых разрешений

Лицензия на продукт безопасности Microsoft 365 обычно дает вам право использовать Microsoft 365 Defender в Центре безопасности Microsoft 365 без дополнительных затрат на лицензирование. Рекомендуем получить лицензию на Microsoft 365 E5, E5 Security, A5 или A5 Security или допустимое сочетание лицензий, которое предоставляет доступ ко всем поддерживаемым службам.

Подробные сведения о лицензировании можно узнать [в требованиях к лицензированию.](prerequisites.md#licensing-requirements)

### <a name="check-your-role"></a>Проверка роли

Чтобы включить Microsoft 365 **Defender,** необходимо быть глобальным администратором или администратором безопасности в Azure Active Directory.  [Просмотр ролей в Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Поддерживаемые службы

Microsoft 365 Defender собирает данные из различных поддерживаемых служб, которые вы уже развернули. Централизованная обработка и хранение данных будут определять новые сведения и делать возможными централизованные процессы ответа. Это делается без влияния на существующие развертывания, параметры или данные, связанные с интегрированными службами.

Чтобы получить лучшую защиту и оптимизировать Microsoft 365 Defender, рекомендуем развернуть в вашей сети все поддерживаемые службы. Дополнительные сведения о [развертывании поддерживаемых служб.](deploy-supported-services.md)

## <a name="before-starting-the-service"></a>Перед запуском службы

Перед тем как включить службу, Центр безопасности Microsoft 365[(security.microsoft.com)](https://security.microsoft.com)отображает страницу параметров Защитника Microsoft 365, когда вы выбираете "Инциденты", "Центр действий" или "Охота" в области навигации.  Эти элементы навигации не показываются, если вы не можете использовать Microsoft 365 Defender.

![Изображение страницы параметров Защитника Microsoft 365, если Защитник Microsoft 365 не включен в параметрах Защитника Microsoft 365 в Центре безопасности ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft 365*

## <a name="starting-the-service"></a>Запуск службы

Чтобы включить Microsoft 365 Defender, просто выберите "Включить **Защитник Microsoft 365"** и применить изменение. Вы также можете получить доступ  к этому параметру, выбрав параметры [(security.microsoft.com/settings)](https://security.microsoft.com/settings)в области навигации, а затем выбрав **Microsoft 365 Defender.**

> [!NOTE]
> Если вы не видите **параметры** в области навигации или не можете получить доступ к странице, проверьте свои разрешения и лицензии.

### <a name="data-center-location"></a>Расположение центра обработки данных

Защитник Microsoft 365 будет хранить и обрабатывать данные в том же расположении, что и [Microsoft Defender для конечной точки.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy) Если у вас нет Microsoft Defender для конечной точки, новое расположение центра обработки данных автоматически выбирается в зависимости от расположения активных служб безопасности Microsoft 365. Выбранное расположение центра обработки данных отображается на экране.

Выберите **"Нужна помощь"?** В Центре безопасности Microsoft 365 обратитесь в службу поддержки Майкрософт по поводу предоставления Microsoft 365 Defender в другом расположении центра обработки данных.

> [!NOTE]
> Microsoft Defender для конечной точки автоматически подготовка в центрах обработки данных Европейского Союза (ЕС) при включаемом в Защитнике Azure. Защитник Microsoft 365 автоматически будет в том же центре обработки данных ЕС работать с клиентами, которые таким образом назначили Защитник для конечной точки.

### <a name="confirm-that-the-service-is-on"></a>Подтверждение включения службы

После подготовки службы в нее добавляются:

- [Управление инцидентами](incidents-overview.md)
- Центр уведомлений для управления службой [Автоматического анализа угроз и защиты от атак](mtp-autoir.md)
- [Расширенные возможности охоты](advanced-hunting-overview.md)

![Изображение области навигации Центра безопасности Microsoft 365 с функциями Центра безопасности Microsoft 365 с управлением инцидентами и другими возможностями ](../../media/mtp-enable/mtp-on.png)
 *Защитника Microsoft 365*

### <a name="getting-microsoft-defender-for-identity-data"></a>Получение данных удостоверений в Microsoft Defender

Чтобы поделиться данными Microsoft Defender для удостоверений с Microsoft 365 Defender, убедитесь, что интеграция Microsoft Cloud App Security и Microsoft Defender для удостоверений включена. [Узнайте больше об этой интеграции.](https://docs.microsoft.com/cloud-app-security/mdi-integration)

## <a name="get-assistance"></a>Получение помощи

Чтобы получить ответы на наиболее часто задаваемые вопросы о включаемом Защитнике Microsoft 365, ознакомьтесь [с часто задаваемой проблемой.](mtp-enable-faq.md)

Сотрудники службы поддержки Майкрософт могут помочь в предоставлении или отофровке службы и связанных ресурсов в вашем клиенте. Для помощи выберите **"Нужна помощь"** в Центре безопасности Microsoft 365. Обратитесь в службу поддержки и обратитесь в Службу поддержки Microsoft 365.

## <a name="related-topics"></a>Статьи по теме

- [Вопросы и ответы](mtp-enable-faq.md)
- [Требования к лицензированию и другие предварительные требования](prerequisites.md)
- [Развертывание поддерживаемых служб](deploy-supported-services.md)
- [Обзор Защитника Microsoft 365](microsoft-threat-protection.md)
- [Обзор Microsoft Defender для конечной точки](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Обзор Защитника для Office 365](../office-365-security/office-365-atp.md)
- [Обзор Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Обзор Microsoft Defender для удостоверений](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender для хранения данных конечной точки](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
