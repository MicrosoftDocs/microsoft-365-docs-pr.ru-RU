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
description: Используйте расширенное шифрование сообщений Office 365, чтобы расширить безопасность электронной почты, задав дату окончания срока действия сообщений электронной почты с помощью пользовательского шаблона с фирмой.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bbd018e55592e5b17149edf1a4dc0907c0184417
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769169"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="f6ca2-103">Установка срока действия для электронных писем, зашифрованных с помощью расширенного шифрования сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="f6ca2-103">Set an expiration date for email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="f6ca2-104">Office 365 Advanced Message Encryption входит в [состав Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise/home)корпоративный E5, Office 365 E5, Microsoft 365 E5 (цены для некоммерческих сотрудников), Office 365 корпоративный E5 (цены для некоммерческих сотрудников) и Office 365 для образования A5.</span><span class="sxs-lookup"><span data-stu-id="f6ca2-104">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="f6ca2-105">Если у вашей организации есть подписка, не включаемая в расширенный шифрование сообщений Office 365, вы можете приобрести ее с помощью надстройки SKU соответствия требованиям Microsoft 365 E5 для Microsoft 365 E3, Microsoft 365 E3 (цены для некоммерческих сотрудников) или надстройки Office 365 Advanced Compliance SKU для Microsoft 365 E3, Microsoft 365 E3 (цены для некоммерческих сотрудников) или SKU Office 365.</span><span class="sxs-lookup"><span data-stu-id="f6ca2-105">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="f6ca2-106">Срок действия сообщений можно использовать для сообщений электронной почты, отправляемой пользователями внешним получателям, которые используют портал OME для доступа к зашифрованным электронным письмам.</span><span class="sxs-lookup"><span data-stu-id="f6ca2-106">You can use message expiration on emails that your users send to external recipients who use the OME Portal to access encrypted emails.</span></span> <span data-ttu-id="f6ca2-107">Получатели должны использовать портал OME для просмотра зашифрованных сообщений электронной почты, отправленных вашей организацией, и ответа на них с помощью настраиваемого шаблона с фирменной Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6ca2-107">You force recipients to use the OME portal to view and reply to encrypted emails sent by your organization by using a custom branded template that specifies an expiration date in Windows PowerShell.</span></span>

<span data-ttu-id="f6ca2-108">Как глобальный администратор Office 365, при применении фирменой марки компании для настройки внешний вид сообщений электронной почты организации вы также можете указать срок действия этих сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f6ca2-108">As an Office 365 global administrator, when you apply your company brand to customize the look of your organization's email messages, you can also specify an expiration for these email messages.</span></span> <span data-ttu-id="f6ca2-109">С помощью office 365 Advanced Message Encryption можно создать несколько шаблонов для зашифрованных сообщений электронной почты, отправленных из вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f6ca2-109">With Office 365 Advanced Message Encryption, you can create multiple templates for encrypted emails that originate from your organization.</span></span> <span data-ttu-id="f6ca2-110">С помощью шаблона можно контролировать, как долго получатели имеют доступ к почте, отправленной вашими пользователями.</span><span class="sxs-lookup"><span data-stu-id="f6ca2-110">Using a template, you can control how long recipients have access to mail sent by your users.</span></span>

<span data-ttu-id="f6ca2-111">Когда конечный пользователь получает почту с установленным сроком действия, пользователь видит дату окончания срока действия в сообщении-оболочке.</span><span class="sxs-lookup"><span data-stu-id="f6ca2-111">When an end user receives mail that has an expiration date set, the user sees the expiration date in the wrapper email.</span></span> <span data-ttu-id="f6ca2-112">Если пользователь попытается открыть почту с истекшим сроком действия, на портале OME появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="f6ca2-112">If a user tries to open an expired mail, an error appears in the OME portal.</span></span>

<span data-ttu-id="f6ca2-113">Вы можете установить только даты окончания срока действия сообщений электронной почты для внешних получателей.</span><span class="sxs-lookup"><span data-stu-id="f6ca2-113">You can only set expiration dates for emails to external recipients.</span></span>

<span data-ttu-id="f6ca2-114">В Office 365 Advanced Message Encryption каждый раз, когда вы применяли настраиваемую фирмевую марку, Office 365 применяет оболочку к электронной почте, которая соответствует правилу потока почты, к которому применяется шаблон.</span><span class="sxs-lookup"><span data-stu-id="f6ca2-114">With Office 365 Advanced Message Encryption, anytime you apply custom branding, the Office 365 applies the wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="f6ca2-115">Кроме того, срок действия можно использовать только в том случае, если вы используете настраиваемую фирменую марку.</span><span class="sxs-lookup"><span data-stu-id="f6ca2-115">In addition, you can only use expiration if you use custom branding.</span></span>

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a><span data-ttu-id="f6ca2-116">Создание пользовательского шаблона фирменой настройки для принудительного истечения срока действия почты с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6ca2-116">Create a custom branding template to force mail expiration by using PowerShell</span></span>

1. <span data-ttu-id="f6ca2-117">[Подключите Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) с помощью учетной записи с разрешениями глобального администратора в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f6ca2-117">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) with an account that has global administrator permissions in your organization.</span></span>

2. <span data-ttu-id="f6ca2-118">Запустите New-OMEConfiguration управления.</span><span class="sxs-lookup"><span data-stu-id="f6ca2-118">Run the New-OMEConfiguration cmdlet.</span></span>

    ```powershell
    New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
    ```

<span data-ttu-id="f6ca2-119">Где:</span><span class="sxs-lookup"><span data-stu-id="f6ca2-119">Where:</span></span>

- <span data-ttu-id="f6ca2-120">`Identity` — имя настраиваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="f6ca2-120">`Identity` is the name of the custom template.</span></span>

- <span data-ttu-id="f6ca2-121">`ExternalMailExpiryInDays` определяет количество дней, в течение которых получатели могут хранить почту до истечения срока ее действия.</span><span class="sxs-lookup"><span data-stu-id="f6ca2-121">`ExternalMailExpiryInDays` identifies the number of days that recipients can keep mail before it expires.</span></span> <span data-ttu-id="f6ca2-122">Можно использовать любое значение от 1 до 730 дней.</span><span class="sxs-lookup"><span data-stu-id="f6ca2-122">You can use any value between 1–730 days.</span></span>

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="f6ca2-123">Дополнительные сведения о службе Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="f6ca2-123">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="f6ca2-124">Расширенное шифрование сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="f6ca2-124">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="f6ca2-125">Отзыв электронных писем, зашифрованных с помощью расширенного шифрования сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="f6ca2-125">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>](revoke-ome-encrypted-mail.md)

- [<span data-ttu-id="f6ca2-126">Описание политики сообщений и службы соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="f6ca2-126">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
