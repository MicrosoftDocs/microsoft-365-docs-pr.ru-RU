---
title: Обработка ложных срабатывавай или ложных отрицательных результатов в AIR в Защитнике Microsoft 365
description: Было ли обнаружено что-то пропущенное или неправильное с помощью AIR в Защитнике Microsoft 365? Узнайте, как отправлять ложные срабатываия или ложные отрицательные результаты в корпорацию Майкрософт для анализа.
keywords: автоматизированный, исследование, оповещение, триггер, действие, исправление, ложное срабатываение, ложный отрицательный результат
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 09/16/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: dbef240e28258d1ac4000c05538d0ce073a9d910
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930358"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Обработка ложных срабатывавай и отрицательных результатов в автоматизированном расследовании и реагировании на них

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Не [пропустили ли автоматизированные возможности](mtp-autoir.md) исследования и реагирования в Microsoft 365 Defender или неправильно обнаружили что-то? Чтобы устранить эту проблему, необходимо предпринять несколько действий. Вы можете выполнить указанные ниже действия.

- [Сообщить о ложном срабатывии или отрицательных результатах в Корпорацию Майкрософт;](#report-a-false-positivenegative-to-microsoft-for-analysis)

- [Настройка оповещений](#adjust-an-alert-to-prevent-false-positives-from-recurring) (при необходимости); и 

- [Отмена действий по исправлению, которые были предприняты на устройствах.](#undo-a-remediation-action-that-was-taken-on-a-device) 

Используйте эту статью в качестве руководства. 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Отчет о ложном срабатывии или отрицательном срабатывии корпорации Майкрософт для анализа

|Элемент пропущен или неправильно обнаружен |Служба  |Действия  |
|---------|---------|---------|
|- Сообщение электронной почты <br/>- Вложение электронной почты <br/>- URL-адрес в сообщении электронной почты<br/>- URL-адрес в файле Office      |[Microsoft Defender для Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[Отправка подозрительной нежелательной почты, фишинга, URL-адресов и файлов в корпорацию Майкрософт для проверки](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|Файл или приложение на устройстве    |[Microsoft Defender для конечной точки](https://docs.microsoft.com/windows/security/threat-protection)         |[Отправка файла в корпорацию Майкрософт для анализа вредоносных программ](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Настройка оповещения, чтобы предотвратить повторение ложных срабатывающих

|Сценарий |Служба |Действия |
|--------|--------|--------|
|- Оповещение инициируется при законных основаниях. <br/>- Оповещение неточно    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> или <br/>[Azure Advanced Threat Detection](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[Управление оповещениями на портале Cloud App Security](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|Файл, IP-адрес, URL-адрес или домен рассматриваются как вредоносные программы на устройстве, хотя это безопасно|[Microsoft Defender для конечной точки](https://docs.microsoft.com/windows/security/threat-protection) |[Создание пользовательского индикатора с действием "Разрешить"](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>Отмена действия по исправлению, которое было принято на устройстве

Если действие по исправлению было принято на устройстве (например, на устройстве с Windows 10) и элемент фактически не является угрозой, группа операций безопасности может отменить действие по исправлению в Центре [действий.](mtp-action-center.md)

> [!IMPORTANT]
> Перед выполнением [следующей](mtp-action-center.md#required-permissions-for-action-center-tasks) задачи убедитесь, что у вас есть необходимые разрешения.

1. Перейдите на страницу [https://security.microsoft.com](https://security.microsoft.com) и войдите. 

2. В панели навигации щелкните **Центр уведомлений**. 

3. На **вкладке "История"** выберите действие, которое нужно отменить. Откроется flyout.<br/>
    > [!TIP]
    > Используйте фильтры, чтобы сузить список результатов. 

4. Во flyout для выбранного элемента выберите страницу **"Открыть исследование".**

5. В представлении сведений об исследованиях выберите вкладку **"Действия".**

6. Выберите элемент с состоянием **"Завершено"** и наберись ссылки, например "Утверждено", в столбце **"Решения".** Откроется flyout с дополнительными сведениями о действии.

7. Чтобы отменить действие, выберите **"Удалить исправление".**

## <a name="see-also"></a>См. также

- [Просмотр сведений и результатов автоматического исследования](mtp-autoir-results.md)
- [Упреждающий поиск угроз с помощью расширенных поисков в Защитнике Microsoft 365](advanced-hunting-overview.md)
