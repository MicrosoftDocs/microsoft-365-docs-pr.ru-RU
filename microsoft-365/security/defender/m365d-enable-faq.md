---
title: Часто задаваемые вопросы при Microsoft 365 Defender
description: Получите ответы на наиболее часто задаваемые вопросы о лицензировании, разрешениях, первоначальных настройках и других продуктах и услугах, связанных с Microsoft 365 Defender
keywords: часто задаваемые вопросы, часто задаваемые вопросы, GCC, начать работу, включить Microsoft 365 Defender, Microsoft 365 Defender, M365, безопасность, местоположение данных, необходимые разрешения, право на лицензию, настройки страницы
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
ms.openlocfilehash: 008e3cc6ee65597a032aa932b74a64ac591927f2
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572769"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Часто задаваемые вопросы при Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Прочитайте ответы на наиболее часто задаваемые вопросы о [Microsoft 365 Defender,](microsoft-365-defender.md)включая необходимые лицензии и разрешения, развертывание служб поддержки и первоначальные настройки.

Для получения инструкций о том, как включить службу, [читайте Включите Microsoft 365 Defender](m365d-enable.md).

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>У меня нет лицензии Microsoft 365 E5 лицензии. Могу ли я использовать Microsoft 365 Defender?

Клиенты со следующими лицензиями, не являмися E5, могут использовать Microsoft 365 Defender:

- Microsoft Defender для конечной точки
- Microsoft Defender для удостоверений
- Microsoft Cloud App Security
- Defender для Office 365 (план 2)
 
Полный список поддерживаемых лицензий будут [сшатать требования к лицензированию.](prerequisites.md#licensing-requirements)

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Нужно ли мне что-либо устанавливать или развертывать, чтобы начать использовать Microsoft 365 Defender?

Нет, Microsoft 365 Defender консолидирует данные Microsoft 365 служб безопасности, которые вы уже развернули. Как только вы включите его, опыт работы, автоматизации и охоты начнет работать в рамках развернутых продуктов. Если ни один из этих продуктов не развернут должным образом, Microsoft 365 Defender не будет отображать никаких данных и не сможет принять какие-либо меры.

Чтобы оптимизировать Microsoft 365 Defender, мы рекомендуем развертывать все *поддерживаемые* [Microsoft 365 и услуги безопасности.](deploy-supported-services.md)

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Где Microsoft 365 Defender и хранится ли мои данные?
Microsoft 365 Defender автоматически выбирает оптимальное место для центра обработки и хранения данных. Если у вас есть Microsoft Defender для конечной точки, он выбирает то же место, используемое Defender для конечной точки.

>[!NOTE]
>Microsoft Defender for Endpoint автоматически предоставляет данные в центрах обработки данных Европейского союза (ЕС) при включении через Azure Defender. Microsoft 365 Defender автоматически будет предоставление в том же центре обработки данных ЕС для клиентов, которые предусмотрели Microsoft Defender для конечной точки таким образом. 

Местоположение центра обработки данных отображается до и после предоставления услуги на странице настроек для Microsoft 365 Defender **(Параметры > Microsoft 365 Defender).** Если вы предпочитаете использовать другое местоположение центра обработки данных, **выберите Need help?** в центре Microsoft 365, чтобы связаться с службой поддержки Майкрософт.

## <a name="where-can-i-access-microsoft-365-defender"></a>Где я могу получить доступ Microsoft 365 Defender?

Microsoft 365 Защитник доступен в Microsoft 365 безопасности. Чтобы перейти к центру безопасности, просмотрите URL [https://security.microsoft.com](https://security.microsoft.com) .

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Какие разрешения мне нужны для доступа Microsoft 365 Defender в Microsoft 365 безопасности?

Учетные записи, назначенные следующим Azure Active Directory (Azure AD), могут получить доступ к Microsoft 365 Defender и данным:

- Глобальный администратор
- Администратор безопасности
- Оператор безопасности
- Глобальный читатель
- Читатель сведений о безопасности

>[!NOTE]
>Настройки управления доступом на основе роли в Microsoft Defender for Endpoint влияют на доступ к данным. Для получения дополнительной информации, [прочитайте об управлении доступом к Microsoft 365 Defender](m365d-permissions.md).

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>В каком часовом Microsoft 365 по умолчанию по умолчанию?
По умолчанию Microsoft 365 отображает информацию о времени в часовом поясе UTC. Вы можете изменить этот параметр, чтобы использовать местный часовой пояс. [Подробнее об установлении часового пояса](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Как узнать о новых функциях Microsoft 365 Defender и обновлениях пользовательского интерфейса?

Корпорация Майкрософт регулярно предоставляет информацию по различным каналам, включая:

- Центр [сообщений](../../admin/manage/message-center.md) в Microsoft 365 центре
- Blogposts в [Microsoft 365 безопасности & соответствия технологий сообщества](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Получите последние общедоступные возможности, включив функции [предварительного просмотра.](preview.md)

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Доступен Microsoft 365 Defender для американских облако сообщества для государственных организаций (GCC) или GCC High?
В настоящее время она недоступна.

## <a name="related-topics"></a>Связанные статьи

- [Microsoft 365 Обзор защитника](microsoft-365-defender.md)
- [Включите Microsoft 365 Defender](m365d-enable.md).
- [Требования к лицензированию и другие предварительные требования](prerequisites.md)
- [Развертывание поддерживаемых служб](deploy-supported-services.md)
- [Включение предварительных функций](preview.md)
