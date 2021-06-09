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
description: Используйте Расширенное шифрование сообщений Office 365, чтобы расширить безопасность электронной почты, установив дату истечения срока действия электронной почты с помощью настраиваемой фирменой шаблона.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f936ffa62f31e47f51fc1bcb2765195b0ea809af
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927789"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="9c95a-103">Установка срока действия для электронных писем, зашифрованных с помощью расширенного шифрования сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="9c95a-103">Set an expiration date for email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="9c95a-104">Расширенное шифрование сообщений Office 365 входит в Microsoft 365 корпоративный [E5,](https://www.microsoft.com/microsoft-365/enterprise/home)Office 365 E5, Microsoft 365 E5 (некоммерческие цены персонала), Office 365 корпоративный E5 (некоммерческие цены персонала) и Office 365 для образования A5.</span><span class="sxs-lookup"><span data-stu-id="9c95a-104">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="9c95a-105">Если в вашей организации есть подписка, не включаемая Расширенное шифрование сообщений Office 365, ее можно приобрести с надстройки Соответствие требованиям Microsoft 365 E5 SKU для Microsoft 365 E3, Microsoft 365 E3 (некоммерческие цены на персонал) или надстройки Office 365 Advanced Compliance SKU для Microsoft 365 E3, Microsoft 365 E3 (некоммерческие цены персонала) или Office 365 SKUs.</span><span class="sxs-lookup"><span data-stu-id="9c95a-105">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="9c95a-106">Срок действия сообщения можно использовать в сообщениях электронной почты, которые пользователи отправляют внешним получателям, которые используют портал OME для доступа к зашифрованным электронным письмам.</span><span class="sxs-lookup"><span data-stu-id="9c95a-106">You can use message expiration on emails that your users send to external recipients who use the OME Portal to access encrypted emails.</span></span> <span data-ttu-id="9c95a-107">Вы заставите получателей использовать портал OME для просмотра и ответа на зашифрованные сообщения электронной почты, отправленные вашей организацией, с помощью настраиваемого фирменого шаблона, который указывает срок действия в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c95a-107">You force recipients to use the OME portal to view and reply to encrypted emails sent by your organization by using a custom branded template that specifies an expiration date in Windows PowerShell.</span></span>

<span data-ttu-id="9c95a-108">В качестве Office 365 глобального администратора при применении бренда компании для настройки внешний вид сообщений электронной почты организации можно также указать срок действия этих сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="9c95a-108">As an Office 365 global administrator, when you apply your company brand to customize the look of your organization's email messages, you can also specify an expiration for these email messages.</span></span> <span data-ttu-id="9c95a-109">С Расширенное шифрование сообщений Office 365 вы можете создать несколько шаблонов для зашифрованных сообщений электронной почты, которые происходят из вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9c95a-109">With Office 365 Advanced Message Encryption, you can create multiple templates for encrypted emails that originate from your organization.</span></span> <span data-ttu-id="9c95a-110">С помощью шаблона можно контролировать, как долго получатели имеют доступ к почте, отправленной пользователями.</span><span class="sxs-lookup"><span data-stu-id="9c95a-110">Using a template, you can control how long recipients have access to mail sent by your users.</span></span>

<span data-ttu-id="9c95a-111">Когда конечный пользователь получает почту с набором дат истечения срока действия, пользователь видит дату истечения срока действия в электронной почте обертки.</span><span class="sxs-lookup"><span data-stu-id="9c95a-111">When an end user receives mail that has an expiration date set, the user sees the expiration date in the wrapper email.</span></span> <span data-ttu-id="9c95a-112">Если пользователь пытается открыть просроченную почту, на портале OME появляется ошибка.</span><span class="sxs-lookup"><span data-stu-id="9c95a-112">If a user tries to open an expired mail, an error appears in the OME portal.</span></span>

<span data-ttu-id="9c95a-113">Вы можете устанавливать только даты истечения срока действия электронных писем внешним получателям.</span><span class="sxs-lookup"><span data-stu-id="9c95a-113">You can only set expiration dates for emails to external recipients.</span></span>

<span data-ttu-id="9c95a-114">С Расширенное шифрование сообщений Office 365, в любое время применения настраиваемой торговой марки, Office 365 применяет оболочку к электронной почте, которая соответствует правилу потока почты, к которому применяется шаблон.</span><span class="sxs-lookup"><span data-stu-id="9c95a-114">With Office 365 Advanced Message Encryption, anytime you apply custom branding, the Office 365 applies the wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="9c95a-115">Кроме того, вы можете использовать срок действия только в том случае, если используется настраиваемый брендинг.</span><span class="sxs-lookup"><span data-stu-id="9c95a-115">In addition, you can only use expiration if you use custom branding.</span></span>

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a><span data-ttu-id="9c95a-116">Создайте настраиваемый шаблон брендинга для принудительного истечения срока действия почты с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="9c95a-116">Create a custom branding template to force mail expiration by using PowerShell</span></span>

1. <span data-ttu-id="9c95a-117">[Подключение Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) с учетной записью с глобальными разрешениями администратора в организации.</span><span class="sxs-lookup"><span data-stu-id="9c95a-117">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) with an account that has global administrator permissions in your organization.</span></span>

2. <span data-ttu-id="9c95a-118">Запустите New-OMEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="9c95a-118">Run the New-OMEConfiguration cmdlet.</span></span>

    ```powershell
    New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
    ```

<span data-ttu-id="9c95a-119">Где:</span><span class="sxs-lookup"><span data-stu-id="9c95a-119">Where:</span></span>

- <span data-ttu-id="9c95a-120">`Identity` это имя настраиваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="9c95a-120">`Identity` is the name of the custom template.</span></span>

- <span data-ttu-id="9c95a-121">`ExternalMailExpiryInDays` определяет количество дней, в течение которых получатели могут хранить почту до истечения срока ее действия.</span><span class="sxs-lookup"><span data-stu-id="9c95a-121">`ExternalMailExpiryInDays` identifies the number of days that recipients can keep mail before it expires.</span></span> <span data-ttu-id="9c95a-122">Вы можете использовать любое значение от 1 до 730 дней.</span><span class="sxs-lookup"><span data-stu-id="9c95a-122">You can use any value between 1–730 days.</span></span>

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="9c95a-123">Дополнительные сведения о Расширенное шифрование сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="9c95a-123">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="9c95a-124">Расширенное шифрование сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="9c95a-124">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="9c95a-125">Отзыв электронных писем, зашифрованных с помощью расширенного шифрования сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="9c95a-125">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>](revoke-ome-encrypted-mail.md)

- [<span data-ttu-id="9c95a-126">Описание политики сообщений и службы соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="9c95a-126">Message policy and compliance service description</span></span>](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)