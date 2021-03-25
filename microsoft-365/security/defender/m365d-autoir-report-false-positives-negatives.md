---
title: Обработка ложных срабатыва-срабатывай в AIR в Microsoft 365 Defender
description: Было ли что-то пропущено или неправильно обнаружено air в Microsoft 365 Defender? Узнайте, как отправить ложные срабатыва или ложные отрицательные результаты в Корпорацию Майкрософт для анализа.
keywords: автоматическое, исследование, оповещение, исправление, ложное срабатывательство, ложный отрицательный
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 01/29/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 851fd05f0fec4b8d113e515783092eed0114db0f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199117"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Обработка ложных срабатыва-

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**
- Microsoft 365 Defender

Ложные срабатывательство или отрицательные срабатывательство иногда может возникать с любым решением защиты от угроз. Если [автоматизированные возможности](m365d-autoir.md) расследования и реагирования в Microsoft 365 Defender пропустили или неправильно обнаружили что-то, ваша группа операций безопасности может предпринять следующие действия:

- [Сообщение о ложном срабатыве или отрицательном отзыве в Корпорацию Майкрософт;](#report-a-false-positivenegative-to-microsoft-for-analysis)
- [Настройка оповещений](#adjust-an-alert-to-prevent-false-positives-from-recurring) (при необходимости); и 
- [Отмена действий по исправлению, принятых на устройствах.](#undo-a-remediation-action-that-was-taken-on-a-device) 

В следующих разделах описано, как выполнять эти задачи.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Сообщение о ложном срабатыве или отрицательном сообщении в Корпорацию Майкрософт для анализа

|Элемент, пропущенный или неправильно обнаруженный |Служба  |Действия  |
|---------|---------|---------|
|- Сообщение электронной почты <br/>- Вложение электронной почты <br/>- URL-адрес в сообщении электронной почты<br/>- URL-адрес в файле Office      |[Microsoft Defender для Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)        |[Отправка подозрительных спама, фишинга, URL-адресов и файлов в Корпорацию Майкрософт для сканирования](../office-365-security/admin-submission.md)         |
|Файл или приложение на устройстве    |[Microsoft Defender для конечной точки](/windows/security/threat-protection)         |[Отправка файла в Корпорацию Майкрософт для анализа вредоносных программ](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Настройка оповещений, чтобы предотвратить повторение ложных срабатыва

|Сценарий |Служба |Действия |
|--------|--------|--------|
|- Оповещение вызывается законным использованием <br/>- Оповещение является неточным    |[Microsoft Cloud App Security](/cloud-app-security)<br/> или <br/>[Обнаружение расширенных угроз Azure](/azure/security/fundamentals/threat-detection)         |[Управление оповещениями на портале безопасности облачных приложений](/cloud-app-security/managing-alerts)         |
|Файл, IP-адрес, URL-адрес или домен рассматриваются как вредоносные программы на устройстве, даже если это безопасно|[Microsoft Defender для конечной точки](/windows/security/threat-protection) |[Создание настраиваемой индикаторной области с помощью действия "Разрешить"](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>Отмена действия по исправлению, которое было принято на устройстве

Если для объекта (например, устройства или сообщения электронной почты) было принято действие по исправлению, и затрагиваемая сущность на самом [](m365d-action-center.md)деле не представляет угрозы, ваша группа операций безопасности может отменить действие по исправлению в центре действий.

1. Перейдите на страницу [https://security.microsoft.com](https://security.microsoft.com) и войдите. 
2. В панели навигации щелкните **Центр уведомлений**. 
3. На **вкладке История** выберите действие, которое необходимо отменить. Откроется его поле для вылетов.
4. В области вылетов выберите **Отмена**.

> [!TIP]
> См. [действия отмены завершенных действий.](m365d-autoir-actions.md#undo-completed-actions)

## <a name="see-also"></a>См. также

- [Просмотр сведений и результатов автоматического исследования](m365d-autoir-results.md)
- [Активная охота на угрозы с расширенным поиском в Microsoft 365 Defender](advanced-hunting-overview.md)
- [Устранение ложных срабатыва-минусов в Microsoft Defender для конечной точки](/windows/security/threat-protection/microsoft-defender-atp/defender-endpoint-false-positives-negatives)