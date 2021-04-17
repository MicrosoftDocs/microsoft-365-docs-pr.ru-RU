---
title: Рекомендации по политике предотвращения потери данных
f1.keywords: CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
description: Узнайте, как добавить подсказку политики в политику предотвращения потери данных (DLP), уведомив пользователя о том, что он работает с контентом, который противоречит политике DLP.
ms.custom: seo-marvel-apr2021
ms.openlocfilehash: 693f511b6303fb07d393c62efb4a61631b844474
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876826"
---
# <a name="data-loss-prevention-policy-tips-reference"></a><span data-ttu-id="8a752-103">Рекомендации по политике предотвращения потери данных</span><span class="sxs-lookup"><span data-stu-id="8a752-103">Data Loss Prevention policy tips reference</span></span>

<span data-ttu-id="8a752-104">Рекомендации по политике DLP в Outlook Web Access поддерживаются для всех условий, исключений и действий, применимых к рабочей нагрузке Exchange в политике DLP, за исключением следующих:</span><span class="sxs-lookup"><span data-stu-id="8a752-104">DLP policy tips in Outlook Web Access is supported for all the conditions, exceptions and actions that are applicable on Exchange workload in a DLP policy except the following:</span></span>

<span data-ttu-id="8a752-105">**Условия:**</span><span class="sxs-lookup"><span data-stu-id="8a752-105">**Conditions:**</span></span>

- <span data-ttu-id="8a752-106">Отправитель</span><span class="sxs-lookup"><span data-stu-id="8a752-106">Sender Is</span></span>
- <span data-ttu-id="8a752-107">Домен отправитель</span><span class="sxs-lookup"><span data-stu-id="8a752-107">Sender Domain Is</span></span>
- <span data-ttu-id="8a752-108">Получатель является членом</span><span class="sxs-lookup"><span data-stu-id="8a752-108">Recipient is a member of</span></span>
- <span data-ttu-id="8a752-109">Заготвка содержит слова или фразы</span><span class="sxs-lookup"><span data-stu-id="8a752-109">Header contains words or phrases</span></span>
- <span data-ttu-id="8a752-110">Заготвка соответствует шаблонам</span><span class="sxs-lookup"><span data-stu-id="8a752-110">Header matches patterns</span></span>
- <span data-ttu-id="8a752-111">Размер документа равен или превышает</span><span class="sxs-lookup"><span data-stu-id="8a752-111">Document size equals or is greater than</span></span>
- <span data-ttu-id="8a752-112">Тип сообщения</span><span class="sxs-lookup"><span data-stu-id="8a752-112">Message type is</span></span>
- <span data-ttu-id="8a752-113">Значение сообщения</span><span class="sxs-lookup"><span data-stu-id="8a752-113">Message importance is</span></span>
- <span data-ttu-id="8a752-114">Набор символов контента содержит слова</span><span class="sxs-lookup"><span data-stu-id="8a752-114">Content character set contains words</span></span>
- <span data-ttu-id="8a752-115">Тема или тело содержит слова или фразы</span><span class="sxs-lookup"><span data-stu-id="8a752-115">Subject or body contains words or phrases</span></span>
- <span data-ttu-id="8a752-116">Шаблоны субъекта или тела</span><span class="sxs-lookup"><span data-stu-id="8a752-116">Subject or body matches patterns</span></span>
- <span data-ttu-id="8a752-117">Набор символов контента содержит слова</span><span class="sxs-lookup"><span data-stu-id="8a752-117">Content character set contains words</span></span>
- <span data-ttu-id="8a752-118">Содержимое получается из</span><span class="sxs-lookup"><span data-stu-id="8a752-118">Content is received from</span></span>
- <span data-ttu-id="8a752-119">Переопределяет подсказку политики отправитель</span><span class="sxs-lookup"><span data-stu-id="8a752-119">Has sender overridden the policy tip</span></span>
- <span data-ttu-id="8a752-120">Размер сообщения равен или превышает</span><span class="sxs-lookup"><span data-stu-id="8a752-120">Message size equals or is greater than</span></span>
- <span data-ttu-id="8a752-121">Атрибут Sender AD содержит слова или фразы</span><span class="sxs-lookup"><span data-stu-id="8a752-121">Sender AD attribute contains words or phrases</span></span>
- <span data-ttu-id="8a752-122">Атрибут Sender AD соответствует шаблонам</span><span class="sxs-lookup"><span data-stu-id="8a752-122">Sender AD attribute matches patterns</span></span>
- <span data-ttu-id="8a752-123">Содержимое документа содержит слова или фразы</span><span class="sxs-lookup"><span data-stu-id="8a752-123">Document content contains words or phrases</span></span>
- <span data-ttu-id="8a752-124">Содержимое документа совпадает с шаблонами</span><span class="sxs-lookup"><span data-stu-id="8a752-124">Document content matches patterns</span></span>

<span data-ttu-id="8a752-125">**Действия:**</span><span class="sxs-lookup"><span data-stu-id="8a752-125">**Actions:**</span></span>

- <span data-ttu-id="8a752-126">Переад. сообщение для утверждения руководителю отправи-</span><span class="sxs-lookup"><span data-stu-id="8a752-126">Forward the message for approval to sender’s manager</span></span>
- <span data-ttu-id="8a752-127">Переад. сообщение для утверждения конкретным утверждениям</span><span class="sxs-lookup"><span data-stu-id="8a752-127">Forward the message for approval to specific approvers</span></span>
- <span data-ttu-id="8a752-128">Перенаправление сообщения конкретным пользователям</span><span class="sxs-lookup"><span data-stu-id="8a752-128">Redirect the message to specific users</span></span>
- <span data-ttu-id="8a752-129">Добавление получателей в поле To</span><span class="sxs-lookup"><span data-stu-id="8a752-129">Add recipients to the To Box</span></span>
- <span data-ttu-id="8a752-130">Добавление получателей в поле Cc</span><span class="sxs-lookup"><span data-stu-id="8a752-130">Add recipients to the Cc Box</span></span>
- <span data-ttu-id="8a752-131">Добавление получателей в Bcc Box</span><span class="sxs-lookup"><span data-stu-id="8a752-131">Add recipients to the Bcc Box</span></span>
- <span data-ttu-id="8a752-132">Добавление диспетчера отправитель в качестве получателя</span><span class="sxs-lookup"><span data-stu-id="8a752-132">Add the sender’s manager as recipient</span></span>
- <span data-ttu-id="8a752-133">Добавление отказов в HTML</span><span class="sxs-lookup"><span data-stu-id="8a752-133">Add HTML disclaimer</span></span>
- <span data-ttu-id="8a752-134">Предварительная тема электронной почты</span><span class="sxs-lookup"><span data-stu-id="8a752-134">Prepend email subject</span></span>
- <span data-ttu-id="8a752-135">Удаление шифрования сообщений o365 и защиты прав</span><span class="sxs-lookup"><span data-stu-id="8a752-135">Remove O365 Message Encryption and rights protection</span></span>
- <span data-ttu-id="8a752-136">Удалить</span><span class="sxs-lookup"><span data-stu-id="8a752-136">Remove</span></span>

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a><span data-ttu-id="8a752-137">Outlook 2013 и более поздние поддерживает демонстрацию советов по политике только для некоторых условий и исключений</span><span class="sxs-lookup"><span data-stu-id="8a752-137">Outlook 2013 and later supports showing policy tips for only some conditions and exceptions</span></span>

<span data-ttu-id="8a752-138">В настоящее время Outlook 2013 и более поздние поддерживает отображение советов политики для политик, которые не содержат никаких условий или исключений, кроме указанных ниже условий и соответствующих исключений:</span><span class="sxs-lookup"><span data-stu-id="8a752-138">Currently, Outlook 2013 and later supports showing policy tips for policies which do not contain any condition or exception apart from the below mentioned conditions and corresponding exceptions :</span></span>

- <span data-ttu-id="8a752-139">Содержимое содержит (работает только для типов конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="8a752-139">Content contains (works only for Sensitive information types.</span></span> <span data-ttu-id="8a752-140">Метки конфиденциальности не поддерживаются)</span><span class="sxs-lookup"><span data-stu-id="8a752-140">Sensitivity labels are not supported)</span></span>
- <span data-ttu-id="8a752-141">Общий доступ к контенту</span><span class="sxs-lookup"><span data-stu-id="8a752-141">Content is shared</span></span>

<span data-ttu-id="8a752-142">Обратите внимание, что все условия работают для сообщений электронной почты, которые созданы в клиентских приложениях Outlook, где они будут соответствовать контенту и применять защитные меры к контенту.</span><span class="sxs-lookup"><span data-stu-id="8a752-142">Note that all the conditions work for emails authored in Outlook client app, where they will match content and enforce protective actions on content.</span></span> <span data-ttu-id="8a752-143">Однако отображение советов по политике пользователям еще не поддерживается для любых условий, которые используются отдельно от указанных выше.</span><span class="sxs-lookup"><span data-stu-id="8a752-143">However, showing policy tips to users is not yet supported for any conditions that are used apart from the ones mentioned above.</span></span>

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="8a752-144">Outlook 2013 и более поздние рекомендации по политике поддерживают только некоторые типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="8a752-144">Outlook 2013 and later supports showing policy tips for only some sensitive information types</span></span>

<span data-ttu-id="8a752-145">Список готовых типов конфиденциальной информации, которые будут обнаружены для демонстрации советов по политике DLP в Outlook on Desktop (2013 и более поздней версии):</span><span class="sxs-lookup"><span data-stu-id="8a752-145">The list of out-of-the-box sensitive information types that will be detected for showing DLP policy tips in Outlook on Desktop (2013 and later) are the following :</span></span>

- <span data-ttu-id="8a752-146">Код банка ABA</span><span class="sxs-lookup"><span data-stu-id="8a752-146">ABA Routing Number</span></span>
- <span data-ttu-id="8a752-147">Номер внутреннего удостоверения личности для Аргентины (DNI)</span><span class="sxs-lookup"><span data-stu-id="8a752-147">Argentina National Identity (DNI) Number</span></span>
- <span data-ttu-id="8a752-148">Номер банковского счета для Австралии</span><span class="sxs-lookup"><span data-stu-id="8a752-148">Australia Bank Account Number</span></span>
- <span data-ttu-id="8a752-149">Номер карты медицинского страхования для Австралии</span><span class="sxs-lookup"><span data-stu-id="8a752-149">Australia Medical Account Number</span></span>
- <span data-ttu-id="8a752-150">Номер паспорта гражданина Австралии</span><span class="sxs-lookup"><span data-stu-id="8a752-150">Australia Passport Number</span></span>
- <span data-ttu-id="8a752-151">Номер налогоплательщика для Австралии</span><span class="sxs-lookup"><span data-stu-id="8a752-151">Australia Tax File Number</span></span>
- <span data-ttu-id="8a752-152">Ключ Auth Azure DocumentDB</span><span class="sxs-lookup"><span data-stu-id="8a752-152">Azure DocumentDB Auth Key</span></span>  
- <span data-ttu-id="8a752-153">Строка подключения к базе данных Azure IAAS и строка SQL Azure</span><span class="sxs-lookup"><span data-stu-id="8a752-153">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>  
- <span data-ttu-id="8a752-154">Строка подключения к IoT Azure</span><span class="sxs-lookup"><span data-stu-id="8a752-154">Azure IoT Connection String</span></span>  
- <span data-ttu-id="8a752-155">Пароль параметра Azure Publish</span><span class="sxs-lookup"><span data-stu-id="8a752-155">Azure Publish Setting Password</span></span>  
- <span data-ttu-id="8a752-156">Строка подключения кэша Azure Redis</span><span class="sxs-lookup"><span data-stu-id="8a752-156">Azure Redis Cache Connection String</span></span>  
- <span data-ttu-id="8a752-157">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="8a752-157">Azure SAS</span></span>  
- <span data-ttu-id="8a752-158">Строка подключения к шинам службы Azure</span><span class="sxs-lookup"><span data-stu-id="8a752-158">Azure Service Bus Connection String</span></span>  
- <span data-ttu-id="8a752-159">Ключ учетной записи Azure</span><span class="sxs-lookup"><span data-stu-id="8a752-159">Azure Storage Account Key</span></span>  
- <span data-ttu-id="8a752-160">Ключ учетной записи Azure (общий)</span><span class="sxs-lookup"><span data-stu-id="8a752-160">Azure Storage Account Key (Generic)</span></span>  
- <span data-ttu-id="8a752-161">Внутренний идентификационный номер гражданина Бельгии</span><span class="sxs-lookup"><span data-stu-id="8a752-161">Belgium National Number</span></span>
- <span data-ttu-id="8a752-162">Номер CPF для Бразилии</span><span class="sxs-lookup"><span data-stu-id="8a752-162">Brazil CPF Number</span></span>
- <span data-ttu-id="8a752-163">Номер юридического лица для Бразилии (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="8a752-163">Brazil Legal Entity Number (CNPJ)</span></span>
- <span data-ttu-id="8a752-164">	Номер внутреннего удостоверения личности для Бразилии (RG)</span><span class="sxs-lookup"><span data-stu-id="8a752-164">Brazil National ID Card (RG)</span></span>
- <span data-ttu-id="8a752-165">Номер банковского счета для Канады</span><span class="sxs-lookup"><span data-stu-id="8a752-165">Canada Bank Account Number</span></span>
- <span data-ttu-id="8a752-166">Номер водительского удостоверения для Канады</span><span class="sxs-lookup"><span data-stu-id="8a752-166">Canada Driver's License Number</span></span>
- <span data-ttu-id="8a752-167">Номер службы здравоохранения для Канады</span><span class="sxs-lookup"><span data-stu-id="8a752-167">Canada Health Service Number</span></span>
- <span data-ttu-id="8a752-168">Номер паспорта гражданина Канады</span><span class="sxs-lookup"><span data-stu-id="8a752-168">Canada Passport Number</span></span>
- <span data-ttu-id="8a752-169">Персональный идентификационный номер службы здравоохранения для Канады (PHIN)</span><span class="sxs-lookup"><span data-stu-id="8a752-169">Canada Personal Health Identification Number (PHIN)</span></span>
- <span data-ttu-id="8a752-170">Номер карты социального страхования для Канады</span><span class="sxs-lookup"><span data-stu-id="8a752-170">Canada Social Insurance Number</span></span>
- <span data-ttu-id="8a752-171">	Номер удостоверения личности для Чили</span><span class="sxs-lookup"><span data-stu-id="8a752-171">Chile Identity Card Number</span></span>
- <span data-ttu-id="8a752-172">	Номер удостоверения личности жителя Китая (КНР)</span><span class="sxs-lookup"><span data-stu-id="8a752-172">China Resident Identity Card (PRC) Number</span></span>
- <span data-ttu-id="8a752-173">Номер кредитной карты</span><span class="sxs-lookup"><span data-stu-id="8a752-173">Credit Card Number</span></span>
- <span data-ttu-id="8a752-174">Номер идентификационной карты гражданина Хорватии</span><span class="sxs-lookup"><span data-stu-id="8a752-174">Croatia Identity Card Number</span></span>  
- <span data-ttu-id="8a752-175">Персональный идентификационный номер (OIB) гражданина Хорватии</span><span class="sxs-lookup"><span data-stu-id="8a752-175">Croatia Personal Identification (OIB) Number</span></span>  
- <span data-ttu-id="8a752-176">Чешский персональный номер удостоверения</span><span class="sxs-lookup"><span data-stu-id="8a752-176">Czech Personal Identity Number</span></span>  
- <span data-ttu-id="8a752-177">Персональный идентификационный номер гражданина Дании</span><span class="sxs-lookup"><span data-stu-id="8a752-177">Denmark Personal Identification Number</span></span>
- <span data-ttu-id="8a752-178">Номер Управления по борьбе с наркотиками США (DEA)</span><span class="sxs-lookup"><span data-stu-id="8a752-178">Drug Enforcement Agency (DEA) Number</span></span>
- <span data-ttu-id="8a752-179">Номер банковской карты, Европейский союз</span><span class="sxs-lookup"><span data-stu-id="8a752-179">EU Debit Card Number</span></span>
- <span data-ttu-id="8a752-180">Номер лицензии водителя ЕС</span><span class="sxs-lookup"><span data-stu-id="8a752-180">EU Driver's License Number</span></span>  
- <span data-ttu-id="8a752-181">Номер национальной идентификации ЕС</span><span class="sxs-lookup"><span data-stu-id="8a752-181">EU National Identification Number</span></span>  
- <span data-ttu-id="8a752-182">Номер паспорта ЕС</span><span class="sxs-lookup"><span data-stu-id="8a752-182">EU Passport Number</span></span>  
- <span data-ttu-id="8a752-183">Номер социального обеспечения ЕС (SSN) или эквивалентный ID</span><span class="sxs-lookup"><span data-stu-id="8a752-183">EU Social Security Number (SSN) or Equivalent ID</span></span>  
- <span data-ttu-id="8a752-184">Номер налоговой идентификации ЕС (TIN)</span><span class="sxs-lookup"><span data-stu-id="8a752-184">EU Tax Identification Number (TIN)</span></span>  
- <span data-ttu-id="8a752-185">Национальный идентификационный номер гражданина Финляндии</span><span class="sxs-lookup"><span data-stu-id="8a752-185">Finland National ID</span></span>
- <span data-ttu-id="8a752-186">Номер паспорта гражданина Финляндии</span><span class="sxs-lookup"><span data-stu-id="8a752-186">Finland Passport Number</span></span>
- <span data-ttu-id="8a752-187">Номер водительского удостоверения для Франции</span><span class="sxs-lookup"><span data-stu-id="8a752-187">France Driver's License Number</span></span>
- <span data-ttu-id="8a752-188">Национальная идентификационная карта гражданина Франции (CNI)</span><span class="sxs-lookup"><span data-stu-id="8a752-188">France National ID Card (CNI)</span></span>
- <span data-ttu-id="8a752-189">Номер паспорта гражданина Франции</span><span class="sxs-lookup"><span data-stu-id="8a752-189">France Passport Number</span></span>
- <span data-ttu-id="8a752-190">Номер социального страхования для Франции (INSEE)</span><span class="sxs-lookup"><span data-stu-id="8a752-190">France Social Security Number (INSEE)</span></span>
- <span data-ttu-id="8a752-191">Номер водительского удостоверения для Германии</span><span class="sxs-lookup"><span data-stu-id="8a752-191">German Driver's License Number</span></span>
- <span data-ttu-id="8a752-192">Номер паспорта гражданина Германии</span><span class="sxs-lookup"><span data-stu-id="8a752-192">German Passport Number</span></span>
- <span data-ttu-id="8a752-193">Номер идентификационной карты гражданина Германии</span><span class="sxs-lookup"><span data-stu-id="8a752-193">Germany Identity Card Number</span></span>
- <span data-ttu-id="8a752-194">Национальная идентификационная карта гражданина Греции</span><span class="sxs-lookup"><span data-stu-id="8a752-194">Greece National ID Card</span></span>  
- <span data-ttu-id="8a752-195">Номер удостоверения личности для Гонконга (HKID)</span><span class="sxs-lookup"><span data-stu-id="8a752-195">Hong Kong Identity Card (HKID) Number</span></span>
- <span data-ttu-id="8a752-196">Идентификационный номер налогоплательщика для Индии (PAN)</span><span class="sxs-lookup"><span data-stu-id="8a752-196">India Permanent Account Number (PAN)</span></span>
- <span data-ttu-id="8a752-197">Индивидуальный идентификационный номер (Aadhaar) для Индии</span><span class="sxs-lookup"><span data-stu-id="8a752-197">India Unique Identification (Aadhaar) Number</span></span>
- <span data-ttu-id="8a752-198">Номер удостоверения личности (KTP) для Индонезии</span><span class="sxs-lookup"><span data-stu-id="8a752-198">Indonesia Identity Card (KTP) Number</span></span>
- <span data-ttu-id="8a752-199">Международный номер банковского счета (IBAN)</span><span class="sxs-lookup"><span data-stu-id="8a752-199">International Banking Account Number (IBAN)</span></span>
- <span data-ttu-id="8a752-200">Международная классификация заболеваний (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="8a752-200">International Classification of Diseases (ICD-10-CM)</span></span>  
- <span data-ttu-id="8a752-201">Международная классификация заболеваний (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="8a752-201">International Classification of Diseases (ICD-9-CM)</span></span>  
- <span data-ttu-id="8a752-202">IP-адрес</span><span class="sxs-lookup"><span data-stu-id="8a752-202">IP Address</span></span>
- <span data-ttu-id="8a752-203">Индивидуальный социальный номер (PPS) для Ирландии</span><span class="sxs-lookup"><span data-stu-id="8a752-203">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="8a752-204">Номер банковского счета для Израиля</span><span class="sxs-lookup"><span data-stu-id="8a752-204">Israel Bank Account Number</span></span>
- <span data-ttu-id="8a752-205">Национальный идентификатор для Израиля</span><span class="sxs-lookup"><span data-stu-id="8a752-205">Israel National ID</span></span>
- <span data-ttu-id="8a752-206">Номер водительского удостоверения для Италии</span><span class="sxs-lookup"><span data-stu-id="8a752-206">Italy Driver's License Number</span></span>
- <span data-ttu-id="8a752-207">Номер банковского счета для Японии</span><span class="sxs-lookup"><span data-stu-id="8a752-207">Japan Bank Account Number</span></span>
- <span data-ttu-id="8a752-208">Номер водительского удостоверения для Японии</span><span class="sxs-lookup"><span data-stu-id="8a752-208">Japan Driver's License Number</span></span>
- <span data-ttu-id="8a752-209">Номер паспорта гражданина Японии</span><span class="sxs-lookup"><span data-stu-id="8a752-209">Japan Passport Number</span></span>
- <span data-ttu-id="8a752-210">Номер регистрации резидента Японии</span><span class="sxs-lookup"><span data-stu-id="8a752-210">Japan Resident Registration Number</span></span>
- <span data-ttu-id="8a752-211">Номер карты социального страхования для Японии (SIN)</span><span class="sxs-lookup"><span data-stu-id="8a752-211">Japan Social Insurance Number (SIN)</span></span>
- <span data-ttu-id="8a752-212">Номер карты резидента Японии</span><span class="sxs-lookup"><span data-stu-id="8a752-212">Japanese Residence Card Number</span></span>
- <span data-ttu-id="8a752-213">Номер удостоверения личности в Малайзии</span><span class="sxs-lookup"><span data-stu-id="8a752-213">Malaysia Identity Card Number</span></span>
- <span data-ttu-id="8a752-214">Номер гражданской службы для Нидерландов (BSN)</span><span class="sxs-lookup"><span data-stu-id="8a752-214">Netherlands Citizen's Service (BSN) Number</span></span>  
- <span data-ttu-id="8a752-215">Номер министерства здравоохранения для Новой Зеландии</span><span class="sxs-lookup"><span data-stu-id="8a752-215">New Zealand Ministry of Health Number</span></span>
- <span data-ttu-id="8a752-216">Идентификационный номер гражданина Норвегии</span><span class="sxs-lookup"><span data-stu-id="8a752-216">Norway Identity Number</span></span>  
- <span data-ttu-id="8a752-217">Единый многофункциональный идентификационный номер для Филиппин</span><span class="sxs-lookup"><span data-stu-id="8a752-217">Philippines Unified Multi-Purpose ID Number</span></span>
- <span data-ttu-id="8a752-218">Удостоверение личности гражданина Польши</span><span class="sxs-lookup"><span data-stu-id="8a752-218">Poland Identity Card</span></span>
- <span data-ttu-id="8a752-219">Национальный идентификационный номер гражданина Польши (PESEL)</span><span class="sxs-lookup"><span data-stu-id="8a752-219">Poland National ID (PESEL)</span></span>
- <span data-ttu-id="8a752-220">Паспорт гражданина Польши</span><span class="sxs-lookup"><span data-stu-id="8a752-220">Poland Passport</span></span>
- <span data-ttu-id="8a752-221">Номер карты гражданина Португалии</span><span class="sxs-lookup"><span data-stu-id="8a752-221">Portugal Citizen Card Number</span></span>
- <span data-ttu-id="8a752-222">Национальный идентификатор для Саудовской Аравии</span><span class="sxs-lookup"><span data-stu-id="8a752-222">Saudi Arabia National ID</span></span>
- <span data-ttu-id="8a752-223">Номер внутреннего удостоверения личности гражданина Сингапура (NRIC)</span><span class="sxs-lookup"><span data-stu-id="8a752-223">Singapore National Registration Identity Card (NRIC) Number</span></span>
- <span data-ttu-id="8a752-224">Идентификационный номер для Южной Африки</span><span class="sxs-lookup"><span data-stu-id="8a752-224">South Africa Identification Number</span></span>  
- <span data-ttu-id="8a752-225">Регистрационный номер жителя Южной Кореи</span><span class="sxs-lookup"><span data-stu-id="8a752-225">South Korea Resident Registration Number</span></span>
- <span data-ttu-id="8a752-226">Номер социального страхования Испании (SSN)</span><span class="sxs-lookup"><span data-stu-id="8a752-226">Spain Social Security Number (SSN)</span></span>
- <span data-ttu-id="8a752-227">SQL Server строка подключения</span><span class="sxs-lookup"><span data-stu-id="8a752-227">SQL Server Connection String</span></span>  
- <span data-ttu-id="8a752-228">Национальный идентификационный номер гражданина Швеции</span><span class="sxs-lookup"><span data-stu-id="8a752-228">Sweden National ID</span></span>
- <span data-ttu-id="8a752-229">Номер паспорта гражданина Швеции</span><span class="sxs-lookup"><span data-stu-id="8a752-229">Sweden Passport Number</span></span>
- <span data-ttu-id="8a752-230">Код SWIFT</span><span class="sxs-lookup"><span data-stu-id="8a752-230">SWIFT Code</span></span>
- <span data-ttu-id="8a752-231">Национальный идентификатор, Тайвань</span><span class="sxs-lookup"><span data-stu-id="8a752-231">Taiwan National ID</span></span>
- <span data-ttu-id="8a752-232">	Номер паспорта гражданина Тайваня</span><span class="sxs-lookup"><span data-stu-id="8a752-232">Taiwan Passport Number</span></span>
- <span data-ttu-id="8a752-233">Сертификат резидента Тайваня (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="8a752-233">Taiwan Resident Certificate (ARC/TARC)</span></span>
- <span data-ttu-id="8a752-234">Код идентификации населения Таиланда</span><span class="sxs-lookup"><span data-stu-id="8a752-234">Thai Population Identification Code</span></span>
- <span data-ttu-id="8a752-235">Турецкий национальный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="8a752-235">Turkish National Identification number</span></span>
- <span data-ttu-id="8a752-p103">Номер водительского удостоверения для Соединенного Королевства</span><span class="sxs-lookup"><span data-stu-id="8a752-p103">U.K. Driver's License Number</span></span>
- <span data-ttu-id="8a752-p104">Регистрационный номер избирателя для Соединенного Королевства</span><span class="sxs-lookup"><span data-stu-id="8a752-p104">U.K. Electoral Roll Number</span></span>
- <span data-ttu-id="8a752-p105">Номер национальной службы здравоохранения для Соединенного Королевства</span><span class="sxs-lookup"><span data-stu-id="8a752-p105">U.K. National Health Service Number</span></span>
- <span data-ttu-id="8a752-p106">Номер карты национального страхования для Соединенного Королевства (NINO)</span><span class="sxs-lookup"><span data-stu-id="8a752-p106">U.K. National Insurance Number (NINO)</span></span>
- <span data-ttu-id="8a752-244">U.S. / U.K.</span><span class="sxs-lookup"><span data-stu-id="8a752-244">U.S. / U.K.</span></span> <span data-ttu-id="8a752-245">Passport Number</span><span class="sxs-lookup"><span data-stu-id="8a752-245">Passport Number</span></span>
- <span data-ttu-id="8a752-246">Номер банковского счета для США</span><span class="sxs-lookup"><span data-stu-id="8a752-246">U.S. Bank Account Number</span></span>
- <span data-ttu-id="8a752-247">Номер водительского удостоверения для США</span><span class="sxs-lookup"><span data-stu-id="8a752-247">U.S. Driver's License Number</span></span>
- <span data-ttu-id="8a752-248">Идентификационный номер налогоплательщика для США (ITIN)</span><span class="sxs-lookup"><span data-stu-id="8a752-248">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="8a752-249">Страховой номер для США (SSN)</span><span class="sxs-lookup"><span data-stu-id="8a752-249">U.S. Social Security Number (SSN)</span></span>

<span data-ttu-id="8a752-250">Обратите внимание, что пользовательские типы конфиденциальной информации также поддерживаются для советов по политике DLP в дополнение к перечисленным выше типам конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="8a752-250">Please note that custom sensitive information types are also supported for DLP policy tips in addition to the above out-of-the-box sensitive information types.</span></span>

## <a name="data-loss-prevention-on-endpoint-supports-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="8a752-251">Предотвращение потери данных в конечной точке поддерживает рекомендации по политике только для некоторых типов конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="8a752-251">Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types</span></span>

<span data-ttu-id="8a752-252">Список готовых типов конфиденциальной информации, которые будут обнаруживаться в документах, проживающих на конечных устройствах, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8a752-252">The list of out-of-the-box sensitive information types that will be detected in documents residing on endpoint devices are the following :</span></span>

- <span data-ttu-id="8a752-253">Код банка ABA</span><span class="sxs-lookup"><span data-stu-id="8a752-253">ABA Routing Number</span></span> 
- <span data-ttu-id="8a752-254">Номер внутреннего удостоверения личности для Аргентины (DNI)</span><span class="sxs-lookup"><span data-stu-id="8a752-254">Argentina National Identity (DNI) Number</span></span> 
- <span data-ttu-id="8a752-255">Номер банковского счета для Австралии</span><span class="sxs-lookup"><span data-stu-id="8a752-255">Australia Bank Account Number</span></span> 
- <span data-ttu-id="8a752-256">Номер карты медицинского страхования для Австралии</span><span class="sxs-lookup"><span data-stu-id="8a752-256">Australia Medical Account Number</span></span> 
- <span data-ttu-id="8a752-257">Номер паспорта гражданина Австралии</span><span class="sxs-lookup"><span data-stu-id="8a752-257">Australia Passport Number</span></span> 
- <span data-ttu-id="8a752-258">Номер налогоплательщика для Австралии</span><span class="sxs-lookup"><span data-stu-id="8a752-258">Australia Tax File Number</span></span> 
- <span data-ttu-id="8a752-259">Австралийский номер бизнеса</span><span class="sxs-lookup"><span data-stu-id="8a752-259">Australian Business Number</span></span> 
- <span data-ttu-id="8a752-260">Австралийский номер компании</span><span class="sxs-lookup"><span data-stu-id="8a752-260">Australian Company Number</span></span> 
- <span data-ttu-id="8a752-261">Номер лицензии водителя в Австрии</span><span class="sxs-lookup"><span data-stu-id="8a752-261">Austria Driver's License Number</span></span> 
- <span data-ttu-id="8a752-262">Удостоверение личности в Австрии</span><span class="sxs-lookup"><span data-stu-id="8a752-262">Austria Identity Card</span></span> 
- <span data-ttu-id="8a752-263">Номер паспорта Австрии</span><span class="sxs-lookup"><span data-stu-id="8a752-263">Austria Passport Number</span></span> 
- <span data-ttu-id="8a752-264">Номер социального обеспечения в Австрии</span><span class="sxs-lookup"><span data-stu-id="8a752-264">Austria Social Security Number</span></span> 
- <span data-ttu-id="8a752-265">Номер идентификации налога в Австрии</span><span class="sxs-lookup"><span data-stu-id="8a752-265">Austria Tax Identification Number</span></span> 
- <span data-ttu-id="8a752-266">Номер налога на добавленную стоимость (НДС) в Австрии</span><span class="sxs-lookup"><span data-stu-id="8a752-266">Austria Value Added Tax (VAT) Number</span></span> 
- <span data-ttu-id="8a752-267">Ключ Auth Azure DocumentDB</span><span class="sxs-lookup"><span data-stu-id="8a752-267">Azure DocumentDB Auth Key</span></span> 
- <span data-ttu-id="8a752-268">Строка подключения к базе данных Azure IAAS и строка SQL Azure</span><span class="sxs-lookup"><span data-stu-id="8a752-268">Azure IAAS Database Connection String and Azure SQL Connection String</span></span> 
- <span data-ttu-id="8a752-269">Строка подключения к IoT Azure</span><span class="sxs-lookup"><span data-stu-id="8a752-269">Azure IoT Connection String</span></span> 
- <span data-ttu-id="8a752-270">Пароль параметра Azure Publish</span><span class="sxs-lookup"><span data-stu-id="8a752-270">Azure Publish Setting Password</span></span> 
- <span data-ttu-id="8a752-271">Строка подключения кэша Azure Redis</span><span class="sxs-lookup"><span data-stu-id="8a752-271">Azure Redis Cache Connection String</span></span> 
- <span data-ttu-id="8a752-272">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="8a752-272">Azure SAS</span></span> 
- <span data-ttu-id="8a752-273">Строка подключения к шинам службы Azure</span><span class="sxs-lookup"><span data-stu-id="8a752-273">Azure Service Bus Connection String</span></span> 
- <span data-ttu-id="8a752-274">Ключ учетной записи Azure</span><span class="sxs-lookup"><span data-stu-id="8a752-274">Azure Storage Account Key</span></span> 
- <span data-ttu-id="8a752-275">Ключ учетной записи Azure (общий)</span><span class="sxs-lookup"><span data-stu-id="8a752-275">Azure Storage Account Key (Generic)</span></span> 
- <span data-ttu-id="8a752-276">Номер лицензии водителя Бельгии</span><span class="sxs-lookup"><span data-stu-id="8a752-276">Belgium Driver's License Number</span></span> 
- <span data-ttu-id="8a752-277">Внутренний идентификационный номер гражданина Бельгии</span><span class="sxs-lookup"><span data-stu-id="8a752-277">Belgium National Number</span></span> 
- <span data-ttu-id="8a752-278">Номер паспорта Бельгии</span><span class="sxs-lookup"><span data-stu-id="8a752-278">Belgium Passport Number</span></span> 
- <span data-ttu-id="8a752-279">Номер налога на добавленную стоимость в Бельгии</span><span class="sxs-lookup"><span data-stu-id="8a752-279">Belgium Value Added Tax Number</span></span> 
- <span data-ttu-id="8a752-280">Номер CPF для Бразилии</span><span class="sxs-lookup"><span data-stu-id="8a752-280">Brazil CPF Number</span></span> 
- <span data-ttu-id="8a752-281">Номер юридического лица для Бразилии (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="8a752-281">Brazil Legal Entity Number (CNPJ)</span></span> 
- <span data-ttu-id="8a752-282">	Номер внутреннего удостоверения личности для Бразилии (RG)</span><span class="sxs-lookup"><span data-stu-id="8a752-282">Brazil National ID Card (RG)</span></span> 
- <span data-ttu-id="8a752-283">Номер лицензии водителя Болгарии</span><span class="sxs-lookup"><span data-stu-id="8a752-283">Bulgaria Driver's License Number</span></span> 
- <span data-ttu-id="8a752-284">Номер паспорта Болгарии</span><span class="sxs-lookup"><span data-stu-id="8a752-284">Bulgaria Passport Number</span></span> 
- <span data-ttu-id="8a752-285">Единый гражданский номер Болгарии</span><span class="sxs-lookup"><span data-stu-id="8a752-285">Bulgaria Uniform Civil Number</span></span> 
- <span data-ttu-id="8a752-286">Номер банковского счета для Канады</span><span class="sxs-lookup"><span data-stu-id="8a752-286">Canada Bank Account Number</span></span> 
- <span data-ttu-id="8a752-287">Номер водительского удостоверения для Канады</span><span class="sxs-lookup"><span data-stu-id="8a752-287">Canada Driver's License Number</span></span> 
- <span data-ttu-id="8a752-288">Номер службы здравоохранения для Канады</span><span class="sxs-lookup"><span data-stu-id="8a752-288">Canada Health Service Number</span></span> 
- <span data-ttu-id="8a752-289">Номер паспорта гражданина Канады</span><span class="sxs-lookup"><span data-stu-id="8a752-289">Canada Passport Number</span></span> 
- <span data-ttu-id="8a752-290">Персональный идентификационный номер службы здравоохранения для Канады (PHIN)</span><span class="sxs-lookup"><span data-stu-id="8a752-290">Canada Personal Health Identification Number (PHIN)</span></span> 
- <span data-ttu-id="8a752-291">Номер карты социального страхования для Канады</span><span class="sxs-lookup"><span data-stu-id="8a752-291">Canada Social Insurance Number</span></span> 
- <span data-ttu-id="8a752-292">	Номер удостоверения личности для Чили</span><span class="sxs-lookup"><span data-stu-id="8a752-292">Chile Identity Card Number</span></span> 
- <span data-ttu-id="8a752-293">	Номер удостоверения личности жителя Китая (КНР)</span><span class="sxs-lookup"><span data-stu-id="8a752-293">China Resident Identity Card (PRC) Number</span></span> 
- <span data-ttu-id="8a752-294">Номер кредитной карты</span><span class="sxs-lookup"><span data-stu-id="8a752-294">Credit Card Number</span></span> 
- <span data-ttu-id="8a752-295">Номер лицензии водителя в Хорватии</span><span class="sxs-lookup"><span data-stu-id="8a752-295">Croatia Driver's License Number</span></span> 
- <span data-ttu-id="8a752-296">Номер идентификационной карты гражданина Хорватии</span><span class="sxs-lookup"><span data-stu-id="8a752-296">Croatia Identity Card Number</span></span> 
- <span data-ttu-id="8a752-297">Номер национальной ID-карты Хорватии</span><span class="sxs-lookup"><span data-stu-id="8a752-297">Croatia National ID Card Number</span></span> 
- <span data-ttu-id="8a752-298">Номер паспорта Хорватии</span><span class="sxs-lookup"><span data-stu-id="8a752-298">Croatia Passport Number</span></span> 
- <span data-ttu-id="8a752-299">Персональный идентификационный номер (OIB) гражданина Хорватии</span><span class="sxs-lookup"><span data-stu-id="8a752-299">Croatia Personal Identification (OIB) Number</span></span> 
- <span data-ttu-id="8a752-300">CSCAN-AZURE0060 Azure Storage Account Shared Access Signature</span><span class="sxs-lookup"><span data-stu-id="8a752-300">CSCAN-AZURE0060 Azure Storage Account Shared Access Signature</span></span> 
- <span data-ttu-id="8a752-301">CSCAN-GENERAL0140 General Symmetric Key</span><span class="sxs-lookup"><span data-stu-id="8a752-301">CSCAN-GENERAL0140 General Symmetric Key</span></span> 
- <span data-ttu-id="8a752-302">Номер лицензии водителя На Кипре</span><span class="sxs-lookup"><span data-stu-id="8a752-302">Cyprus Driver's License Number</span></span> 
- <span data-ttu-id="8a752-303">Удостоверение личности на Кипре</span><span class="sxs-lookup"><span data-stu-id="8a752-303">Cyprus Identity Card</span></span> 
- <span data-ttu-id="8a752-304">Номер паспорта Кипра</span><span class="sxs-lookup"><span data-stu-id="8a752-304">Cyprus Passport Number</span></span> 
- <span data-ttu-id="8a752-305">Номер идентификации налога на Кипр</span><span class="sxs-lookup"><span data-stu-id="8a752-305">Cyprus Tax Identification Number</span></span> 
- <span data-ttu-id="8a752-306">Номер лицензии чешского водителя</span><span class="sxs-lookup"><span data-stu-id="8a752-306">Czech Driver's License Number</span></span> 
- <span data-ttu-id="8a752-307">Чешский персональный номер удостоверения</span><span class="sxs-lookup"><span data-stu-id="8a752-307">Czech Personal Identity Number</span></span> 
- <span data-ttu-id="8a752-308">Номер паспорта Чешской Республики</span><span class="sxs-lookup"><span data-stu-id="8a752-308">Czech Republic Passport Number</span></span> 
- <span data-ttu-id="8a752-309">Номер водительских прав Дании</span><span class="sxs-lookup"><span data-stu-id="8a752-309">Denmark Driver's License Number</span></span> 
- <span data-ttu-id="8a752-310">Номер паспорта Дании</span><span class="sxs-lookup"><span data-stu-id="8a752-310">Denmark Passport Number</span></span> 
- <span data-ttu-id="8a752-311">Персональный идентификационный номер гражданина Дании</span><span class="sxs-lookup"><span data-stu-id="8a752-311">Denmark Personal Identification Number</span></span> 
- <span data-ttu-id="8a752-312">Номер Управления по борьбе с наркотиками США (DEA)</span><span class="sxs-lookup"><span data-stu-id="8a752-312">Drug Enforcement Agency (DEA) Number</span></span> 
- <span data-ttu-id="8a752-313">Номер водительских прав Эстонии</span><span class="sxs-lookup"><span data-stu-id="8a752-313">Estonia Driver's License Number</span></span> 
- <span data-ttu-id="8a752-314">Номер паспорта Эстонии</span><span class="sxs-lookup"><span data-stu-id="8a752-314">Estonia Passport Number</span></span> 
- <span data-ttu-id="8a752-315">Код личной идентификации Эстонии</span><span class="sxs-lookup"><span data-stu-id="8a752-315">Estonia Personal Identification Code</span></span> 
- <span data-ttu-id="8a752-316">Номер банковской карты, Европейский союз</span><span class="sxs-lookup"><span data-stu-id="8a752-316">EU Debit Card Number</span></span> 
- <span data-ttu-id="8a752-317">Номер лицензии водителя ЕС</span><span class="sxs-lookup"><span data-stu-id="8a752-317">EU Driver's License Number</span></span> 
- <span data-ttu-id="8a752-318">Номер национальной идентификации ЕС</span><span class="sxs-lookup"><span data-stu-id="8a752-318">EU National Identification Number</span></span> 
- <span data-ttu-id="8a752-319">Номер паспорта ЕС</span><span class="sxs-lookup"><span data-stu-id="8a752-319">EU Passport Number</span></span> 
- <span data-ttu-id="8a752-320">Номер социального обеспечения ЕС (SSN) или эквивалентный ID</span><span class="sxs-lookup"><span data-stu-id="8a752-320">EU Social Security Number (SSN) or Equivalent ID</span></span> 
- <span data-ttu-id="8a752-321">Номер налоговой идентификации ЕС (TIN)</span><span class="sxs-lookup"><span data-stu-id="8a752-321">EU Tax Identification Number (TIN)</span></span> 
- <span data-ttu-id="8a752-322">Номер лицензии водителя Финляндии</span><span class="sxs-lookup"><span data-stu-id="8a752-322">Finland Driver's License Number</span></span> 
- <span data-ttu-id="8a752-323">Номер Европейского медицинского страхования Финляндии</span><span class="sxs-lookup"><span data-stu-id="8a752-323">Finland European Health Insurance Number</span></span> 
- <span data-ttu-id="8a752-324">Национальный идентификационный номер гражданина Финляндии</span><span class="sxs-lookup"><span data-stu-id="8a752-324">Finland National ID</span></span> 
- <span data-ttu-id="8a752-325">Номер паспорта гражданина Финляндии</span><span class="sxs-lookup"><span data-stu-id="8a752-325">Finland Passport Number</span></span> 
- <span data-ttu-id="8a752-326">Номер водительского удостоверения для Франции</span><span class="sxs-lookup"><span data-stu-id="8a752-326">France Driver's License Number</span></span> 
- <span data-ttu-id="8a752-327">Номер медицинского страхования Франции</span><span class="sxs-lookup"><span data-stu-id="8a752-327">France Health Insurance Number</span></span> 
- <span data-ttu-id="8a752-328">Национальная идентификационная карта гражданина Франции (CNI)</span><span class="sxs-lookup"><span data-stu-id="8a752-328">France National ID Card (CNI)</span></span> 
- <span data-ttu-id="8a752-329">Номер паспорта гражданина Франции</span><span class="sxs-lookup"><span data-stu-id="8a752-329">France Passport Number</span></span> 
- <span data-ttu-id="8a752-330">Номер социального страхования для Франции (INSEE)</span><span class="sxs-lookup"><span data-stu-id="8a752-330">France Social Security Number (INSEE)</span></span> 
- <span data-ttu-id="8a752-331">Номер идентификации налога франции (numéro SPI.)</span><span class="sxs-lookup"><span data-stu-id="8a752-331">France Tax Identification Number (numéro SPI.)</span></span> 
- <span data-ttu-id="8a752-332">Номер налога на добавленную стоимость во Франции</span><span class="sxs-lookup"><span data-stu-id="8a752-332">France Value Added Tax Number</span></span> 
- <span data-ttu-id="8a752-333">Номер водительского удостоверения для Германии</span><span class="sxs-lookup"><span data-stu-id="8a752-333">German Driver's License Number</span></span> 
- <span data-ttu-id="8a752-334">Номер паспорта гражданина Германии</span><span class="sxs-lookup"><span data-stu-id="8a752-334">German Passport Number</span></span> 
- <span data-ttu-id="8a752-335">Номер идентификационной карты гражданина Германии</span><span class="sxs-lookup"><span data-stu-id="8a752-335">Germany Identity Card Number</span></span> 
- <span data-ttu-id="8a752-336">Номер идентификации налога в Германии</span><span class="sxs-lookup"><span data-stu-id="8a752-336">Germany Tax Identification Number</span></span> 
- <span data-ttu-id="8a752-337">Номер налога на добавленную стоимость в Германии</span><span class="sxs-lookup"><span data-stu-id="8a752-337">Germany Value Added Tax Number</span></span> 
- <span data-ttu-id="8a752-338">Номер лицензии водителя в Греции</span><span class="sxs-lookup"><span data-stu-id="8a752-338">Greece Driver's License Number</span></span> 
- <span data-ttu-id="8a752-339">Национальная идентификационная карта гражданина Греции</span><span class="sxs-lookup"><span data-stu-id="8a752-339">Greece National ID Card</span></span> 
- <span data-ttu-id="8a752-340">Номер паспорта Греции</span><span class="sxs-lookup"><span data-stu-id="8a752-340">Greece Passport Number</span></span> 
- <span data-ttu-id="8a752-341">Номер социального обеспечения Греции (AMKA)</span><span class="sxs-lookup"><span data-stu-id="8a752-341">Greece Social Security Number (AMKA)</span></span> 
- <span data-ttu-id="8a752-342">Греческий номер налоговой идентификации</span><span class="sxs-lookup"><span data-stu-id="8a752-342">Greek Tax identification Number</span></span> 
- <span data-ttu-id="8a752-343">Номер удостоверения личности для Гонконга (HKID)</span><span class="sxs-lookup"><span data-stu-id="8a752-343">Hong Kong Identity Card (HKID) Number</span></span> 
- <span data-ttu-id="8a752-344">Венгерский номер социального обеспечения (TAJ)</span><span class="sxs-lookup"><span data-stu-id="8a752-344">Hungarian Social Security Number (TAJ)</span></span> 
- <span data-ttu-id="8a752-345">Номер налога на добавленную стоимость в Венгрии</span><span class="sxs-lookup"><span data-stu-id="8a752-345">Hungarian Value Added Tax Number</span></span> 
- <span data-ttu-id="8a752-346">Номер лицензии водителя Венгрии</span><span class="sxs-lookup"><span data-stu-id="8a752-346">Hungary Driver's License Number</span></span> 
- <span data-ttu-id="8a752-347">Номер паспорта Венгрии</span><span class="sxs-lookup"><span data-stu-id="8a752-347">Hungary Passport Number</span></span> 
- <span data-ttu-id="8a752-348">Личный идентификационный номер Венгрии</span><span class="sxs-lookup"><span data-stu-id="8a752-348">Hungary Personal Identification Number</span></span> 
- <span data-ttu-id="8a752-349">Номер идентификации налога в Венгрии</span><span class="sxs-lookup"><span data-stu-id="8a752-349">Hungary Tax identification Number</span></span> 
- <span data-ttu-id="8a752-350">Идентификационный номер налогоплательщика для Индии (PAN)</span><span class="sxs-lookup"><span data-stu-id="8a752-350">India Permanent Account Number (PAN)</span></span> 
- <span data-ttu-id="8a752-351">Индивидуальный идентификационный номер (Aadhaar) для Индии</span><span class="sxs-lookup"><span data-stu-id="8a752-351">India Unique Identification (Aadhaar) Number</span></span> 
- <span data-ttu-id="8a752-352">Номер удостоверения личности (KTP) для Индонезии</span><span class="sxs-lookup"><span data-stu-id="8a752-352">Indonesia Identity Card (KTP) Number</span></span> 
- <span data-ttu-id="8a752-353">Международный номер банковского счета (IBAN)</span><span class="sxs-lookup"><span data-stu-id="8a752-353">International Banking Account Number (IBAN)</span></span> 
- <span data-ttu-id="8a752-354">Международная классификация заболеваний (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="8a752-354">International Classification of Diseases (ICD-10-CM)</span></span> 
- <span data-ttu-id="8a752-355">Международная классификация заболеваний (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="8a752-355">International Classification of Diseases (ICD-9-CM)</span></span> 
- <span data-ttu-id="8a752-356">IP-адрес</span><span class="sxs-lookup"><span data-stu-id="8a752-356">IP Address</span></span> 
- <span data-ttu-id="8a752-357">Номер лицензии водителя Ирландии</span><span class="sxs-lookup"><span data-stu-id="8a752-357">Ireland Driver's License Number</span></span> 
- <span data-ttu-id="8a752-358">Номер паспорта Ирландии</span><span class="sxs-lookup"><span data-stu-id="8a752-358">Ireland Passport Number</span></span> 
- <span data-ttu-id="8a752-359">Индивидуальный социальный номер (PPS) для Ирландии</span><span class="sxs-lookup"><span data-stu-id="8a752-359">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="8a752-360">Номер банковского счета для Израиля</span><span class="sxs-lookup"><span data-stu-id="8a752-360">Israel Bank Account Number</span></span> 
- <span data-ttu-id="8a752-361">Национальный идентификатор для Израиля</span><span class="sxs-lookup"><span data-stu-id="8a752-361">Israel National ID</span></span> 
- <span data-ttu-id="8a752-362">Номер водительского удостоверения для Италии</span><span class="sxs-lookup"><span data-stu-id="8a752-362">Italy Driver's License Number</span></span> 
- <span data-ttu-id="8a752-363">Финансовый кодекс Италии</span><span class="sxs-lookup"><span data-stu-id="8a752-363">Italy Fiscal Code</span></span> 
- <span data-ttu-id="8a752-364">Номер паспорта Италии</span><span class="sxs-lookup"><span data-stu-id="8a752-364">Italy Passport Number</span></span> 
- <span data-ttu-id="8a752-365">Номер налога на добавленную стоимость в Италии</span><span class="sxs-lookup"><span data-stu-id="8a752-365">Italy Value Added Tax Number</span></span> 
- <span data-ttu-id="8a752-366">Номер банковского счета для Японии</span><span class="sxs-lookup"><span data-stu-id="8a752-366">Japan Bank Account Number</span></span> 
- <span data-ttu-id="8a752-367">Номер водительского удостоверения для Японии</span><span class="sxs-lookup"><span data-stu-id="8a752-367">Japan Driver's License Number</span></span> 
- <span data-ttu-id="8a752-368">Номер паспорта гражданина Японии</span><span class="sxs-lookup"><span data-stu-id="8a752-368">Japan Passport Number</span></span> 
- <span data-ttu-id="8a752-369">Номер регистрации резидента Японии</span><span class="sxs-lookup"><span data-stu-id="8a752-369">Japan Resident Registration Number</span></span> 
- <span data-ttu-id="8a752-370">Номер карты социального страхования для Японии (SIN)</span><span class="sxs-lookup"><span data-stu-id="8a752-370">Japan Social Insurance Number (SIN)</span></span> 
- <span data-ttu-id="8a752-371">Японский My Number Corporate</span><span class="sxs-lookup"><span data-stu-id="8a752-371">Japanese My Number Corporate</span></span> 
- <span data-ttu-id="8a752-372">Японский Мой номер личный</span><span class="sxs-lookup"><span data-stu-id="8a752-372">Japanese My Number Personal</span></span> 
- <span data-ttu-id="8a752-373">Номер карты резидента Японии</span><span class="sxs-lookup"><span data-stu-id="8a752-373">Japanese Residence Card Number</span></span> 
- <span data-ttu-id="8a752-374">Номер лицензии водителя в Латвии</span><span class="sxs-lookup"><span data-stu-id="8a752-374">Latvia Driver's License Number</span></span> 
- <span data-ttu-id="8a752-375">Номер паспорта Латвии</span><span class="sxs-lookup"><span data-stu-id="8a752-375">Latvia Passport Number</span></span> 
- <span data-ttu-id="8a752-376">Личный код Латвии</span><span class="sxs-lookup"><span data-stu-id="8a752-376">Latvia Personal Code</span></span> 
- <span data-ttu-id="8a752-377">Номер лицензии водителя Литвы</span><span class="sxs-lookup"><span data-stu-id="8a752-377">Lithuania Driver's License Number</span></span> 
- <span data-ttu-id="8a752-378">Номер паспорта Литвы</span><span class="sxs-lookup"><span data-stu-id="8a752-378">Lithuania Passport Number</span></span> 
- <span data-ttu-id="8a752-379">Личный код Литвы</span><span class="sxs-lookup"><span data-stu-id="8a752-379">Lithuania Personal Code</span></span> 
- <span data-ttu-id="8a752-380">Номер лицензии водителя в Люксембурге</span><span class="sxs-lookup"><span data-stu-id="8a752-380">Luxemburg Driver's License Number</span></span> 
- <span data-ttu-id="8a752-381">Национальный идентификационный номер Люксембурга (природные лица)</span><span class="sxs-lookup"><span data-stu-id="8a752-381">Luxemburg National Identification Number (Natural persons)</span></span> 
- <span data-ttu-id="8a752-382">Номер национального идентификации в Люксембурге (не естественное лицо)</span><span class="sxs-lookup"><span data-stu-id="8a752-382">Luxemburg National Identification Number (Non-natural persons)</span></span> 
- <span data-ttu-id="8a752-383">Номер паспорта Люксембурга</span><span class="sxs-lookup"><span data-stu-id="8a752-383">Luxemburg Passport Number</span></span> 
- <span data-ttu-id="8a752-384">Номер удостоверения личности в Малайзии</span><span class="sxs-lookup"><span data-stu-id="8a752-384">Malaysia Identity Card Number</span></span> 
- <span data-ttu-id="8a752-385">Номер лицензии водителя Мальты</span><span class="sxs-lookup"><span data-stu-id="8a752-385">Malta Driver's License Number</span></span> 
- <span data-ttu-id="8a752-386">Номер удостоверения личности Мальты</span><span class="sxs-lookup"><span data-stu-id="8a752-386">Malta Identity Card Number</span></span> 
- <span data-ttu-id="8a752-387">Номер паспорта Мальты</span><span class="sxs-lookup"><span data-stu-id="8a752-387">Malta Passport Number</span></span> 
- <span data-ttu-id="8a752-388">Номер налогового номера Мальты</span><span class="sxs-lookup"><span data-stu-id="8a752-388">Malta Tax ID Number</span></span> 
- <span data-ttu-id="8a752-389">Номер гражданской службы для Нидерландов (BSN)</span><span class="sxs-lookup"><span data-stu-id="8a752-389">Netherlands Citizen's Service (BSN) Number</span></span> 
- <span data-ttu-id="8a752-390">Номер лицензии водителя Нидерландов</span><span class="sxs-lookup"><span data-stu-id="8a752-390">Netherlands Driver's License Number</span></span> 
- <span data-ttu-id="8a752-391">Номер паспорта Нидерландов</span><span class="sxs-lookup"><span data-stu-id="8a752-391">Netherlands Passport Number</span></span> 
- <span data-ttu-id="8a752-392">Номер налоговой идентификации в Нидерландах</span><span class="sxs-lookup"><span data-stu-id="8a752-392">Netherlands Tax Identification Number</span></span> 
- <span data-ttu-id="8a752-393">Номер налога на добавленную стоимость в Нидерландах</span><span class="sxs-lookup"><span data-stu-id="8a752-393">Netherlands Value Added Tax Number</span></span> 
- <span data-ttu-id="8a752-394">Номер банковского счета в Новой Зеландии</span><span class="sxs-lookup"><span data-stu-id="8a752-394">New Zealand bank account number</span></span> 
- <span data-ttu-id="8a752-395">Номер лицензии водителя в Новой Зеландии</span><span class="sxs-lookup"><span data-stu-id="8a752-395">New Zealand Driver License Number</span></span> 
- <span data-ttu-id="8a752-396">Номер внутренних доходов Новой Зеландии</span><span class="sxs-lookup"><span data-stu-id="8a752-396">New Zealand Inland Revenue number</span></span> 
- <span data-ttu-id="8a752-397">Номер министерства здравоохранения для Новой Зеландии</span><span class="sxs-lookup"><span data-stu-id="8a752-397">New Zealand Ministry of Health Number</span></span> 
- <span data-ttu-id="8a752-398">Номер социального обеспечения Новой Зеландии</span><span class="sxs-lookup"><span data-stu-id="8a752-398">New Zealand Social Welfare Number</span></span> 
- <span data-ttu-id="8a752-399">Идентификационный номер гражданина Норвегии</span><span class="sxs-lookup"><span data-stu-id="8a752-399">Norway Identity Number</span></span> 
- <span data-ttu-id="8a752-400">Единый многофункциональный идентификационный номер для Филиппин</span><span class="sxs-lookup"><span data-stu-id="8a752-400">Philippines Unified Multi-Purpose ID Number</span></span> 
- <span data-ttu-id="8a752-401">Номер лицензии водителя в Польше</span><span class="sxs-lookup"><span data-stu-id="8a752-401">Poland Driver's License Number</span></span> 
- <span data-ttu-id="8a752-402">Удостоверение личности гражданина Польши</span><span class="sxs-lookup"><span data-stu-id="8a752-402">Poland Identity Card</span></span> 
- <span data-ttu-id="8a752-403">Национальный идентификационный номер гражданина Польши (PESEL)</span><span class="sxs-lookup"><span data-stu-id="8a752-403">Poland National ID (PESEL)</span></span> 
- <span data-ttu-id="8a752-404">Паспорт гражданина Польши</span><span class="sxs-lookup"><span data-stu-id="8a752-404">Poland Passport</span></span> 
- <span data-ttu-id="8a752-405">Номер налоговой идентификации в Польше</span><span class="sxs-lookup"><span data-stu-id="8a752-405">Poland Tax Identification Number</span></span> 
- <span data-ttu-id="8a752-406">Польский номер REGON</span><span class="sxs-lookup"><span data-stu-id="8a752-406">Polish REGON Number</span></span> 
- <span data-ttu-id="8a752-407">Номер карты гражданина Португалии</span><span class="sxs-lookup"><span data-stu-id="8a752-407">Portugal Citizen Card Number</span></span> 
- <span data-ttu-id="8a752-408">Номер лицензии водителя Португалии</span><span class="sxs-lookup"><span data-stu-id="8a752-408">Portugal Driver's License Number</span></span> 
- <span data-ttu-id="8a752-409">Номер паспорта Португалии</span><span class="sxs-lookup"><span data-stu-id="8a752-409">Portugal Passport Number</span></span> 
- <span data-ttu-id="8a752-410">Номер идентификации налога в Португалии</span><span class="sxs-lookup"><span data-stu-id="8a752-410">Portugal Tax Identification Number</span></span> 
- <span data-ttu-id="8a752-411">Номер лицензии водителя в Румынии</span><span class="sxs-lookup"><span data-stu-id="8a752-411">Romania Driver's License Number</span></span> 
- <span data-ttu-id="8a752-412">Номер паспорта Румынии</span><span class="sxs-lookup"><span data-stu-id="8a752-412">Romania Passport Number</span></span> 
- <span data-ttu-id="8a752-413">Личный числимый код Румынии (CNP)</span><span class="sxs-lookup"><span data-stu-id="8a752-413">Romania Personal Numerical Code (CNP)</span></span> 
- <span data-ttu-id="8a752-414">Номер российского паспорта (внутренний)</span><span class="sxs-lookup"><span data-stu-id="8a752-414">Russian Passport Number (Domestic)</span></span> 
- <span data-ttu-id="8a752-415">Номер российского паспорта (Международный)</span><span class="sxs-lookup"><span data-stu-id="8a752-415">Russian Passport Number (International)</span></span> 
- <span data-ttu-id="8a752-416">Национальный идентификатор для Саудовской Аравии</span><span class="sxs-lookup"><span data-stu-id="8a752-416">Saudi Arabia National ID</span></span> 
- <span data-ttu-id="8a752-417">Номер внутреннего удостоверения личности гражданина Сингапура (NRIC)</span><span class="sxs-lookup"><span data-stu-id="8a752-417">Singapore National Registration Identity Card (NRIC) Number</span></span> 
- <span data-ttu-id="8a752-418">Номер лицензии водителя Словакии</span><span class="sxs-lookup"><span data-stu-id="8a752-418">Slovakia Driver's License Number</span></span> 
- <span data-ttu-id="8a752-419">Номер паспорта Словакии</span><span class="sxs-lookup"><span data-stu-id="8a752-419">Slovakia Passport Number</span></span> 
- <span data-ttu-id="8a752-420">Личный номер Словакии</span><span class="sxs-lookup"><span data-stu-id="8a752-420">Slovakia Personal Number</span></span> 
- <span data-ttu-id="8a752-421">Номер лицензии водителя Словении</span><span class="sxs-lookup"><span data-stu-id="8a752-421">Slovenia Driver's License Number</span></span> 
- <span data-ttu-id="8a752-422">Номер паспорта Словении</span><span class="sxs-lookup"><span data-stu-id="8a752-422">Slovenia Passport Number</span></span> 
- <span data-ttu-id="8a752-423">Номер идентификации налога в Словении</span><span class="sxs-lookup"><span data-stu-id="8a752-423">Slovenia Tax Identification Number</span></span> 
- <span data-ttu-id="8a752-424">Уникальный номер гражданина Словении</span><span class="sxs-lookup"><span data-stu-id="8a752-424">Slovenia Unique Master Citizen Number</span></span> 
- <span data-ttu-id="8a752-425">Идентификационный номер для Южной Африки</span><span class="sxs-lookup"><span data-stu-id="8a752-425">South Africa Identification Number</span></span> 
- <span data-ttu-id="8a752-426">Регистрационный номер жителя Южной Кореи</span><span class="sxs-lookup"><span data-stu-id="8a752-426">South Korea Resident Registration Number</span></span> 
- <span data-ttu-id="8a752-427">DNI Испании</span><span class="sxs-lookup"><span data-stu-id="8a752-427">Spain DNI</span></span> 
- <span data-ttu-id="8a752-428">Номер лицензии водителя Испании</span><span class="sxs-lookup"><span data-stu-id="8a752-428">Spain Driver's License Number</span></span> 
- <span data-ttu-id="8a752-429">Номер паспорта Испании</span><span class="sxs-lookup"><span data-stu-id="8a752-429">Spain Passport Number</span></span> 
- <span data-ttu-id="8a752-430">Номер социального страхования Испании (SSN)</span><span class="sxs-lookup"><span data-stu-id="8a752-430">Spain Social Security Number (SSN)</span></span> 
- <span data-ttu-id="8a752-431">Номер идентификации налога в Испании</span><span class="sxs-lookup"><span data-stu-id="8a752-431">Spain Tax Identification Number</span></span> 
- <span data-ttu-id="8a752-432">SQL Server строка подключения</span><span class="sxs-lookup"><span data-stu-id="8a752-432">SQL Server Connection String</span></span> 
- <span data-ttu-id="8a752-433">Номер лицензии водителя Швеции</span><span class="sxs-lookup"><span data-stu-id="8a752-433">Sweden Driver's License Number</span></span> 
- <span data-ttu-id="8a752-434">Национальный идентификационный номер гражданина Швеции</span><span class="sxs-lookup"><span data-stu-id="8a752-434">Sweden National ID</span></span> 
- <span data-ttu-id="8a752-435">Номер паспорта гражданина Швеции</span><span class="sxs-lookup"><span data-stu-id="8a752-435">Sweden Passport Number</span></span> 
- <span data-ttu-id="8a752-436">Номер идентификации налога в Швеции</span><span class="sxs-lookup"><span data-stu-id="8a752-436">Sweden Tax Identification Number</span></span> 
- <span data-ttu-id="8a752-437">Код SWIFT</span><span class="sxs-lookup"><span data-stu-id="8a752-437">SWIFT Code</span></span> 
- <span data-ttu-id="8a752-438">Швейцарский номер социального обеспечения AHV</span><span class="sxs-lookup"><span data-stu-id="8a752-438">Swiss Social Security Number AHV</span></span> 
- <span data-ttu-id="8a752-439">Национальный идентификатор, Тайвань</span><span class="sxs-lookup"><span data-stu-id="8a752-439">Taiwan National ID</span></span> 
- <span data-ttu-id="8a752-440">	Номер паспорта гражданина Тайваня</span><span class="sxs-lookup"><span data-stu-id="8a752-440">Taiwan Passport Number</span></span> 
- <span data-ttu-id="8a752-441">Сертификат резидента Тайваня (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="8a752-441">Taiwan Resident Certificate (ARC/TARC)</span></span> 
- <span data-ttu-id="8a752-442">Код идентификации населения Таиланда</span><span class="sxs-lookup"><span data-stu-id="8a752-442">Thai Population Identification Code</span></span> 
- <span data-ttu-id="8a752-443">Турецкий национальный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="8a752-443">Turkish National Identification number</span></span> 
- <span data-ttu-id="8a752-p108">Номер водительского удостоверения для Соединенного Королевства</span><span class="sxs-lookup"><span data-stu-id="8a752-p108">U.K. Driver's License Number</span></span> 
- <span data-ttu-id="8a752-p109">Регистрационный номер избирателя для Соединенного Королевства</span><span class="sxs-lookup"><span data-stu-id="8a752-p109">U.K. Electoral Roll Number</span></span> 
- <span data-ttu-id="8a752-p110">Номер национальной службы здравоохранения для Соединенного Королевства</span><span class="sxs-lookup"><span data-stu-id="8a752-p110">U.K. National Health Service Number</span></span> 
- <span data-ttu-id="8a752-p111">Номер карты национального страхования для Соединенного Королевства (NINO)</span><span class="sxs-lookup"><span data-stu-id="8a752-p111">U.K. National Insurance Number (NINO)</span></span> 
- <span data-ttu-id="8a752-452">U.K.</span><span class="sxs-lookup"><span data-stu-id="8a752-452">U.K.</span></span> <span data-ttu-id="8a752-453">Уникальный номер ссылки на налогоплательщика</span><span class="sxs-lookup"><span data-stu-id="8a752-453">Unique Taxpayer Reference Number</span></span> 
- <span data-ttu-id="8a752-454">U.S. / U.K.</span><span class="sxs-lookup"><span data-stu-id="8a752-454">U.S. / U.K.</span></span> <span data-ttu-id="8a752-455">Passport Number</span><span class="sxs-lookup"><span data-stu-id="8a752-455">Passport Number</span></span> 
- <span data-ttu-id="8a752-456">Номер банковского счета для США</span><span class="sxs-lookup"><span data-stu-id="8a752-456">U.S. Bank Account Number</span></span> 
- <span data-ttu-id="8a752-457">Номер водительского удостоверения для США</span><span class="sxs-lookup"><span data-stu-id="8a752-457">U.S. Driver's License Number</span></span> 
- <span data-ttu-id="8a752-458">Идентификационный номер налогоплательщика для США (ITIN)</span><span class="sxs-lookup"><span data-stu-id="8a752-458">U.S. Individual Taxpayer Identification Number (ITIN)</span></span> 
- <span data-ttu-id="8a752-459">Страховой номер для США (SSN)</span><span class="sxs-lookup"><span data-stu-id="8a752-459">U.S. Social Security Number (SSN)</span></span> 
- <span data-ttu-id="8a752-460">Номер паспорта Украины (внутренний)</span><span class="sxs-lookup"><span data-stu-id="8a752-460">Ukraine Passport Number (Domestic)</span></span> 
- <span data-ttu-id="8a752-461">Номер паспорта Украины (Международный)</span><span class="sxs-lookup"><span data-stu-id="8a752-461">Ukraine Passport Number (International)</span></span> 
 
<span data-ttu-id="8a752-462">Обратите внимание, что настраиваемые типы конфиденциальной информации также будут обнаружены в дополнение к перечисленным выше типам конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="8a752-462">Please note that custom sensitive information types will also be detected in addition to the above out-of-the-box sensitive information types</span></span>

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a><span data-ttu-id="8a752-463">Советы по поддержке матрицы политики DLP в приложениях Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8a752-463">Support Matrix for DLP policy tips across Microsoft apps</span></span>

|<span data-ttu-id="8a752-464">**Приложение и платформа**</span><span class="sxs-lookup"><span data-stu-id="8a752-464">**App and platform**</span></span>|<span data-ttu-id="8a752-465">**Поддержка отзывов политики DLP**</span><span class="sxs-lookup"><span data-stu-id="8a752-465">**DLP policy tip support**</span></span>|<span data-ttu-id="8a752-466">**Поддерживаемые типы конфиденциальной информации**</span><span class="sxs-lookup"><span data-stu-id="8a752-466">**Sensitive information types supported**</span></span>|<span data-ttu-id="8a752-467">**Предикаты и поддерживаемые действия**</span><span class="sxs-lookup"><span data-stu-id="8a752-467">**Predicates and actions supported**</span></span>|<span data-ttu-id="8a752-468">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="8a752-468">**Comments**</span></span>|
|:--|:--|:--|:--|:--|
|<span data-ttu-id="8a752-469">**Outlook Web Access**.</span><span class="sxs-lookup"><span data-stu-id="8a752-469">**Outlook Web Access**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="8a752-470">Все</span><span class="sxs-lookup"><span data-stu-id="8a752-470">All</span></span>|<span data-ttu-id="8a752-471">Subset</span><span class="sxs-lookup"><span data-stu-id="8a752-471">Subset</span></span>|<span data-ttu-id="8a752-472">См. ссылку на рекомендации по [предотвращению потери данных](#data-loss-prevention-policy-tips-reference)</span><span class="sxs-lookup"><span data-stu-id="8a752-472">See [Data Loss Prevention policy tips reference](#data-loss-prevention-policy-tips-reference)</span></span>|
|<span data-ttu-id="8a752-473">**Outlook Win32 (Outlook 2013 и более)**</span><span class="sxs-lookup"><span data-stu-id="8a752-473">**Outlook Win32 (Outlook 2013 and beyond)**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="8a752-474">Subset</span><span class="sxs-lookup"><span data-stu-id="8a752-474">Subset</span></span>|<span data-ttu-id="8a752-475">Subset</span><span class="sxs-lookup"><span data-stu-id="8a752-475">Subset</span></span>|<span data-ttu-id="8a752-476">См. в outlook [2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) и более поздних поддержках рекомендаций по политике только для некоторых условий и исключений и [Outlook 2013,](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-sensitive-information-types) а затем поддерживает демонстрацию советов по политике только для некоторых типов конфиденциальной информации для получения сведений о поддержке типов конфиденциальной информации и условий DLP и действий, поддерживаемых для демонстрации советов по политике DLP в Outlook Win32.</span><span class="sxs-lookup"><span data-stu-id="8a752-476">See [Outlook 2013 and later supports showing policy tips for only some conditions and exceptions](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) and [Outlook 2013 and later supports showing policy tips for only some sensitive information types](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-sensitive-information-types) for details on support for sensitive information types and DLP conditions and actions supported for showing DLP policy tips on Outlook Win32.</span></span>|
|<span data-ttu-id="8a752-477">**Outlook Mobile (iOS, Android)/Outlook Mac**</span><span class="sxs-lookup"><span data-stu-id="8a752-477">**Outlook Mobile (iOS, Android)/Outlook Mac**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="8a752-478">Нет</span><span class="sxs-lookup"><span data-stu-id="8a752-478">None</span></span>|<span data-ttu-id="8a752-479">Нет</span><span class="sxs-lookup"><span data-stu-id="8a752-479">None</span></span>|<span data-ttu-id="8a752-480">Советы по политике DLP не поддерживаются на мобильных устройствах Outlook</span><span class="sxs-lookup"><span data-stu-id="8a752-480">DLP policy tips are not supported on Outlook mobile</span></span>|
|<span data-ttu-id="8a752-481">**Sharepoint Online/One Drive для бизнес-веб-клиента**</span><span class="sxs-lookup"><span data-stu-id="8a752-481">**Sharepoint Online/One Drive for Business Web client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="8a752-482">Все</span><span class="sxs-lookup"><span data-stu-id="8a752-482">All</span></span>|<span data-ttu-id="8a752-483">Все предикаты и действия SPO/ODB в DLP</span><span class="sxs-lookup"><span data-stu-id="8a752-483">All SPO/ODB predicates and actions in DLP</span></span>||
|<span data-ttu-id="8a752-484">**Клиент Sharepoint Win32/One Drive для бизнеса Win32**</span><span class="sxs-lookup"><span data-stu-id="8a752-484">**Sharepoint Win32/ One Drive for Business Win32 client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="8a752-485">Нет</span><span class="sxs-lookup"><span data-stu-id="8a752-485">None</span></span>|<span data-ttu-id="8a752-486">Нет</span><span class="sxs-lookup"><span data-stu-id="8a752-486">None</span></span>|<span data-ttu-id="8a752-487">Советы по политике DLP не поддерживаются в клиентских приложениях Sharepoint или OneDrive</span><span class="sxs-lookup"><span data-stu-id="8a752-487">DLP policy tips are not supported on Sharepoint or OneDrive desktop client apps</span></span>|
|<span data-ttu-id="8a752-488">**Word, Excel, Powerpoint Web Client**</span><span class="sxs-lookup"><span data-stu-id="8a752-488">**Word, Excel, Powerpoint Web Client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="8a752-489">Все</span><span class="sxs-lookup"><span data-stu-id="8a752-489">All</span></span>|<span data-ttu-id="8a752-490">Все предикаты и действия SPO/ODB в DLP</span><span class="sxs-lookup"><span data-stu-id="8a752-490">All SPO/ODB predicates and actions in DLP</span></span>|<span data-ttu-id="8a752-491">Совет политики DLP поддерживается, если документ размещен в веб-приложении SPO или ODB и политика DLP уже штамповка.</span><span class="sxs-lookup"><span data-stu-id="8a752-491">DLP policy tip is supported if the document is hosted on SPO or ODB web app and the DLP policy is already stamped.</span></span>|
|<span data-ttu-id="8a752-492">**Word, Excel, Powerpoint Mobile Client**</span><span class="sxs-lookup"><span data-stu-id="8a752-492">**Word, Excel, Powerpoint Mobile Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="8a752-493">Нет</span><span class="sxs-lookup"><span data-stu-id="8a752-493">None</span></span>|<span data-ttu-id="8a752-494">Нет</span><span class="sxs-lookup"><span data-stu-id="8a752-494">None</span></span>|<span data-ttu-id="8a752-495">Советы по политике DLP не поддерживаются в мобильных приложениях для Office.</span><span class="sxs-lookup"><span data-stu-id="8a752-495">DLP policy tips are not supported in mobile apps for Office.</span></span>|
|<span data-ttu-id="8a752-496">**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**</span><span class="sxs-lookup"><span data-stu-id="8a752-496">**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="8a752-497">Все</span><span class="sxs-lookup"><span data-stu-id="8a752-497">All</span></span>|<span data-ttu-id="8a752-498">Все команды предикат в политике DLP</span><span class="sxs-lookup"><span data-stu-id="8a752-498">All Teams predicates in DLP policy</span></span>|<span data-ttu-id="8a752-499">Советы политики покажут, когда сообщение помечено как "Это сообщение помечено.</span><span class="sxs-lookup"><span data-stu-id="8a752-499">Policy tips will show when a message is flagged as “This message has been flagged.</span></span> <span data-ttu-id="8a752-500">Что я могу сделать?</span><span class="sxs-lookup"><span data-stu-id="8a752-500">What can I do?”</span></span> <span data-ttu-id="8a752-501">При нажатии ссылки пользователь может просмотреть типы конфиденциальной информации, обнаруженные и переопределить или сообщить о проблеме, если это разрешено администратором. Обратите внимание, что советы политики не показаны для файлов.</span><span class="sxs-lookup"><span data-stu-id="8a752-501">When clicking the link, the user can review the sensitive info types detected and override or report an issue if allowed by the admin. Note that no policy tips are shown for files.</span></span> <span data-ttu-id="8a752-502">Когда получатель пытается получить доступ к документу, ему может быть отказано в доступе, если это запрещено.</span><span class="sxs-lookup"><span data-stu-id="8a752-502">When the recipient tries to access the document, they might get access denied if not allowed.</span></span>|
|<span data-ttu-id="8a752-503">**Устройства конечных точек Win32**</span><span class="sxs-lookup"><span data-stu-id="8a752-503">**Win32 Endpoint Devices**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="8a752-504">Subset</span><span class="sxs-lookup"><span data-stu-id="8a752-504">Subset</span></span>|<span data-ttu-id="8a752-505">Все предикаты ИПД конечной точки и действия в политике DLP</span><span class="sxs-lookup"><span data-stu-id="8a752-505">All Endpoint DLP predicates and actions in DLP policy</span></span>|<span data-ttu-id="8a752-506">См. в руб. Предупреждение потери данных [в конечной точке поддерживает советы по политике только для некоторых типов конфиденциальной информации](#data-loss-prevention-on-endpoint-supports-policy-tips-for-only-some-sensitive-information-types)</span><span class="sxs-lookup"><span data-stu-id="8a752-506">See [Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types](#data-loss-prevention-on-endpoint-supports-policy-tips-for-only-some-sensitive-information-types)</span></span>|
|<span data-ttu-id="8a752-507">**Устройства Mac**</span><span class="sxs-lookup"><span data-stu-id="8a752-507">**Mac devices**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="8a752-508">Нет</span><span class="sxs-lookup"><span data-stu-id="8a752-508">None</span></span>|<span data-ttu-id="8a752-509">Нет</span><span class="sxs-lookup"><span data-stu-id="8a752-509">None</span></span>|<span data-ttu-id="8a752-510">Предотвращение потери данных не может применяться на устройствах Mac в настоящее время</span><span class="sxs-lookup"><span data-stu-id="8a752-510">Data loss prevention are not enforceable on Mac devices today</span></span>|
|<span data-ttu-id="8a752-511">**Облачные приложения 3-й стороны**</span><span class="sxs-lookup"><span data-stu-id="8a752-511">**3rd party cloud apps**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="8a752-512">Нет</span><span class="sxs-lookup"><span data-stu-id="8a752-512">None</span></span>|<span data-ttu-id="8a752-513">Нет</span><span class="sxs-lookup"><span data-stu-id="8a752-513">None</span></span>|<span data-ttu-id="8a752-514">Защита от потери данных</span><span class="sxs-lookup"><span data-stu-id="8a752-514">Data Loss Prevention</span></span>|
|<span data-ttu-id="8a752-515">**On-prem**</span><span class="sxs-lookup"><span data-stu-id="8a752-515">**On-prem**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="8a752-516">Нет</span><span class="sxs-lookup"><span data-stu-id="8a752-516">None</span></span>|<span data-ttu-id="8a752-517">Нет</span><span class="sxs-lookup"><span data-stu-id="8a752-517">None</span></span>||
|<span data-ttu-id="8a752-518">**Клиент Word, Excel, Powerpoint Win32**</span><span class="sxs-lookup"><span data-stu-id="8a752-518">**Word, Excel, Powerpoint Win32 Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="8a752-519">Subset</span><span class="sxs-lookup"><span data-stu-id="8a752-519">Subset</span></span>|<span data-ttu-id="8a752-520">Subset</span><span class="sxs-lookup"><span data-stu-id="8a752-520">Subset</span></span>|<span data-ttu-id="8a752-521">Советы по политике для клиентских приложений WXP будут работать для документов, хранимых в Sharepoint Online или One Drive для бизнес-сайтов для всех политик DLP, которые имеют точное ниже или подмножество условий или действий в политике DLP:</span><span class="sxs-lookup"><span data-stu-id="8a752-521">Policy tips for WXP client apps will work for documents stored on Sharepoint Online or One Drive for Business Sites for all DLP policies which have exactly the below or a subset of conditions or actions in the DLP policy:</span></span></br> <ul><li><span data-ttu-id="8a752-522">Содержимое содержит типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="8a752-522">Content contains sensitive information types</span></span></li><li><span data-ttu-id="8a752-523">Область доступа (содержимое является общим внутренним или внешним)</span><span class="sxs-lookup"><span data-stu-id="8a752-523">Access Scope (Content is shared internally/externally)</span></span></li><li><span data-ttu-id="8a752-524">Уведомление пользователя (советы по политике и уведомления пользователей)</span><span class="sxs-lookup"><span data-stu-id="8a752-524">Notify User (policy tips/user notifications)</span></span></li><li><span data-ttu-id="8a752-525">Блокировка всех</span><span class="sxs-lookup"><span data-stu-id="8a752-525">Block everyone</span></span></li><li><span data-ttu-id="8a752-526">Отчеты об инцидентах</span><span class="sxs-lookup"><span data-stu-id="8a752-526">Incident reports</span></span></li></ul></br> <span data-ttu-id="8a752-527">Если имеется любое другое условие или действие, подсказка политики DLP для этой политики не будет отображаться в настольных приложениях Word, Excel или PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="8a752-527">If any other condition or action is present, the DLP policy tip for that policy will not appear in the desktop apps of Word, Excel or PowerPoint.</span></span>|
||||||