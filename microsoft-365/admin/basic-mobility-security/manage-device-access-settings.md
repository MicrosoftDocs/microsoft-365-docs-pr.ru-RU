---
title: Управление настройками доступа к устройствам в Basic Mobility and Security
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Базовая мобильность и безопасность могут помочь вам обеспечить безопасность и управление мобильными устройствами.
ms.openlocfilehash: 24eeb1dfccef3d30e577b15ecb9d2fda4d902cdc
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228163"
---
# <a name="manage-device-access-settings-in-basic-mobility-and-security"></a><span data-ttu-id="2c407-103">Управление настройками доступа к устройствам в Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="2c407-103">Manage device access settings in Basic Mobility and Security</span></span>

<span data-ttu-id="2c407-104">Если вы используете basic Mobility и Security, могут быть устройства, с помощью которые вы не можете управлять с помощью Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="2c407-104">If you're using Basic Mobility and Security, there might be devices that you can't manage with Basic Mobility and Security.</span></span> <span data-ttu-id="2c407-105">В этом случае необходимо Exchange ActiveSync доступ Microsoft 365 электронной почты для мобильных устройств, которые не поддерживаются базовой мобильностью и безопасностью.</span><span class="sxs-lookup"><span data-stu-id="2c407-105">If so, you should block Exchange ActiveSync app access to Microsoft 365 email for mobile devices that aren't supported by Basic Mobility and Security.</span></span> <span data-ttu-id="2c407-106">Это помогает обезопасить сведения организации на других устройствах.</span><span class="sxs-lookup"><span data-stu-id="2c407-106">This helps secure your organization information across more devices.</span></span>

<span data-ttu-id="2c407-107">Используйте следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2c407-107">Use these steps:</span></span>

1. <span data-ttu-id="2c407-108">Во входе Microsoft 365 с глобальной учетной записью администратора.</span><span class="sxs-lookup"><span data-stu-id="2c407-108">Sign in to  Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="2c407-109">В браузере введите:  [https://protection.office.com](https://protection.office.com/) .</span><span class="sxs-lookup"><span data-stu-id="2c407-109">In your browser, type: [https://protection.office.com](https://protection.office.com/).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2c407-110">Если вы впервые используете базовую мобильность и безопасность для Microsoft 365 бизнес стандарт, активируйте его здесь: Активируйте базовую [безопасность и мобильность.](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)</span><span class="sxs-lookup"><span data-stu-id="2c407-110">If this is the first time you're using Basic Mobility and Security for Microsoft 365 Business Standard, activate it here: [Activate Basic Security and Mobility](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="2c407-111">После активации управления устройствами с помощью Office 365 [безопасности & соответствия](https://protection.office.com/)требованиям.</span><span class="sxs-lookup"><span data-stu-id="2c407-111">After you've activated it, manage your devices with [Office 365 Security & Compliance](https://protection.office.com/).</span></span>

3. <span data-ttu-id="2c407-112">Перейдите к политике > \*\*\*\* устройств управления данными и выберите параметры доступа к устройствам для всей   >  \*\*\*\* **организации.**</span><span class="sxs-lookup"><span data-stu-id="2c407-112">Go to Data loss prevention > **Device management** > **Device policies**, and select **Manage organization-wide device access settings**.</span></span>

4. <span data-ttu-id="2c407-113">Выберите **блок**.</span><span class="sxs-lookup"><span data-stu-id="2c407-113">Select **Block**.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Блок-ящик доступа Basic Mobility и Security":::

5. <span data-ttu-id="2c407-115">Выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2c407-115">Select **Save**.</span></span>

<span data-ttu-id="2c407-116">Чтобы узнать, какие устройства поддерживают базовую мобильность и безопасность, см. в руб. [Возможности базовой мобильности и безопасности.](capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="2c407-116">To learn what devices Basic Mobility and Security supports, see [Capabilities of Basic Mobility and Security](capabilities.md).</span></span>
