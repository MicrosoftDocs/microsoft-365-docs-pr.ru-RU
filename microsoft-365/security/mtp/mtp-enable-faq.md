---
title: Часто задаваемые вопросы о включении защитника Microsoft 365
description: Ответы на часто задаваемые вопросы о лицензировании, разрешениях, начальных параметрах и других продуктах и службах, связанных с включением Microsoft 365 Defender
keywords: часто задаваемые вопросы, FAQ, GCC, начало работы, включение MTP, защита от угроз Майкрософт, M365, безопасность, расположение данных, необходимые разрешения, права на лицензирование, страница параметров
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
ms.openlocfilehash: 3dae9f208f5bb08d694322eb9f7cff35986930da
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920494"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Часто задаваемые вопросы о включении защитника Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

В этой статье приведены ответы на часто задаваемые вопросы о включении [защитника Microsoft 365](microsoft-threat-protection.md), в том числе о необходимых лицензиях и разрешениях, развертывании служб поддержки и начальных параметрах.

Для получения инструкций по включению службы, [Прочтите статью включение защитника Microsoft 365](mtp-enable.md).

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>У меня нет лицензии на Microsoft 365. Можно ли по-прежнему использовать защитник Microsoft 365?

Клиенты со следующими лицензиями, не являющимися неизменяемыми лицензиями, могут использовать защитник Microsoft 365:

- Microsoft Defender для конечной точки
- Microsoft Defender для удостоверений
- Microsoft Cloud App Security
- Защитник для Office 365 (план 2)
 
Чтобы получить полный список поддерживаемых лицензий, [Ознакомьтесь с требованиями к лицензированию](prerequisites.md#licensing-requirements).

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Нужно ли устанавливать или развертывать все, чтобы начать использовать защитник Microsoft 365?

Нет, защитник Microsoft 365 объединяет данные из уже развернутых служб безопасности Microsoft 365. После включения функции, инцидентов, автоматизации и поиска по поиску начинают работать в пределах развернутых продуктов. Если ни один из этих продуктов не развертывается надлежащим образом, защитник Microsoft 365 не будет отображать данные и не сможет предпринимать никаких действий.

Чтобы оптимизировать взаимодействие с защитником Microsoft 365, рекомендуем развернуть *все* поддерживаемые [продукты и службы безопасности Microsoft 365](deploy-supported-services.md).

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Где работает защитник Microsoft 365 и хранятся данные?
Защитник Microsoft 365 автоматически выбирает оптимальное расположение для центра обработки данных, в котором хранятся и обрабатываются консолидированные данные. Если у вас есть защитник Майкрософт для конечной точки, он выбирает то же расположение, которое используется защитником для конечной точки.

>[!NOTE]
>Защитник Майкрософт для конечных точек автоматически подготавливается в центрах обработки данных Европейского союза (ЕС) при включенном защитнике Azure. Защитник Microsoft 365 автоматически подготавливается к работе с тем же центром обработки данных ЕС для клиентов, у которых в такой манере подготовлен защитник Майкрософт для конечной точки. 

Расположение центра обработки данных показано до и после подготовки службы на странице "Параметры" для защитника Microsoft 365 ( **параметры > защитника microsoft 365** ). Если вы предпочитаете использовать другое расположение центра обработки данных, выберите **нужна помощь?** в центре безопасности Майкрософт 365 для обращения в службу поддержки Майкрософт.

## <a name="where-can-i-access-microsoft-365-defender"></a>Где можно получить доступ к защитнику Microsoft 365?

Защитник Microsoft 365 доступен в центре безопасности Майкрософт 365. Чтобы перейти в центр обеспечения безопасности, перейдите по URL-адресу [https://security.microsoft.com](https://security.microsoft.com) .

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Какие разрешения необходимы для доступа к защитнику Microsoft 365 в центре безопасности Майкрософт 365?

Учетные записи, назначенные следующим ролям Azure Active Directory (AD), могут получать доступ к функциям и данным защитника Microsoft 365:

- Глобальный администратор
- Администратор безопасности
- Оператор безопасности
- Глобальный читатель
- Читатель сведений о безопасности

>[!NOTE]
>Параметры управления доступом на основе ролей в защитнике Майкрософт для конечной точки влияют на доступ к данным. Для получения дополнительных сведений об [управлении доступом к защитнику Microsoft 365](mtp-permissions.md).

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>В каком часовом поясе по умолчанию используется защитник Microsoft 365?
По умолчанию защитник Microsoft 365 отображает сведения о времени в часовом поясе в формате UTC. Вы можете изменить этот параметр, чтобы использовать местный часовой пояс. [Сведения о настройке часового пояса](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Как узнать о новых функциях защитника Microsoft 365 и обновлениях пользовательского интерфейса?

Корпорация Майкрософт регулярно предоставляет информацию по различным каналам, в том числе:

- [Центр сообщений](../../admin/manage/message-center.md) в центре администрирования Microsoft 365
- Блогпостс в [сообществе 365 Майкрософт по безопасности & обеспечения соответствия требованиям](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Получите последние общедоступные возможности, включив [функции предварительного просмотра](preview.md).

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Доступен ли защитник Microsoft 365 для облака сообщества США (GCC) или GCC High?
В настоящее время она недоступна.

## <a name="related-topics"></a>Статьи по теме

- [Обзор защитника Microsoft 365](microsoft-threat-protection.md)
- [Включите Защитник Microsoft 365](mtp-enable.md).
- [Требования к лицензированию и другие предварительные требования](prerequisites.md)
- [Развертывание поддерживаемых служб](deploy-supported-services.md)
- [Включение предварительных функций](preview.md)
