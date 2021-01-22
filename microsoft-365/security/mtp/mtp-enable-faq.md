---
title: Вопросы и ответы при включаемом Защитнике Microsoft 365
description: Получите ответы на наиболее часто задамые вопросы о лицензировании, разрешениях, начальных параметрах и других продуктах и службах, связанных с включением Microsoft 365 Defender
keywords: вопросы и ответы, GCC, начало работы, включить MTP, Защиту от угроз (Майкрософт), M365, безопасность, расположение данных, необходимые разрешения, право на лицензию, страница параметров
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 2cb9aed070959644e3660188835386118d5f4d9b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930190"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Вопросы и ответы при включаемом Защитнике Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Ознакомьтесь с ответами на наиболее часто задамые вопросы о включаемом [Microsoft 365 Defender,](microsoft-threat-protection.md)включая необходимые лицензии и разрешения, развертывание служб поддержки и начальные параметры.

Инструкции по включению службы: ["Включить Microsoft 365 Defender".](mtp-enable.md)

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>У меня нет лицензии Microsoft 365 E5. Можно ли по-прежнему использовать Microsoft 365 Defender?

Клиенты со следующими лицензиями, не относямися к E5, могут использовать Microsoft 365 Defender:

- Microsoft Defender для конечной точки
- Microsoft Defender для удостоверений
- Microsoft Cloud App Security
- Защитник для Office 365 (план 2)
 
Полный список поддерживаемых лицензий: [ознакомьтесь с требованиями лицензирования.](prerequisites.md#licensing-requirements)

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Нужно ли устанавливать или развертывать что-либо, чтобы начать использовать Microsoft 365 Defender?

Нет, Microsoft 365 Defender консолидирует данные из служб безопасности Microsoft 365, которые вы уже развернули. После его включив, инциденты, автоматизация и охота начнут работать в области развернутых продуктов. Если ни один из этих продуктов не развернут должным образом, Microsoft 365 Defender не будет отображать какие-либо данные и не сможет принять никаких действий.

Чтобы оптимизировать работу Защитника Microsoft 365, рекомендуем развернуть все поддерживаемые продукты и службы безопасности [Microsoft 365.](deploy-supported-services.md) 

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Где Microsoft 365 Defender обрабатывает и сохраняет мои данные?
Защитник Microsoft 365 автоматически выбирает оптимальное расположение для центра обработки и хранения консолидированных данных. Если у вас есть Microsoft Defender для конечной точки, он выбирает то же расположение, что и Защитник для конечной точки.

>[!NOTE]
>Microsoft Defender для конечной точки автоматически подготовка в центрах обработки данных Европейского Союза (ЕС) при включаемом в Защитнике Azure. Защитник Microsoft 365 автоматически будет автоматически подготовка в том же центре обработки данных ЕС для клиентов, которые таким образом назначили Microsoft Defender для конечной точки. 

Расположение центра обработки данных отображается до и после предоставления службы на странице параметров Защитника Microsoft 365 (параметры >**Microsoft 365 Defender).** If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.

## <a name="where-can-i-access-microsoft-365-defender"></a>Где можно получить доступ к Microsoft 365 Defender?

Microsoft 365 Defender доступен в Центре безопасности Microsoft 365. Чтобы перейти в центр безопасности, перейдите по [https://security.microsoft.com](https://security.microsoft.com) URL-адресу.

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Какие разрешения необходимы для доступа к Microsoft 365 Defender в Центре безопасности Microsoft 365?

Учетные записи с следующими ролями Azure Active Directory (AD) могут получать доступ к функциям и данным Защитника Microsoft 365:

- Глобальный администратор
- Администратор безопасности
- Оператор безопасности
- Глобальный читатель
- Читатель сведений о безопасности

>[!NOTE]
>Параметры управления доступом на основе ролей в Microsoft Defender для конечной точки влияют на доступ к данным. Дополнительные сведения об управлении [доступом к Microsoft 365 Defender.](mtp-permissions.md)

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>Какой часовой пояс по умолчанию имеет Защитник Microsoft 365?
По умолчанию Защитник Microsoft 365 отображает сведения о времени в часовом поясе UTC. Вы можете изменить этот параметр, чтобы использовать локальный часовой пояс. [Узнайте, как установить часовой пояс](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Как узнать о новых функциях Защитника Microsoft 365 и обновлениях пользовательского интерфейса?

Корпорация Майкрософт регулярно предоставляет информацию по различным каналам, в том числе:

- Центр [сообщений в](../../admin/manage/message-center.md) Центре администрирования Microsoft 365
- Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Получите последние общедоступные возможности, включив [функции предварительного просмотра.](preview.md)

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Доступен ли Защитник Microsoft 365 для облака сообщества для государственных организаций США (GCC) или GCC High?
В настоящее время она недоступна.

## <a name="related-topics"></a>Статьи по теме

- [Обзор Защитника Microsoft 365](microsoft-threat-protection.md)
- [Включив Microsoft 365 Defender.](mtp-enable.md)
- [Требования к лицензированию и другие предварительные требования](prerequisites.md)
- [Развертывание поддерживаемых служб](deploy-supported-services.md)
- [Включение предварительных функций](preview.md)
