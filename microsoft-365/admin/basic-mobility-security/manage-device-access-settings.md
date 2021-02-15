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
description: Базовые функции мобильности и безопасности помогают защитить мобильные устройства и управлять ими.
ms.openlocfilehash: dd9d777798c2c96776a8f9b40a3c4dfe0b95702a
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876952"
---
# <a name="manage-device-access-settings-in-basic-mobility-and-security"></a><span data-ttu-id="113b6-103">Управление настройками доступа к устройствам в Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="113b6-103">Manage device access settings in Basic Mobility and Security</span></span>

<span data-ttu-id="113b6-104">Если вы используете Basic Mobility and Security, возможно, вы не сможете управлять устройствами с помощью Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="113b6-104">If you're using Basic Mobility and Security, there might be devices that you can't manage with Basic Mobility and Security.</span></span> <span data-ttu-id="113b6-105">В этом случае следует заблокировать доступ Exchange ActiveSync к электронной почте Microsoft 365 для мобильных устройств, которые не поддерживаются basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="113b6-105">If so, you should block Exchange ActiveSync app access to Microsoft 365 email for mobile devices that aren't supported by Basic Mobility and Security.</span></span> <span data-ttu-id="113b6-106">Это помогает защитить информацию организации на других устройствах.</span><span class="sxs-lookup"><span data-stu-id="113b6-106">This helps secure your organization information across more devices.</span></span>

<span data-ttu-id="113b6-107">Используйте следующие действия:</span><span class="sxs-lookup"><span data-stu-id="113b6-107">Use these steps:</span></span>

1. <span data-ttu-id="113b6-108">Во sign in to Microsoft 365 with your global admin account.</span><span class="sxs-lookup"><span data-stu-id="113b6-108">Sign in to  Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="113b6-109">В браузере введите:  [https://protection.office.com](https://protection.office.com/) .</span><span class="sxs-lookup"><span data-stu-id="113b6-109">In your browser, type: [https://protection.office.com](https://protection.office.com/).</span></span>    

    >[!IMPORTANT]
    ><span data-ttu-id="113b6-110">Если вы впервые используете Basic Mobility and Security для Microsoft 365 business Standard, активируйте его здесь: [Активация базовой безопасности и мобильности.](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)</span><span class="sxs-lookup"><span data-stu-id="113b6-110">If this is the first time you're using Basic Mobility and Security for Microsoft 365 Business Standard, activate it here: [Activate Basic Security and Mobility](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="113b6-111">После активации системы управляйте устройствами с помощью [office 365 Security & Compliance.](https://protection.office.com/)</span><span class="sxs-lookup"><span data-stu-id="113b6-111">After you've activated it, manage your devices with [Office 365 Security & Compliance](https://protection.office.com/).</span></span>

3. <span data-ttu-id="113b6-112">Перейдите в >политики  \*\*\*\* устройств управления устройствами и выберите параметры управления доступом к устройствам для всей   >  \*\*\*\* **организации.**</span><span class="sxs-lookup"><span data-stu-id="113b6-112">Go to Data loss prevention > **Device management** > **Device policies**, and select **Manage organization-wide device access settings**.</span></span>

4. <span data-ttu-id="113b6-113">Выберите **блок**.</span><span class="sxs-lookup"><span data-stu-id="113b6-113">Select **Block**.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Контрольный элемент блокировки доступа Basic Mobility and Security":::

5. <span data-ttu-id="113b6-115">Выберите **"Сохранить"**</span><span class="sxs-lookup"><span data-stu-id="113b6-115">Select **Save**.</span></span>

<span data-ttu-id="113b6-116">Чтобы узнать, какие устройства поддерживаются в Basic Mobility and Security, см. ["Возможности базовой мобильности и безопасности".](capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="113b6-116">To learn what devices Basic Mobility and Security supports, see [Capabilities of Basic Mobility and Security](capabilities.md).</span></span>