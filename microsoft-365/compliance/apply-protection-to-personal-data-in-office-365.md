---
title: Применение защиты к персональным данным в Office 365
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 02/07/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
- SPO_Content
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Узнайте, как использовать политики защиты от потери данных (DLP) для защиты персональных данных в Office 365.
ms.openlocfilehash: b529a6d58537c4effca3cf198dcf807a0680129d
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596066"
---
# <a name="apply-protection-to-personal-data-in-office-365"></a><span data-ttu-id="d8170-103">Применение защиты к персональным данным в Office 365</span><span class="sxs-lookup"><span data-stu-id="d8170-103">Apply protection to personal data in Office 365</span></span>

<span data-ttu-id="d8170-104">Защита персональных данных в Office 365 включает использование функций защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="d8170-104">Protection of personal information in Office 365 includes using data loss prevention capabilities.</span></span> <span data-ttu-id="d8170-105">Политики защиты от потери данных в Центре соответствия требованиям позволяют определять, отслеживать и автоматически защищать конфиденциальную информацию в Office 365.</span><span class="sxs-lookup"><span data-stu-id="d8170-105">With data loss prevention (DLP) policies in the compliance center, you can identify, monitor, and automatically protect sensitive information across Office 365.</span></span>

<span data-ttu-id="d8170-p102">В этой статье описано, как защитить персональные данные с помощью защиты от потери данных. Кроме того, в ней также перечислены другие возможности защиты, которые можно использовать для обеспечения соответствия требованиям регламента GDPR, в том числе путем установки разрешений в библиотеках SharePoint и с помощью политик доступа к устройствам.</span><span class="sxs-lookup"><span data-stu-id="d8170-p102">This topic describes how to use DLP to protect personal data. This topic also lists other protection capabilities that can be used to achieve GDPR compliance, including setting permissions in SharePoint libraries and using device access policies.</span></span>

## <a name="apply-protection-using-data-loss-prevention-in-office-365"></a><span data-ttu-id="d8170-108">Обеспечение безопасности с помощью защиты от потери данных в Office 365</span><span class="sxs-lookup"><span data-stu-id="d8170-108">Apply protection using data loss prevention in Office 365</span></span>

<span data-ttu-id="d8170-109">Защита от потери данных позволяет:</span><span class="sxs-lookup"><span data-stu-id="d8170-109">With DLP, you can:</span></span>

-   <span data-ttu-id="d8170-110">находить конфиденциальную информацию в ряде расположений;</span><span class="sxs-lookup"><span data-stu-id="d8170-110">Identify sensitive information across many locations.</span></span>

-   <span data-ttu-id="d8170-111">предотвращать случайное предоставление общего доступа к конфиденциальным данным;</span><span class="sxs-lookup"><span data-stu-id="d8170-111">Prevent accidental sharing of sensitive information.</span></span>

-   <span data-ttu-id="d8170-112">помогать пользователям соответствовать требованиям организации, не прерывая рабочий процесс;</span><span class="sxs-lookup"><span data-stu-id="d8170-112">Help users learn how to stay compliant without interrupting their workflow.</span></span>

-   <span data-ttu-id="d8170-113">просматривать отчеты DLP, в которых перечисляется содержимое, нарушающее политики защиты от потери данных вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d8170-113">View DLP reports showing content that matches your organization’s DLP policies.</span></span>

<span data-ttu-id="d8170-114">Подробнее см. в статье [Обзор политик защиты от потери данных](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e).</span><span class="sxs-lookup"><span data-stu-id="d8170-114">For more information, see [Overview of data loss prevention policies](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e).</span></span>

![Способы создания политики защиты от потери данных](Media/Apply-protection-to-personal-data-in-Office-365-image1.png)

<span data-ttu-id="d8170-116">На этом рисунке показаны способы создания политики защиты от потери данных:</span><span class="sxs-lookup"><span data-stu-id="d8170-116">This illustration shows the options for creating a DLP policy:</span></span>

-   <span data-ttu-id="d8170-p103">Выберите защиту, которую необходимо применить. Она может включать:</span><span class="sxs-lookup"><span data-stu-id="d8170-p103">Choose the protection to apply. Protection can include:</span></span>

    -   <span data-ttu-id="d8170-119">подсказки политик для пользователей;</span><span class="sxs-lookup"><span data-stu-id="d8170-119">Policy tips for users</span></span>

    -   <span data-ttu-id="d8170-120">отчет для администраторов, отправляемый по электронной почте;</span><span class="sxs-lookup"><span data-stu-id="d8170-120">Email report for admins</span></span>

    -   <span data-ttu-id="d8170-121">запрет на предоставление внутреннего и/или внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="d8170-121">Prevent sharing externally, internally, or both</span></span>

-   <span data-ttu-id="d8170-p104">Выберите условия для применения защиты. Примените защиту к документам с соответствующим типом содержимого: вы можете настроить использование типов конфиденциальной информации и/или меток.</span><span class="sxs-lookup"><span data-stu-id="d8170-p104">Choose the criteria for applying the protection. Apply the protection to documents with this type of content: you can configure the policy to use sensitive information types and/or labels.</span></span>

### <a name="using-dlp-for-gdpr-compliance"></a><span data-ttu-id="d8170-124">Использование защиты от потери данных для обеспечения соответствия требованиям регламента GDPR</span><span class="sxs-lookup"><span data-stu-id="d8170-124">Using DLP for GDPR compliance</span></span>

<span data-ttu-id="d8170-p105">Одна из главных целей защиты от потери данных в Office 365 — выявление персональных данных, связанными с субъектами данных из ЕС в среде Office 365. С помощью защиты от потери данных в Office 365 ответственные за обеспечение соответствия требованиям могут узнавать, где хранятся персональные данные в SharePoint Online и OneDrive для бизнеса, а также получать уведомления об отправке сообщений электронной почты с персональными данными. Кроме того, благодаря защите от потери данных ваши сотрудники могут получать подсказки политик при работе с персональными данными, относящимися к жителям ЕС.</span><span class="sxs-lookup"><span data-stu-id="d8170-p105">One of the primary uses of Office 365 DLP is to identify personal data related to EU data subjects in your Office 365 environment. Office 365 DLP can notify your compliance teams of where personal information is stored in SharePoint Online and OneDrive for Business, or when users send email containing personal information. DLP can also provide policy tips to your employees when working with personal information related to EU residents.</span></span>

<span data-ttu-id="d8170-p106">Повышение осведомленности сотрудников о местах хранения данных резидентов ЕС в вашей среде, а также контроль над разрешениями на управление этими данными представляет собой один уровень защиты информации Office 365. Часто сотрудникам, у которых уже есть доступ к информации такого типа, необходим доступ на этом уровне для выполнения повседневных задач. Для применения политик защиты от потери данных с целью соблюдения регламента GDPR может не требоваться ограничение доступа.</span><span class="sxs-lookup"><span data-stu-id="d8170-p106">Educating and raising awareness to where EU resident data is stored in your environment and how your employees are permitted to handle it represents one level of information protection using Office 365 DLP. Often, employees who already have access to this type of information require this access to do their day to day work. Enforcing DLP policies to help comply with GDPR may not require restricting access.</span></span>

<span data-ttu-id="d8170-p107">Тем не менее соответствие организации требованиям регламента GDPR, как правило, включает оценку рисков с точки зрения соблюдения законодательства и обеспечения информационной безопасности, определение типов персональных данных и мест их хранения, а также наличие юридических оснований для хранения и обработки этих сведений. С учетом этой оценки для внедрения политик с целью защиты организации и соблюдения регламента GDPR может потребоваться запретить сотрудникам доступ к документам, содержащим личные сведения субъектов данных ЕС. Для усиленной защиты можно настроить дополнительные параметры защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="d8170-p107">However, complying with GDPR typically involves a risk-based assessment of the organization from both a legal and information security perspective, identification of what type and where personal information is stored, as well as if there's a legal justification to store and process that information. Based on this assessment, implementing policies to protect the organization and comply with GDPR might require removing access for employees to documents that contain personal information for EU data subjects. In cases where further protection is required, additional DLP protection can be configured.</span></span>

<span data-ttu-id="d8170-p108">В таблице ниже приведены три конфигурации, которые позволяют повысить уровень защиты от потери данных. Первая конфигурация (информирование) может использоваться в качестве отправной точки для обеспечения минимального уровня защиты в соответствии с регламентом GDPR.</span><span class="sxs-lookup"><span data-stu-id="d8170-p108">The following table lists three configurations of increasing protection using DLP. The first configuration, awareness, can be used as a starting point and minimum level of protection for GDPR.</span></span>

### <a name="example-protection-levels-that-can-be-configured-with-dlp-policies-and-used-for-gdpr-compliance"></a><span data-ttu-id="d8170-136">Примеры уровней защиты, которые настраиваются с помощью политик защиты от потери данных и используются для соблюдения регламента GDPR</span><span class="sxs-lookup"><span data-stu-id="d8170-136">Example protection levels that can be configured with DLP policies and used for GDPR compliance</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d8170-137"><strong>Уровень защиты</strong></span><span class="sxs-lookup"><span data-stu-id="d8170-137"><strong>Protection level</strong></span></span></th>
<th align="left"><span data-ttu-id="d8170-138"><strong>Настройка защиты от потери данных для документов с персональными данными, связанными с субъектами данных ЕС</strong></span><span class="sxs-lookup"><span data-stu-id="d8170-138"><strong>DLP configuration for documents with personal information related to EU data subjects</strong></span></span></th>
<th align="left"><span data-ttu-id="d8170-139"><strong>Преимущества и риски</strong></span><span class="sxs-lookup"><span data-stu-id="d8170-139"><strong>Benefits and risks</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="d8170-140">Информирование</span><span class="sxs-lookup"><span data-stu-id="d8170-140">Awareness</span></span></td>
<td align="left"><p><span data-ttu-id="d8170-141">Отправка ответственным за обеспечение соответствия требованиям уведомлений по электронной почте при обнаружении таких данных в документах в SharePoint Online и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d8170-141">Send email notifications to compliance teams when this data is found in documents in SharePoint Online and OneDrive for Business.</span></span></p>
<p><span data-ttu-id="d8170-142">Настройка и отображение подсказок политик в SharePoint и OneDrive для бизнеса при доступе к документам, содержащим эти данные.</span><span class="sxs-lookup"><span data-stu-id="d8170-142">Customize and display Policy Tips to employees in SharePoint and OneDrive for Business when accessing documents containing this data.</span></span></p>
<p><span data-ttu-id="d8170-143">Обнаружение случаев предоставления общего доступа к этим данным и создание соответствующих отчетов.</span><span class="sxs-lookup"><span data-stu-id="d8170-143">Detect and report when this data is being shared.</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8170-144">Повышение осведомленности команд и сотрудников, ответственных за обеспечение соответствия требованиям, о местах хранения этих данных.</span><span class="sxs-lookup"><span data-stu-id="d8170-144">Raise awareness with compliance teams and employees about where this data is stored.</span></span></p>
<p><span data-ttu-id="d8170-145">Ознакомление сотрудников с корпоративной политикой по работе с документами, содержащими эти данные.</span><span class="sxs-lookup"><span data-stu-id="d8170-145">Educate employees on corporate policy for handling documents containing this data.</span></span></p>
<p><span data-ttu-id="d8170-146">Сотрудники могут предоставлять внутренний и внешний доступ к этим данным.</span><span class="sxs-lookup"><span data-stu-id="d8170-146">Does not prevent employees from sharing this data internally or externally.</span></span></p>
<p><span data-ttu-id="d8170-147">Вы можете просмотреть отчеты по защите от потери данных для общих данных и решить, нужно ли повысить уровень защиты.</span><span class="sxs-lookup"><span data-stu-id="d8170-147">You can review DLP reports for shared data and decide if you need to increase the protection.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="d8170-148">Предотвращение внешнего общего доступа</span><span class="sxs-lookup"><span data-stu-id="d8170-148">Prevent external sharing</span></span></td>
<td align="left"><p><span data-ttu-id="d8170-149">Ограничение доступа в SharePoint Online и OneDrive для бизнеса к документам, которые содержат эти данные, если доступ к этому содержимому предоставляется внешним пользователям.</span><span class="sxs-lookup"><span data-stu-id="d8170-149">Restrict access to documents that contain this data in SharePoint Online and OneDrive for Business when that content is shared with external users.</span></span></p>
<p><span data-ttu-id="d8170-150">Запрет отправки внешним получателям сообщений электронной почты с документами, которые содержат эти данные.</span><span class="sxs-lookup"><span data-stu-id="d8170-150">Prevent sending emails with documents that contain this data to external recipients.</span></span></p>
<p><span data-ttu-id="d8170-151">Обнаружение случаев предоставления общего доступа к этим данным и создание соответствующих отчетов.</span><span class="sxs-lookup"><span data-stu-id="d8170-151">Detect and report when this data is being shared.</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8170-152">Запрет внешнего общего доступа к таким данным и разрешение на работу с ними в пределах организации.</span><span class="sxs-lookup"><span data-stu-id="d8170-152">Prevents external sharing of this data while allowing for employees to work with this data internally.</span></span></p>
<p><span data-ttu-id="d8170-153">Вы можете просмотреть отчеты по защите от потери данных для данных, к которым предоставляется общий доступ в пределах организации, и решить, нужно ли повысить уровень защиты.</span><span class="sxs-lookup"><span data-stu-id="d8170-153">You can review DLP reports for internally shared data and decide if you need to increase this protection.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="d8170-154">Предотвращение внутреннего и внешнего общего доступа</span><span class="sxs-lookup"><span data-stu-id="d8170-154">Prevent internal and external sharing</span></span></td>
<td align="left"><p><span data-ttu-id="d8170-155">Ограничение доступа в SharePoint Online и OneDrive для бизнеса к документам, которые содержат эти данные, если к этому содержимому предоставляется общий доступ в организации или за ее пределами.</span><span class="sxs-lookup"><span data-stu-id="d8170-155">Restrict access to documents that contain this data in SharePoint Online and OneDrive for Business when that content is shared internally or externally.</span></span></p>
<p><span data-ttu-id="d8170-156">Запрет отправки внутренним и внешним получателям сообщений электронной почты, содержащих эти данные.</span><span class="sxs-lookup"><span data-stu-id="d8170-156">Prevent sending emails that contain this data to both internal and external recipients.</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8170-157">Предотвращение внутреннего и внешнего общего доступа к таким данным.</span><span class="sxs-lookup"><span data-stu-id="d8170-157">Prevents internal and external sharing of this data.</span></span></p>
<p><span data-ttu-id="d8170-158">Возможно, сотрудники не смогут выполнять задачи, для которых требуются эти данные.</span><span class="sxs-lookup"><span data-stu-id="d8170-158">Employees might not be able to complete tasks that require working with this data.</span></span></p>
<p><span data-ttu-id="d8170-159">Вы можете просмотреть отчеты по защите от потери данных для данных, к которым предоставляется общий доступ в организации или за ее пределами, и решить, требуется ли обучение пользователей.</span><span class="sxs-lookup"><span data-stu-id="d8170-159">You can review DLP reports for internally or externally shared data and decide if end-user training is needed.</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d8170-p109">Примечание. Повышение уровней защиты в некоторых случаях приводит к ограничению доступа пользователей к информации, что может затронуть их производительность или способность выполнять повседневные задачи. Повышение уровней защиты путем внедрения политик, которые влияют на сотрудников, обычно сопровождается обучением пользователей, в ходе которого они знакомятся с новыми политиками безопасности и процедурами, помогающими эффективно работать в более безопасной среде.</span><span class="sxs-lookup"><span data-stu-id="d8170-p109">Note: As the levels of protection increase, the ability of users to access information will decrease in some cases, and could potentially impact their productivity or ability to complete day to day tasks. Increasing protection levels by implementing policies that impact employees is typically accompanied by end-user training, educating users on new security policies and procedures to help them continue to be productive in a more secure environment.</span></span>

### <a name="example-dlp-policy-for-gdpr--awareness"></a><span data-ttu-id="d8170-162">Пример политики защиты от потери данных для соблюдения регламента GDPR — информирование</span><span class="sxs-lookup"><span data-stu-id="d8170-162">Example DLP policy for GDPR — Awareness</span></span> 

<span data-ttu-id="d8170-163">Имя. Информирование о персональных данных, подпадающих под действие регламента GDPR.</span><span class="sxs-lookup"><span data-stu-id="d8170-163">Name: Awareness for personal data that is subject to GDPR.</span></span>

<span data-ttu-id="d8170-164">Описание. Отображение подсказок политик для сотрудников, уведомление ответственных за обеспечение соответствия требованиям о наличии этих данных в документах в SharePoint Online и OneDrive для бизнеса, обнаружение случаев предоставления общего доступа к этим данным за пределами организации и создание соответствующих отчетов.</span><span class="sxs-lookup"><span data-stu-id="d8170-164">Description: Display policy tips to employees, notify compliance teams when this data is found in documents in SharePoint Online and OneDrive for Business, detect and report when this data is being shared outside your organization.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d8170-165"><strong>Элемент управления</strong></span><span class="sxs-lookup"><span data-stu-id="d8170-165"><strong>Control</strong></span></span></th>
<th align="left"><span data-ttu-id="d8170-166"><strong>Настройки</strong></span><span class="sxs-lookup"><span data-stu-id="d8170-166"><strong>Settings</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="d8170-167">Выбор информации для защиты</span><span class="sxs-lookup"><span data-stu-id="d8170-167">Choose information to protect</span></span></td>
<td align="left"><span data-ttu-id="d8170-168">Выберите шаблон специальной политики.</span><span class="sxs-lookup"><span data-stu-id="d8170-168">Select a Custom policy template.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="d8170-169">Расположения</span><span class="sxs-lookup"><span data-stu-id="d8170-169">Locations</span></span></td>
<td align="left"><span data-ttu-id="d8170-170">Все расположения в Office 365</span><span class="sxs-lookup"><span data-stu-id="d8170-170">All locations in Office 365</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="d8170-171">Поиск определенного содержимого</span><span class="sxs-lookup"><span data-stu-id="d8170-171">Find content that contains</span></span></td>
<td align="left"><span data-ttu-id="d8170-172">Нажмите кнопку "Изменить" и добавьте все типы конфиденциальной информации, подобранные для вашей среды.</span><span class="sxs-lookup"><span data-stu-id="d8170-172">Click ‘Edit’ and add all the sensitive information types you curated for your environment.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="d8170-173">Обнаружение случаев предоставления общего доступа к этому содержимому</span><span class="sxs-lookup"><span data-stu-id="d8170-173">Detect when this content is shared</span></span></td>
<td align="left"><span data-ttu-id="d8170-174">Установите этот флажок и выберите "Пользователям за пределами моей организации".</span><span class="sxs-lookup"><span data-stu-id="d8170-174">Check this box and select ‘with people outside my organization.’</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="d8170-175">Уведомление пользователей о соответствии содержимого параметрам политики</span><span class="sxs-lookup"><span data-stu-id="d8170-175">Notify users when content matches the policy settings</span></span></td>
<td align="left"><p><span data-ttu-id="d8170-176">Установите этот флажок ("Отображать подсказки политик пользователям и отправлять уведомление по электронной почте").</span><span class="sxs-lookup"><span data-stu-id="d8170-176">Check this box (“Show policy tips to users and send them an email notification.”)</span></span></p>
<p><span data-ttu-id="d8170-p110">Щелкните "Настройка подсказки и уведомления по электронной почте" и обновите эти элементы в своей среде. Описание стандартных уведомлений см. в статье <a href="https://support.office.com/article/Send-email-notifications-and-show-policy-tips-for-DLP-policies-87496bc5-9601-4473-8021-cb05c71369c1?ui=en-US&amp;rs=en-US&amp;ad=US">Отправка уведомлений и отображение подсказок для политик защиты от потери данных</a>.</span><span class="sxs-lookup"><span data-stu-id="d8170-p110">Click ‘Customize the tip and email’ and update these for your environment. See the default notifications in this article: <a href="https://support.office.com/article/Send-email-notifications-and-show-policy-tips-for-DLP-policies-87496bc5-9601-4473-8021-cb05c71369c1?ui=en-US&amp;rs=en-US&amp;ad=US">Send email notifications and show policy tips for DLP policies</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="d8170-179">Обнаружение случаев одновременного предоставления общего доступа к конфиденциальной информации в определенном объеме</span><span class="sxs-lookup"><span data-stu-id="d8170-179">Detect when a specific amount of sensitive info is being shared at one time</span></span></td>
<td align="left"><p><span data-ttu-id="d8170-180">"Определять, когда предоставляемый контент содержит: хотя бы такое количество экземпляров одного типа конфиденциальных данных: ____": укажите значение 1.</span><span class="sxs-lookup"><span data-stu-id="d8170-180">‘Detect when content that’s being shared contains: At least ____ instances of the same sensitive info type’ — Set this to 1.</span></span></p>
<p><span data-ttu-id="d8170-p111">"Отправлять отчеты об инцидентах по электронной почте": установите этот флажок. Щелкните "Выберите содержимое отчета и получателей". Обязательно добавьте ответственных за обеспечение соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="d8170-p111">‘Send incident reports in email’ — check this box. Click ‘Choose what to include in the report and who receives it.’ Be sure to add your compliance team.</span></span></p>
<p><span data-ttu-id="d8170-184">"Ограничить доступ к содержимому и переопределить политику": снимите этот флажок, чтобы получать уведомления о конфиденциальной информации, не ограничивая доступ к ней для пользователей.</span><span class="sxs-lookup"><span data-stu-id="d8170-184">‘Restrict who can access the content and override the policy’ — clear this checkbox to receive notifications about sensitive information without preventing users from access that information.</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d8170-185">Все расположения включают:</span><span class="sxs-lookup"><span data-stu-id="d8170-185">All locations includes:</span></span>

- <span data-ttu-id="d8170-186">SharePoint Online;</span><span class="sxs-lookup"><span data-stu-id="d8170-186">SharePoint Online</span></span>

- <span data-ttu-id="d8170-187">учетные записи OneDrive для бизнеса;</span><span class="sxs-lookup"><span data-stu-id="d8170-187">OneDrive for Business accounts</span></span>

- <span data-ttu-id="d8170-188">Почтовые ящики Exchange</span><span class="sxs-lookup"><span data-stu-id="d8170-188">Exchange mailboxes</span></span>

<span data-ttu-id="d8170-189">Так как веб-часть "Поиск контента" сейчас не позволяет проверить типы конфиденциальной информации с помощью электронной почты, рекомендуется создать отдельные политики для Exchange с подмножеством типов конфиденциальной информации в каждой политике и отследить развертывание этих политик.</span><span class="sxs-lookup"><span data-stu-id="d8170-189">Because Content Search doesn’t currently let you test sensitive information types with email, consider creating separate policies for Exchange with a subset of sensitive information types in each policy and monitoring the rollout of these policies.</span></span>

## <a name="additional-protection-you-can-apply-to-protect-personal-data-in-office-365"></a><span data-ttu-id="d8170-190">Дополнительная защита персональных данных в Office 365</span><span class="sxs-lookup"><span data-stu-id="d8170-190">Additional protection you can apply to protect personal data in Office 365</span></span>

<span data-ttu-id="d8170-p112">Типы конфиденциальной информации, метки и политики защиты от потери данных помогают определять документы, содержащие определенные данные, и применять к ним защиту. Тем не менее эти средства защиты зависят от соответствующих разрешений на доступ к данным, пользователей с нескомпрометированными учетными записями и работоспособных устройств.</span><span class="sxs-lookup"><span data-stu-id="d8170-p112">Sensitive information types, labels, and data loss protection policies help you identify documents containing specific data and apply protection. However, these protections depend on appropriate permissions being set for access to data, users with accounts that aren't compromised, and devices that are healthy.</span></span>

<span data-ttu-id="d8170-193">Ниже показаны дополнительные категории защиты, которые можно применить для ограничения доступа к персональным данным.</span><span class="sxs-lookup"><span data-stu-id="d8170-193">The following illustration details additional protection you can apply to protect access to personal data.</span></span>

![Дополнительная защита для ограничения доступа к персональным данным](Media/Apply-protection-to-personal-data-in-Office-365-image2.png)

<span data-ttu-id="d8170-195">Для поддержки специальных возможностей данные, изображенные на рисунке, также приведены в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="d8170-195">For accessibility, the following table provides the same information in the illustration.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d8170-196"><strong>Область защиты</strong></span><span class="sxs-lookup"><span data-stu-id="d8170-196"><strong>Scope of protection</strong></span></span></th>
<th align="left"><span data-ttu-id="d8170-197"><strong>Возможности</strong></span><span class="sxs-lookup"><span data-stu-id="d8170-197"><strong>Capabilities</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="d8170-198">Защита на уровне документов и электронной почты (в том числе передаваемых сообщений; сейчас защита не применяется к неактивным данным в почтовых ящиках)</span><span class="sxs-lookup"><span data-stu-id="d8170-198">Document and email-level protection (includes mail in transit, but not currently mailboxes at rest)</span></span></td>
<td align="left"><p><span data-ttu-id="d8170-199">Типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="d8170-199">Sensitive information types</span></span></p>
<p><span data-ttu-id="d8170-200">Метки Office</span><span class="sxs-lookup"><span data-stu-id="d8170-200">Office labels</span></span></p>
<p><span data-ttu-id="d8170-201">Политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="d8170-201">Data loss prevention policies</span></span></p>
<p><span data-ttu-id="d8170-202">Шифрование сообщений Office 365 для электронной почты</span><span class="sxs-lookup"><span data-stu-id="d8170-202">Office 365 Message Encryption for email</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="d8170-203">Защита на уровне сайта и библиотеки (в том числе сайтов SharePoint Online и OneDrive для бизнеса)</span><span class="sxs-lookup"><span data-stu-id="d8170-203">Site and library-level protection (includes SharePoint Online and OneDrive for Business sites)</span></span></td>
<td align="left"><p><span data-ttu-id="d8170-204">Разрешения для сайтов и библиотек SharePoint Online и OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="d8170-204">Permissions for SharePoint Online and OneDrive for Business sites and libraries</span></span></p>
<p><span data-ttu-id="d8170-205">Политики внешнего общего доступа для SharePoint Online и OneDrive для бизнеса (на уровне сайтов)</span><span class="sxs-lookup"><span data-stu-id="d8170-205">External sharing policies for SharePoint Online and OneDrive for Business (site-level)</span></span></p>
<p><span data-ttu-id="d8170-206">Политики доступа к устройствам на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="d8170-206">Site-level device access policies</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="d8170-207">Защита при доступе к службам (включая доступ ко всем службам в Office 365)</span><span class="sxs-lookup"><span data-stu-id="d8170-207">Service access protection (includes access to all services in Office 365)</span></span></td>
<td align="left"><p><span data-ttu-id="d8170-208">Защита идентификации и доступа к устройствам в наборе Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="d8170-208">Identity and device access protection in Enterprise Mobility + Security (EMS) suite</span></span></p>
<p><span data-ttu-id="d8170-209">управление привилегированным доступом;</span><span class="sxs-lookup"><span data-stu-id="d8170-209">Privileged access management</span></span></p>
<p><span data-ttu-id="d8170-210">возможности защиты Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d8170-210">Windows 10 security capabilities</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d8170-211">Дополнительные сведения о каждой из этих категорий защиты приведены далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="d8170-211">The rest of this article provides more information on each of these categories of protection.</span></span>

### <a name="capabilities-that-are-ok-to-use-with-gdpr"></a><span data-ttu-id="d8170-212">Возможности, совместимые с регламентом GDPR</span><span class="sxs-lookup"><span data-stu-id="d8170-212">Capabilities that are OK to use with GDPR</span></span>

<span data-ttu-id="d8170-p113">В среде, настроенной на соблюдение регламента GDPR, можно использовать приведенные ниже возможности. Они не являются обязательными для обеспечения соответствия требованиям регламента GDPR, но их можно применять без негативного воздействия на вашу способность выявлять, защищать и отслеживать данные, связанные с соблюдением регламента GDPR, а также создавать соответствующие отчеты.</span><span class="sxs-lookup"><span data-stu-id="d8170-p113">You can use the following capabilities in an environment configured for GDPR compliance. These capabilities are not necessary for GDPR compliance, but they can be used without adversely affecting your ability to discover, protect, monitor, and report on data related to GDPR compliance.</span></span>

<span data-ttu-id="d8170-p114">Ключ клиента: позволяет клиентам обеспечить и сохранить контроль над ключами шифрования, которые используются для шифрования неактивных данных в среде Office 365. Рекомендуется только для клиентов, которым требуется управлять собственными ключами шифрования для соблюдения нормативных требований.</span><span class="sxs-lookup"><span data-stu-id="d8170-p114">Customer Key — Allows customers to provide and retain control over the encryption keys that are used to encrypt data at rest within Office 365. Recommended only for customers with a regulatory need to manage their own encryption keys.</span></span>

<span data-ttu-id="d8170-p115">Защищенное хранилище: позволяет вам управлять доступом сотрудника службы поддержки Майкрософт к вашим данным, если это требуется для устранения технических проблем в отдельных случаях. Вы можете предоставить сотруднику службы поддержки доступ к своим данным или отказать в нем. При каждом запросе указывается время окончания срока действия.</span><span class="sxs-lookup"><span data-stu-id="d8170-p115">Customer Lockbox — Customer lockbox allows you to control how a Microsoft support engineer accesses your data, if needed, to fix a technical issue on a case by case basis. You can control whether to give the support engineer access to your data or not. An expiration time is provided with each request.</span></span>

## <a name="site-and-library-level-protection"></a><span data-ttu-id="d8170-220">Защита на уровне сайта и библиотеки</span><span class="sxs-lookup"><span data-stu-id="d8170-220">Site and library-level protection</span></span>

### <a name="permissions-for-sharepoint-and-onedrive-for-business-libraries"></a><span data-ttu-id="d8170-221">Разрешения для библиотек SharePoint и OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="d8170-221">Permissions for SharePoint and OneDrive for Business libraries</span></span>

<span data-ttu-id="d8170-p116">Используйте разрешения в SharePoint, чтобы предоставить пользователям доступ к сайту или его содержимому или отказать в нем. Добавьте отдельных пользователей или группы Azure Active Directory в стандартные группы SharePoint. Кроме того, можно создать настраиваемую группу для более точного управления.</span><span class="sxs-lookup"><span data-stu-id="d8170-p116">Use permissions in SharePoint to provide or restrict user access to the site or its contents. Add individual users or Azure Active Directory groups to the default SharePoint groups. Or, create a custom group for finer-grain control.</span></span>

![Уровни разрешений от "Полный доступ" до "Только просмотр"](Media/Apply-protection-to-personal-data-in-Office-365-image3.png)

<span data-ttu-id="d8170-p117">На этом рисунке изображены уровни разрешений от "Полный доступ" до "Только просмотр". Аналогичные сведения приведены в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="d8170-p117">The illustration plots permission levels from Full control to View Only. The following table includes the same information.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d8170-228"><strong>Полный доступ</strong></span><span class="sxs-lookup"><span data-stu-id="d8170-228"><strong>Full Control</strong></span></span></th>
<th align="left"><span data-ttu-id="d8170-229"><strong>Разработка</strong></span><span class="sxs-lookup"><span data-stu-id="d8170-229"><strong>Design</strong></span></span></th>
<th align="left"><span data-ttu-id="d8170-230"><strong>Правка</strong></span><span class="sxs-lookup"><span data-stu-id="d8170-230"><strong>Edit</strong></span></span></th>
<th align="left"><span data-ttu-id="d8170-231"><strong>Участие</strong></span><span class="sxs-lookup"><span data-stu-id="d8170-231"><strong>Contribute</strong></span></span></th>
<th align="left"><span data-ttu-id="d8170-232"><strong>Чтение</strong></span><span class="sxs-lookup"><span data-stu-id="d8170-232"><strong>Read</strong></span></span></th>
<th align="left"><span data-ttu-id="d8170-233"><strong>Только просмотр</strong></span><span class="sxs-lookup"><span data-stu-id="d8170-233"><strong>View Only</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"></td>
<td align="left"><span data-ttu-id="d8170-234">Участие + утверждение и настройка</span><span class="sxs-lookup"><span data-stu-id="d8170-234">Contribute + approve and customize</span></span></td>
<td align="left"><span data-ttu-id="d8170-235">Участие + добавление, правка и удаление списков (а не только элементов списков)</span><span class="sxs-lookup"><span data-stu-id="d8170-235">Contribute + add, edit, and delete lists (not just list items)</span></span></td>
<td align="left"><span data-ttu-id="d8170-236">Просмотр, добавление, обновление, удаление элементов списков и документов</span><span class="sxs-lookup"><span data-stu-id="d8170-236">View, add, update, delete list items and documents</span></span></td>
<td align="left"><span data-ttu-id="d8170-237">Просмотр и скачивание</span><span class="sxs-lookup"><span data-stu-id="d8170-237">View and download</span></span></td>
<td align="left"><span data-ttu-id="d8170-238">Просмотр без скачивания</span><span class="sxs-lookup"><span data-stu-id="d8170-238">View, no download</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d8170-239">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="d8170-239">More information:</span></span>

-   [<span data-ttu-id="d8170-240">Уровни разрешений в SharePoint</span><span class="sxs-lookup"><span data-stu-id="d8170-240">Understanding permission levels in SharePoint</span></span>](https://support.office.com/en-US/article/Understanding-permission-levels-in-SharePoint-87ecbb0e-6550-491a-8826-c075e4859848)

-   [<span data-ttu-id="d8170-241">Общие сведения о группах SharePoint</span><span class="sxs-lookup"><span data-stu-id="d8170-241">Understanding SharePoint groups</span></span>](https://support.office.com/en-US/article/Understanding-SharePoint-groups-94d9b261-161e-4ace-829e-eca1c8cd2eb8)

### <a name="external-sharing-policies-for-sharepoint-and-onedrive-for-business-libraries"></a><span data-ttu-id="d8170-242">Политики внешнего общего доступа для библиотек SharePoint и OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="d8170-242">External sharing policies for SharePoint and OneDrive for Business libraries</span></span>

<span data-ttu-id="d8170-p118">Во многих организациях разрешен внешний общий доступ для поддержки совместной работы. Узнайте, как настроить параметры для всего клиента. Затем проверьте параметры внешнего доступа для сайтов, которые содержат персональные данные.</span><span class="sxs-lookup"><span data-stu-id="d8170-p118">Many organizations allow external sharing to support collaboration. Find out how your tenant-wide settings are configured. Then review the external sharing settings for sites that contain personal data.</span></span>

<span data-ttu-id="d8170-246">Внешний пользователь — это пользователь за пределами вашей организации, получивший доступ к вашим сайтам и документам SharePoint Online, но у которого нет лицензии на вашу подписку на SharePoint Online или Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="d8170-246">An external user is someone outside of your organization who is invited to access your SharePoint Online sites and documents but doesn't have a license for your SharePoint Online or Microsoft Office 365 subscription.</span></span>

<span data-ttu-id="d8170-247">Политики внешнего общего доступа применяются к SharePoint Online и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d8170-247">External sharing policies apply to both SharePoint Online and OneDrive for Business.</span></span>

-   <span data-ttu-id="d8170-248">Настраивать политики общего доступа может только администратор SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d8170-248">You must be a SharePoint Online admin to configure sharing policies.</span></span>

-   <span data-ttu-id="d8170-249">Предоставить общий доступ к сайту или документу внешним пользователям может только владелец сайта или пользователь с разрешениями на полный доступ.</span><span class="sxs-lookup"><span data-stu-id="d8170-249">You must be a Site Owner or have full control permissions to share a site or document with external users.</span></span>

<span data-ttu-id="d8170-250">В таблице ниже перечислены проверки, которые вы можете настроить.</span><span class="sxs-lookup"><span data-stu-id="d8170-250">The following table summarizes the controls you can configure.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d8170-251"><strong>Категория проверки</strong></span><span class="sxs-lookup"><span data-stu-id="d8170-251"><strong>Control category</strong></span></span></th>
<th align="left"><span data-ttu-id="d8170-252"><strong>Параметры</strong></span><span class="sxs-lookup"><span data-stu-id="d8170-252"><strong>Options</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="d8170-253">Тип общего доступа</span><span class="sxs-lookup"><span data-stu-id="d8170-253">Type of sharing</span></span></td>
<td align="left"><p><span data-ttu-id="d8170-254">Не разрешать общий доступ за пределами организации (можно задать для отдельных семейств веб-сайтов)</span><span class="sxs-lookup"><span data-stu-id="d8170-254">Don’t allow sharing outside your organization (can be set for individual site collections)</span></span></p>
<p><span data-ttu-id="d8170-255">Разрешить общий доступ только внешним пользователям, которые прошли проверку подлинности (разрешать доступ для новых или только существующих пользователей, можно задать для отдельных семейств веб-сайтов)\*</span><span class="sxs-lookup"><span data-stu-id="d8170-255">Allow sharing to authenticated external users only (allow new or limit to existing, can be set for individual site collections)\*</span></span></p>
<p><span data-ttu-id="d8170-256">Разрешить общий доступ внешним пользователям со ссылкой для анонимного доступа (можно задать для отдельных семейств веб-сайтов)</span><span class="sxs-lookup"><span data-stu-id="d8170-256">Allow sharing to external users with an anonymous access link (can be set for individual site collections)</span></span></p>
<p><span data-ttu-id="d8170-257">Ограничить внешний общий доступ с помощью доменов (список разрешенных и запрещенных)</span><span class="sxs-lookup"><span data-stu-id="d8170-257">Limit external sharing using domains (allow and deny list)</span></span></p>
<p><span data-ttu-id="d8170-258">Выбрать стандартный тип ссылки (анонимный доступ, общий доступ в пределах компании или ограниченный доступ)</span><span class="sxs-lookup"><span data-stu-id="d8170-258">Choose the default link type (anonymous, company shareable, or restricted)</span></span></p>
</td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="d8170-259">Возможности, предоставленные внешним пользователям</span><span class="sxs-lookup"><span data-stu-id="d8170-259">What external users can do</span></span></td>
<td align="left"><p><span data-ttu-id="d8170-260">Запретить внешним пользователям предоставлять общий доступ к файлам, папкам и сайтам, которые им не принадлежат</span><span class="sxs-lookup"><span data-stu-id="d8170-260">Prevent external users from sharing files, folders, sites they don’t own</span></span></p>
<p><span data-ttu-id="d8170-261">Требовать, чтобы внешние пользователи принимали приглашения на общий доступ в учетной записи, на которую были отправлены эти приглашения</span><span class="sxs-lookup"><span data-stu-id="d8170-261">Require external users to accept sharing invitations with the same account the invitation was sent to</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="d8170-262">Уведомления</span><span class="sxs-lookup"><span data-stu-id="d8170-262">Notifications</span></span></td>
<td align="left"><p><span data-ttu-id="d8170-p119">Сейчас доступны только в OneDrive для бизнеса. Пользователи получают уведомления, когда:</span><span class="sxs-lookup"><span data-stu-id="d8170-p119">Currently only available in OneDrive for Business. Notify owners when:</span></span></p>
- <p><span data-ttu-id="d8170-265">пользователи отправляют дополнительным внешним пользователям приглашения на доступ к общим файлам;</span><span class="sxs-lookup"><span data-stu-id="d8170-265">Users invite additional external users to shared files</span></span></p>
- <p><span data-ttu-id="d8170-266">внешние пользователи принимают приглашения на доступ к файлам;</span><span class="sxs-lookup"><span data-stu-id="d8170-266">External users accept invitations to access files</span></span></p>
- <p><span data-ttu-id="d8170-267">создается или изменяется ссылка для анонимного доступа.</span><span class="sxs-lookup"><span data-stu-id="d8170-267">An anonymous access link is created or changed</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d8170-268">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="d8170-268">More information:</span></span>

-   [<span data-ttu-id="d8170-269">Управление внешним доступом для среды SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d8170-269">Manage external sharing for your SharePoint Online environment</span></span>](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&rs=en-US&ad=US)

-   [<span data-ttu-id="d8170-270">Предоставление общего доступа к сайтам и документам пользователям за пределами организации</span><span class="sxs-lookup"><span data-stu-id="d8170-270">Share sites or documents with people outside your organization</span></span>](https://support.office.com/en-US/article/Share-sites-or-documents-with-people-outside-your-organization-80e49744-e30f-44db-8d51-16661b1d4232)

### <a name="site-level-device-access-policies"></a><span data-ttu-id="d8170-271">Политики доступа к устройствам на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="d8170-271">Site-level device access policies</span></span>

<span data-ttu-id="d8170-p120">В SharePoint Online и OneDrive для бизнеса можно настроить политики доступа к устройствам на уровне сайта. Это позволяет настроить дополнительные параметры защиты для сайтов с конфиденциальными данными.</span><span class="sxs-lookup"><span data-stu-id="d8170-p120">SharePoint Online and OneDrive for Business let you configure device access policies at the site level. This lets you configure more protection for sites with sensitive data.</span></span>

<span data-ttu-id="d8170-274">Настраивая политики доступа к устройствам на уровне сайта, обязательно согласовывайте их с политиками на уровне клиента, а также с политиками доступа, настроенными в Azure Active Directory, Intune и Intune App Management.</span><span class="sxs-lookup"><span data-stu-id="d8170-274">If you configure site-level device access policies, be sure to coordinate these with tenant-level policies and also with access policies that are configured in Azure Active Directory, Intune, and Intune App Management.</span></span>

<span data-ttu-id="d8170-p121">Политики доступа к устройствам в SharePoint и OneDrive для бизнеса требуют наличия вспомогательных политик в Azure Active Directory и Microsoft Intune в зависимости от внедряемого сценария. В таблице ниже перечислены цели, которых можно достичь с помощью политик доступа к устройствам, а также приведены продукты, требующие вспомогательных политик.</span><span class="sxs-lookup"><span data-stu-id="d8170-p121">Device access policies for SharePoint and OneDrive for Business require supporting policies in Azure Active Directory and Microsoft Intune depending on the scenario you're implementing. The following table summarizes objectives you can achieve with device access policies and indicates which products require supporting policies.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="d8170-277">Разрешить доступ только с определенных IP-адресов</span><span class="sxs-lookup"><span data-stu-id="d8170-277">Only allow access from specific IP address locations</span></span></th>
<th align="left"><span data-ttu-id="d8170-278">Запретить пользователям скачивать файлы на устройства, которые не присоединены к домену</span><span class="sxs-lookup"><span data-stu-id="d8170-278">Prevent users from downloading files to non-domain joined devices</span></span></th>
<th align="left"><span data-ttu-id="d8170-279">Блокировать доступ на устройствах, которые не присоединены к домену</span><span class="sxs-lookup"><span data-stu-id="d8170-279">Block access on non-domain joined devices</span></span></th>
<th align="left"><span data-ttu-id="d8170-280">Запретить пользователям скачивать файлы на устройства, которые не соответствуют требованиям</span><span class="sxs-lookup"><span data-stu-id="d8170-280">Prevent users from downloading files to non-compliant devices</span></span></th>
<th align="left"><span data-ttu-id="d8170-281">Блокировать доступ на устройствах, которые не соответствуют требованиям</span><span class="sxs-lookup"><span data-stu-id="d8170-281">Block access on non-compliant devices</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="d8170-282">Центр администрирования SharePoint</span><span class="sxs-lookup"><span data-stu-id="d8170-282">SharePoint admin center</span></span></td>
<td align="left"><span data-ttu-id="d8170-283">Да</span><span class="sxs-lookup"><span data-stu-id="d8170-283">Yes</span></span></td>
<td align="left"><span data-ttu-id="d8170-284">Да</span><span class="sxs-lookup"><span data-stu-id="d8170-284">Yes</span></span></td>
<td align="left"><span data-ttu-id="d8170-285">Да</span><span class="sxs-lookup"><span data-stu-id="d8170-285">Yes</span></span></td>
<td align="left"><span data-ttu-id="d8170-286">Да</span><span class="sxs-lookup"><span data-stu-id="d8170-286">Yes</span></span></td>
<td align="left"><span data-ttu-id="d8170-287">Да</span><span class="sxs-lookup"><span data-stu-id="d8170-287">Yes</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="d8170-288">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d8170-288">Azure Active Directory</span></span></td>
<td align="left"></td>
<td align="left"><span data-ttu-id="d8170-289">Да</span><span class="sxs-lookup"><span data-stu-id="d8170-289">Yes</span></span></td>
<td align="left"><span data-ttu-id="d8170-290">Да</span><span class="sxs-lookup"><span data-stu-id="d8170-290">Yes</span></span></td>
<td align="left"><span data-ttu-id="d8170-291">Да</span><span class="sxs-lookup"><span data-stu-id="d8170-291">Yes</span></span></td>
<td align="left"><span data-ttu-id="d8170-292">ДА</span><span class="sxs-lookup"><span data-stu-id="d8170-292">Yes</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="d8170-293">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d8170-293">Microsoft Intune</span></span></td>
<td align="left"></td>
<td align="left"></td>
<td align="left"></td>
<td align="left"><span data-ttu-id="d8170-294">ДА</span><span class="sxs-lookup"><span data-stu-id="d8170-294">Yes</span></span></td>
<td align="left"><span data-ttu-id="d8170-295">Да</span><span class="sxs-lookup"><span data-stu-id="d8170-295">Yes</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d8170-296">Дополнительные сведения: [Центр администрирования SharePoint Online. Управление доступом с неуправляемых устройств](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="d8170-296">More information: [SharePoint Online admin center: Control access from unmanaged devices](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&rs=en-US&ad=US).</span></span>

## <a name="service-access-protection-for-identities-and-devices"></a><span data-ttu-id="d8170-297">Защита при доступе к службам для пользователей и устройств</span><span class="sxs-lookup"><span data-stu-id="d8170-297">Service access protection for identities and devices</span></span>

<span data-ttu-id="d8170-p122">Корпорация Майкрософт рекомендует настроить защиту для пользователей и устройств, которые получают доступ к службе. Параметры защиты доступа к службам Office 365 также можно использовать для защиты доступа к другим службам SaaS, PaaS и даже приложениям в других облачных службах.</span><span class="sxs-lookup"><span data-stu-id="d8170-p122">Microsoft recommends you configure protection for identities and devices that access the service. The work you put into protecting access to Office 365 services can also be used to protect access to other SaaS services, PaaS services, and even apps in other cloud providers.</span></span>

<span data-ttu-id="d8170-300">Защита доступа для пользователей и устройств обеспечивает базовую безопасность, гарантируя защиту удостоверений и устройств, а также изолирование и безопасность данных организации, расположенных на устройствах.</span><span class="sxs-lookup"><span data-stu-id="d8170-300">Access protection for identities and devices provides a baseline of protection to ensure that identities aren't compromised, devices are safe, and organization data that is accessed on devices is isolated and protected.</span></span>

<span data-ttu-id="d8170-301">Начальные рекомендации и указания по настройке см. в статье [Руководство по безопасности (Майкрософт) для политических кампаний, некоммерческих и других динамических организаций](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance).</span><span class="sxs-lookup"><span data-stu-id="d8170-301">For starting point recommendations and configuration guidance, see [Microsoft security guidance for political campaigns, nonprofits, and other agile organizations](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance).</span></span>

<span data-ttu-id="d8170-302">Инструкции для сред с гибридными удостоверениями и AD FS см. в статье, посвященной [рекомендуемым политикам и конфигурациям безопасности](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance).</span><span class="sxs-lookup"><span data-stu-id="d8170-302">For hybrid identity environments with AD FS, see [Recommended security policies and configurations](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance).</span></span>

<span data-ttu-id="d8170-p123">Ниже показано, как связаны между собой облачные службы (SaaS, PaaS), типы учетных записей (учетные записи доменов клиента и учетные записи типа "бизнес-бизнес") и возможности доступа к службам. Важно отметить, какие возможности можно использовать с учетными записями типа "бизнес-бизнес".</span><span class="sxs-lookup"><span data-stu-id="d8170-p123">The following illustration describes how cloud services (SaaS, PaaS), account types (tenant domain accounts vs. B2B accounts), and service access capabilities relate. It’s important to note which capabilities can be used with B2B accounts.</span></span>

![Облачные службы, типы учетных записей и возможности доступа](Media/Apply-protection-to-personal-data-in-Office-365-image4.png)

<span data-ttu-id="d8170-306">Для работы специальных возможностей данные, изображенные на рисунке, также приведены далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="d8170-306">For accessibility, the rest of this section describes this illustration.</span></span>

### <a name="cloud-services"></a><span data-ttu-id="d8170-307">Облачные службы</span><span class="sxs-lookup"><span data-stu-id="d8170-307">Cloud services</span></span>

<span data-ttu-id="d8170-p124">Azure Active Directory обеспечивает доступ на основе удостоверений к любой облачной службе, в том числе службам сторонних поставщиков, таким как Amazon Web Services. На рисунке показаны службы Office 365, "Другое приложение SaaS" и "Приложение PaaS". Стрелки указывают с Azure Active Directory на каждую из этих служб, то есть Azure Active Directory можно использовать для проверки подлинности во всех этих приложениях.</span><span class="sxs-lookup"><span data-stu-id="d8170-p124">Azure Active Directory provides identity access to any cloud service, including non-Microsoft providers such as Amazon Web Services. The illustration shows Office 365, “Other SaaS app,” and “PaaS app.” Arrows point from Azure Active Directory to each of these services, showing that Azure Active Directory can be used for authentication to all of these app types.</span></span>

### <a name="types-of-accounts"></a><span data-ttu-id="d8170-311">Типы учетных записей</span><span class="sxs-lookup"><span data-stu-id="d8170-311">Types of accounts</span></span>

<span data-ttu-id="d8170-p125">Учетные записи доменов клиента — это учетные записи, которые вы непосредственно добавляете в свой клиент и которыми вы управляете. Учетные записи типа "бизнес-бизнес" предназначены для пользователей за пределами вашей организации, которых вы пригласили для совместной работы. Они могут включать другие учетные записи Office 365, учетные записи других организаций или обычные учетные записи (например, Gmail). На рисунке показаны оба типа учетных записей в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d8170-p125">Tenant domain accounts are account you add to your tenant and manage directly. B2B accounts are accounts for users outside your organization you invite to collaborate with. These can be other Office 365 accounts, other organization accounts, or consumer accounts (such as Gmail). The illustration shows both account types within Azure Active Directory.</span></span>

### <a name="capabilities"></a><span data-ttu-id="d8170-316">Возможности</span><span class="sxs-lookup"><span data-stu-id="d8170-316">Capabilities</span></span>

<span data-ttu-id="d8170-p126">Возможности, приведенные в таблице ниже, предназначены для защиты удостоверений и устройств. В таблице, как и на рисунке, показано, какие возможности также можно использовать с учетными записями типа "бизнес-бизнес".</span><span class="sxs-lookup"><span data-stu-id="d8170-p126">The capabilities in the following table protect identities and devices. The table indicates which capabilities can also be used with B2B accounts, similar to the illustration.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d8170-319"><strong>Возможность</strong></span><span class="sxs-lookup"><span data-stu-id="d8170-319"><strong>Capability</strong></span></span></th>
<th align="left"><span data-ttu-id="d8170-320"><strong>Поддержка учетных записей доменов клиента</strong></span><span class="sxs-lookup"><span data-stu-id="d8170-320"><strong>Works with tenant domain accounts</strong></span></span></th>
<th align="left"><span data-ttu-id="d8170-321"><strong>Поддержка учетных записей Azure типа "бизнес-бизнес" (без дополнительного лицензирования)</strong></span><span class="sxs-lookup"><span data-stu-id="d8170-321"><strong>Works with Azure B2B accounts (without additional licensing)</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="d8170-322">Многофакторная проверка подлинности и условный доступ</span><span class="sxs-lookup"><span data-stu-id="d8170-322">Multi-factor authentication and conditional access</span></span></td>
<td align="left"><span data-ttu-id="d8170-323">Да</span><span class="sxs-lookup"><span data-stu-id="d8170-323">Yes</span></span></td>
<td align="left"><span data-ttu-id="d8170-324">Да</span><span class="sxs-lookup"><span data-stu-id="d8170-324">Yes</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="d8170-325">Защита идентификации Azure AD</span><span class="sxs-lookup"><span data-stu-id="d8170-325">Azure AD Identity Protection</span></span></td>
<td align="left"><span data-ttu-id="d8170-326">Да</span><span class="sxs-lookup"><span data-stu-id="d8170-326">Yes</span></span></td>
<td align="left"><span data-ttu-id="d8170-327">Да</span><span class="sxs-lookup"><span data-stu-id="d8170-327">Yes</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="d8170-328">Azure AD Privileged Identity Management</span><span class="sxs-lookup"><span data-stu-id="d8170-328">Azure AD Privileged Identity Management</span></span></td>
<td align="left"><span data-ttu-id="d8170-329">Да</span><span class="sxs-lookup"><span data-stu-id="d8170-329">Yes</span></span></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="d8170-330">Управление мобильными приложениями (MAM)</span><span class="sxs-lookup"><span data-stu-id="d8170-330">Mobile Application Management (MAM)</span></span></td>
<td align="left"><span data-ttu-id="d8170-331">Да</span><span class="sxs-lookup"><span data-stu-id="d8170-331">Yes</span></span></td>
<td align="left"></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="d8170-332">Регистрация устройств и управление ими</span><span class="sxs-lookup"><span data-stu-id="d8170-332">Device enrollment and management</span></span></td>
<td align="left"><span data-ttu-id="d8170-333">Да</span><span class="sxs-lookup"><span data-stu-id="d8170-333">Yes</span></span></td>
<td align="left"><span data-ttu-id="d8170-334">Управлять устройством может только одна организация.</span><span class="sxs-lookup"><span data-stu-id="d8170-334">Only one organization can manage a device</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="d8170-335">Возможности защиты Windows 10 (для условного доступа на основе соответствия устройства требованиям требуется управление устройством)</span><span class="sxs-lookup"><span data-stu-id="d8170-335">Windows 10 security capabilities (conditional access based on device compliance requires device management)</span></span></td>
<td align="left"><span data-ttu-id="d8170-336">Да</span><span class="sxs-lookup"><span data-stu-id="d8170-336">Yes</span></span></td>
<td align="left"><span data-ttu-id="d8170-337">Да</span><span class="sxs-lookup"><span data-stu-id="d8170-337">Yes</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d8170-338">Вы можете добавить лицензии в учетные записи типа "бизнес-бизнес", чтобы предоставить этим пользователям дополнительные возможности, если это требуется для защиты доступа к персональным данным в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="d8170-338">You can add licenses to B2B accounts to give these users additional capabilities, if needed, to protect access to personal data in your environment.</span></span>
