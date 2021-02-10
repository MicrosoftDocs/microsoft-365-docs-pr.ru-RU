---
title: Как сообщить о ложных срабатывах или ложных отрицательных результатах после автоматического исследования в Microsoft Defender для Office 365
description: Было ли обнаружено что-то пропущенное или неправильное с помощью AIR в Microsoft Defender для Office 365? Узнайте, как отправлять ложные срабатываия или ложные отрицательные результаты в корпорацию Майкрософт для анализа.
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
ms.date: 01/29/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 451a6b19139502a3765795694860e884a7a469bf
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175755"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Как сообщать о ложных срабатываах и отрицательных результатах в автоматизированном расследовании и реагировании на них

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Microsoft Defender для Office 365 (план 2)](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Если функции автоматического исследования и [реагирования (AIR) в Office 365](automated-investigation-response-office.md) пропущены или неправильно обнаружены какие-либо действия, ваша группа по работе с безопасностью может предпринять необходимые действия, чтобы устранить эту проблему. К таким действиям относятся:

- [Сообщение о ложном срабатывии или отрицательных результатах в Корпорацию Майкрософт;](#report-a-false-positivenegative-to-microsoft-for-analysis)
- [Настройка оповещений](#adjust-an-alert-to-prevent-false-positives-from-recurring) (при необходимости); и
- [Отмена принятых действий по исправлению.](#undo-a-remediation-action)

Используйте эту статью в качестве руководства.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Отчет о ложном срабатывии или отрицательном срабатывии корпорации Майкрософт для анализа

Если AIR в Microsoft Defender для Office 365 пропустил сообщение электронной почты, вложение электронной почты, URL-адрес в сообщении электронной почты или URL-адрес в файле Office, вы можете отправить подозрительные спам, фишинг, URL-адреса и файлы в корпорацию Майкрософт для сканирования [Office 365.](admin-submission.md)

Вы также можете [отправить файл в корпорацию Майкрософт для анализа вредоносных программ.](https://www.microsoft.com/wdsi/filesubmission)

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Настройка оповещения, чтобы предотвратить повторение ложных срабатывающих

Если оповещение инициируется законным использованием или оповещение неточно, вы можете управлять оповещениями на портале [Cloud App Security.](https://docs.microsoft.com/cloud-app-security/managing-alerts)

Если ваша организация использует [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection) для конечной точки в дополнение к Office 365, а файл, IP-адрес, URL-адрес или домен рассматриваются как вредоносная программа на устройстве, хотя это безопасно, вы можете создать настраиваемый индикатор с действием ["Разрешить"](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)для вашего устройства.

## <a name="undo-a-remediation-action"></a>Отмена действия по исправлению

В большинстве случаев, если для сообщения электронной почты, вложения электронной почты или URL-адреса было предприняно действие по исправлению и элемент фактически не представляет угрозы, ваша группа по работе с безопасностью может отменить действие по исправлению и принять меры, чтобы предотвратить повторение ложного срабатывания. Для отмены действия можно использовать [обозреватель угроз](#undo-an-action-using-threat-explorer) или вкладку ["Действия".](#undo-an-action-in-the-action-center)

> [!IMPORTANT]
> Перед выполнением следующих задач убедитесь, что у вас есть необходимые разрешения.

### <a name="undo-an-action-using-threat-explorer"></a>Отмена действия с помощью обозревателя угроз

С помощью обозревателя угроз группа операций безопасности может найти сообщение электронной почты, на которое влияет действие, и, возможно, отменить действие.

|Сценарий|Параметры отмены|Подробнее|
|---|---|---|
|Сообщение электронной почты было отправлено в папку нежелательной почты пользователя|- Переместить сообщение в папку пользователя "Удаленные"<br/>- Переместить сообщение в почтовый ящик пользователя<br/>- Удалить сообщение|[Поиск и изучение вредоносной электронной почты, доставленной в Office 365](investigate-malicious-email-that-was-delivered.md)|
|Сообщение электронной почты или файл были отправлены на карантин|- Освободить сообщение электронной почты или файл<br/>- Удалить сообщение электронной почты или файл|[Управление сообщениями на карантине от имени администратора](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a>Отмена действия в центре действий

В центре действий можно увидеть действия по исправлению, которые были предприняты, и, возможно, отменить это действие.

1. Перейдите в Центр безопасности Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) ).
2. В области навигации выберите **"Центр действий".** 
3. Выберите **вкладку "История",** чтобы просмотреть список завершенных действий.
4. Выберите элемент. Откроется его вылетная области. 
5. Во flyout pane, select **Undo**. (Только действия, которые можно отменить, будут иметь кнопку **"Отменить".)**

## <a name="see-also"></a>См. также

- [Microsoft Defender для Office 365](office-365-atp.md)
- [Автоматизированные исследования в Microsoft Defender для Office 365](office-365-air.md)
