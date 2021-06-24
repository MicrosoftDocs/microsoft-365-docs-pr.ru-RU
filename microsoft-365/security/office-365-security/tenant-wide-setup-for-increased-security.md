---
title: 'Настройка клиента Microsoft 365 для улучшения безопасности '
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/11/2018
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: 8d274fe3-db51-4107-ba64-865e7155b355
ms.custom:
- seo-marvel-apr2020
description: В этом разделе вы можете пройти рекомендуемую конфигурацию для параметров для всех клиентов, которые влияют на безопасность Microsoft 365 среды.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b1bb3f9bf6507e41d8b927137a9ab9ea8803637c
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105528"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>Настройка клиента Microsoft 365 для улучшения безопасности 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

В этом разделе вы можете пройти рекомендуемую конфигурацию для параметров для всех клиентов, которые влияют на безопасность Microsoft 365 среды. Для обеспечения безопасности может потребоваться более или менее безопасная безопасность. Используйте эти рекомендации в качестве отправной точки.

## <a name="check-office-365-secure-score"></a>Проверка Office 365 баллов

Office 365 Secure Score анализирует безопасность организации на основе регулярных действий и параметров безопасности и назначает оценку. Начните с сведений о текущем показателе. Настройка некоторых параметров для клиента увеличит ваш балл. Цель заключается не в достижении максимального балла, а в том, чтобы иметь возможность защитить окружающую среду, которая не влияет на производительность для пользователей. См. [запись Microsoft Secure Score](../defender/microsoft-secure-score.md).

## <a name="tune-threat-management-policies-in-the-microsoft-365-defender-portal"></a>Настройка политик управления угрозами на Microsoft 365 Defender портале

Портал Microsoft 365 Defender включает возможности, защищающие среду. Он также включает отчеты и панели мониторинга, которые можно использовать для мониторинга и принятия мер. В некоторых областях есть конфигурации политик по умолчанию. В некоторых областях не содержатся политики или правила по умолчанию. Посетите эти политики в статье **Email & политики** совместной & правила политики угрозы для настройки параметров управления угрозами для более \>  \>  безопасной среды.

<br>

****

|Область|Политика по умолчанию?|Рекомендация|
|---|---|---|
|**Anti-phishing**|Да|Настройка политики защиты от фишинга по умолчанию, как описано здесь: Настройка параметров защиты от фишинга в [EOP](protect-against-threats.md#part-2---anti-phishing-protection-in-eop-and-defender-for-office-365)и Defender для Office 365 . <p> Дополнительные сведения: <ul><li>[Политики защиты от фишинга в Microsoft 365](set-up-anti-phishing-policies.md)</li><li>[Рекомендуемые параметры политики защиты от фишинга в Microsoft Defender для Office 365](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)</li><li> [Сведения об олицетворении](impersonation-insight.md)</li><li>[Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md)</li><li>[Управление списком разрешить или блокировать клиента.](tenant-allow-block-list.md)</li></ul>|
|**Двигатель для борьбы с вредоносными программами**|Да|Настройка политики защиты от вредоносных программ по умолчанию, как описано здесь: Настройка параметров защиты от вредоносных программ [в EOP](protect-against-threats.md#part-1---anti-malware-protection-in-eop). <p> Дополнительные сведения: <ul><li>[Защита от вредоносных программ](anti-malware-protection.md)</li><li>[Рекомендуемые параметры политики по борьбе с вредоносными программами](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)</li><li>[Настройка политик защиты от вредоносных программ](configure-anti-malware-policies.md)</li></ul>|
|**Безопасные вложения в Defender для Office 365**|Нет|Настройка глобальных параметров для Сейф вложений и создание политики Сейф вложений, как описано здесь: Настройка параметров Сейф в [Microsoft Defender](protect-against-threats.md#safe-attachments-policies-in-microsoft-defender-for-office-365)для Office 365 . <p> Дополнительные сведения: <ul><li>[Рекомендуемые Сейф вложения](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</li><li>[Сейф Вложения в Microsoft Defender для Office 365](safe-attachments.md)</li><li>[Настройка политик безопасных вложений](set-up-safe-attachments-policies.md)</li><li>[Безопасные вложения для SharePoint, OneDrive и Microsoft Teams](mdo-for-spo-odb-and-teams.md)</li><li>[Безопасные документы в Microsoft 365 E5](safe-docs.md)</li></ul>|
|**Сейф Ссылки в Microsoft Defender для Office 365**|Нет|Настройка глобальных параметров для Сейф ссылок и создание политики ссылок Сейф, как описано здесь: Настройка параметров Сейф ссылок в [Microsoft Defender](protect-against-threats.md#safe-links-policies-in-microsoft-defender-for-office-365)для Office 365 . <p> Дополнительные сведения: <ul><li>[Рекомендуемые Сейф ссылки](recommended-settings-for-eop-and-office365.md#safe-links-settings)</li><li>[Настройка политик Безопасных ссылок](set-up-safe-links-policies.md)</li><li>[Сейф Ссылки в Microsoft Defender для Office 365](safe-links.md)</li><li>[Настройка глобальных параметров для Сейф ссылок в Microsoft Defender для Office 365](configure-global-settings-for-safe-links.md)</li></ul>|
|**Анти-спам (фильтрация почты)**|Да|Настройка политики защиты от нежелательной почты по умолчанию, как описано здесь: Настройка параметров защиты от нежелательной почты [в EOP](protect-against-threats.md#part-3---anti-spam-protection-in-eop) <p> Дополнительные сведения: <ul><li>[Рекомендуемые параметры политики по борьбе со спамом](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)</li><li>[Защита от нежелательной почты в EOP](anti-spam-protection.md)</li><li>[Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md)</li></ul>|
|***Проверка подлинности электронной почты***|Да|Проверка подлинности электронной почты использует записи DNS для добавления проверяемых сведений в сообщения электронной почты об источнике и отправителье сообщений. Microsoft 365 автоматически настраивает проверку подлинности электронной почты для домена по умолчанию (onmicrosoft.com), но Microsoft 365 администраторы также могут настроить проверку подлинности электронной почты для настраиваемых доменов. Используются три метода проверки подлинности: <ul><li>Структура политики отправитель (или SPF).</li><ul><li>Для установки [см. в Microsoft 365 настройка SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)для предотвращения подмены.</li></ul> <li>DomainKeys Identified Mail (DKIM).</li><ul><li>См. [в этой ссылке Использование DKIM для проверки исходящие сообщения электронной почты, отправленной из настраиваемого домена.](use-dkim-to-validate-outbound-email.md)</li><li>После настройки DKIM встроим его на Microsoft 365 Defender портале.</li></ul><li>Проверка подлинности, отчетности и соответствия на основе доменных сообщений (DMARC).</li><ul><li>Для установки DMARC [используйте DMARC](use-dmarc-to-validate-email.md)для проверки электронной почты в Microsoft 365.</li></ul></ul>|
|

> [!NOTE]
> Для нестандартных развертывания SPF, гибридных развертывания и устранения неполадок: как Microsoft 365 [использует sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md)для предотвращения подмены.

## <a name="view-dashboards-and-reports-in-the-microsoft-365-defender-portal"></a>Просмотр панелей мониторинга и отчетов на Microsoft 365 Defender портале

Чтобы узнать больше о состоянии среды, посетите эти отчеты и панели мониторинга. Данные в этих отчетах станут богаче по мере использования Office 365 служб. На данный момент ознакомьтесь с тем, что можно отслеживать и принимать меры.

<br>

****

|Информационная панель|Описание|
|---|---|
|Отчеты о безопасности электронной почты|Эти отчеты доступны в Exchange Online Protection. Дополнительные сведения см. в [обзоре отчетов](view-email-security-reports.md)о безопасности электронной почты на Microsoft 365 Defender.|
|Defender для Office 365 отчетов|Отчеты доступны только в Defender для Office 365. Дополнительные сведения см. в Office 365 отчетов View [Defender на портале Microsoft 365 Defender.](view-reports-for-mdo.md)|
|Отчеты и сведения о потоке почты|Эти отчеты и сведения доступны в центре администрирования Exchange (EAC). Дополнительные сведения см. [в отчетах о](/exchange/monitoring/mail-flow-reports/mail-flow-reports) потоке почты и [сведениях о потоке почты.](/exchange/monitoring/mail-flow-insights/mail-flow-insights)|
|[отчет обозревателя угроз (или обнаружение в режиме реального времени)](threat-explorer.md);|При расследовании или атаке на клиента используйте Explorer (или обнаружения в режиме реального времени) для анализа угроз. Обозреватель (и отчет о обнаружениях в режиме реального времени) показывает объем атак с течением времени, и эти данные можно анализировать по семействам угроз, инфраструктуре злоумышленников и более. Вы также можете отметить любое подозрительное сообщение электронной почты в списке Инциденты.|
|

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>Настройка дополнительных параметров Exchange Online для клиента

Вот несколько дополнительных параметров, которые рекомендуется.

<br>

****

|Область|Рекомендация|
|---|---|
|**Правила потока почты** (также известные как правила транспорта)|Добавьте правило потока почты, чтобы защититься от программ-вымогателей, блокируя исполняемые типы файлов и Office, содержащие макрос. Дополнительные сведения см. в приложении [Use mail flow rules to inspect message attachments in Exchange Online.](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments) <p> Дополнительные разделы: <ul><li>[Защита от программ-шантажистов](../../admin/security-and-compliance/secure-your-business-data.md#5-protect-against-ransomware)</li><li>[Защита от вредоносных программ и программ-вымогателей в Microsoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection)</li><li>[Восстановление после атаки вымогателей в Office 365](recover-from-ransomware.md)</li></ul> <p> Создайте правило потока почты для предотвращения автоматической пересылки электронной почты во внешние домены. Дополнительные сведения см. в сведениях о смягчении правил внешнего переададации клиентов [с помощью безопасной оценки.](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score) <p> Дополнительные сведения: правила потока [почты (правила транспорта) в Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**Современная проверка подлинности**|Современная проверка подлинности является обязательным условием для использования многофакторной проверки подлинности (MFA). MFA рекомендуется для обеспечения доступа к облачным ресурсам, включая электронную почту. <p> См. эти разделы: <ul><li>[Включение и отключение современной проверки подлинности в Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)</li><li>[Skype для бизнеса Online: Включить клиента для современной проверки подлинности](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</li></ul> <p> Современная проверка подлинности включена по умолчанию для Office 2016 года, SharePoint Online и OneDrive для бизнеса. <p> Дополнительные сведения. Как работает современная проверка подлинности [для Office 2013 и Office 2016 г.](../../enterprise/modern-auth-for-office-2013-and-2016.md)|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>Настройка политик общего доступа для клиента в SharePoint центре администрирования

Рекомендации Корпорации Майкрософт по настройке SharePoint сайтов группы на более высоких уровнях защиты, начиная с базовой защиты. Дополнительные сведения см. в рекомендациях политики по обеспечению безопасности [SharePoint сайтов и файлов.](sharepoint-file-access-policies.md)

SharePoint сайтов группы, настроенных на базовом уровне, позволяют обмениваться файлами с внешними пользователями с помощью анонимных ссылок доступа. Рекомендуется использовать этот подход вместо отправки файлов по электронной почте.

Для поддержки целей базовой защиты настройте политики общего доступа для всех клиентов, как это рекомендуется здесь. Параметры общего доступа для отдельных сайтов могут быть более жесткими, чем эта политика для клиента, но не более допустимой.

<br>

****

|Область|Включает политику по умолчанию|Рекомендация|
|---|---|---|
|**Общий** доступ (SharePoint Online и OneDrive для бизнеса)|Да|Внешний общий доступ включен по умолчанию. Рекомендуется использовать эти параметры: <ul><li>Разрешить общий доступ к аутентификации внешних пользователей и использование анонимных ссылок доступа (параметр по умолчанию).</li><li>Анонимные ссылки доступа истекают в течение многих дней. Введите номер при желании, например 30 дней.</li><li>Тип ссылки по умолчанию — выберите Внутренний (только для людей в организации). Пользователи, желающие поделиться с помощью анонимных ссылок, должны выбрать этот параметр из меню общего доступа.</li></ul> <p> Дополнительные сведения. [Обзор внешнего общего доступа](/sharepoint/external-sharing-overview)|
|

SharePoint центра администрирования и OneDrive для бизнеса центра администрирования включают те же параметры. Параметры в любом центре администрирования применяются к обоим.

## <a name="configure-settings-in-azure-active-directory"></a>Настройка параметров в Azure Active Directory

Не забудьте посетить эти две области в Azure Active Directory, чтобы завершить настройку для более безопасных сред для клиента.

### <a name="configure-named-locations-under-conditional-access"></a>Настройка именных местоположений (при условном доступе)

Если в вашей организации есть офисы с защищенным доступом к сети, добавьте надежные диапазоны IP-адресов в Azure Active Directory именуемого расположения. Эта функция помогает уменьшить количество сообщений о ложных срабатывательном элементе для событий риска при входе.

См.: [Имена местоположений в Azure Active Directory](/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>Блокировка приложений, которые не поддерживают современную проверку подлинности

Многофакторная проверка подлинности требует приложений, поддерживаюющих современную проверку подлинности. Приложения, которые не поддерживают современную проверку подлинности, не могут быть заблокированы с помощью правил условного доступа.

В безопасных средах обязательно отключать проверку подлинности для приложений, которые не поддерживают современную проверку подлинности. Это можно сделать в Azure Active Directory с помощью скорого управления.

В то же время используйте один из следующих методов для выполнения этого для SharePoint Online и OneDrive для бизнеса:

- Используйте PowerShell, [см. в рублях Block apps, которые не используют современную](/mem/intune/protect/app-modern-authentication-block)проверку подлинности (ADAL).
- Настройте это в центре администрирования SharePoint на странице "Доступ к устройству" — "Управление доступом из приложений, не пользуемых современной проверкой подлинности". Выберите блок.

## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>Начало работы с Cloud App Security или Office 365 Cloud App Security

Используйте Office 365 Cloud App Security для оценки риска, оповещения о подозрительной активности и автоматического принятия действий. Требуется Office 365 E5 плана.

Или используйте Microsoft Cloud App Security для получения более глубокой видимости даже после предоставления доступа, комплексного управления и улучшенной защиты для всех облачных приложений, включая Office 365.

Так как это решение рекомендует план EMS E5, рекомендуется начать с Cloud App Security, чтобы использовать его с другими приложениями SaaS в среде. Начните с политик и параметров по умолчанию.

Дополнительные сведения:

- [Развертывание Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security)
- [Дополнительные сведения о Microsoft Cloud App Security](https://www.microsoft.com/cloud-platform/cloud-app-security)
- [Что такое Cloud App Security?](/cloud-app-security/what-is-cloud-app-security)

![Панель мониторинга Cloud App Security](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>Дополнительные ресурсы

Эти статьи и руководства предоставляют дополнительные предписывающие сведения для обеспечения безопасности Microsoft 365 среды:

- [Руководство по безопасности](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) Корпорации Майкрософт для политических кампаний, некоммерческих организаций и других гибких организаций (эти рекомендации можно использовать в любой среде, особенно в облачных средах)

- [Рекомендуемые политики безопасности и конфигурации](microsoft-365-policies-configurations.md) для удостоверений и устройств (эти рекомендации включают помощь для сред AD FS)
