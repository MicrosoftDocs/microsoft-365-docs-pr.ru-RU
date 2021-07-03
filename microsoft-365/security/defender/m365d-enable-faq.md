---
title: Часто задающие вопросы при включаемой Microsoft 365 Defender
description: Получение ответов на наиболее часто задамые вопросы о лицензировании, разрешениях, начальных параметрах и других продуктах и службах, связанных с включением Microsoft 365 Defender
keywords: часто задаваемые вопросы, часто задаваемые вопросы, GCC, начало работы, включить Microsoft 365 Defender, Microsoft 365 Defender, M365, безопасность, расположение данных, необходимые разрешения, право на лицензию, страницу параметров
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
ms.openlocfilehash: 1ba049e9fe608ba8bd559180c5a30060b10ee9e0
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53285989"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Часто задающие вопросы при включаемой Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Ознакомьтесь с ответами на наиболее часто задамые вопросы о включании [Microsoft 365 Defender,](microsoft-365-defender.md)включая необходимые лицензии и разрешения, развертывание служб поддержки и начальные параметры.

Инструкции по включению службы читайте в [Microsoft 365 Defender.](m365d-enable.md)

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>У меня нет Microsoft 365 E5 лицензии. Можно ли использовать Microsoft 365 Defender?

Клиенты со следующими лицензиями без E5 могут использовать Microsoft 365 Defender:

- Microsoft Defender для конечной точки
- Microsoft Defender для удостоверений
- Microsoft Cloud App Security
- Defender для Office 365 (план 2)

Полный список поддерживаемых лицензий [ознакомьтесь с требованиями лицензирования.](prerequisites.md#licensing-requirements)

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Необходимо ли установить или развернуть что-либо, чтобы начать использовать Microsoft 365 Defender?

Нет, Microsoft 365 Defender консолидирует данные из Microsoft 365 служб безопасности, которые вы уже развернули. После его включения опыты инцидентов, автоматизации и охоты начнут работать в пределах развернутых продуктов. Если ни один из этих продуктов не развернут должным образом, Microsoft 365 Defender не будет отображать какие-либо данные и не сможет принять никаких действий.

Чтобы оптимизировать Microsoft 365 Defender, рекомендуем развернуть все  поддерживаемые Microsoft 365 и [службы.](deploy-supported-services.md)

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Где Microsoft 365 Defender обработку и хранение данных?

Microsoft 365 Defender автоматически выбирает оптимальное расположение для центра обработки и хранения консолидированных данных. Если у вас есть Microsoft Defender для конечной точки, он выбирает то же расположение, что и Защитник для конечной точки.

>[!NOTE]
>Microsoft Defender для конечной точки автоматически содержит положения в центрах обработки данных Европейского союза (ЕС) при включении через Azure Defender. Microsoft 365 Defender автоматически будет в том же центре обработки данных ЕС для клиентов, которые таким образом обуяли Microsoft Defender для конечной точки.

Расположение центра обработки данных отображается до и после предоставления службы на странице параметров для Microsoft 365 Defender **(Параметры > Microsoft 365 Defender).** Если вы предпочитаете использовать другое расположение центра обработки данных, выберите "Нужна **помощь"?** в центре Microsoft 365, чтобы связаться с поддержкой Майкрософт.

## <a name="where-can-i-access-microsoft-365-defender"></a>Где можно получить доступ к Microsoft 365 Defender?

Microsoft 365 Defender доступно в центре Microsoft 365 безопасности. Чтобы перейти в центр безопасности, просмотрите <https://security.microsoft.com> URL-адрес.

## <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Какие разрешения мне нужно получить доступ к Microsoft 365 Defender в Microsoft 365 центре безопасности?

Учетные записи, задав следующие роли Azure Active Directory Azure AD, могут получать доступ к Microsoft 365 Defender и данным:

- Глобальный администратор
- Администратор безопасности
- Оператор безопасности
- Глобальный читатель
- Читатель сведений о безопасности

> [!NOTE]
> Параметры управления доступом на основе ролей в Microsoft Defender для конечной точки влияют на доступ к данным. Дополнительные сведения об управлении [доступом к](m365d-permissions.md)Microsoft 365 Defender .

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>Какой часовой пояс Microsoft 365 Defender по умолчанию?

По умолчанию Microsoft 365 Defender отображает сведения о времени в часовом поясе UTC. Этот параметр можно изменить, чтобы использовать локальный часовой пояс. [Узнайте о настройке часовой зоны](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Как узнать о новых Microsoft 365 Defender и обновлениях пользовательского интерфейса?

Корпорация Майкрософт регулярно предоставляет информацию по различным каналам, в том числе:

- Центр [сообщений](../../admin/manage/message-center.md) в Центр администрирования Microsoft 365
- Blogposts в [сообществе Microsoft 365 безопасности & соответствия требованиям](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Получите последние общедоступные возможности, включив функции [предварительного просмотра.](preview.md)

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Доступно ли Microsoft 365 Defender для облако сообщества для государственных организаций (GCC) или GCC High?

В настоящее время она недоступна.

## <a name="related-topics"></a>Статьи по теме

- [Microsoft 365 Defender обзор](microsoft-365-defender.md)
- [Включи Microsoft 365 Defender.](m365d-enable.md)
- [Требования к лицензированию и другие предварительные требования](prerequisites.md)
- [Развертывание поддерживаемых служб](deploy-supported-services.md)
- [Включение предварительных функций](preview.md)
