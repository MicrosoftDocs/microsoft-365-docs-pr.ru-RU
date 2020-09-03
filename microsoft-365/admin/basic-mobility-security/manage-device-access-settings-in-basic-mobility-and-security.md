---
title: Управление параметрами доступа к устройствам в базовом мобильном и системном обеспечении безопасности
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
description: Основные возможности обеспечения мобильности и безопасности обеспечивают безопасность и управление мобильными устройствами.
ms.openlocfilehash: 0d8f4293c45bcc1dc2a71dbc749641cf3791337e
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "47337039"
---
# <a name="manage-device-access-settings-in-basic-mobility-and-security"></a><span data-ttu-id="f5761-103">Управление параметрами доступа к устройствам в базовом мобильном и системном обеспечении безопасности</span><span class="sxs-lookup"><span data-stu-id="f5761-103">Manage device access settings in Basic Mobility and Security</span></span>

<span data-ttu-id="f5761-104">Если вы используете базовые возможности мобильной работы и обеспечения безопасности, могут быть устройства, которыми нельзя управлять с помощью базовых функций мобильной связи и безопасности.</span><span class="sxs-lookup"><span data-stu-id="f5761-104">If you're using Basic Mobility and Security, there might be devices that you can't manage with Basic Mobility and Security.</span></span> <span data-ttu-id="f5761-105">В этом случае следует заблокировать доступ приложений Exchange ActiveSync к электронной почте Microsoft 365 для мобильных устройств, которые не поддерживаются базовыми мобильностью и безопасностью.</span><span class="sxs-lookup"><span data-stu-id="f5761-105">If so, you should block Exchange ActiveSync app access to Microsoft 365 email for mobile devices that aren't supported by Basic Mobility and Security.</span></span> <span data-ttu-id="f5761-106">Это помогает защитить информацию Организации между несколькими устройствами.</span><span class="sxs-lookup"><span data-stu-id="f5761-106">This helps secure your organization information across more devices.</span></span>

<span data-ttu-id="f5761-107">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f5761-107">Use these steps:</span></span>

1. <span data-ttu-id="f5761-108">Войдите в Microsoft 365 с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="f5761-108">Sign in to  Microsoft 365 with your global admin account.</span></span>
    
2. <span data-ttu-id="f5761-109">В браузере введите:  [https://protection.office.com](https://protection.office.com/) .</span><span class="sxs-lookup"><span data-stu-id="f5761-109">In your browser, type: [https://protection.office.com](https://protection.office.com/).</span></span>    

    >[!IMPORTANT]
    ><span data-ttu-id="f5761-110">Если вы впервые используете MDM для Microsoft 365 Business Standard, активируйте его здесь: [Активация управления мобильными устройствами](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span><span class="sxs-lookup"><span data-stu-id="f5761-110">If this is the first time you're using MDM for Microsoft 365 Business Standard, activate it here: [Activate Mobile Device Management](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="f5761-111">После активации вы Управляйте своими устройствами с помощью [Office 365 Security & соответствия требованиям](https://protection.office.com/).</span><span class="sxs-lookup"><span data-stu-id="f5761-111">After you've activated it, manage your devices with [Office 365 Security & Compliance](https://protection.office.com/).</span></span>

3. <span data-ttu-id="f5761-112">Перейдите к разделу защита от  **Device management**потери данных >  >  **политик устройств**управления устройствами и выберите пункт **Управление параметрами доступа к устройствам в масштабах Организации**.</span><span class="sxs-lookup"><span data-stu-id="f5761-112">Go to Data loss prevention > **Device management** > **Device policies**, and select **Manage organization-wide device access settings**.</span></span>
    
4. <span data-ttu-id="f5761-113">Выберите пункт **блокировать**.</span><span class="sxs-lookup"><span data-stu-id="f5761-113">Select **Block**.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Флажок основного доступа к мобильному и защищенному блокам безопасности":::

5. <span data-ttu-id="f5761-115">Нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f5761-115">Select **Save**.</span></span> 

<span data-ttu-id="f5761-116">Чтобы узнать, какие устройства поддерживаются базовыми возможностями и мобильностью, ознакомьтесь с разрешениями [основной мобильной работы и обеспечения безопасности](capabilities-of-basic-mobility-and-secruity.md).</span><span class="sxs-lookup"><span data-stu-id="f5761-116">To learn what devices Basic Mobility and Security supports, see [Capabilities of Basic Mobility and Security](capabilities-of-basic-mobility-and-secruity.md).</span></span>