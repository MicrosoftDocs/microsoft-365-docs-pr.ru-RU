---
title: Общие сведения о защите информации в Office 365 в соответствии с регламентом GDPR
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Ознакомьтесь с защитой информации в Office 365 в соответствии с регламентом GDPR. Узнайте, как искать, классифицировать, защищать и отслеживать персональные данные.
ms.openlocfilehash: 72ce55b5ceb2ec3ff95cada481ec4aee0bbe8eef
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197410"
---
# <a name="overview-of-office-365-information-protection-for-gdpr"></a><span data-ttu-id="dc831-104">Общие сведения о защите информации в Office 365 в соответствии с регламентом GDPR</span><span class="sxs-lookup"><span data-stu-id="dc831-104">Overview of Office 365 Information Protection for GDPR</span></span>

<span data-ttu-id="dc831-p102">Это решение демонстрирует, как защитить конфиденциальные данные, которые хранятся в службах Office 365. Оно включает предписывающие рекомендации по обнаружению, классификации, защите и отслеживанию персональных данных. В этом решении в качестве примера используется Общий регламент по защите данных (GDPR), но аналогичный процесс можно применить, чтобы обеспечить соответствие требованиям ряда других нормативов.</span><span class="sxs-lookup"><span data-stu-id="dc831-p102">This solution demonstrates how to protect sensitive data that is stored in Office 365 services. It includes prescriptive recommendations for discovering, classifying, protecting, and monitoring personal data. This solution uses General Data Protection Regulation (GDPR) as an example, but you can apply the same process to achieve compliance with many other regulations.</span></span>

<span data-ttu-id="dc831-p103">Регламент GDPR регулирует сбор, хранение, обработку и совместное использование персональных данных. Эти данные в регламенте GDPR имеют очень широкое определение, включая любые сведения, которые касаются идентифицированных или идентифицируемых физических лиц, проживающих в Европейском союзе (ЕС).</span><span class="sxs-lookup"><span data-stu-id="dc831-p103">GDPR regulates the collection, storage, processing, and sharing of personal data. Personal data is defined very broadly under the GDPR as any data that relates to an identified or identifiable natural person that is a resident of the European Union (EU).</span></span>

<span data-ttu-id="dc831-110">Статья 4. Определения</span><span class="sxs-lookup"><span data-stu-id="dc831-110">Article 4 – Definitions</span></span>

> <span data-ttu-id="dc831-111">Под "персональными данными" подразумевается любая информация, связанная с идентифицированным или идентифицируемым физическим лицом ("субъектом данных"). Идентифицируемым физическим лицом считается лицо, которого можно прямо или косвенно определить, в частности с помощью идентификатора, такого как имя, идентификационный номер, данные о местоположении, идентификатор в сети, либо с использованием одного или нескольких факторов, связанных с физическими, физиологическими, генетическими, ментальными, экономическими, культурными или социальными характеристиками этого физического лица.</span><span class="sxs-lookup"><span data-stu-id="dc831-111">‘personal data’ means any information relating to an identified or identifiable natural person (‘data subject’); an identifiable natural person is one who can be identified, directly or indirectly, in particular by reference to an identifier such as a name, an identification number, location data, an online identifier or to one or more factors specific to the physical, physiological, genetic, mental, economic, cultural or social identity of that natural person;</span></span>

<span data-ttu-id="dc831-p104">Цель этого решения — помочь организациям обнаруживать и защищать персональные данные в Office 365, на которые может распространяться регламент GDPR. Это решение не используется для подтверждения соответствия требованиям регламента GDPR. Организации несут ответственность за обеспечение своего соответствия требованиям этого регламента. Им рекомендуется обратиться к собственным юристам и группам по обеспечению соответствия требованиям либо к третьим лицам, которые специализируются на обеспечении соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="dc831-p104">This solution is intended to help organizations discover and protect personal data in Office 365 that might be subject to the GDPR. It is not offered as a GDPR compliance attestation. Organizations are responsible for ensuring their own GDPR compliance and are advised to consult their legal and compliance teams or to seek guidance and advice from third parties that specialize in compliance.</span></span>

<span data-ttu-id="dc831-115">[GDPR Assessment](https://www.microsoft.com/cyberassessment/en/gdpr/uso365?ls=Email&mkt_tok=eyJpIjoiTTJFeE5USXlOR1EwTWpJMiIsInQiOiJQTmdCYWR5NTlOd3JLWHZlb2NzNldKclQ4ZVBzVmhGeUhoUlFcL1pvSDIyXC9Ka05iTUR1aGpxT0YxQ0FUeGNDOUlkbWZLM1U4SUZWZmEyaGF6XC9ueUxkTHJzZnB3VDRMZlhPdkR4MzRLWkF5ckRNdWwxUkgzXC9yRU8yNkttSHhTb3VpZjNyVlJrNm9TTVZRYU5HR240a0FRPT0ifQ%3D%3D) — это простое в использовании сетевое средство самостоятельной проверки, с помощью которой ваша организация может бесплатно проверить свое соответствие требованиям регламента GDPR.</span><span class="sxs-lookup"><span data-stu-id="dc831-115">[GDPR Assessment](https://www.microsoft.com/cyberassessment/en/gdpr/uso365?ls=Email&mkt_tok=eyJpIjoiTTJFeE5USXlOR1EwTWpJMiIsInQiOiJQTmdCYWR5NTlOd3JLWHZlb2NzNldKclQ4ZVBzVmhGeUhoUlFcL1pvSDIyXC9Ka05iTUR1aGpxT0YxQ0FUeGNDOUlkbWZLM1U4SUZWZmEyaGF6XC9ueUxkTHJzZnB3VDRMZlhPdkR4MzRLWkF5ckRNdWwxUkgzXC9yRU8yNkttSHhTb3VpZjNyVlJrNm9TTVZRYU5HR240a0FRPT0ifQ%3D%3D) is a quick, online self-evaluation tool available at no cost to help your organization review its overall level of readiness to comply with the GDPR.</span></span>

## <a name="assess-and-manage-your-compliance-risk"></a><span data-ttu-id="dc831-116">Оценка рисков, связанных с соответствием требованиям, и управление ими</span><span class="sxs-lookup"><span data-stu-id="dc831-116">Assess and manage your compliance risk</span></span>

<span data-ttu-id="dc831-p105">Для обеспечения соответствия требованиям регламента GDPR в первую очередь необходимо определить, распространяется ли этот регламент на вашу организацию, и если да, то в какой степени. Для этого нужно понимать, какие данные обрабатывает ваша организация, и знать, где они хранятся.</span><span class="sxs-lookup"><span data-stu-id="dc831-p105">The first step towards GDPR compliance is to assess whether the GDPR applies to your organization, and, if so, to what extent. This analysis includes understanding the data your organization processes and where it resides.</span></span>

### <a name="step-1--use-compliance-manager-to-view-the-regulation-requirements-and-track-your-progress"></a><span data-ttu-id="dc831-119">Шаг 1. Просмотр нормативных требований и отслеживание вашего прогресса в диспетчере соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="dc831-119">Step 1 — Use Compliance Manager to view the regulation requirements and track your progress</span></span>

<span data-ttu-id="dc831-120">Диспетчер соответствия требованиям позволяет отслеживать и внедрять аудиторские проверки, а также управлять ими. Благодаря этому ваша организация сможет обеспечить соответствие требованиям различных стандартов, в том числе GDPR.</span><span class="sxs-lookup"><span data-stu-id="dc831-120">Compliance Manager helps you track, implement, and manage the auditing controls to help your organization reach compliance against various standards, including GDPR.</span></span>

![Просмотр требований и отслеживание прогресса в диспетчере соответствия требованиям](../media/Overview-image1.png)

<span data-ttu-id="dc831-122">Дополнительные сведения см. в статье [Диспетчер соответствия требованиям](compliance-manager.md).</span><span class="sxs-lookup"><span data-stu-id="dc831-122">For more information, see [Compliance Manager](compliance-manager.md).</span></span>

### <a name="step-2--use-content-search-and-sensitive-information-types-to-find-personal-data"></a><span data-ttu-id="dc831-123">Шаг 2. Поиск персональных данных с помощью веб-части "Поиск контента" и типов конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="dc831-123">Step 2 — Use Content Search and sensitive information types to find personal data</span></span> 

<span data-ttu-id="dc831-p106">Выявляйте в своей среде персональные данные, подпадающее под действие регламента GDPR. Используйте веб-часть "Поиск контента" вместе с типами конфиденциальной информации для:</span><span class="sxs-lookup"><span data-stu-id="dc831-p106">Discover personal data in your environment that is subject to the GDPR. Use Content Search together with sensitive information types to:</span></span>

- <span data-ttu-id="dc831-126">поиска персональных данных и составления отчетов об их расположении;</span><span class="sxs-lookup"><span data-stu-id="dc831-126">Find and report on where personal data resides.</span></span>

- <span data-ttu-id="dc831-127">оптимизации типов конфиденциальных данных и других запросов для поиска всех персональных данных в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="dc831-127">Optimize sensitive data types and other queries to find all personal data in your environment.</span></span>

![Поиск персональных данных с помощью веб-части "Поиск контента" и типов конфиденциальной информации](../media/Overview-image2.png)

<span data-ttu-id="dc831-p107">Типы конфиденциальной информации определяют, как автоматизированный процесс распознает определенные типы данных, такие как номера медицинской страховки и кредитных карт. В этой статье описан набор средств, которые можно использовать в качестве отправной точки. В ближайшее время будет представлен ряд дополнительных типов конфиденциальной информации для персональных данных в странах ЕС.</span><span class="sxs-lookup"><span data-stu-id="dc831-p107">Sensitive information types define how the automated process recognizes specific information types such as health service numbers and credit card numbers. This article includes a set you can use as a starting point. Many more sensitive information types are coming soon for personal data in EU countries.</span></span>

<span data-ttu-id="dc831-132">Дополнительные сведения см. в статье [Поиск персональных данных](search-for-and-find-personal-data.md).</span><span class="sxs-lookup"><span data-stu-id="dc831-132">For more information, see [Search for and find personal data](search-for-and-find-personal-data.md).</span></span> 

## <a name="classify-protect-and-monitor-personal-data-in-office-365-and-other-saas-apps"></a><span data-ttu-id="dc831-133">Классификация, защита и отслеживание персональных данных в Office 365 и других приложениях SaaS</span><span class="sxs-lookup"><span data-stu-id="dc831-133">Classify, protect, and monitor personal data in Office 365 and other SaaS apps</span></span>

<span data-ttu-id="dc831-134">Некоторые возможности, используемые для защиты информации в Office 365, также можно применять для защиты конфиденциальных данных в других приложениях SaaS.</span><span class="sxs-lookup"><span data-stu-id="dc831-134">Some of the capabilities used for information protection in Office 365 can also be used to protect sensitive data in other SaaS applications.</span></span>

![Классификация, защита и отслеживание персональных данных](../media/Overview-image3.png)

<span data-ttu-id="dc831-136">Содержимое этого рисунка описано в следующих разделах (шаги 3–5).</span><span class="sxs-lookup"><span data-stu-id="dc831-136">This illustration is described by the rest this section (steps 3-5).</span></span>

### <a name="step-3--decide-if-you-want-to-use-labels-in-addition-to-sensitive-information-types"></a><span data-ttu-id="dc831-137">Шаг 3. Выбор целесообразности использования меток в дополнение к типам конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="dc831-137">Step 3 — Decide if you want to use labels in addition to sensitive information types</span></span>

<span data-ttu-id="dc831-p108">Типы конфиденциальной информации — это разновидность классификации. См. статью [Разработка архитектуры схемы классификации для персональных данных](architect-a-classification-schema-for-personal-data.md), чтобы решить, нужно ли внедрить метки. Процесс применения меток описан в статье [Применение меток к персональным данным в Office 365](apply-labels-to-personal-data-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="dc831-p108">Sensitive information types are a form of classification. See [Architect a classification schema for personal data](architect-a-classification-schema-for-personal-data.md), to decide if you also want to implement labels. To apply labels, see [Apply labels to personal data in Office 365](apply-labels-to-personal-data-in-office-365.md).</span></span>

<span data-ttu-id="dc831-p109">На рисунке выше типы конфиденциальной информации и метки используются во всей системе Office 365. В ближайшее время их можно будет применять с Cloud App Security для поиска конфиденциальных данных в других приложениях SaaS, таких как Box и Salesforce.</span><span class="sxs-lookup"><span data-stu-id="dc831-p109">In the illustration, sensitive information types and labels work across Office 365. Coming soon, you can use these with Cloud App Security to find sensitive data in other SaaS apps, such as Box and Salesforce.</span></span>

### <a name="step-4--protect-personal-data-in-office-365"></a><span data-ttu-id="dc831-143">Шаг 4. Защита персональных данных в Office 365</span><span class="sxs-lookup"><span data-stu-id="dc831-143">Step 4 — Protect personal data in Office 365</span></span> 

<span data-ttu-id="dc831-p110">Защита персональных данных начинается с защиты от потери данных Office 365. Для защиты доступа к персональным данным также используются другие возможности, в частности шифрование сообщений Office 365 для электронной почты.</span><span class="sxs-lookup"><span data-stu-id="dc831-p110">Protection for personal data starts with Office 365 data loss prevention. There are several other capabilities recommended for protecting access to personal data, including Office 365 Message Encryption for email.</span></span>

<span data-ttu-id="dc831-146">Эти средства защиты можно применять к определенным наборам данных:</span><span class="sxs-lookup"><span data-stu-id="dc831-146">These protections can be targeted to specific data sets:</span></span>

- <span data-ttu-id="dc831-147">разрешения на уровне сайта и библиотеки;</span><span class="sxs-lookup"><span data-stu-id="dc831-147">Site and library-level permissions</span></span>

- <span data-ttu-id="dc831-148">политики внешнего общего доступа на уровне сайта;</span><span class="sxs-lookup"><span data-stu-id="dc831-148">Site-level external sharing policies</span></span>

- <span data-ttu-id="dc831-149">политики доступа к устройствам на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="dc831-149">Site-level device access policies</span></span>

<span data-ttu-id="dc831-150">Защита доступа к Office 365 и другим облачным службам включает:</span><span class="sxs-lookup"><span data-stu-id="dc831-150">Protection for access to Office 365 and other cloud services include:</span></span>

- <span data-ttu-id="dc831-151">защиту доступа с учетных записей и устройств в Enterprise Mobility + Security (EMS);</span><span class="sxs-lookup"><span data-stu-id="dc831-151">Identity and device access protection in Enterprise Mobility + Security (EMS)</span></span>

- <span data-ttu-id="dc831-152">управление привилегированным доступом;</span><span class="sxs-lookup"><span data-stu-id="dc831-152">Privileged access management</span></span>

- <span data-ttu-id="dc831-153">возможности защиты Windows 10.</span><span class="sxs-lookup"><span data-stu-id="dc831-153">Windows 10 security capabilities</span></span>

<span data-ttu-id="dc831-154">Дополнительные сведения см. в статье [Применение защиты к персональным данным в Office 365](apply-protection-to-personal-data-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="dc831-154">For more information about applying protection, see [Apply protection to personal data in Office 365](apply-protection-to-personal-data-in-office-365.md).</span></span>

### <a name="step-5--monitor-for-leaks-of-personal-data"></a><span data-ttu-id="dc831-155">Шаг 5. Отслеживание утечек персональных данных</span><span class="sxs-lookup"><span data-stu-id="dc831-155">Step 5 — Monitor for leaks of personal data</span></span>

<span data-ttu-id="dc831-p111">Отчеты о защите от потери данных в Office 365 включают больше всего сведений для отслеживания конфиденциальных данных. Вы можете настроить автоматические оповещения и исследовать нарушения с помощью журнала аудита. Cloud App Security включает возможность поиска и отслеживания конфиденциальных данных для других поставщиков SaaS. Дополнительные сведения об этих средствах см. в статье, посвященной [отслеживанию нарушений в отношении персональных данных](/security/office-365-security/monitor-for-leaks-of-personal-data.md).</span><span class="sxs-lookup"><span data-stu-id="dc831-p111">Office 365 data loss prevention reports provide the greatest level of detail for monitoring sensitive data. You can setup automated alerts and investigate breaches by using the audit log. Cloud App Security extends the ability to find and monitor sensitive data to other SaaS providers. For more information on these tools, see [Monitor for breaches of personal data](/security/office-365-security/monitor-for-leaks-of-personal-data.md).</span></span>
