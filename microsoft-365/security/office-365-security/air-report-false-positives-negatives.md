---
title: Составление отчетов о ложных срабатываниях и ложных отрицательных отрицательных результатов в Office 365 автоматизированное исследование и отклик
description: Было ли что-то пошло или неправильно обнаружено в Office 365 Advanced Threat protection? Сведения о том, как передавать ложные срабатывания или ложные отрицательные результаты в корпорацию Майкрософт для анализа.
keywords: автоматические, исследование, оповещение, триггер, действие, исправление, ложное срабатывание, ложные отрицательные значения
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 05/15/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 826d8561ba0c9618f21458493416b7dbd75af9e1
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656865"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Составление отчетов о ложных положительных и отрицательных значениях при автоматическом расследовании и возможностях реагирования

**Область применения:**
- Office 365 Advanced Threat Protection

Были ли [автоматизированные функции расследования и реагирования (AIR) в Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) пропустили или ошибочно обнаружить что-то? Чтобы устранить эту проблему, выполните указанные ниже действия. Вы можете выполнить указанные ниже действия.
- [Сообщить о ложных положительных и отрицательных значениях корпорации Майкрософт](#report-a-false-positivenegative-to-microsoft-for-analysis);
- [Настройте оповещения](#adjust-an-alert-to-prevent-false-positives-from-recurring) (при необходимости); с 
- [Отмена выполненных действий по исправлению](#undo-a-remediation-action). 

Используйте эту статью в качестве руководства. 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Сообщить о ложном положительном/отрицательном виде в корпорацию Майкрософт для анализа

Если в Office 365 воздух пропустил сообщение электронной почты, вложение электронной почты, URL-адрес в сообщении электронной почты или URL-адрес в файле Office, вы можете [отправлять сообщения о подозрениях, фишинг, URL-адреса и файлы в корпорацию Майкрософт для сканирования в office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).

Вы также можете [передать файл в корпорацию Майкрософт для анализа вредоносных программ](https://www.microsoft.com/wdsi/filesubmission).

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Настройка оповещения для предотвращения повторения ложных срабатываний

Если оповещение инициировано законным использованием или оповещение неточны, вы можете [управлять оповещениями на портале Cloud App Security](https://docs.microsoft.com/cloud-app-security/managing-alerts).

Если в организации используется [Advanced Threat protection (Майкрософт](https://docs.microsoft.com/windows/security/threat-protection) ) в дополнение к Office 365, а файл, IP-адрес, URL-адрес или домен считаются вредоносными программами на устройстве, даже если это безопасно, можно [создать настраиваемый индикатор с действием "разрешить" для вашего устройства](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).

## <a name="undo-a-remediation-action"></a>Отмена действия по исправлению

В большинстве случаев, если действие по исправлению было выполнено над сообщением электронной почты, вложением электронной почты или URL-адресом, а на самом деле это не угроза, Группа "операции по обеспечению безопасности" может отменить действие по исправлению и предпринять меры по предотвращению ложного срабатывания. Для отмены действия можно использовать [Обозреватель угроз](#undo-an-action-using-threat-explorer) или [вкладку действия для исследования](#undo-an-action-using-the-actions-tab-for-an-investigation) . 

> [!IMPORTANT]
> Перед попыткой выполнения следующих задач убедитесь, что у вас есть необходимые разрешения.

### <a name="undo-an-action-using-threat-explorer"></a>Отмена действия с помощью обозревателя угроз

В обозревателе угроз группа "операции безопасности" может найти сообщение электронной почты, затронутое действием, и, возможно, отменить действие.

****

|Сценарий|Параметры отмены|Дополнительные сведения|
|---|---|---|
|Сообщение электронной почты было перенаправлено в папку нежелательной почты пользователя|— Переместить сообщение в папку "Удаленные" пользователя.<br/>— Переместить сообщение в папку "Входящие" пользователя <br/>— Удалить сообщение.|[Поиск и исследование вредоносных сообщений электронной почты, которые были доставлены в Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered)|
|Сообщение электронной почты или файл помещено в карантин|— Освободите электронную почту или файл. <br/>— Удаление электронной почты или файла|[Управление сообщениями, помещенными в карантин, и файлами в качестве администратора в Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files)|
|

### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a>Отмена действия с помощью вкладки "действия" для исследования

В центре уведомлений вы можете просмотреть принятые действия по исправлению и потенциально отменить действие.

1. Перейдите на страницу [https://protection.office.com](https://protection.office.com) и войдите. Откроется Центр безопасности & соответствия требованиям.

2. Перейдите на страницу расследования по **управлению угрозами**  >  **Investigations**.

3. В списке исследований выберите значок **Открыть в новом окне** рядом с идентификатором элемента.

4. Перейдите на вкладку **действия** .

5. Выберите элемент с состоянием " **завершено**" и найдите ссылку, например " **утверждено**", в столбце " **решение** ". Откроется всплывающее окно с дополнительными сведениями о действии.

6. Чтобы отменить действие, выберите **Удалить исправление**.

## <a name="related-articles"></a>Статьи по теме

[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)

[Начало работы с автоматизированным исследованием и откликом (AIR) в Office 365](office-365-air.md)
