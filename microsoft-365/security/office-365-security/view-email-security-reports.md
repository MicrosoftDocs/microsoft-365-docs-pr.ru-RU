---
title: Просмотр отчетов о безопасности электронной почты в &amp; центре безопасности и соответствия требованиям безопасности, скомпрометированных пользователей, шифрования, защиты от угроз, обнаруженных вредоносных программ, основных вредоносных программ, обнаружения нежелательной почты, отправленных и полученных сообщений, пользователь сообщил сообщения, сведения о безопасности, обнаружение, данные безопасности, сведения о безопасности
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 01/16/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Узнайте, как найти и использовать отчеты по обеспечению безопасности электронной почты для вашей организации. Отчеты о безопасности электронной почты доступны в центре &amp; безопасности и соответствия требованиям.
ms.openlocfilehash: 59090e53389b4e95d8987989819e71be6fce61e2
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598116"
---
# <a name="view-email-security-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="e7970-104">Просмотр отчетов о безопасности электронной почты в &amp; центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="e7970-104">View email security reports in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="e7970-105">В [центре соответствия требованиям безопасности &amp; ](https://protection.office.com) доступны разнообразные отчеты, которые помогут вам понять, как функции безопасности электронной почты, такие как защита от нежелательной почты, защита от вредоносных программ и функции шифрования в Office 365 защищают вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="e7970-105">A variety of reports are available in the [Security &amp; Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Office 365 are protecting your organization.</span></span> <span data-ttu-id="e7970-106">Если у вас есть [необходимые разрешения](#what-permissions-are-needed-to-view-these-reports), вы можете просмотреть эти отчеты в центре обеспечения &amp; безопасности, перейдя на \*\*\*\* \> **панель мониторинга**отчетов.</span><span class="sxs-lookup"><span data-stu-id="e7970-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security &amp; Compliance Center by going to **Reports** \> **Dashboard**.</span></span>
  
![Панель мониторинга, на которой вы видите, как работает Advanced Threat protection](../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="e7970-108">К отчетам по безопасности электронной почты относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="e7970-108">Your email security reports include the following:</span></span>
- [<span data-ttu-id="e7970-109">Отчет о скомпрометированных пользователях (**New!**)</span><span class="sxs-lookup"><span data-stu-id="e7970-109">Compromised Users report (**NEW!**)</span></span>](#compromised-users-report-new)
- [<span data-ttu-id="e7970-110">Отчет о шифровании</span><span class="sxs-lookup"><span data-stu-id="e7970-110">Encryption report</span></span>](#encryption-report)
- <span data-ttu-id="e7970-111">[отчет о состоянии защиты от угроз](#threat-protection-status-report);</span><span class="sxs-lookup"><span data-stu-id="e7970-111">[Threat Protection Status report](#threat-protection-status-report)</span></span> 
- [<span data-ttu-id="e7970-112">Отчет об обнаружении вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="e7970-112">Malware Detections report</span></span>](#malware-detections-report) 
- [<span data-ttu-id="e7970-113">Отчет о самых вредоносных программах</span><span class="sxs-lookup"><span data-stu-id="e7970-113">Top Malware report</span></span>](#top-malware-report)
- [<span data-ttu-id="e7970-114">Отчет по основным отправителям и получателям</span><span class="sxs-lookup"><span data-stu-id="e7970-114">Top Senders and Recipients report</span></span>](#top-senders-and-recipients-report)
- [<span data-ttu-id="e7970-115">Отчет об обнаружении поддельных поддельных</span><span class="sxs-lookup"><span data-stu-id="e7970-115">Spoof Detections report</span></span>](#spoof-detections-report)
- [<span data-ttu-id="e7970-116">Отчет об обнаружении нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="e7970-116">Spam Detections report</span></span>](#spam-detections-report)
- [<span data-ttu-id="e7970-117">Отчет о отправленных и полученных сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="e7970-117">Sent and received email report</span></span>](#sent-and-received-email-report)
- [<span data-ttu-id="e7970-118">Отчет о сообщениях, отчет о пользователях</span><span class="sxs-lookup"><span data-stu-id="e7970-118">User-reported messages report</span></span>](#user-reported-messages-report)


## <a name="compromised-users-report-new"></a><span data-ttu-id="e7970-119">Отчет о скомпрометированных пользователях (**New!**)</span><span class="sxs-lookup"><span data-stu-id="e7970-119">Compromised Users report (**NEW!**)</span></span> 

<span data-ttu-id="e7970-120">Этот отчет, доступный всем пользователям Exchange Online Protection, показывает количество учетных записей пользователей, помеченных как подозрительные или ограниченные, данные, особенно полезные в качестве учетных записей, могут быть непроблематичными или даже раскрыты.</span><span class="sxs-lookup"><span data-stu-id="e7970-120">This report, available to anyone with Exchange Online Protection, shows the number of user accounts marked as Suspicious or Restricted users, data particularly useful as accounts enter either of the states that indicate the user account may be problematic, or even compromised.</span></span> <span data-ttu-id="e7970-121">При частом использовании отчет о скомпрометированных пользователях может нарушить пиковые значения и даже тенденции в учетных записях, помеченных в подозрительных или ограниченных состояниях, что свидетельствует о проблемах с безопасностью и веллнесс клиента.</span><span class="sxs-lookup"><span data-stu-id="e7970-121">With frequent use, the Compromised User report can spot spikes, and even trends, in accounts marked in suspicious or restricted states, giving evidence there could be an issue with security and the wellness of your tenant.</span></span>

![Отчет "скомпрометированные пользователи" в том виде, в котором он отображается в Office 365.](../media/tp-threatProtectStatRpt-CompromisedUserRpt.png)

## <a name="encryption-report"></a><span data-ttu-id="e7970-123">Отчет о шифровании</span><span class="sxs-lookup"><span data-stu-id="e7970-123">Encryption report</span></span>

<span data-ttu-id="e7970-124">В **отчете о шифровании** представлены сведения о зашифрованных сообщениях электронной почты с помощью политик организации или конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="e7970-124">The **Encryption report** shows information about email messages that were encrypted, either through your organization's policies, or through end-user controls.</span></span> <span data-ttu-id="e7970-125">Группа безопасности Организации может использовать сведения из этого отчета для определения шаблонов и профилактического применения или настройки политик для конфиденциальных сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e7970-125">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span>

<span data-ttu-id="e7970-126">Чтобы просмотреть этот отчет, в центре безопасности & соответствия требованиям откройте **отчет о шифровании** **панели мониторинга** \> **отчетов** \> .</span><span class="sxs-lookup"><span data-stu-id="e7970-126">To view this report, in the Security & Compliance Center, go to **Reports** \> **Dashboard** \> **Encryption report**.</span></span>

![Отчет о шифровании](../media/encryptionreport-defaultview.png) 

<span data-ttu-id="e7970-128">При первом открытии отчета вы увидите сведения о методах шифрования, используемых в сообщениях электронной почты за прошедшие семь (7) дней.</span><span class="sxs-lookup"><span data-stu-id="e7970-128">When the report first opens, you'll see data about encryption methods used on email messages for the past seven (7) days.</span></span> <span data-ttu-id="e7970-129">Вы можете изменить диапазон дат и сведения, отображаемые в отчете, щелкнув **фильтры** в правом верхнем углу экрана.</span><span class="sxs-lookup"><span data-stu-id="e7970-129">You can change the date range and the details that are displayed in the report by clicking **Filters** in the upper right corner of the screen.</span></span>

![Фильтры отчета о шифровании](../media/encryptionreport-filters.png)   

<span data-ttu-id="e7970-131">Для просмотра данных с помощью шаблона шифрования (или метода) также можно использовать меню " **разделить по** ".</span><span class="sxs-lookup"><span data-stu-id="e7970-131">You can also use the **Break down by** menu to view data by encryption template (or method).</span></span>

![Метод шифрования или шаблон](../media/encryptionreport-breakdownby.png)

<span data-ttu-id="e7970-133">Вы также можете использовать меню **Просмотр данных,** чтобы изменить представление, чтобы увидеть количество зашифрованных сообщений для пяти самых популярных доменов получателей.</span><span class="sxs-lookup"><span data-stu-id="e7970-133">And, you can use the **View data by** menu to change the view to see counts of encrypted messages to the top five recipient domains.</span></span>

![Данные представления отчета о шифровании по меню](../media/encryptionreport-viewdataby.png)

<span data-ttu-id="e7970-135">Благодаря гибкости нового отчета о шифровании можно просматривать тенденции и выполнять соответствующие действия.</span><span class="sxs-lookup"><span data-stu-id="e7970-135">With the flexibility of the new Encryption report, you can view trends and take appropriate actions.</span></span> <span data-ttu-id="e7970-136">Например, если вы видите большое количество сообщений электронной почты, зашифрованных пользователями, может потребоваться добавить политику шифрования для автоматизации шифрования для определенных вариантов использования.</span><span class="sxs-lookup"><span data-stu-id="e7970-136">For example, if you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="e7970-137">(Чтобы получить помощь, ознакомьтесь со статьей [Определение правил для обработки почтового процесса для шифрования сообщений электронной почты в Office 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).) Другой пример: если у вас есть доступ к шаблонам шифрования, но никто их не использует, вы можете узнать, требуется ли пользователям обучение для этой функции.</span><span class="sxs-lookup"><span data-stu-id="e7970-137">(To get help with that, see [Define mail flow rules to encrypt email messages in Office 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).) As another example, if you have a number of encryption templates available but no one is using them, you might explore whether users need training for that feature.</span></span> 

<span data-ttu-id="e7970-138">Используйте этот отчет, чтобы группа безопасности и соответствия требованиям Организации отслеживать использование шифрования сообщений и требуются ли дальнейшие действия.</span><span class="sxs-lookup"><span data-stu-id="e7970-138">Use this report enables your organization's security and compliance team to monitor how message encryption is being used, and whether further actions are needed.</span></span> <span data-ttu-id="e7970-139">Дополнительные сведения о шифровании приведены [в статье шифрование электронной почты в Office 365](../../compliance/email-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="e7970-139">To learn more about encryption, see [Email encryption in Office 365](../../compliance/email-encryption.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="e7970-140">отчет о состоянии защиты от угроз;</span><span class="sxs-lookup"><span data-stu-id="e7970-140">Threat Protection Status report</span></span>

<span data-ttu-id="e7970-141">Отчет **о состоянии защиты от угроз** — это интеллектуальный отчет, показывающий вредоносную электронную почту, которая была обнаружена и заблокирована службой Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="e7970-141">The **Threat Protection Status** report is a smart report that shows malicious email that was detected and blocked by Exchange Online Protection.</span></span> <span data-ttu-id="e7970-142">Этот отчет полезен для просмотра сообщений электронной почты, определенных в качестве вредоносных программ или фишинговых атак, с течением времени (до 90 дней), а также позволяет администраторам безопасности определять тенденции или определять необходимость внесения изменений в политики.</span><span class="sxs-lookup"><span data-stu-id="e7970-142">This report is useful for viewing email identified as malware or a phishing attempt over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span>

> [!NOTE]
> <span data-ttu-id="e7970-143">Отчет о состоянии защиты от угроз доступен клиентам, у которых есть [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) или [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop) (EOP); Однако сведения, отображаемые в отчете о состоянии защиты от угроз для клиентов ATP, скорее всего, будут содержать данные, отличные от данных, которые могут видеть пользователи EOP.</span><span class="sxs-lookup"><span data-stu-id="e7970-143">A Threat Protection Status report is available to customers who have either [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) or [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="e7970-144">Например, пользователи EOP могут просматривать сведения о вредоносных программах, обнаруженных в электронной почте, но не могут получить сведения о [вредоносных файлах, обнаруженных в SharePoint Online, OneDrive или Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams), с возможностью, характерной для ATP.</span><span class="sxs-lookup"><span data-stu-id="e7970-144">For example, EOP customers can view information about malware detected in email, but not information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams), an ATP-specific capability.</span></span> <span data-ttu-id="e7970-145">([Дополнительные сведения об отчетах ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp).)</span><span class="sxs-lookup"><span data-stu-id="e7970-145">([Learn more about ATP reports](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp).)</span></span>
  
<span data-ttu-id="e7970-146">Чтобы просмотреть этот отчет, в [центре безопасности &amp; и соответствия требованиям](https://protection.office.com)выберите **состояние защиты от угроз**для **панели мониторинга** \> **отчетов** \> .</span><span class="sxs-lookup"><span data-stu-id="e7970-146">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![отчет о состоянии защиты от угроз;](../media/0ff86e12-c2b2-4d89-92a5-cefb054dc070.png)
  
<span data-ttu-id="e7970-148">Когда вы впервые открываете отчет о состоянии защиты от угроз, в отчете отображаются данные за прошедшие семь дней по умолчанию; Тем не менее, вы можете выбрать **фильтры** и изменить диапазон дат в течение до 90 дней.</span><span class="sxs-lookup"><span data-stu-id="e7970-148">When you first open the Threat Protection Status report, the report shows data for the past seven days by default; however, you can click **Filters** and change the date range for up to 90 days of detail.</span></span> <span data-ttu-id="e7970-149">(Если вы используете пробную подписку, вы можете использовать не более 30 дней данных.)</span><span class="sxs-lookup"><span data-stu-id="e7970-149">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>

<span data-ttu-id="e7970-150">Этот отчет полезен для просмотра эффективности и воздействия [функций Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features)в Организации, а также для долгосрочного тенденций.</span><span class="sxs-lookup"><span data-stu-id="e7970-150">This report is useful for viewing the effectiveness and impact of your organization's [Exchange Online Protection features](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features), and for longer-term trending.</span></span> 
  
![Фильтры отчета о состоянии защиты от угроз](../media/ab6b6b8d-e97a-4c3a-8fb1-c4940dcb7a07.png)
  
<span data-ttu-id="e7970-152">Вы также можете выбрать, следует ли просматривать данные для сообщений электронной почты, определенных как вредоносные, сообщения электронной почты, которые определены как почтовые фишингы, или как содержащие вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="e7970-152">You can also choose whether to view data for email identified as malicious, email identified as a phishing attempts, or email identified as containing malware.</span></span>
  
![Параметры представления отчета о состоянии защиты от угроз](../media/d429ecd7-cb7a-4c99-8d27-79a2832cf467.png)
  
## <a name="malware-detections-report"></a><span data-ttu-id="e7970-154">Отчет об обнаружении вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="e7970-154">Malware Detections report</span></span>

<span data-ttu-id="e7970-155">Отчет об **обнаружении вредоносных программ** показывает, сколько входящих и исходящих сообщений было обнаружено как содержащее вредоносные программы для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e7970-155">The **Malware Detections** report shows how many incoming and outgoing messages were detected as containing malware for your organization.</span></span> 
  
<span data-ttu-id="e7970-156">Чтобы просмотреть этот отчет, в [центре безопасности &amp; и соответствия требованиям](https://protection.office.com)перейдите в раздел **отчеты об** \> **обнаружении вредоносных программ**на **панели мониторинга** \> отчетов.</span><span class="sxs-lookup"><span data-stu-id="e7970-156">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Malware Detections**.</span></span>
  
![Пример отчета об обнаружении вредоносных программ](../media/a1ba61a3-565a-46d6-b0d5-6a6cff6b31d7.png)
  
<span data-ttu-id="e7970-158">Как и в случае с другими отчетами, например с [отчетом о состоянии защиты от угроз](#threat-protection-status-report), в отчете по умолчанию отображаются данные за прошедшие семь дней.</span><span class="sxs-lookup"><span data-stu-id="e7970-158">Similar to other reports, like the [Threat Protection Status report](#threat-protection-status-report), the report displays data for the past seven days by default.</span></span> <span data-ttu-id="e7970-159">Тем не менее, вы можете выбрать **фильтры** , чтобы изменить диапазон дат.</span><span class="sxs-lookup"><span data-stu-id="e7970-159">However, you can choose **Filters** to change the date range.</span></span> 
  
## <a name="top-malware-report"></a><span data-ttu-id="e7970-160">Отчет о самых вредоносных программах</span><span class="sxs-lookup"><span data-stu-id="e7970-160">Top Malware report</span></span>

<span data-ttu-id="e7970-161">В отчете о **самых вредоносных программах** отображаются различные виды вредоносных программ, обнаруженных в [Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features).</span><span class="sxs-lookup"><span data-stu-id="e7970-161">The **Top Malware** report shows the various kinds of malware that was detected by [Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features).</span></span> 
  
<span data-ttu-id="e7970-162">Чтобы просмотреть этот отчет, в [центре безопасности &amp; и соответствия требованиям](https://protection.office.com)перейдите на страницу **Основные вредоносные программы** **панели мониторинга** \> **отчетов** \> .</span><span class="sxs-lookup"><span data-stu-id="e7970-162">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Top Malware**.</span></span>
  
![SCC — EOP самые распространенные вредоносные программы](../media/763330b3-f56e-4ba4-b0bb-051500ae950a.png)
  
<span data-ttu-id="e7970-164">При наведении указателя на сектор на круговой диаграмме отображается название типа вредоносных программ и количество сообщений, обнаруженных при наличии вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="e7970-164">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>
  
<span data-ttu-id="e7970-165">Щелкните отчет, чтобы открыть его в новом окне браузера, где можно получить более подробное представление отчета.</span><span class="sxs-lookup"><span data-stu-id="e7970-165">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
![В этом отчете представлены самые популярные вредоносные программы, обнаруженные в Организации](../media/3fded224-fb31-4713-86f2-8afce5ce2991.png)
  
<span data-ttu-id="e7970-167">Под диаграммой вы увидите список обнаруженных вредоносных программ и количество сообщений, обнаруженных при наличии вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="e7970-167">Below the chart, you'll see a list of detected malware and how many messages were detected as having that malware.</span></span>
  
## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="e7970-168">Отчет по основным отправителям и получателям</span><span class="sxs-lookup"><span data-stu-id="e7970-168">Top Senders and Recipients report</span></span>

<span data-ttu-id="e7970-169">Отчет по **верхнему отправителям и получателям** представляет собой круговую диаграмму, в которой показаны лучшие отправители электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e7970-169">The **Top Senders and Recipients** report is a pie chart showing your top email senders.</span></span> 
  
<span data-ttu-id="e7970-170">Чтобы просмотреть этот отчет, в [центре безопасности &amp; и соответствия требованиям](https://protection.office.com)перейдите на страницу **лучшие отправители и получатели** **панели мониторинга** \> **отчетов** \> .</span><span class="sxs-lookup"><span data-stu-id="e7970-170">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Top Senders and Recipients**.</span></span>
  
![Чтобы просмотреть этот отчет, в центре безопасности &amp; и соответствия требованиям откройте панель мониторинга \> \> отчетов лучшие отправители и получатели](../media/b5506b5c-2420-4a5a-9ea3-d654294ac838.png)
  
<span data-ttu-id="e7970-172">При наведении указателя на сектор на круговой диаграмме можно увидеть количество отправленных или полученных сообщений.</span><span class="sxs-lookup"><span data-stu-id="e7970-172">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>
  
<span data-ttu-id="e7970-173">Щелкните отчет, чтобы открыть его в новом окне браузера, где можно получить более подробное представление отчета.</span><span class="sxs-lookup"><span data-stu-id="e7970-173">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
<span data-ttu-id="e7970-174">Используйте список **Показать данные** , чтобы выбрать, следует ли просматривать данные для отправителей, получателей, нежелательной почты и получателей вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="e7970-174">Use the **Show data for** list to choose whether to view data for top senders, receivers, spam recipients, and malware recipients.</span></span> <span data-ttu-id="e7970-175">Вы также можете узнать, кто получил вредоносную программу, обнаруженную [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop).</span><span class="sxs-lookup"><span data-stu-id="e7970-175">You can also see who received malware that was detected by [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop).</span></span> 
  
![Использование списка Показать данные для просмотра определенных данных](../media/bd91449f-7d42-4749-8666-7b44044049b8.png)
  
<span data-ttu-id="e7970-177">Под диаграммой вы узнаете, кто из первых отправителя или получателей почтовых сообщений, а также количество сообщений, отправленных или полученных в течение определенного периода времени.</span><span class="sxs-lookup"><span data-stu-id="e7970-177">Below the chart, you'll see who the top email senders or recipients were, along with a count of messages sent or received for the given time period.</span></span>
  
## <a name="spoof-detections-report"></a><span data-ttu-id="e7970-178">Отчет об обнаружении поддельных поддельных</span><span class="sxs-lookup"><span data-stu-id="e7970-178">Spoof Detections report</span></span>

<span data-ttu-id="e7970-179">Отчет об **обнаружении поддельных** поддельных сообщений показывает, сколько почтовых сообщений было обнаружено и какие из них были признаны "хорошими" (подделка почты выполнена по законным бизнес-причинам).</span><span class="sxs-lookup"><span data-stu-id="e7970-179">The **Spoof Detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> 
  
<span data-ttu-id="e7970-180">Чтобы просмотреть этот отчет, в [центре безопасности &amp; и соответствия требованиям](https://protection.office.com)перейдите в раздел " **поддельная** **панель мониторинга** \> **отчетов** \> ".</span><span class="sxs-lookup"><span data-stu-id="e7970-180">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Spoof Mail**.</span></span>
  
![В центре безопасности &amp; и соответствия требованиям выберите поддельную \> панель мониторинга отчетов \>](../media/0427e85c-9e40-4225-a0f0-e21a4e8b0e44.png)
  
<span data-ttu-id="e7970-182">Когда вы наводите указатель мыши на день в диаграмме, вы можете узнать, сколько поступило поддельное сообщение.</span><span class="sxs-lookup"><span data-stu-id="e7970-182">When you hover over a day in the chart, you can see how many spoof mail messages came through.</span></span>
  
<span data-ttu-id="e7970-183">Щелкните отчет, чтобы открыть его в новом окне браузера, где можно получить более подробное представление отчета.</span><span class="sxs-lookup"><span data-stu-id="e7970-183">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span> <span data-ttu-id="e7970-184">Чтобы узнать больше о защите от спуфинга, ознакомьтесь со статьей [Защита от спуфинга в Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spoofing-protection).</span><span class="sxs-lookup"><span data-stu-id="e7970-184">To learn more about anti-spoof protection, see [Anti-spoofing protection in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spoofing-protection).</span></span>
  
## <a name="spam-detections-report"></a><span data-ttu-id="e7970-185">Отчет об обнаружении нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="e7970-185">Spam Detections report</span></span>

<span data-ttu-id="e7970-186">В отчете **обнаружения нежелательной почты** отображается весь нежелательный контент, заблокированный Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e7970-186">The **Spam Detections** report shows all the spam content blocked by Exchange Online.</span></span> <span data-ttu-id="e7970-187">Сообщения подсчитываются для каждого сообщения, а не для каждого получателя.</span><span class="sxs-lookup"><span data-stu-id="e7970-187">Messages are counted per message, and not per recipient.</span></span> <span data-ttu-id="e7970-188">Например, если сообщение электронной почты было отправлено получателям в Организации 100, оно считается одним сообщением.</span><span class="sxs-lookup"><span data-stu-id="e7970-188">For example, if an email message was sent to 100 recipients in your organization, it is counted as one message.</span></span>
  
<span data-ttu-id="e7970-189">Чтобы просмотреть этот отчет, в [центре безопасности &amp; и соответствия требованиям](https://protection.office.com)перейдите в раздел **отчеты об** \> **обнаружении нежелательной почты**на **панели мониторинга** \> .</span><span class="sxs-lookup"><span data-stu-id="e7970-189">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Spam Detections**.</span></span>
  
![Чтобы просмотреть этот отчет, в центре безопасности &amp; и соответствия требованиям перейдите к панели \> мониторинга \> отчетов EOP обнаружения нежелательной почты](../media/028cff3c-79ce-4ec0-8f0f-ec32ac28243a.png)
  
<span data-ttu-id="e7970-191">Когда вы наводите указатель мыши на день в диаграмме, вы можете узнать, сколько элементов было заблокировано в этот день, а также как эти элементы классифицируются по категориям.</span><span class="sxs-lookup"><span data-stu-id="e7970-191">When you hover over a day in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span> <span data-ttu-id="e7970-192">Например, вы можете узнать, сколько нежелательных сообщений было отфильтровано, и сколько элементов было получено из IP-адреса, заблокированного протоколом Интернета (IP).</span><span class="sxs-lookup"><span data-stu-id="e7970-192">For example, you can see how many spam messages were filtered, and how many items came from a blocked Internet Protocol (IP) address.</span></span>
  
<span data-ttu-id="e7970-193">Щелкните отчет, чтобы открыть его в новом окне браузера, где можно получить более подробное представление отчета.</span><span class="sxs-lookup"><span data-stu-id="e7970-193">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
![Отчет об обнаружении нежелательной почты содержит сведения о том, сколько нежелательных сообщений заблокировано или отфильтровано.](../media/370ec67d-eb30-4863-bfcf-68a41be02295.png)
  
<span data-ttu-id="e7970-195">Под диаграммой вы увидите список обнаруженных сообщений о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="e7970-195">Below the chart, you'll see a list of spam items that were detected.</span></span> <span data-ttu-id="e7970-196">Выберите элемент, чтобы просмотреть дополнительные сведения, например сведения о том, является ли сообщение нежелательной почтой входящим или исходящим, его ИДЕНТИФИКАТОРом и получателем.</span><span class="sxs-lookup"><span data-stu-id="e7970-196">Select an item to view additional information, such as whether the spam item was inbound or outbound, its message ID, and its recipient.</span></span> <span data-ttu-id="e7970-197">Дополнительные сведения о защите от нежелательной почты см в статье [Office 365 защита от нежелательной](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)почты.</span><span class="sxs-lookup"><span data-stu-id="e7970-197">To learn more about anti-spam protection, see [Office 365 email anti-spam protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection).</span></span>
  
## <a name="sent-and-received-email-report"></a><span data-ttu-id="e7970-198">Отчет о отправленных и полученных сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="e7970-198">Sent and received email report</span></span>

<span data-ttu-id="e7970-199">Отчет о **отправленных и полученных сообщениях** — это интеллектуальный отчет, в котором отображаются сведения о входящих и исходящих сообщениях электронной почты, в том числе об обнаружении нежелательной почты, вредоносных программах и сообщениях электронной почты, определенных</span><span class="sxs-lookup"><span data-stu-id="e7970-199">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> 
  
<span data-ttu-id="e7970-200">Чтобы просмотреть этот отчет, в [центре безопасности &amp; и соответствия требованиям](https://protection.office.com)откройте **панель мониторинга** \> **отчетов** \> **Отправленные и полученные сообщения электронной почты**.</span><span class="sxs-lookup"><span data-stu-id="e7970-200">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Sent and received email**.</span></span>
  
![Чтобы просмотреть этот отчет, в центре безопасности &amp; и соответствия требованиям перейдите к панели \> мониторинга \> отчетов отправленные и полученные сообщения электронной почты](../media/0e710ed0-1b0e-4dac-8796-94a01a710f3a.png)
  
<span data-ttu-id="e7970-202">Когда вы наводите указатель мыши на день в диаграмме, вы можете видеть, сколько сообщений было поступило, и как эти сообщения классифицируются по категориям.</span><span class="sxs-lookup"><span data-stu-id="e7970-202">When you hover over a day in the chart, you can see how many messages came in, and how those messages are categorized.</span></span> <span data-ttu-id="e7970-203">Например, вы можете узнать, сколько сообщений было определено как содержащие вредоносные программы, и сколько было определено как спам.</span><span class="sxs-lookup"><span data-stu-id="e7970-203">For example, you can see how many messages were detected as containing malware, and how many were identified as spam.</span></span>
  
<span data-ttu-id="e7970-204">Щелкните отчет, чтобы открыть его в новом окне браузера, где можно получить более подробное представление отчета.</span><span class="sxs-lookup"><span data-stu-id="e7970-204">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
<span data-ttu-id="e7970-205">Для просмотра сведений по типу или по направлению (входящее и исходящее) можно использовать список **разбивки по** списку.</span><span class="sxs-lookup"><span data-stu-id="e7970-205">You can use the **Break down by** list to view information by type or by direction (incoming and outgoing).</span></span> 
  
![Используйте разбивку по списку для просмотра сведений по типу или направлению](../media/a5b30c94-d75f-4bfc-851a-cb155685b177.png)
  
<span data-ttu-id="e7970-207">Под диаграммой вы увидите список категорий электронной почты, например **гудмаил**, **спамконтентфилтеред**и т. д.</span><span class="sxs-lookup"><span data-stu-id="e7970-207">Below the chart, you'll see a list of email categories, such as **GoodMail**, **SpamContentFiltered**, and so on.</span></span> <span data-ttu-id="e7970-208">Выберите категорию, чтобы просмотреть дополнительные сведения, такие как действия, предпринятые для вредоносных программ, а также сведения о том, является ли электронная почта входящей или исходящей.</span><span class="sxs-lookup"><span data-stu-id="e7970-208">Select a category to view additional information, such as actions that were taken for malware, and whether email was incoming or outgoing.</span></span>
  
![В этом отчете рассказывается о средствах защиты от вредоносных программ, защиты от нежелательной почты и других обнаруженных сообщениях](../media/9ea4b606-f27a-46ee-97a7-be018e2b839c.png)

<span data-ttu-id="e7970-210">Дополнительные сведения об аналитике электронной почты см [в статье Управление почтовыми сообщениями в Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-intelligence-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="e7970-210">To learn more about email intelligence, see [Mail flow intelligence in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-intelligence-in-office-365).</span></span>
  
## <a name="user-reported-messages-report"></a><span data-ttu-id="e7970-211">Отчет о сообщениях, отчет о пользователях</span><span class="sxs-lookup"><span data-stu-id="e7970-211">User-reported messages report</span></span>

<span data-ttu-id="e7970-212">Отчет о сообщениях в отчетах о **пользователях** содержит сведения о сообщениях электронной почты, которые пользователи сообщили как нежелательные, фишинговые попытки или хорошие сообщения с помощью [надстройки Report Message](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).</span><span class="sxs-lookup"><span data-stu-id="e7970-212">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).</span></span>
  
<span data-ttu-id="e7970-213">Для каждого сообщения доступны подробные сведения, в том числе причина доставки, такие как исключение политики нежелательной почты или правило обработки почты, настроенное для Организации.</span><span class="sxs-lookup"><span data-stu-id="e7970-213">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="e7970-214">Чтобы просмотреть сведения, выберите элемент в списке пользователь — отчеты, а затем просмотрите сведения на вкладках **Сводка** и **сведения** .</span><span class="sxs-lookup"><span data-stu-id="e7970-214">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span> 
  
![Отчет о сообщениях с отчетами о пользователях показывает, что пользователи помечаются как нежелательная, Нежелательная почта или фишинговые попытки.](../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)
  
<span data-ttu-id="e7970-216">Чтобы просмотреть этот отчет, в [центре безопасности &amp; и соответствия требованиям](https://protection.office.com)выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="e7970-216">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), do one of the following:</span></span>
  
- <span data-ttu-id="e7970-217">Перейдите к **сообщению, сообщенному пользователями** \> **панели** \> **управления угрозами** .</span><span class="sxs-lookup"><span data-stu-id="e7970-217">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>
    
- <span data-ttu-id="e7970-218">Перейдите к разделу \> **Управление угрозами** **Обзор** \> **сообщений, отправленных пользователями**.</span><span class="sxs-lookup"><span data-stu-id="e7970-218">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>
    
![В центре безопасности &amp; и соответствия требованиям выберите Обзор \> \> управления угрозами сообщения о пользователе](../media/e372c57c-1414-4616-957b-bc933b8c8711.png)
  
> [!IMPORTANT]
> <span data-ttu-id="e7970-220">Чтобы отчет о сообщениях, отправленных пользователями, работал правильно, **необходимо включить ведение журнала аудита** для среды Office 365.</span><span class="sxs-lookup"><span data-stu-id="e7970-220">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="e7970-221">Это обычно делается для пользователей, которым назначена роль "журналы аудита" в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e7970-221">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="e7970-222">Дополнительную информацию можно узнать [в статье Включение и отключение поиска в журнале аудита Office 365](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span><span class="sxs-lookup"><span data-stu-id="e7970-222">For more information, see [Turn Office 365 audit log search on or off](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span> 
  
## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="e7970-223">Какие разрешения необходимы для просмотра отчетов?</span><span class="sxs-lookup"><span data-stu-id="e7970-223">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="e7970-224">Для просмотра и использования отчетов, описанных в этой статье, **необходимо назначить соответствующую роль для центра безопасности &amp; и центра администрирования Exchange**.</span><span class="sxs-lookup"><span data-stu-id="e7970-224">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="e7970-225">Для центра соответствия &amp; требованиям безопасности необходимо назначить одну из следующих ролей:</span><span class="sxs-lookup"><span data-stu-id="e7970-225">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="e7970-226">Управление организацией</span><span class="sxs-lookup"><span data-stu-id="e7970-226">Organization Management</span></span>
    - <span data-ttu-id="e7970-227">Администратор безопасности (это можно назначить в центре администрирования Azure Active Directory ([https://aad.portal.azure.com](https://aad.portal.azure.com)).</span><span class="sxs-lookup"><span data-stu-id="e7970-227">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>
    - <span data-ttu-id="e7970-228">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="e7970-228">Security Reader</span></span>

- <span data-ttu-id="e7970-229">Для Exchange Online необходимо назначить одну из следующих ролей в центре администрирования Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) или с помощью командлетов PowerShell (см. [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span><span class="sxs-lookup"><span data-stu-id="e7970-229">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="e7970-230">Управление организацией</span><span class="sxs-lookup"><span data-stu-id="e7970-230">Organization Management</span></span>
    - <span data-ttu-id="e7970-231">Управление организацией с правами только на просмотр</span><span class="sxs-lookup"><span data-stu-id="e7970-231">View-only Organization Management</span></span>
    - <span data-ttu-id="e7970-232">Роль получателей с правами только на просмотр</span><span class="sxs-lookup"><span data-stu-id="e7970-232">View-Only Recipients role</span></span>
    - <span data-ttu-id="e7970-233">Управление соответствием требованиям</span><span class="sxs-lookup"><span data-stu-id="e7970-233">Compliance Management</span></span>

<span data-ttu-id="e7970-234">Для получения дополнительных сведений ознакомьтесь с приведенными ниже ресурсами.</span><span class="sxs-lookup"><span data-stu-id="e7970-234">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="e7970-235">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="e7970-235">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)

- [<span data-ttu-id="e7970-236">Разрешения компонентов в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e7970-236">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="e7970-237">Что делать, если в отчетах данные не отображаются?</span><span class="sxs-lookup"><span data-stu-id="e7970-237">What if the reports aren't showing data?</span></span>

<span data-ttu-id="e7970-238">Если вы не видите данные в отчетах, дважды проверьте правильность настройки политик.</span><span class="sxs-lookup"><span data-stu-id="e7970-238">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="e7970-239">Чтобы узнать больше, ознакомьтесь [со статьей защита от угроз в Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).</span><span class="sxs-lookup"><span data-stu-id="e7970-239">To learn more, see [Protect against threats in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e7970-240">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="e7970-240">Related topics</span></span>

[<span data-ttu-id="e7970-241">Защита от спама электронной почты в Office 365</span><span class="sxs-lookup"><span data-stu-id="e7970-241">Office 365 Email Anti-Spam Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)
  
[<span data-ttu-id="e7970-242">Отчеты и аналитика в центре безопасности &amp; и соответствия требованиям Office 365</span><span class="sxs-lookup"><span data-stu-id="e7970-242">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/reports-and-insights-in-security-and-compliance)
  
[<span data-ttu-id="e7970-243">Создание расписания для отчета в центре безопасности &amp; и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="e7970-243">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-a-schedule-for-a-report)
  
[<span data-ttu-id="e7970-244">Настройка и загрузка настраиваемого отчета в центре безопасности &amp; и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="e7970-244">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-and-download-a-custom-report)
  

