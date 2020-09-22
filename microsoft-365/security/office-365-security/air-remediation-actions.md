---
title: Действия по исправлению в Microsoft 365 автоматизированное исследование и ответ
keywords: ВОЗДУШный, Аутоир, ATP, автоматизированный, исследование, ответ, исправление, угрозы, усовершенствованный, угроза, защита
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Сведения о действиях по исправлению в автоматическом расследовании и возможностях реагирования в Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: c327bdf505b774532600169e9579ffa6acfac1b1
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199905"
---
# <a name="remediation-actions-in-microsoft-365"></a>Действия по исправлению в Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="remediation-actions"></a>Действия по исправлению

[Автоматизированное исследование и возможности реагирования](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) в [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) Plan 2 включают некоторые действия по исправлению. При каждом запуске или завершении автоматизированного исследования, как правило, отображается одна или несколько мер по исправлению, требующих утверждения службой обеспечения безопасности. Такие действия по исправлению могут включать в себя следующее:

- Обратимое удаление сообщений электронной почты или кластеров
- Блокирование URL-адреса (во время щелчка)
- Отключение внешней переадресации почты
- Отключение делегирования

> [!NOTE]
> В Office 365 ATP автоматическое расследование не выполняется автоматически. Действия по устранению угроз и их последствий предпринимаются только после их утверждения группой безопасности вашей организации.

## <a name="threats-and-remediation-actions"></a>Действия для угроз и исправления

В следующей таблице приведена сводка угроз и соответствующих действий по исправлению в Office 365 ATP. В некоторых случаях автоматическое исследование не приводит к определенным действиям по исправлению. Ваша группа по обеспечению безопасности может далее исследовать и предпринимать соответствующие действия, как описано в приведенной ниже таблице.

****

|Категория|Угроза и риск|Действия по исправлению|
|---|---|---|
|Электронная почта|Вредоносные программы|Обратимое удаление электронной почты и кластера <br/><br/>Если несколько сообщений электронной почты в кластере содержат вредоносные программы, кластер считается вредоносным.|
|Электронная почта|Вредоносный URL-адрес<br/>(Безопасный URL-адрес был обнаружен в [Office 365 ATP Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/how-atp-safe-links-works).)|Обратимое удаление электронной почты и кластера <br/><br/>Сообщение электронной почты, содержащее вредоносный URL-адрес, считается вредоносным.|
|Электронная почта|Фишинг|Обратимое удаление электронной почты и кластера <br/><br/>Если несколько сообщений электронной почты в кластере содержат попытки фишинга, кластер считается ложным.|
|Электронная почта|Заппед фишинг <br/>(Сообщения электронной почты доставляются и [заппед](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge).)|Обратимое удаление электронной почты и кластера <br/><br/>Доступны отчеты для просмотра сообщений заппед. [Проверьте, переместил ли ZAP сообщение и ответы на часто задаваемые вопросы](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge#how-to-see-if-zap-moved-your-message).|
|Электронная почта|Пропущенная поддельная почта, [о которой сообщил](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) пользователь|[Автоматическое исследование, инициированное отчетом пользователя](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|Электронная почта|Аномалия тома <br/>(Последние количества по электронной почте превышают предыдущие 7-10 дней для условий соответствия).|Автоматическое исследование не приводит к выполнению определенного ожидающего действия. <br/><br/>Аномалия тома не является очевидной угрозой, но это просто указывает на более крупные дни электронной почты по сравнению с последними 7-10 днями в последние дней. Хотя это может указывать на возможные проблемы, в случае вредоносных вердиктс или ручного просмотра сообщений электронной почты или кластеров требуется подтверждение. Узнайте [, как найти и удалить подозрительные сообщения электронной почты, которые были доставлены](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered#find-and-delete-suspicious-email-that-was-delivered).|
|Электронная почта|Угрозы не найдены <br/>(Система не обнаружила угроз на основе файлов, URL-адресов или анализа кластера электронной почты вердиктс.)|Автоматическое исследование не приводит к выполнению определенного ожидающего действия. <br/><br/>Угрозы, обнаруженные и [заппед](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge) после завершения расследования, не отражаются в числовых возможностях расследования, но такие угрозы отображаются в [обозревателе угроз](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer).|
|Пользователь|Пользователь нащелкаю вредоносный URL-адрес <br/>(Пользователь перешел на страницу, которая ранее была обнаружена в качестве вредоносной, или пользователь может пропустить [страницу предупреждения о безопасных ссылках](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-warning-pages) , чтобы получить доступ к вредоносной странице.)|Автоматическое исследование не приводит к выполнению определенного ожидающего действия. <br/><br/>Используйте обозреватель угроз для [просмотра данных об URL-адресах и щелкните вердиктс](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer#view-data-about-phishing-urls-and-click-verdict). <br/><br/>Если в вашей организации используется [Advanced Threat Protection в защитнике Microsoft](https://docs.microsoft.com/windows/security/threat-protection/), рассмотрите возможность [изучения пользователя](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) , чтобы определить, нарушена ли его учетная запись.|
|Пользователь|Пользователь отправляет вредоносную или фишинг|Автоматическое исследование не приводит к выполнению определенного ожидающего действия. <br/><br/>Пользователь может создавать отчеты о вредоносных и фишинговых атаках, а кто-то может [подменить пользователя](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spoofing-protection) в ходе атаки. Использование [обозревателя угроз](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) для просмотра и обработки сообщений электронной почты, содержащих [вредоносные программы](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views#email--malware) или [Фишинг](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views#email--phish).|
|Пользователь|Переадресация почты <br/>(Настраиваются правила переадресации почтовых ящиков, которые можно использовать для ексфилтратион данных.)|Удаление правила пересылки <br/><br/>Используйте [аналитику обработки почты](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-insights-v2), в том числе [отчет о автоматически пересылаемых сообщениях](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report), для просмотра более подробных сведений о пересылаемой электронной почте.|
|Пользователь|Правила делегирования электронной почты <br/>(Для учетной записи пользователя настроено делегирование.)|Удаление правила делегирования <br/><br/> Если в вашей организации используется [Advanced Threat Protection в защитнике Microsoft](https://docs.microsoft.com/windows/security/threat-protection/), рассмотрите вопрос о [пользователе](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) , который получает разрешение на делегирование.|
|Пользователь|Кража данных<br/>(Пользователь нарушил электронную почту или [политики защиты от потери](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)данных при совместном использовании файлов.)|Автоматическое исследование не приводит к выполнению определенного ожидающего действия. <br/><br/>[Просмотр отчетов DLP и выполнение действий](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports).|
|Пользователь|Аномальная отправка электронной почты <br/>(Пользователь недавно отправил сообщение электронной почты, а не в течение предыдущих 7-10 дней.)|Автоматическое исследование не приводит к выполнению определенного ожидающего действия. <br/><br/>Отправка большого числа сообщений не является вредоносной. пользователю может быть отправлено сообщение электронной почты большой группе получателей для события. Чтобы определить, что происходит и что нужно действие, используйте [аналитику почтовых ящиков](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-insights-v2), включая [отчет карты обработки почты](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-mail-flow-map-report) .|
|

## <a name="next-steps"></a>Дальнейшие действия

- [Просмотр сведений и результатов автоматического исследования в Microsoft 365](air-view-investigation-results.md)

- [Просмотр ожидающих или завершенных действий по исправлению, следующих за автоматическим исследованием в Microsoft 365](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>Статьи по теме

- [Автоматическое исследование в Advanced Threat Protection в защитнике Майкрософт](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Сведения о защите от угроз Майкрософт](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
