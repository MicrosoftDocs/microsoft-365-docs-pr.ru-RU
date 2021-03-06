---
title: Включи Microsoft 365 Defender в центре Microsoft 365 безопасности
description: Узнайте, как включить Microsoft 365 Defender и приступить к интеграции инцидентов и ответных действий в области безопасности.
keywords: начать работу, включить Microsoft 365 Defender, Microsoft 365 Defender, M365, безопасность, расположение данных, необходимые разрешения, право на лицензию, страницу параметров
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 102666834562d0576920c746842582c2870b3738
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007613"
---
# <a name="turn-on-microsoft-365-defender"></a>Включение Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-365-defender.md) объединяет процесс реагирования на инциденты, интегрируя ключевые возможности в Microsoft Defender для конечной точки, Microsoft Defender для Office 365, Microsoft Cloud App Security и Microsoft Defender for Identity. В этом едином интерфейсе добавлены мощные функции, к которым можно получить доступ в Центре безопасности Майкрософт 365.

Microsoft 365 Defender автоматически включается, когда подходящие клиенты с нужными разрешениями посещают Microsoft 365 центр безопасности. Ознакомьтесь с этой статьей, чтобы понять различные предпосылки и Microsoft 365 Defender подготовка.

## <a name="check-license-eligibility-and-required-permissions"></a>Проверка прав на лицензию и необходимых разрешений

Лицензия на продукт Microsoft 365 безопасности обычно дает право на использование Microsoft 365 Defender в центре Microsoft 365 безопасности без дополнительных затрат на лицензирование. Мы рекомендуем получить лицензию Microsoft 365 E5, E5 Security, A5 или A5 Security или допустимое сочетание лицензий, которые предоставляют доступ ко всем поддерживаемым службам.

Подробные сведения о лицензировании [читайте в публикации "Ъ" "Требования к лицензированию".](prerequisites.md#licensing-requirements)

### <a name="check-your-role"></a>Проверка роли

Вы должны быть глобальным **администратором** или **администратором** безопасности в Azure Active Directory, чтобы включить Microsoft 365 Defender. [Просмотр ролей в Azure AD](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Поддерживаемые службы

Microsoft 365 Defender собирает данные из различных поддерживаемых служб, которые вы уже развернули. Централизованная обработка и хранение данных будут определять новые сведения и делать возможными процессы централизованного реагирования. Это делается без влияния на существующие развертывания, параметры или данные, связанные с интегрированными службами.

Чтобы получить лучшую защиту и оптимизировать Microsoft 365 Defender, рекомендуется развернуть все применимые поддерживаемые службы в вашей сети. Дополнительные сведения читайте [в публикации "Ъ" "Развертывание поддерживаемых служб".](deploy-supported-services.md)

## <a name="onboard-to-the-service"></a>На борту службы
В Microsoft 365 Defender просто. В меню навигации выберите любой элемент, **например**& оповещений,  **охоты,** центра действий или аналитики угроз, чтобы инициировать процесс взбора. 

### <a name="data-center-location"></a>Расположение центра обработки данных

Microsoft 365 Defender будет хранить и обрабатывать данные в том же расположении, что и [Microsoft Defender для конечной точки.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy) Если у вас нет Microsoft Defender для конечной точки, новое расположение центра обработки данных автоматически выбирается в зависимости от расположения активных служб Microsoft 365 безопасности. Выбранное расположение центра обработки данных отображается на экране.

Выберите **Необходимую помощь?** в центре Microsoft 365, чтобы связаться с службой поддержки Майкрософт по Microsoft 365 Defender в другом расположении центра обработки данных.

> [!NOTE]
> В прошлом Центр обработки данных Microsoft Defender для конечной точки автоматически был включен в центрах обработки данных Европейского союза (ЕС) при включенном в Azure Defender. Microsoft 365 Defender автоматическое предоставление в том же центре обработки данных ЕС для клиентов, которые в прошлом таким образом обуяли Defender для конечной точки.

### <a name="confirm-that-the-service-is-on"></a>Подтверждение включения службы

После подготовки службы в нее добавляются:

- [Управление инцидентами](incidents-overview.md)
- [Очередь оповещений](investigate-alerts.md)
- Центр уведомлений для управления службой [Автоматического анализа угроз и защиты от атак](m365d-autoir.md)
- [Расширенные возможности](advanced-hunting-overview.md) охоты
- Аналитика угроз

![Изображение области навигации Microsoft 365 центра безопасности с Microsoft 365 Defender функциями Microsoft 365 безопасности с управлением инцидентами и другими ](../../media/overview-incident.png)
 *Microsoft 365 Defender возможностями*

### <a name="getting-microsoft-defender-for-identity-data"></a>Получение данных Microsoft Defender для удостоверений 
Чтобы включить интеграцию Microsoft Cloud App Security, необходимо хотя бы один раз войти в Microsoft Cloud App Security.

## <a name="get-assistance"></a>Получение помощи

Чтобы получить ответы на наиболее часто задаваемые вопросы о включаемой Microsoft 365 Defender, ознакомьтесь [с часто задаваемой проблемой.](m365d-enable-faq.md)

Сотрудники службы поддержки Майкрософт могут помочь в предоставлении или откормке службы и связанных с ней ресурсов на клиенте. Для оказания помощи выберите **"Нужна помощь"?** в центре Microsoft 365 безопасности. При контакте с поддержкой упоминают Microsoft 365 Defender.

## <a name="related-topics"></a>Статьи по теме

- [Вопросы и ответы](m365d-enable-faq.md)
- [Требования к лицензированию и другие предварительные требования](prerequisites.md)
- [Развертывание поддерживаемых служб](deploy-supported-services.md)
- [Microsoft 365 Defender обзор](microsoft-365-defender.md)
- [Обзор Microsoft Defender для конечной точки](../defender-endpoint/microsoft-defender-endpoint.md)
- [Обзор defender для Office 365](../office-365-security/defender-for-office-365.md)
- [Обзор Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)
- [Обзор Microsoft Defender для удостоверений](/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender для хранения данных конечной точки](../defender-endpoint/data-storage-privacy.md)
