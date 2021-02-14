---
title: Создание политики типов конфиденциальной информации с помощью шифрования сообщений Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: Узнайте, как создать политику типов конфиденциальной информации для организации с помощью шифрования сообщений Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bfc77fa88ff798f98d260682dfbdbdd57b17af69
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545989"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a><span data-ttu-id="e6329-103">Создание политики типов конфиденциальной информации для организации с помощью шифрования сообщений</span><span class="sxs-lookup"><span data-stu-id="e6329-103">Create a sensitive information type policy for your organization using Message Encryption</span></span>

<span data-ttu-id="e6329-104">Для создания политики типов конфиденциальной информации с шифрованием сообщений Office 365 можно использовать правила потока обработки почты Exchange или DLP.</span><span class="sxs-lookup"><span data-stu-id="e6329-104">You can use either Exchange mail flow rules or Data Loss Prevention (DLP) to create a sensitive information type policy with Office 365 Message Encryption.</span></span> <span data-ttu-id="e6329-105">Чтобы создать правило потока обработки почты Exchange, можно использовать Центр администрирования Exchange (EAC) или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6329-105">To create an Exchange mail flow rule, you can use either the Exchange admin center (EAC) or PowerShell.</span></span>

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a><span data-ttu-id="e6329-106">Создание политики с помощью правил потока почты в EAC</span><span class="sxs-lookup"><span data-stu-id="e6329-106">To create the policy by using mail flow rules in the EAC</span></span>

<span data-ttu-id="e6329-107">Войдите в Центр администрирования Exchange (EAC) и перейдите к **правилам потока обработки**  >  **почты.**</span><span class="sxs-lookup"><span data-stu-id="e6329-107">Sign in to the Exchange admin center (EAC) and go to **Mail flow** > **Rules**.</span></span> <span data-ttu-id="e6329-108">На странице "Правила" создайте правило, применяя шифрование сообщений Office 365.</span><span class="sxs-lookup"><span data-stu-id="e6329-108">On the Rules page, create a rule that applies Office 365 Message Encryption.</span></span> <span data-ttu-id="e6329-109">Правило можно создать на основе таких условий, как наличие определенных ключевых слов или типов конфиденциальной информации в сообщении или вложении.</span><span class="sxs-lookup"><span data-stu-id="e6329-109">You can create a rule based on conditions such as the presence of certain keywords or sensitive information types in the message or attachment.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a><span data-ttu-id="e6329-110">Создание политики с помощью правил потока почты в PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6329-110">To create the policy by using mail flow rules in PowerShell</span></span>

<span data-ttu-id="e6329-111">Используйте учетную запись для работы или учебного заведения с разрешениями глобального администратора в организации, запустите сеанс Windows PowerShell и подключите его к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e6329-111">Use a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e6329-112">Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="e6329-112">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span> <span data-ttu-id="e6329-113">Используйте Set-IRMConfiguration и New-TransportRule для создания политики.</span><span class="sxs-lookup"><span data-stu-id="e6329-113">Use the Set-IRMConfiguration and New-TransportRule cmdlets to create the policy.</span></span>

## <a name="example-mail-flow-rule-created-with-powershell"></a><span data-ttu-id="e6329-114">Пример правила потока почты, созданного с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6329-114">Example mail flow rule created with PowerShell</span></span>

<span data-ttu-id="e6329-115">Запустите следующие команды в PowerShell, чтобы создать правило потока почты Exchange, которое  автоматически шифрует сообщения, отправленные за пределы организации, с помощью политики "Только шифрование", если сообщения электронной почты или их вложения содержат следующие типы конфиденциальной информации:</span><span class="sxs-lookup"><span data-stu-id="e6329-115">Run the following commands in PowerShell to create an Exchange mail flow rule that automatically encrypts emails sent outside your organization with the *Encrypt-Only* policy if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="e6329-116">Номер маршрутки ABA</span><span class="sxs-lookup"><span data-stu-id="e6329-116">ABA routing number</span></span>
- <span data-ttu-id="e6329-117">Номер кредитной карты</span><span class="sxs-lookup"><span data-stu-id="e6329-117">Credit card Number</span></span>
- <span data-ttu-id="e6329-118">Номер агентства по правоохранительным органам (DEA)</span><span class="sxs-lookup"><span data-stu-id="e6329-118">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="e6329-119">США и Сша</span><span class="sxs-lookup"><span data-stu-id="e6329-119">U.S. / U.K.</span></span> <span data-ttu-id="e6329-120">passport number</span><span class="sxs-lookup"><span data-stu-id="e6329-120">passport number</span></span>
- <span data-ttu-id="e6329-121">Номер банковского счета в США</span><span class="sxs-lookup"><span data-stu-id="e6329-121">U.S. bank account number</span></span>
- <span data-ttu-id="e6329-122">Идентификационный номер налогоплательщика для США (ITIN)</span><span class="sxs-lookup"><span data-stu-id="e6329-122">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="e6329-123">Страховой номер для США (SSN)</span><span class="sxs-lookup"><span data-stu-id="e6329-123">U.S. Social Security Number (SSN)</span></span>

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

<span data-ttu-id="e6329-124">Дополнительные сведения [см. в настройках Set-IRMConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-irmconfiguration) и [New-TransportRule.](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)</span><span class="sxs-lookup"><span data-stu-id="e6329-124">For more information, see [Set-IRMConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-irmconfiguration) and [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-recipients-access-attachments"></a><span data-ttu-id="e6329-125">Как получатели имеют доступ к вложениям</span><span class="sxs-lookup"><span data-stu-id="e6329-125">How recipients access attachments</span></span>

<span data-ttu-id="e6329-126">После шифрования сообщения корпорацией Майкрософт у получателей будет неограниченный доступ к вложениям, когда они будут получать доступ к зашифрованной электронной почте и открывать ее.</span><span class="sxs-lookup"><span data-stu-id="e6329-126">After Microsoft encrypts a message, recipients have unrestricted access to attachments when they access and open their encrypted email.</span></span>

## <a name="to-prepare-for-this-change"></a><span data-ttu-id="e6329-127">Подготовка к этому изменению</span><span class="sxs-lookup"><span data-stu-id="e6329-127">To prepare for this change</span></span>

<span data-ttu-id="e6329-128">Вам может потребоваться обновить все применимые документацию и обучающие материалы для подготовки сотрудников организации к этому изменению.</span><span class="sxs-lookup"><span data-stu-id="e6329-128">You may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change.</span></span> <span data-ttu-id="e6329-129">При необходимости поделитесь этими ресурсами шифрования сообщений Office 365 с пользователями:</span><span class="sxs-lookup"><span data-stu-id="e6329-129">Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="e6329-130">Отправка, просмотр зашифрованных сообщений и ответ на них в Outlook для ПК</span><span class="sxs-lookup"><span data-stu-id="e6329-130">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="e6329-131">Видео о Microsoft 365 essentials: шифрование сообщений Office</span><span class="sxs-lookup"><span data-stu-id="e6329-131">Microsoft 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a><span data-ttu-id="e6329-132">Просмотр этих изменений в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="e6329-132">View these changes in the audit log</span></span>

<span data-ttu-id="e6329-133">Microsoft 365 проводит аудит этого действия и делает его доступным для администраторов.</span><span class="sxs-lookup"><span data-stu-id="e6329-133">Microsoft 365 audits this activity and makes it available to administrators.</span></span> <span data-ttu-id="e6329-134">Операция " New-TransportRule" и фрагмент примера записи аудита из поиска в журнале аудита в центре безопасности & соответствия требованиям ниже:</span><span class="sxs-lookup"><span data-stu-id="e6329-134">The operation is 'New-TransportRule' and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a><span data-ttu-id="e6329-135">Отключение или настройка политики типов конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="e6329-135">To disable or customize the sensitive information types policy</span></span>

<span data-ttu-id="e6329-136">После создания правила потока обработки почты [](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) Exchange вы можете отключить или изменить правило, переходить к правилам потока обработки почты в Центре администрирования  >   Exchange (EAC) и отключить правило *"Шифровать* исходящие конфиденциальные сообщения электронной почты (из правила").</span><span class="sxs-lookup"><span data-stu-id="e6329-136">Once you've created the Exchange mail flow rule, you can [disable or edit the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule "*Encrypt outbound sensitive emails (out of box rule)*".</span></span>
