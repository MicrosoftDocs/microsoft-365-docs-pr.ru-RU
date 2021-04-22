---
title: Часто задающие вопросы при включив Microsoft 365 Defender
description: Получение ответов на наиболее часто задамые вопросы о лицензировании, разрешениях, начальных параметрах и других продуктах и службах, связанных с включением Microsoft 365 Defender
keywords: часто задаваемые вопросы, GCC, привнося начало, включить Microsoft 365 Defender, Microsoft 365 Defender, M365, безопасность, расположение данных, необходимые разрешения, право на лицензию, страницу параметров
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
ms.openlocfilehash: 55c1a3807fe8e28ca12f4f638c1ab2ca717523ed
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933437"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Часто задающие вопросы при включив Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Ознакомьтесь с ответами на наиболее часто задамые вопросы о включании [защитника Microsoft 365,](microsoft-365-defender.md)включая необходимые лицензии и разрешения, развертывание служб поддержки и начальные параметры.

Инструкции по включению службы читайте в публикации ["Включи Microsoft 365 Defender".](m365d-enable.md)

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>У меня нет лицензии Microsoft 365 E5. Могу ли я по-прежнему использовать Microsoft 365 Defender?

Клиенты со следующими лицензиями, не относясь к E5, могут использовать Microsoft 365 Defender:

- Microsoft Defender для конечной точки
- Microsoft Defender для удостоверений
- Microsoft Cloud App Security
- Defender for Office 365 (Plan 2)
 
Полный список поддерживаемых лицензий [ознакомьтесь с требованиями лицензирования.](prerequisites.md#licensing-requirements)

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Необходимо ли установить или развернуть что-либо, чтобы начать использовать Microsoft 365 Defender?

Нет, Microsoft 365 Defender консолидирует данные из служб безопасности Microsoft 365, которые вы уже развернули. После его включения опыты инцидентов, автоматизации и охоты начнут работать в пределах развернутых продуктов. Если ни один из этих продуктов не развернут должным образом, Microsoft 365 Defender не будет отображать данные и не сможет принять никаких действий.

Для оптимизации работы с Microsoft 365 Defender  рекомендуется развернуть все поддерживаемые продукты и службы безопасности [Microsoft 365.](deploy-supported-services.md)

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Где Microsoft 365 Defender обрабатывает и хранит мои данные?
Microsoft 365 Defender автоматически выбирает оптимальное расположение для центра обработки и хранения консолидированных данных. Если у вас есть Microsoft Defender для конечной точки, он выбирает то же расположение, что и Защитник для конечной точки.

>[!NOTE]
>Microsoft Defender для конечной точки автоматически содержит положения в центрах обработки данных Европейского союза (ЕС) при включении через Azure Defender. Microsoft 365 Defender автоматически будет предоставление в том же центре обработки данных ЕС для клиентов, которые таким образом провизировали Microsoft Defender для конечной точки. 

Расположение центра обработки данных отображается до и после предоставления службы на странице параметры для Microsoft 365 Defender **(Параметры > Microsoft 365 Defender).** Если вы предпочитаете использовать другое расположение центра обработки данных, выберите "Нужна **помощь"?** в центре безопасности Microsoft 365 обратитесь в службу поддержки Майкрософт.

## <a name="where-can-i-access-microsoft-365-defender"></a>Где можно получить доступ к Microsoft 365 Defender?

Microsoft 365 Defender доступен в центре безопасности Microsoft 365. Чтобы перейти в центр безопасности, просмотрите [https://security.microsoft.com](https://security.microsoft.com) URL-адрес.

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Какие разрешения необходимо получить доступ к Microsoft 365 Defender в центре безопасности Microsoft 365?

Учетные записи, на которые назначены следующие роли Azure Active Directory (AD), могут получать доступ к функциям и данным Microsoft 365 Defender:

- Глобальный администратор
- Администратор безопасности
- Оператор безопасности
- Глобальный читатель
- Читатель сведений о безопасности

>[!NOTE]
>Параметры управления доступом на основе ролей в Microsoft Defender для конечной точки влияют на доступ к данным. Дополнительные сведения об управлении доступом к [Microsoft 365 Defender](m365d-permissions.md).

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>В каком часовом поясе по умолчанию работает Microsoft 365 Defender?
По умолчанию Microsoft 365 Defender отображает сведения о времени в часовом поясе UTC. Этот параметр можно изменить, чтобы использовать локальный часовой пояс. [Узнайте о настройке часовой зоны](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Как узнать о новых обновлениях функции Защитника Microsoft 365 и пользовательского интерфейса?

Корпорация Майкрософт регулярно предоставляет информацию по различным каналам, в том числе:

- Центр [сообщений в](../../admin/manage/message-center.md) центре администрирования Microsoft 365
- Blogposts в [сообществе безопасности Microsoft 365 & соответствия требованиям](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Получите последние общедоступные возможности, включив функции [предварительного просмотра.](preview.md)

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Доступен ли Microsoft 365 Defender для облачных правительственных сообществ США (GCC) или GCC High?
В настоящее время она недоступна.

## <a name="related-topics"></a>Похожие темы

- [Обзор Защитника Microsoft 365](microsoft-365-defender.md)
- [Включи Microsoft 365 Defender.](m365d-enable.md)
- [Требования к лицензированию и другие предварительные требования](prerequisites.md)
- [Развертывание поддерживаемых служб](deploy-supported-services.md)
- [Включение предварительных функций](preview.md)
