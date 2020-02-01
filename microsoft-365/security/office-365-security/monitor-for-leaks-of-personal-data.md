---
title: Отслеживание утечек персональных данных
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 02/07/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Узнайте о трех средствах, которые можно использовать для отслеживания утечек персональных данных.
ms.openlocfilehash: fbdae1222a8969b5f7bdd928e7baadfda70bb937
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598796"
---
# <a name="monitor-for-leaks-of-personal-data"></a><span data-ttu-id="16984-103">Отслеживание утечек персональных данных</span><span class="sxs-lookup"><span data-stu-id="16984-103">Monitor for leaks of personal data</span></span>

<span data-ttu-id="16984-p101">Для отслеживания использования и транспортировки персональных данных можно использовать ряд средств. В этой статье описаны три популярных средства.</span><span class="sxs-lookup"><span data-stu-id="16984-p101">There are many tools that can be used to monitor the use and transport of personal data. This topic describes three tools that work well.</span></span>

![Средства для отслеживания использования и транспортировки персональных данных](../media/Monitor-for-leaks-of-personal-data-image1.png)

<span data-ttu-id="16984-107">На этом рисунке:</span><span class="sxs-lookup"><span data-stu-id="16984-107">In the illustration:</span></span>

- <span data-ttu-id="16984-p102">Сначала используйте отчеты Office 365 для защиты от потери данных, чтобы отслеживать персональные данные в SharePoint Online, OneDrive для бизнеса и передаваемой электронной почте. Они обеспечивают максимальный уровень детализации для отслеживания персональных данных. Тем не менее эти отчеты включают не все службы в Office 365.</span><span class="sxs-lookup"><span data-stu-id="16984-p102">Start with Office 365 data loss prevention reports for monitoring personal data in SharePoint Online, OneDrive for Business, and email in transit. These provide the greatest level of detail for monitoring personal data. However, these reports don't include all services in Office 365.</span></span>

- <span data-ttu-id="16984-p103">После этого используйте политики оповещений и журнал аудита Office 365, чтобы отслеживать действия в службах Office 365. Настройте текущее отслеживание или выполните поиск в журнале аудита, чтобы исследовать инцидент. Журнал аудита Office 365 можно использовать в различных службах Office 365, таких как Sway, PowerBI, Dynamics 365, Microsoft Flow, Microsoft Teams, OneDrive для бизнеса и SharePoint Online, а также для обнаружения электронных данных, анализа действий администратора, отслеживания передаваемой почты и неактивных почтовых ящиков. Беседы Skype включаются в неактивные почтовые ящики.</span><span class="sxs-lookup"><span data-stu-id="16984-p103">Next, use alert policies and the Office 365 audit log to monitor activity across Office 365 services. Setup ongoing monitoring or search the audit log to investigate an incident. The Office 365 audit log works across Office 365 services — Sway, PowerBI, eDiscovery, Dynamics 365, Microsoft Flow, Microsoft Teams, Admin activity, OneDrive for Business, SharePoint Online, mail in transit, and mailboxes at rest. Skype conversations are included in mailboxes at rest.</span></span>

- <span data-ttu-id="16984-p104">Наконец, используйте Microsoft Cloud App Security для отслеживания файлов с конфиденциальными данными в службах SaaS других поставщиков. В ближайшее время вы сможете использовать типы конфиденциальной информации Office 365 и единообразные метки в Azure Information Protection и Office с Cloud App Security. Вы можете настроить политики, которые применяются ко всем или отдельным (например, Box) приложениям SaaS. С помощью Cloud App Security невозможно обнаруживать файлы в Exchange Online, в том числе файлы, вложенные в сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="16984-p104">Finally, Use Microsoft Cloud App Security to monitor files with sensitive data in other SaaS providers. Coming soon is the ability to use Office 365 sensitive information types and unified labels across Azure Information Protection and Office with Cloud App Security. You can setup policies that apply to all of your SaaS apps or specific apps (like Box). Cloud App Security doesn't discover files in Exchange Online, including files attached to email.</span></span>

## <a name="office-365-data-loss-prevention-reports"></a><span data-ttu-id="16984-119">Отчеты о защите от потери данных в Office 365</span><span class="sxs-lookup"><span data-stu-id="16984-119">Office 365 data loss prevention reports</span></span>

<span data-ttu-id="16984-p105">Создав политики защиты от потери данных, необходимо убедиться, что они работают правильно и помогают обеспечивать соответствие требованиям. С помощью отчетов о защите от потери данных в Office 365 можно быстро просматривать количество совпадений, переопределений и ложных срабатываний касательно таких политик, динамику их использования, а также фильтровать отчеты различными способами и отображать дополнительные сведения, выбирая точки на линии графика.</span><span class="sxs-lookup"><span data-stu-id="16984-p105">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant. With the DLP reports in Office 365, you can quickly view the number of DLP policy matches, overrides, or false positives; see whether they're trending up or down over time; filter the report in different ways; and view additional details by selecting a point on a line on the graph.</span></span>

<span data-ttu-id="16984-122">Отчеты о защите от потери данных позволяют:</span><span class="sxs-lookup"><span data-stu-id="16984-122">You can use the DLP reports to:</span></span>

- <span data-ttu-id="16984-123">сосредоточиться на определенных периодах времени и определить причины скачков и тенденций;</span><span class="sxs-lookup"><span data-stu-id="16984-123">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>

- <span data-ttu-id="16984-124">выявить бизнес-процессы, которые нарушают политики защиты от потери данных вашей организации;</span><span class="sxs-lookup"><span data-stu-id="16984-124">Discover business processes that violate your organization's DLP policies.</span></span>

- <span data-ttu-id="16984-125">определить влияние политик защиты от потери данных на работу вашей организации;</span><span class="sxs-lookup"><span data-stu-id="16984-125">Understand any business impact of the DLP policies.</span></span>

- <span data-ttu-id="16984-126">просматривать основания, которые пользователи предоставляют для отправки сообщения о ложном срабатывании или для переопределения политики при ознакомлении с подсказкой политики;</span><span class="sxs-lookup"><span data-stu-id="16984-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy or reporting a false positive.</span></span>

- <span data-ttu-id="16984-127">проверить соответствие требованиям конкретной политики защиты от потери данных, отображая все совпадения с правилами этой политики;</span><span class="sxs-lookup"><span data-stu-id="16984-127">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>

- <span data-ttu-id="16984-128">просмотреть список файлов с конфиденциальными данными, который соответствует правилам политик защиты от потери данных вашей организации, в области сведений.</span><span class="sxs-lookup"><span data-stu-id="16984-128">View a list of files with sensitive data that matches your DLP policies in the details pane.</span></span>

<span data-ttu-id="16984-129">Кроме того, эти отчеты можно использовать для точной настройки ваших политик защиты от потери данных при их выполнении в тестовом режиме.</span><span class="sxs-lookup"><span data-stu-id="16984-129">In addition, you can use the DLP reports to fine tune your DLP policies as you run them in test mode.</span></span>

<span data-ttu-id="16984-130">Отчеты защиты от потери данных (DLP) можно просмотреть в Центре безопасности и Центре соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="16984-130">DLP reports are in the security center and the compliance center.</span></span> <span data-ttu-id="16984-131">Откройте Отчеты \> Просмотр отчетов.</span><span class="sxs-lookup"><span data-stu-id="16984-131">Navigate to Reports \> View reports.</span></span> <span data-ttu-id="16984-132">В разделе Защита от потери данных (DLP) перейдите либо по в раздел «Совпадения по правилу и политике защиты от потери данных», или в раздел «Ложные срабатывания и переопределения функции защиты от потери данных».</span><span class="sxs-lookup"><span data-stu-id="16984-132">Under Data loss prevention (DLP), go to either DLP policy and rule matches or DLP false positives and overrides.</span></span>

<span data-ttu-id="16984-133">Дополнительные сведения см. в статье [Просмотр отчетов о защите от потери данных](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports).</span><span class="sxs-lookup"><span data-stu-id="16984-133">For more information, see [View the reports for data loss prevention](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports).</span></span>

![Отчет, в котором показаны совпадения по политике защиты от потери данных](../media/Monitor-for-leaks-of-personal-data-image2.png)

## <a name="office-365-audit-log-and-alert-policies"></a><span data-ttu-id="16984-135">Журнал аудита Office 365 и политики оповещений</span><span class="sxs-lookup"><span data-stu-id="16984-135">Office 365 audit log and alert policies</span></span>

<span data-ttu-id="16984-136">Журнал аудита Office 365 включает события из Exchange Online, SharePoint Online, OneDrive для бизнеса, Azure Active Directory, Microsoft Teams, Power BI, Sway и других служб Office 365.</span><span class="sxs-lookup"><span data-stu-id="16984-136">The Office 365 audit log contains events from Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory, Microsoft Teams, Power BI, Sway, and other Office 365 services.</span></span>

<span data-ttu-id="16984-137">Центр безопасности и Центр соответствия требованиям поддерживают два способа отслеживания журнала аудита Office 365 и создания отчетов:</span><span class="sxs-lookup"><span data-stu-id="16984-137">The security center and compliance center provide two ways to monitor and report against the Office 365 audit log:</span></span>

- <span data-ttu-id="16984-138">Настройка политик оповещения, просмотр оповещений и отслеживание тенденций: используйте новую политику оповещений и инструменты панели оповещений либо в Центре безопасности, либо в Центре соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="16984-138">Setup alert policies, view alerts, and monitor trends — Use the alert policy and alert dashboard tools in either the security center or compliance center.</span></span>

- <span data-ttu-id="16984-p107">непосредственный поиск в журнале аудита: поиск можно выполнять по всем событиям в указанном диапазоне дат. Кроме того, можно фильтровать результаты на основе заданных условий, например по пользователю, выполнившему действие, по действию или целевому объекту.</span><span class="sxs-lookup"><span data-stu-id="16984-p107">Search the audit log directly — Search for all events in a specified date rage. Or you can filter the results based on specific criteria, such as the user who performed the action, the action, or the target object.</span></span>

<span data-ttu-id="16984-p108">Группы по обеспечению информационной безопасности и соответствия требованиям могут использовать эти средства для упреждающей проверки действий пользователей и администраторов в службах Office 365. Можно настроить автоматические оповещения, чтобы отправлять по электронной почте уведомления об определенных действиях в конкретных семействах веб-сайтов (например, о предоставлении общего доступа к содержимому с веб-сайтов, на которых имеются данные, подпадающие под действие регламента GDPR). Таким образом, эти группы смогут отслеживать соблюдение пользователями корпоративных политик безопасности либо предоставить им дополнительные услуги по обучению.</span><span class="sxs-lookup"><span data-stu-id="16984-p108">Information security and compliance teams can use these tools to proactively review activities performed by both end users and administrators across Office 365 services. Automatic alerts can be configured to send email notifications when certain activities occur on specific site collections - for example when content is shared from sites known to contain GDPR related information. This allows those teams to follow up with users to ensure that corporate security policies are followed, or to provide additional training.</span></span>

<span data-ttu-id="16984-p109">Кроме того, группы по обеспечению информационной безопасности могут выполнять поиск в журнале аудита для исследования потенциальных нарушений безопасности данных, определяя как первопричины, так и степень этих нарушений. Эта встроенная возможность позволяет обеспечить соответствие требованиям статей 33 и 34 регламента GDPR, согласно которым в течение определенного периода времени о нарушении безопасности данных требуется уведомить как надзорный орган GDPR, так и самих субъектов данных. Записи журнала аудита сохраняются в службе только на протяжении 90 дней. Тем не менее эти журналы часто рекомендуется хранить в течение большего периода времени (и так поступают многие организации).</span><span class="sxs-lookup"><span data-stu-id="16984-p109">Information security teams can also search the audit log to investigate suspected data breaches and determine both root cause and the extent of the breach. This built in capability facilitates compliance with article 33 and 34 of the GDPR, which require notifications be provided to the GDPR supervisory authority and to the data subjects themselves of a data breach within a specific time period. Audit log entries are only retained for 90 days within the service - it is often recommended and many organizations required that these logs be retained for longer periods of time.</span></span>

<span data-ttu-id="16984-p110">Доступны решения, которые обеспечивают подписку на единые журналы аудита с помощью API действий управления Microsoft, сохранение записей журналов (при необходимости) и предоставление расширенных панелей мониторинга и оповещений. Пример такого решения — [Microsoft Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/oms-solution-office-365).</span><span class="sxs-lookup"><span data-stu-id="16984-p110">Solutions are available which subscribe to the Unified Audit Logs through the Microsoft Management Activity API and can both store log entries as needed, and provide advanced dashboards and alerts. One example is [Microsoft Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/oms-solution-office-365).</span></span>

<span data-ttu-id="16984-149">Дополнительные сведения о политиках оповещений и поиске в журнале аудита:</span><span class="sxs-lookup"><span data-stu-id="16984-149">More information about alert policies and searching the audit log:</span></span>

- [<span data-ttu-id="16984-150">Политики оповещений в Центре безопасности и соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="16984-150">Alert policies in the Microsoft 365 security and compliance centers</span></span>](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)

- <span data-ttu-id="16984-151">[Поиск действий пользователей и администраторов в журнале аудита в Office 365](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log) (введение)</span><span class="sxs-lookup"><span data-stu-id="16984-151">[Search the audit log for user and admin activity in Office 365](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log) (introduction)</span></span>

- [<span data-ttu-id="16984-152">Включение и отключение поиска в журнале аудита Office 365</span><span class="sxs-lookup"><span data-stu-id="16984-152">Turn Office 365 audit log search on or off</span></span>](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)

- [<span data-ttu-id="16984-153">Поиск в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="16984-153">Search the audit log</span></span>](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

- <span data-ttu-id="16984-154">[Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) (командлет)</span><span class="sxs-lookup"><span data-stu-id="16984-154">[Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) (cmdlet)</span></span>

- [<span data-ttu-id="16984-155">Подробные свойства в журнале аудита Office 365</span><span class="sxs-lookup"><span data-stu-id="16984-155">Detailed properties in the Office 365 audit log</span></span>](https://docs.microsoft.com/microsoft-365/compliance/detailed-properties-in-the-office-365-audit-log)

## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="16984-156">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="16984-156">Microsoft Cloud App Security</span></span>

<span data-ttu-id="16984-157">Microsoft Cloud App Security позволяет обнаруживать другие приложения SaaS, используемые в ваших сетях, и конфиденциальные данные, которые отправляются в эти приложения или из них.</span><span class="sxs-lookup"><span data-stu-id="16984-157">Microsoft Cloud App Security helps you discover other SaaS apps in use across your networks and sensitive data that is sent to and from these apps.</span></span>

<span data-ttu-id="16984-p111">Microsoft Cloud App Security — это полнофункциональная служба, обеспечивающая глубокую наглядность, детальные элементы управления и улучшенную защиту облачных приложений от угроз. Она позволяет идентифицировать более чем 15 000 облачных приложений в сети на всех устройствах, гарантируя постоянную оценку и анализ рисков. Отпадает необходимость в агентах: из брандмауэров и прокси-серверов собираются полные контекстные данные об использовании облачных решений и теневых ИТ.</span><span class="sxs-lookup"><span data-stu-id="16984-p111">Microsoft Cloud App Security is a comprehensive service providing deep visibility, granular controls and enhanced threat protection for your cloud apps. It identifies more than 15,000 cloud applications in your network-from all devices-and provides risk scoring and ongoing risk assessment and analytics. No agents required: information is collected from your firewalls and proxies to give you complete visibility and context for cloud usage and shadow IT.</span></span>

<span data-ttu-id="16984-p112">Для лучшего понимания вашей облачной среды доступная в Cloud App Security функция исследования позволяет получить подробные данные обо всех действиях, файлах и учетных записях для санкционированных и управляемых приложений. Вы можете получить детальные сведения на уровне файлов и определить пути перемещения данных в облачных приложениях.</span><span class="sxs-lookup"><span data-stu-id="16984-p112">To better understand your cloud environment, Cloud App Security investigate feature provides deep visibility into all activities, files and accounts for sanctioned and managed apps. You can gain detailed information on a file level and discover where data travels in the cloud apps.</span></span>

<span data-ttu-id="16984-163">Например, на рисунке ниже приведены две политики Cloud App Security, которые помогут обеспечить соответствие требованиям регламента GDPR.</span><span class="sxs-lookup"><span data-stu-id="16984-163">For examples, the following illustration demonstrates two Cloud App Security policies that can help with GDPR.</span></span>

![Примеры политик Cloud App Security](../media/Monitor-for-leaks-of-personal-data-image3.png)

<span data-ttu-id="16984-165">Первая политика оповещает вас о предоставлении общего доступа к предопределенному атрибуту личных сведений или выбранному вами настраиваемому выражению за пределами организации из указанных приложений SaaS.</span><span class="sxs-lookup"><span data-stu-id="16984-165">The first policy alerts when files with a predefined PII attribute or custom expression that you choose is shared outside the organization from the SaaS apps that you choose.</span></span>

<span data-ttu-id="16984-p113">Вторая политика блокирует скачивание файлов на любое неуправляемое устройство. Вы выбираете искомые атрибуты в файлах и приложения SaaS, к которым необходимо применить политику.</span><span class="sxs-lookup"><span data-stu-id="16984-p113">The second policy blocks downloads of files to any unmanaged device. You choose the attributes within the files to look for and the SaaS apps you want the policy to apply to.</span></span>

<span data-ttu-id="16984-168">В ближайшее время в Cloud App Security будут представлены следующие типы атрибутов:</span><span class="sxs-lookup"><span data-stu-id="16984-168">These attribute types are coming soon to Cloud App Security:</span></span>

- <span data-ttu-id="16984-169">типы конфиденциальной информации Office 365;</span><span class="sxs-lookup"><span data-stu-id="16984-169">Office 365 sensitive information types</span></span>

- <span data-ttu-id="16984-170">единообразные метки в Office 365 и Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="16984-170">Unified labels across Office 365 and Azure Information Protection</span></span>

### <a name="cloud-app-security-dashboard"></a><span data-ttu-id="16984-171">Панель мониторинга Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="16984-171">Cloud App Security dashboard</span></span>

<span data-ttu-id="16984-p114">Если вы еще не начали использовать Cloud App Security, сначала запустите это решение. Получите доступ к Cloud App Security по следующему адресу: <https://portal.cloudappsecurity.com>.</span><span class="sxs-lookup"><span data-stu-id="16984-p114">If you haven't yet started to use Cloud App Security, begin by starting it up. To access Cloud App Security: <https://portal.cloudappsecurity.com>.</span></span>

<span data-ttu-id="16984-p115">Примечание. Обязательно установите флажок "Автоматически сканировать файлы на наличие меток классификации Azure Information Protection" (в общих параметрах), прежде чем приступить к работе с Cloud App Security или назначить метки. После настройки Cloud App Security выполняет повторное сканирование имеющихся файлов только после их изменения.</span><span class="sxs-lookup"><span data-stu-id="16984-p115">Note: Be sure to enable 'Automatically scan files for Azure Information Protection classification labels' (in General settings) when getting started with Cloud App Security or before you assign labels. After setup, Cloud App Security does not scan existing files again until they are modified.</span></span>

![Панель мониторинга со сведениями об оповещениях](../media/Monitor-for-leaks-of-personal-data-image4.png)

<span data-ttu-id="16984-177">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="16984-177">More information:</span></span>

- [<span data-ttu-id="16984-178">Развертывание Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="16984-178">Deploy Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)

- [<span data-ttu-id="16984-179">Дополнительные сведения о Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="16984-179">More information about Microsoft Cloud App Security</span></span>](https://www.microsoft.com/cloud-platform/cloud-app-security)

- [<span data-ttu-id="16984-180">Блокировка скачивания конфиденциальных данных с помощью прокси-сервера Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="16984-180">Block downloads of sensitive information using the Microsoft Cloud App Security proxy</span></span>](https://docs.microsoft.com/cloud-app-security/use-case-proxy-block-session-aad)

## <a name="example-file-and-activity-policies-to-detect-sharing-of-personal-data"></a><span data-ttu-id="16984-181">Примеры политик файлов и действий для обнаружения случаев предоставления общего доступа к персональным данным</span><span class="sxs-lookup"><span data-stu-id="16984-181">Example file and activity policies to detect sharing of personal data</span></span>

### <a name="detect-sharing-of-files-containing-pii--credit-card-number"></a><span data-ttu-id="16984-182">Обнаружение случаев предоставления общего доступа к файлам, содержащим личные сведения — номер кредитной карты</span><span class="sxs-lookup"><span data-stu-id="16984-182">Detect sharing of files containing PII — Credit card number</span></span>

<span data-ttu-id="16984-183">Отправка оповещений о случаях предоставления общего доступа к файлу, содержащему номер кредитной карты, из утвержденного облачного приложения.</span><span class="sxs-lookup"><span data-stu-id="16984-183">Alert when a file containing a credit card number is shared from an approved cloud app.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="16984-184"><strong>Элемент управления</strong></span><span class="sxs-lookup"><span data-stu-id="16984-184"><strong>Control</strong></span></span></th>
<th align="left"><span data-ttu-id="16984-185"><strong>Настройки</strong></span><span class="sxs-lookup"><span data-stu-id="16984-185"><strong>Settings</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="16984-186">Тип политики</span><span class="sxs-lookup"><span data-stu-id="16984-186">Policy type</span></span></td>
<td align="left"><span data-ttu-id="16984-187">Политика файлов</span><span class="sxs-lookup"><span data-stu-id="16984-187">File policy</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16984-188">Шаблон политики</span><span class="sxs-lookup"><span data-stu-id="16984-188">Policy template</span></span></td>
<td align="left"><span data-ttu-id="16984-189">Без шаблона</span><span class="sxs-lookup"><span data-stu-id="16984-189">No template</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16984-190">Серьезность политики</span><span class="sxs-lookup"><span data-stu-id="16984-190">Policy severity</span></span></td>
<td align="left"><span data-ttu-id="16984-191">Высокая</span><span class="sxs-lookup"><span data-stu-id="16984-191">High</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16984-192">Категория</span><span class="sxs-lookup"><span data-stu-id="16984-192">Category</span></span></td>
<td align="left"><span data-ttu-id="16984-193">Защита от потери данных</span><span class="sxs-lookup"><span data-stu-id="16984-193">DLP</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16984-194">Параметры фильтра</span><span class="sxs-lookup"><span data-stu-id="16984-194">Filter settings</span></span></td>
<td align="left"><p><span data-ttu-id="16984-195">Уровень доступа = "Общедоступный (Интернет)", "Общедоступный", "Внешний"</span><span class="sxs-lookup"><span data-stu-id="16984-195">Access level = Public (Internet), Public, External</span></span></p>
<p><span data-ttu-id="16984-196">Приложение = &lt;select apps&gt; (используйте этот параметр, чтобы отслеживать только определенные приложения SaaS)</span><span class="sxs-lookup"><span data-stu-id="16984-196">App = &lt;select apps&gt; (use this setting if you want to limit monitoring to specific SaaS apps)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16984-197">Применимо к</span><span class="sxs-lookup"><span data-stu-id="16984-197">Apply to</span></span></td>
<td align="left"><span data-ttu-id="16984-198">Всем файлам, всем владельцам</span><span class="sxs-lookup"><span data-stu-id="16984-198">All files, all owners</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16984-199">Проверка содержимого</span><span class="sxs-lookup"><span data-stu-id="16984-199">Content inspection</span></span></td>
<td align="left"><p><span data-ttu-id="16984-200">Включает файлы, которые соответствуют текущему выражению: "Все страны": "Финансы": "Номер кредитной карты"</span><span class="sxs-lookup"><span data-stu-id="16984-200">Includes files that match a present expression: All countries: Finance: Credit card number</span></span></p>
<p><span data-ttu-id="16984-201">Флажок "Не требовать наличие релевантного контекста": снят (будут учитываться как ключевые слова, так и регулярное выражение)</span><span class="sxs-lookup"><span data-stu-id="16984-201">Don't require relevant context: unchecked (this will match keywords as well as regex)</span></span></p>
<p><span data-ttu-id="16984-202">Включает файлы с хотя бы 1 совпадением</span><span class="sxs-lookup"><span data-stu-id="16984-202">Includes files with at least 1 match</span></span></p>
<p><span data-ttu-id="16984-203">Флажок "Снять маску с последних четырех символов нарушения": установлен</span><span class="sxs-lookup"><span data-stu-id="16984-203">Unmask the last 4 characters of the violation: checked</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16984-204">Оповещения</span><span class="sxs-lookup"><span data-stu-id="16984-204">Alerts</span></span></td>
<td align="left"><p><span data-ttu-id="16984-205">Флажок "Создать оповещение для каждого соответствующего файла": установлен</span><span class="sxs-lookup"><span data-stu-id="16984-205">Create an alert for each matching file: checked</span></span></p>
<p><span data-ttu-id="16984-206">Ежедневный лимит оповещений: 1000</span><span class="sxs-lookup"><span data-stu-id="16984-206">Daily alert limit: 1000</span></span></p>
<p><span data-ttu-id="16984-207">Флажок "Выбрать оповещение по электронной почте": установлен</span><span class="sxs-lookup"><span data-stu-id="16984-207">Select an alert as email: checked</span></span></p>
<p><span data-ttu-id="16984-208">Получатель: infosec@contoso.com</span><span class="sxs-lookup"><span data-stu-id="16984-208">To: infosec@contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16984-209">Управление</span><span class="sxs-lookup"><span data-stu-id="16984-209">Governance</span></span></td>
<td align="left"><p><span data-ttu-id="16984-210">Microsoft OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="16984-210">Microsoft OneDrive for Business</span></span></p>
<p><span data-ttu-id="16984-211">Придание конфиденциального статуса: установите флажок "Удалить доступ для внешних пользователей"</span><span class="sxs-lookup"><span data-stu-id="16984-211">Make private: check Remove External Users</span></span></p>
<p><span data-ttu-id="16984-212">Все другие флажки: сняты</span><span class="sxs-lookup"><span data-stu-id="16984-212">All other settings: unchecked</span></span></p>
<p><span data-ttu-id="16984-213">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="16984-213">Microsoft SharePoint Online</span></span></p>
<p><span data-ttu-id="16984-214">Придание конфиденциального статуса: установите флажок "Удалить доступ для внешних пользователей"</span><span class="sxs-lookup"><span data-stu-id="16984-214">Make private: check Remove External Users</span></span></p>
<p><span data-ttu-id="16984-215">Все другие флажки: сняты</span><span class="sxs-lookup"><span data-stu-id="16984-215">All other settings: unchecked</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16984-216">Похожие политики:</span><span class="sxs-lookup"><span data-stu-id="16984-216">Similar policies:</span></span>

- <span data-ttu-id="16984-217">обнаружение случаев предоставления общего доступа к файлам, содержащим личные сведения — адрес электронной почты;</span><span class="sxs-lookup"><span data-stu-id="16984-217">Detect sharing of Files containing PII - Email Address</span></span>

- <span data-ttu-id="16984-218">обнаружение случаев предоставления общего доступа к файлам, содержащим личные сведения — номер паспорта.</span><span class="sxs-lookup"><span data-stu-id="16984-218">Detect sharing of Files containing PII - Passport Number</span></span>

### <a name="detect-customer-or-hr-data-in-box-or-onedrive-for-business"></a><span data-ttu-id="16984-219">Обнаружение данных о клиентах или персонале в приложении Box или OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="16984-219">Detect Customer or HR Data in Box or OneDrive for Business</span></span>

<span data-ttu-id="16984-220">Отправка оповещений о передаче файла с меткой "Данные клиента" или "Данные о персонале" в OneDrive для бизнеса или в приложение Box.</span><span class="sxs-lookup"><span data-stu-id="16984-220">Alert when a file labeled as Customer Data or HR Data is uploaded to OneDrive for Business or Box.</span></span>

<span data-ttu-id="16984-221">Примечания.</span><span class="sxs-lookup"><span data-stu-id="16984-221">Notes:</span></span>

- <span data-ttu-id="16984-222">Для отслеживания приложения Box необходимо настроить соединитель с помощью пакета SDK для API Connector.</span><span class="sxs-lookup"><span data-stu-id="16984-222">Box monitoring requires a connector be configured using the API Connector SDK.</span></span>

- <span data-ttu-id="16984-223">Для этой политики требуются возможности, которые сейчас доступны только в закрытой предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="16984-223">This policy requires capabilities that are currently in private preview.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="16984-224"><strong>Элемент управления</strong></span><span class="sxs-lookup"><span data-stu-id="16984-224"><strong>Control</strong></span></span></th>
<th align="left"><span data-ttu-id="16984-225"><strong>Настройки</strong></span><span class="sxs-lookup"><span data-stu-id="16984-225"><strong>Settings</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="16984-226">Тип политики</span><span class="sxs-lookup"><span data-stu-id="16984-226">Policy type</span></span></td>
<td align="left"><span data-ttu-id="16984-227">Политика действий</span><span class="sxs-lookup"><span data-stu-id="16984-227">Activity policy</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16984-228">Шаблон политики</span><span class="sxs-lookup"><span data-stu-id="16984-228">Policy template</span></span></td>
<td align="left"><span data-ttu-id="16984-229">Без шаблона</span><span class="sxs-lookup"><span data-stu-id="16984-229">No template</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16984-230">Серьезность политики</span><span class="sxs-lookup"><span data-stu-id="16984-230">Policy severity</span></span></td>
<td align="left"><span data-ttu-id="16984-231">Высокая</span><span class="sxs-lookup"><span data-stu-id="16984-231">High</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16984-232">Категория</span><span class="sxs-lookup"><span data-stu-id="16984-232">Category</span></span></td>
<td align="left"><span data-ttu-id="16984-233">Управление общим доступом</span><span class="sxs-lookup"><span data-stu-id="16984-233">Sharing Control</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16984-234">Выполнение действий над</span><span class="sxs-lookup"><span data-stu-id="16984-234">Act on</span></span></td>
<td align="left"><span data-ttu-id="16984-235">Одиночное действие</span><span class="sxs-lookup"><span data-stu-id="16984-235">Single activity</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16984-236">Параметры фильтра</span><span class="sxs-lookup"><span data-stu-id="16984-236">Filter settings</span></span></td>
<td align="left"><p><span data-ttu-id="16984-237">Тип действия = отправка файла</span><span class="sxs-lookup"><span data-stu-id="16984-237">Activity type = Upload File</span></span></p>
<p><span data-ttu-id="16984-238">Приложение = Microsoft OneDrive для бизнеса и Box</span><span class="sxs-lookup"><span data-stu-id="16984-238">App = Microsoft OneDrive for Business and Box</span></span></p>
<p><span data-ttu-id="16984-239">Метка классификации (сейчас доступна в закрытой предварительной версии): Azure Information Protection = "Данные клиента", "Управление персоналом — данные о зарплате", "Управление персоналом — данные о сотрудниках"</span><span class="sxs-lookup"><span data-stu-id="16984-239">Classification Label (currently in private preview): Azure Information Protection = Customer Data, Human Resources—Salary Data, Human Resources—Employee Data</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16984-240">Оповещения</span><span class="sxs-lookup"><span data-stu-id="16984-240">Alerts</span></span></td>
<td align="left"><p><span data-ttu-id="16984-241">Флажок "Создать оповещение": установлен</span><span class="sxs-lookup"><span data-stu-id="16984-241">Create an alert: checked</span></span></p>
<p><span data-ttu-id="16984-242">Ежедневный лимит оповещений: 1000</span><span class="sxs-lookup"><span data-stu-id="16984-242">Daily alert limit: 1000</span></span></p>
<p><span data-ttu-id="16984-243">Флажок "Выбрать оповещение по электронной почте": установлен</span><span class="sxs-lookup"><span data-stu-id="16984-243">Select an alert as email: checked</span></span></p>
<p><span data-ttu-id="16984-244">Получатель: infosec@contoso.com</span><span class="sxs-lookup"><span data-stu-id="16984-244">To: infosec@contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16984-245">Управление</span><span class="sxs-lookup"><span data-stu-id="16984-245">Governance</span></span></td>
<td align="left"><p><span data-ttu-id="16984-246">Все приложения</span><span class="sxs-lookup"><span data-stu-id="16984-246">All apps</span></span></p>
<p><span data-ttu-id="16984-247">Флажок "Поместить пользователя в карантин": установлен</span><span class="sxs-lookup"><span data-stu-id="16984-247">Put user in quarantine: check</span></span></p>
<p><span data-ttu-id="16984-248">Все другие флажки: сняты</span><span class="sxs-lookup"><span data-stu-id="16984-248">All other settings: unchecked</span></span></p>
<p><span data-ttu-id="16984-249">Office 365</span><span class="sxs-lookup"><span data-stu-id="16984-249">Office 365</span></span></p>
<p><span data-ttu-id="16984-250">Флажок "Поместить пользователя в карантин": установлен</span><span class="sxs-lookup"><span data-stu-id="16984-250">Put user in quarantine: check</span></span></p>
<p><span data-ttu-id="16984-251">Все другие флажки: сняты</span><span class="sxs-lookup"><span data-stu-id="16984-251">All other settings: unchecked</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16984-252">Похожие политики:</span><span class="sxs-lookup"><span data-stu-id="16984-252">Similar policies:</span></span>

- <span data-ttu-id="16984-253">обнаружение скачиваний данных о клиентах или персонале в больших объемах — отправка оповещений о случаях, когда отдельный пользователь в течение короткого периода времени скачивает много файлов, содержащих данные о клиентах или персонале;</span><span class="sxs-lookup"><span data-stu-id="16984-253">Detect large downloads of Customer data or HR Data — Alert when a large number of files containing customer data or HR data have been detected being downloaded by a single user within a short period of time.</span></span>

- <span data-ttu-id="16984-254">обнаружение случаев предоставления общего доступа к данным о клиентах или персонале — отправка оповещений о случаях предоставления общего доступа к данным о клиентах или персонале.</span><span class="sxs-lookup"><span data-stu-id="16984-254">Detect Sharing of Customer and HR Data — Alert when files containing Customer or HR Data are shared.</span></span>
