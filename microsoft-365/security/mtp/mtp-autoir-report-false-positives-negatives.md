---
title: Как сообщить о ложном срабатывании или ложных негативах в AIR в Microsoft Threat protection
description: Было ли что-то пошло не так, как было обнаружено ВОЗДУХом в защите от угроз Майкрософт? Сведения о том, как передавать ложные срабатывания или ложные отрицательные результаты в корпорацию Майкрософт для анализа.
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
ms.date: 01/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 44c90c6c9394b1f9fee34b8eb068bb7c232c4d78
ms.sourcegitcommit: a6686a68b068adec29b72f998ac9bc95992981df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2020
ms.locfileid: "41627975"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Составление отчетов о ложных положительных и отрицательных значениях при автоматическом расследовании и возможностях реагирования

**Область применения:**
- Защита от угроз (Майкрософт)

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Выполнялось ли [автоматизированное исследование и возможности реагирования](mtp-autoir.md) в целях защиты от угроз Майкрософт или неправильно обнаруживают что-либо? Чтобы устранить эту проблему, выполните указанные ниже действия. Вы можете выполнить указанные ниже действия.
- [Сообщить о ложных положительных и отрицательных значениях корпорации Майкрософт](#report-a-false-positivenegative-to-microsoft-for-analysis);
- [Настройте оповещения](#adjust-an-alert-to-prevent-false-positives-from-recurring) (при необходимости); с 
- [Отмена действий по исправлению, сделанных на устройствах](#undo-a-remediation-action-that-was-taken-on-a-device). 

Используйте эту статью в качестве руководства. 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Сообщить о ложном положительном/отрицательном виде в корпорацию Майкрософт для анализа

|Элемент пропущен или неправильно обнаружен |Служба  |Действия  |
|---------|---------|---------|
|— Сообщение электронной почты <br/>— Вложение электронной почты <br/>-URL в сообщении электронной почты<br/>-URL в файле Office      |[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[Отправляются сообщения об обнаружении нежелательной почты, фишинга, URL-адреса и файлов в Майкрософт для сканирования Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|Файл или приложение на устройстве    |[Advanced Threat Protection в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection)         |[Передача файла в корпорацию Майкрософт для анализа вредоносных программ](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Настройка оповещения для предотвращения повторения ложных срабатываний

|Сценарий |Служба |Действия |
|--------|--------|--------|
|— Оповещение инициировано законным использованием <br/>— Неточное оповещение    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> или <br/>[Расширенная угроза обнаружения угроз Azure](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[Управление оповещениями на портале Cloud App Security](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|Файл, IP-адрес, URL-адрес или домен считается вредоносным по на устройстве, даже если он является безопасным|[Advanced Threat Protection в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection) |[Создание настраиваемого индикатора с действием "разрешить"](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>Отмена действия по исправлению, сделанного на устройстве

Если действие по исправлению было выполнено на устройстве (например, на устройстве с Windows 10), и элемент, который действительно очищается, Группа "операции по обеспечению безопасности" может отменить действие "Устранение неполадок" в [центре уведомлений](mtp-action-center.md).

> [!IMPORTANT]
> Перед попыткой выполнения следующей задачи убедитесь, что у вас есть [необходимые разрешения](mtp-action-center.md#required-permissions-for-action-center-tasks) .

1. Перейдите на страницу [https://security.microsoft.com](https://security.microsoft.com) и войдите. 

2. В панели навигации щелкните **Центр уведомлений**. 

3. На вкладке **Журнал** выберите действие, которое необходимо отменить. Откроется всплывающее окно.<br/>
    > [!TIP]
    > Используйте фильтры для сужения списка результатов. 

4. В всплывающем меню для выбранного элемента выберите **открыть страницу расследования**.

5. В представлении сведения об расследовании перейдите на вкладку **действия** .

6. Выберите элемент с состоянием " **завершено**" и найдите ссылку, например " **утверждено**", в столбце " **решения** ". Откроется всплывающее окно с дополнительными сведениями о действии.

7. Чтобы отменить действие, выберите **Удалить исправление**.

## <a name="related-articles"></a>Статьи по теме

- [Утверждение или отклонение действий, относящихся к автоматизированному анализу угроз и реакции на угрозы](mtp-autoir-actions.md)
- [Дополнительные сведения о центре уведомлений](mtp-action-center.md)
- [Защита от угроз (Майкрософт) позволяет осуществлять их расширенное выслеживание на профилактической основе](advanced-hunting-overview.md)
