---
title: Что поступает в показателях безопасности Майкрософт?
description: В этой статье описывается оценка безопасности Майкрософт в центре безопасности Майкрософт 365, вычисление сведений и возможные Администраторы безопасности.
keywords: безопасность, вредоносные программы, Microsoft 365, M365, Оценка безопасности, центр безопасности, действия по улучшению
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: efb75f26d66258880c9defa94869f27e18685052
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2020
ms.locfileid: "42372007"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="81b17-104">Что поступает в показателях безопасности Майкрософт?</span><span class="sxs-lookup"><span data-stu-id="81b17-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="81b17-105">Чтобы сделать Microsoft Secure рейтинг более подходящим для вашей безопасности и улучшить удобство использования, мы будем вносить некоторые изменения в ближайшем будущем.</span><span class="sxs-lookup"><span data-stu-id="81b17-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="81b17-106">Ваш рейтинг и максимально возможный показатель будут меняться.</span><span class="sxs-lookup"><span data-stu-id="81b17-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="81b17-107">Однако это не подразумевает изменения в безопасности.</span><span class="sxs-lookup"><span data-stu-id="81b17-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="81b17-108">Чтобы узнать о последних изменениях, ознакомьтесь со статьей " [новые возможности оценки безопасности Майкрософт".](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="81b17-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="march-16th-2020"></a><span data-ttu-id="81b17-109">16 марта 2020</span><span class="sxs-lookup"><span data-stu-id="81b17-109">March 16th 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="81b17-110">Удаление действий улучшения, которые не отвечают ожиданиям для надежного измерения, или не предоставляют удобного представления безопасности</span><span class="sxs-lookup"><span data-stu-id="81b17-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="81b17-111">Чтобы обеспечить осмысленность оценки безопасности Майкрософт и обеспечить надежность и надежность каждого действия по улучшению, мы удаляем следующие действия по улучшению.</span><span class="sxs-lookup"><span data-stu-id="81b17-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="81b17-112">Хранение документов пользователей в OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="81b17-112">Store user documents in OneDrive for Business</span></span>
- <span data-ttu-id="81b17-113">Настройка политик безопасных вложений Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="81b17-113">Set up Office 365 ATP Safe Attachment policies</span></span>
- <span data-ttu-id="81b17-114">Настройка безопасных ссылок на Office 365 для проверки URL-адресов</span><span class="sxs-lookup"><span data-stu-id="81b17-114">Set up Office 365 Safe Links to verify URLs</span></span>
- <span data-ttu-id="81b17-115">Не разрешать делегирование почтовых ящиков</span><span class="sxs-lookup"><span data-stu-id="81b17-115">Do not allow mailbox delegation</span></span>
- <span data-ttu-id="81b17-116">Разрешить ссылки анонимного общего доступа к гостям для сайтов и документов</span><span class="sxs-lookup"><span data-stu-id="81b17-116">Allow anonymous guest sharing links for sites and docs</span></span>
- <span data-ttu-id="81b17-117">Включение консоли Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="81b17-117">Turn on Cloud App Security Console</span></span>
- <span data-ttu-id="81b17-118">Настройка времени истечения срока для ссылок внешнего общего доступа</span><span class="sxs-lookup"><span data-stu-id="81b17-118">Configure expiration time for external sharing links</span></span>

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a><span data-ttu-id="81b17-119">Поддержка параметров безопасности по умолчанию для действий по улучшению Azure AD</span><span class="sxs-lookup"><span data-stu-id="81b17-119">Supporting security defaults for Azure AD improvement actions</span></span>

<span data-ttu-id="81b17-120">Оценка безопасности Майкрософт будет обновлять действия по улучшению для поддержки параметров [безопасности по умолчанию в Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), что облегчит защиту Организации с помощью предварительно настроенных параметров безопасности для распространенных атак.</span><span class="sxs-lookup"><span data-stu-id="81b17-120">Microsoft Secure Score will be updating improvement actions to support [security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="81b17-121">Он повлияет на следующие действия по улучшению:</span><span class="sxs-lookup"><span data-stu-id="81b17-121">It will affect the following improvement actions:</span></span>

- <span data-ttu-id="81b17-122">Убедитесь, что все пользователи могут выполнять многофакторную проверку подлинности для безопасного доступа</span><span class="sxs-lookup"><span data-stu-id="81b17-122">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="81b17-123">Требовать использование MFA для административных ролей</span><span class="sxs-lookup"><span data-stu-id="81b17-123">Require MFA for administrative roles</span></span>
- <span data-ttu-id="81b17-124">Включение политики для блокирования устаревшей проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="81b17-124">Enable policy to block legacy authentication</span></span>
