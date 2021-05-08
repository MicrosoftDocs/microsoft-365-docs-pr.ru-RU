---
title: Сообщение о ложных срабатывах или ложных отрицательных результатах после автоматического расследования в Microsoft Defender для Office 365
description: Было ли что-то пропущено или неправильно обнаружено air в Microsoft Defender для Office 365? Узнайте, как отправить ложные срабатыва или ложные отрицательные результаты в Корпорацию Майкрософт для анализа.
keywords: автоматическое, исследование, оповещение, триггер, действие, исправление, ложное срабатывательство, ложный отрицательный
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
ms.prod: m365-security
ms.date: 01/29/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 036ef1c97788f310c5b906ae5f80076ca2359cdb
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275088"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Как сообщать о ложных срабатывах и отрицательных результатах в возможностях автоматического расследования и ответа

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Microsoft Defender для Office 365 (план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Если возможности автоматического расследования и реагирования [(AIR)](automated-investigation-response-office.md) в Office 365 что-то пропустили или неправильно обнаружили, есть действия, которые может предпринять ваша группа операций безопасности, чтобы исправить это. Такие действия включают:

- [Сообщение о ложном срабатыве или отрицательном срабатывии в Корпорации Майкрософт;](#report-a-false-positivenegative-to-microsoft-for-analysis)
- [Настройка оповещений](#adjust-an-alert-to-prevent-false-positives-from-recurring) (при необходимости); и
- [Отмена принятых действий по исправлению.](#undo-a-remediation-action)

Используйте эту статью в качестве руководства.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Сообщение о ложном срабатыве или отрицательном сообщении в Корпорацию Майкрософт для анализа

Если AIR в Microsoft Defender для Office 365 пропустил сообщение электронной почты, вложение электронной почты, URL-адрес в сообщении электронной почты или URL-адрес в файле Office, вы можете отправить подозрительный [спам, фишинг,](admin-submission.md)URL-адреса и файлы в Корпорацию Майкрософт для Office 365 сканирования .

Вы также можете [отправить файл в Корпорацию Майкрософт для анализа вредоносных программ.](https://www.microsoft.com/wdsi/filesubmission)

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Настройка оповещений, чтобы предотвратить повторение ложных срабатыва

Если оповещение вызывается законным использованием или оповещение является неточным, вы можете управлять оповещениями на Cloud App Security [портале](/cloud-app-security/managing-alerts).

Если ваша организация использует [Microsoft Defender](/windows/security/threat-protection) для конечной точки в дополнение к Office 365, а файл, IP-адрес, URL-адрес или домен рассматриваются как вредоносные программы на устройстве, даже если это безопасно, вы можете создать настраиваемый индикатор с действием ["Разрешить"](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)для вашего устройства .

## <a name="undo-a-remediation-action"></a>Отмена действия по исправлению

В большинстве случаев, если в сообщении электронной почты, вложении электронной почты или URL-адресе было предприняно действие по исправлению, и этот элемент фактически не представляет угрозы, группа операций безопасности может отменить действие по исправлению и принять меры, чтобы предотвратить повторение ложного срабатывания. Для отмены действия можно использовать [обозреватель угроз](#undo-an-action-using-threat-explorer) или вкладку [Действия](#undo-an-action-in-the-action-center) для расследования.

> [!IMPORTANT]
> Убедитесь, что у вас есть необходимые разрешения перед выполнением следующих задач.

### <a name="undo-an-action-using-threat-explorer"></a>Отмена действия с помощью обозревателя угроз

С помощью обозревателя угроз группа операций безопасности может найти электронное сообщение, затрагиваемую действием, и, возможно, отменить действие.

|Сценарий|Отмена параметров|Подробнее|
|---|---|---|
|Сообщение электронной почты было отправлено в папку нежелательной почты пользователя|- Перемещение сообщения в папку удаленных элементов пользователя<br/>- Перемещение сообщения в почтовый ящик пользователя<br/>- Удаление сообщения|[Поиск и расследование вредоносной электронной почты, доставленной в Office 365](investigate-malicious-email-that-was-delivered.md)|
|Сообщение электронной почты или файл были на карантине|- Освобождение электронной почты или файла<br/>- Удаление электронной почты или файла|[Управление карантинными сообщениями в качестве администратора](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a>Отмена действия в центре действий

В центре действий можно увидеть действия по исправлению, которые были приняты и потенциально отменяют действие.

1. Перейдите в центр Microsoft 365 безопасности ( <https://security.microsoft.com> ).
2. В области навигации выберите **Центр действий.**
3. Выберите **вкладку История,** чтобы просмотреть список завершенных действий.
4. Выберите элемент. Откроется его поле для вылетов.
5. В области вылетов выберите **Отмена**. (Только действия, которые можно отменить, будут иметь кнопку **Undo.)**

## <a name="see-also"></a>См. также

- [Microsoft Defender для Office 365](defender-for-office-365.md)
- [Автоматизированные расследования в Microsoft Defender для Office 365](office-365-air.md)
