---
title: Установка срока действия для электронных писем, зашифрованных с помощью расширенного шифрования сообщений Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/8/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Использование расширенного шифрования сообщений Office 365 для расширения безопасности электронной почты путем установки срока действия электронной почты с помощью настраиваемого фирменного шаблона.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bbd018e55592e5b17149edf1a4dc0907c0184417
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769169"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="ac2af-103">Установка срока действия для электронных писем, зашифрованных с помощью расширенного шифрования сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="ac2af-103">Set an expiration date for email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="ac2af-104">Расширенное шифрование сообщений Office 365 включено в [microsoft 365 корпоративный](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365, Microsoft 365, Microsoft (ценообразование для сотрудников), Office 365 Enterprise и Office 365 образование A5.</span><span class="sxs-lookup"><span data-stu-id="ac2af-104">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="ac2af-105">Если в вашей организации есть подписка, не включающая в себя приложение Office 365 Advanced Message Encryption, вы можете приобрести его с помощью надстройки Microsoft 365 для обеспечения соответствия требованиям для Microsoft 365 E3, Microsoft 365 E3 (ценообразование для некоммерческих сотрудников) или надстройки Office 365 для расширенного соответствия требованиям для Microsoft 365 E3, Microsoft 365 E3 (ценообразование для некоммерческих сотрудников) или SKU Office 365</span><span class="sxs-lookup"><span data-stu-id="ac2af-105">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="ac2af-106">Истечение срока действия сообщений можно использовать в сообщениях, отправляемых пользователями внешним получателям, которые используют портал OME для доступа к зашифрованным сообщениям электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ac2af-106">You can use message expiration on emails that your users send to external recipients who use the OME Portal to access encrypted emails.</span></span> <span data-ttu-id="ac2af-107">Вы можете использовать портал OME для просмотра зашифрованных сообщений электронной почты, отправляемых вашей организацией, и ответа на них с помощью настраиваемого фирменного шаблона, который задает срок действия в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac2af-107">You force recipients to use the OME portal to view and reply to encrypted emails sent by your organization by using a custom branded template that specifies an expiration date in Windows PowerShell.</span></span>

<span data-ttu-id="ac2af-108">Как глобальный администратор Office 365 при применении фирменной символики компании для настройки внешнего вида электронных сообщений Организации можно также указать срок действия этих сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ac2af-108">As an Office 365 global administrator, when you apply your company brand to customize the look of your organization's email messages, you can also specify an expiration for these email messages.</span></span> <span data-ttu-id="ac2af-109">С помощью расширенного шифрования сообщений Office 365 вы можете создать несколько шаблонов для зашифрованных сообщений электронной почты, исходящих из вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ac2af-109">With Office 365 Advanced Message Encryption, you can create multiple templates for encrypted emails that originate from your organization.</span></span> <span data-ttu-id="ac2af-110">С помощью шаблона можно контролировать, как долго получатели имеют доступ к сообщениям, отправляемым пользователями.</span><span class="sxs-lookup"><span data-stu-id="ac2af-110">Using a template, you can control how long recipients have access to mail sent by your users.</span></span>

<span data-ttu-id="ac2af-111">Когда конечный пользователь получает почту с установленным сроком действия, пользователь видит дату окончания срока действия в сообщении-оболочке.</span><span class="sxs-lookup"><span data-stu-id="ac2af-111">When an end user receives mail that has an expiration date set, the user sees the expiration date in the wrapper email.</span></span> <span data-ttu-id="ac2af-112">Если пользователь пытается открыть просроченную почту, на портале OME появляется ошибка.</span><span class="sxs-lookup"><span data-stu-id="ac2af-112">If a user tries to open an expired mail, an error appears in the OME portal.</span></span>

<span data-ttu-id="ac2af-113">Даты истечения срока действия сообщений для внешних получателей можно задать только для внешних получателей.</span><span class="sxs-lookup"><span data-stu-id="ac2af-113">You can only set expiration dates for emails to external recipients.</span></span>

<span data-ttu-id="ac2af-114">С помощью расширенного шифрования сообщений Office 365, когда вы применяете специальную фирменную символику, Office 365 применяет программу-оболочку к электронной почте, удовлетворяющую правилу обработки почты, к которому применяется шаблон.</span><span class="sxs-lookup"><span data-stu-id="ac2af-114">With Office 365 Advanced Message Encryption, anytime you apply custom branding, the Office 365 applies the wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="ac2af-115">Кроме того, истечение срока действия можно использовать только при использовании специальной фирменной символики.</span><span class="sxs-lookup"><span data-stu-id="ac2af-115">In addition, you can only use expiration if you use custom branding.</span></span>

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a><span data-ttu-id="ac2af-116">Создание настраиваемого шаблона фирменной символики для принудительного истечения срока действия почты с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac2af-116">Create a custom branding template to force mail expiration by using PowerShell</span></span>

1. <span data-ttu-id="ac2af-117">[Подключитесь к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) , используя учетную запись с разрешениями глобального администратора в Организации.</span><span class="sxs-lookup"><span data-stu-id="ac2af-117">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) with an account that has global administrator permissions in your organization.</span></span>

2. <span data-ttu-id="ac2af-118">Выполните командлет New-OMEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="ac2af-118">Run the New-OMEConfiguration cmdlet.</span></span>

    ```powershell
    New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
    ```

<span data-ttu-id="ac2af-119">Где:</span><span class="sxs-lookup"><span data-stu-id="ac2af-119">Where:</span></span>

- <span data-ttu-id="ac2af-120">`Identity` — Имя настраиваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="ac2af-120">`Identity` is the name of the custom template.</span></span>

- <span data-ttu-id="ac2af-121">`ExternalMailExpiryInDays` Указывает количество дней, в течение которых получатели могут хранить почту до истечения срока действия.</span><span class="sxs-lookup"><span data-stu-id="ac2af-121">`ExternalMailExpiryInDays` identifies the number of days that recipients can keep mail before it expires.</span></span> <span data-ttu-id="ac2af-122">Вы можете использовать любое значение в диапазоне от 1 до 730 дней.</span><span class="sxs-lookup"><span data-stu-id="ac2af-122">You can use any value between 1–730 days.</span></span>

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="ac2af-123">Дополнительные сведения о расширенном шифровании сообщений в Office 365</span><span class="sxs-lookup"><span data-stu-id="ac2af-123">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="ac2af-124">Расширенное шифрование сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="ac2af-124">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="ac2af-125">Отзыв электронных писем, зашифрованных с помощью расширенного шифрования сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="ac2af-125">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>](revoke-ome-encrypted-mail.md)

- [<span data-ttu-id="ac2af-126">Описание политики сообщений и службы соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="ac2af-126">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
