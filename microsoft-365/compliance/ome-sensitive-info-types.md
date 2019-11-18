---
title: Создание политики типов конфиденциальной информации для организации с помощью шифрования сообщений Office 365
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
description: 'Сводка: политика шифрования сообщений Office 365 для типов конфиденциальной информации.'
ms.openlocfilehash: 8632a0419b443d2810afd3554da572ab2197ae2a
ms.sourcegitcommit: 6dfa646b9de30336dedfd0cac7320c57ad74ae11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "38690879"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-office-365-message-encryption"></a><span data-ttu-id="9e661-103">Создание политики типов конфиденциальной информации для организации с помощью шифрования сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="9e661-103">Create a sensitive information type policy for your organization using Office 365 Message Encryption</span></span>

<span data-ttu-id="9e661-104">Для создания политики типов конфиденциальной информации с помощью шифрования сообщений Office 365 можно использовать правила для обработки почты Exchange или предотвращение потери данных (DLP) Office 365.</span><span class="sxs-lookup"><span data-stu-id="9e661-104">You can use either Exchange mail flow rules or Office 365 Data Loss Prevention (DLP) to create a sensitive information type policy with Office 365 Message Encryption.</span></span> <span data-ttu-id="9e661-105">Чтобы создать правило для процесса обработки почты Exchange, можно использовать центр администрирования Exchange или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9e661-105">To create an Exchange mail flow rule, you can use either the Exchange admin center (EAC) or PowerShell.</span></span>

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a><span data-ttu-id="9e661-106">Создание политики с помощью правил для почтового процесса в центре администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="9e661-106">To create the policy by using mail flow rules in the EAC</span></span>

<span data-ttu-id="9e661-107">Войдите в центр администрирования Exchange и перейдите к разделу**правила**для обработки **почтового процесса** > .</span><span class="sxs-lookup"><span data-stu-id="9e661-107">Sign in to the Exchange admin center (EAC) and go to **Mail flow** > **Rules**.</span></span> <span data-ttu-id="9e661-108">На странице Правила создайте правило, которое применяет шифрование сообщений Office 365.</span><span class="sxs-lookup"><span data-stu-id="9e661-108">On the Rules page, create a rule that applies Office 365 Message Encryption.</span></span> <span data-ttu-id="9e661-109">Вы можете создать правило на основе таких условий, как присутствие определенных ключевых слов или типов конфиденциальной информации в сообщении или вложении.</span><span class="sxs-lookup"><span data-stu-id="9e661-109">You can create a rule based on conditions such as the presence of certain keywords or sensitive information types in the message or attachment.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a><span data-ttu-id="9e661-110">Создание политики с помощью правил для почтового процесса в PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e661-110">To create the policy by using mail flow rules in PowerShell</span></span>

<span data-ttu-id="9e661-111">Используйте рабочую или учебную учетную запись с разрешениями глобального администратора в организации Office 365, запустите сеанс Windows PowerShell и подключитесь к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9e661-111">Use a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="9e661-112">Инструкции можно найти [в статье подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="9e661-112">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span> <span data-ttu-id="9e661-113">Используйте командлеты Set – IRMConfiguration и New – TransportRule для создания политики.</span><span class="sxs-lookup"><span data-stu-id="9e661-113">Use the Set-IRMConfiguration and New-TransportRule cmdlets to create the policy.</span></span>

## <a name="example-mail-flow-rule-created-with-powershell"></a><span data-ttu-id="9e661-114">Пример правила для процесса обработки почты, созданного с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e661-114">Example mail flow rule created with PowerShell</span></span>

<span data-ttu-id="9e661-115">Выполните следующие команды в PowerShell, чтобы создать правило потока обработки почты Exchange, которое автоматически шифрует сообщения, отправляемые за границы Организации, с помощью политики *только для шифрования* , если сообщения электронной почты или их вложения содержат следующие типы конфиденциальной информации:</span><span class="sxs-lookup"><span data-stu-id="9e661-115">Run the following commands in PowerShell to create an Exchange mail flow rule that automatically encrypts emails sent outside your organization with the *Encrypt-Only* policy if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="9e661-116">Номер маршрутизации код банка ABA</span><span class="sxs-lookup"><span data-stu-id="9e661-116">ABA routing number</span></span>
- <span data-ttu-id="9e661-117">Номер кредитной карты</span><span class="sxs-lookup"><span data-stu-id="9e661-117">Credit card Number</span></span>
- <span data-ttu-id="9e661-118">Номер агентства для применения наркотиков (DEA)</span><span class="sxs-lookup"><span data-stu-id="9e661-118">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="9e661-119">США/ВЕЛИКОБРИТАНИЯ</span><span class="sxs-lookup"><span data-stu-id="9e661-119">U.S. / U.K.</span></span> <span data-ttu-id="9e661-120">passport number</span><span class="sxs-lookup"><span data-stu-id="9e661-120">passport number</span></span>
- <span data-ttu-id="9e661-121">Номер банковского счета США</span><span class="sxs-lookup"><span data-stu-id="9e661-121">U.S. bank account number</span></span>
- <span data-ttu-id="9e661-122">Идентификационный номер налогоплательщика для США (ITIN)</span><span class="sxs-lookup"><span data-stu-id="9e661-122">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="9e661-123">Страховой номер для США (SSN)</span><span class="sxs-lookup"><span data-stu-id="9e661-123">U.S. Social Security Number (SSN)</span></span>

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

<span data-ttu-id="9e661-124">Дополнительные сведения см. в статье [Set – IRMConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-irmconfiguration?view=exchange-ps) и [New – TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="9e661-124">For more information, see [Set-IRMConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-irmconfiguration?view=exchange-ps) and [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule?view=exchange-ps).</span></span>

## <a name="how-recipients-access-attachments"></a><span data-ttu-id="9e661-125">Как получатели обращаются к вложениям</span><span class="sxs-lookup"><span data-stu-id="9e661-125">How recipients access attachments</span></span>

<span data-ttu-id="9e661-126">После того как Office 365 шифрует сообщение, получатели имеют неограниченный доступ к вложениям при обращении к зашифрованным электронным сообщениям и их открытии.</span><span class="sxs-lookup"><span data-stu-id="9e661-126">After Office 365 encrypts a message, recipients have unrestricted access to attachments when they access and open their encrypted email.</span></span>

## <a name="to-prepare-for-this-change"></a><span data-ttu-id="9e661-127">Подготовка к выполнению этого изменения</span><span class="sxs-lookup"><span data-stu-id="9e661-127">To prepare for this change</span></span>

<span data-ttu-id="9e661-128">Вам может потребоваться обновить любую документацию конечного пользователя и обучающие материалы, чтобы подготовить пользователей в Организации к этому изменению.</span><span class="sxs-lookup"><span data-stu-id="9e661-128">You may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change.</span></span> <span data-ttu-id="9e661-129">Предоставьте им доступ к этим ресурсам по шифрованию сообщений Office 365, используя соответствующие пользователи:</span><span class="sxs-lookup"><span data-stu-id="9e661-129">Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="9e661-130">Отправка, просмотр зашифрованных сообщений и ответ на них в Outlook для компьютера</span><span class="sxs-lookup"><span data-stu-id="9e661-130">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="9e661-131">Видео Office 365 Essentials: шифрование сообщений Office</span><span class="sxs-lookup"><span data-stu-id="9e661-131">Office 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a><span data-ttu-id="9e661-132">Просмотр изменений в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="9e661-132">View these changes in the Audit log</span></span>

<span data-ttu-id="9e661-133">Office 365 выполняет аудит этого действия и делает его доступным для администраторов Office 365.</span><span class="sxs-lookup"><span data-stu-id="9e661-133">Office 365 audits this activity and makes it available to Office 365 administrators.</span></span> <span data-ttu-id="9e661-134">Операция — "New-TransportRule", а фрагмент примера записи аудита из поиска в журнале аудита в центре безопасности & соответствия требованиям ниже:</span><span class="sxs-lookup"><span data-stu-id="9e661-134">The operation is ‘New-TransportRule’ and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications”…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a><span data-ttu-id="9e661-135">Отключение или Настройка политики типов конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="9e661-135">To disable or customize the sensitive information types policy</span></span>

<span data-ttu-id="9e661-136">После создания правила для процесса обработки почты Exchange можно [отключить или изменить правило](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) , перейдя к**правилам** обработки **почтового ящика** > в центре администрирования Exchange, и отключить правило "*шифровать исходящие сообщения электронной почты от*".</span><span class="sxs-lookup"><span data-stu-id="9e661-136">Once you've created the Exchange mail flow rule, you can [disable or edit the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule “*Encrypt outbound sensitive emails (out of box rule)*”.</span></span>
