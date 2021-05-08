---
title: Шаг 5 — стереть и заблокировать мобильное устройство бывшего сотрудника
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Выполните следующие действия, чтобы заблокировать доступ к мобильным устройствам бывшего сотрудника.
ms.openlocfilehash: 1ce12b06b6a0a74615ff8ac43b8f333456a469bb
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244296"
---
# <a name="step-5---wipe-and-block-a-former-employees-mobile-device"></a><span data-ttu-id="17845-103">Шаг 5 — стереть и заблокировать мобильное устройство бывшего сотрудника</span><span class="sxs-lookup"><span data-stu-id="17845-103">Step 5 - Wipe and block a former employee's mobile device</span></span>

<span data-ttu-id="17845-104">Если у вашего бывшего сотрудника был телефон организации, вы можете использовать центр администрирования Exchange для удаления и блокировки этого устройства, чтобы все данные организации были удалены с устройства и он больше не может подключаться к Office 365.</span><span class="sxs-lookup"><span data-stu-id="17845-104">If your former employee had an organization phone, you can use the Exchange admin center to wipe and block that device so that all organization data is removed from the device and it can no longer connect to Office 365.</span></span> <span data-ttu-id="17845-105">Если ваша организация использует basic Mobility и Security для управления мобильными устройствами, вы можете стереть и заблокировать эти устройства с помощью Basic Mobility и Security.</span><span class="sxs-lookup"><span data-stu-id="17845-105">If your organization uses Basic Mobility and Security to manage mobile devices, you can wipe and block those devices using Basic Mobility and Security.</span></span>

## <a name="wipe-mobile-device-using-the-exchange-admin-center"></a><span data-ttu-id="17845-106">Wipe mobile device using the Exchange admin center</span><span class="sxs-lookup"><span data-stu-id="17845-106">Wipe mobile device using the Exchange admin center</span></span>

1. <span data-ttu-id="17845-107">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Центр администрирования Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="17845-107">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
2. <span data-ttu-id="17845-108">В Центре администрирования Exchange выберите **Получатели** \> **Почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="17845-108">In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.</span></span>
3. <span data-ttu-id="17845-109">Выберите пользователя, а в статье **Мобильные устройства** выберите **сведения Просмотр**.</span><span class="sxs-lookup"><span data-stu-id="17845-109">Select the user, and under **Mobile Devices**, select **View details**.</span></span>
4. <span data-ttu-id="17845-110">На странице **Сведения о мобильных устройствах** в статье **Мобильные устройства** выберите мобильное устройство, выберите устройство Wipe **Data** Wipe и выберите ![ ](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png) **Блок**.</span><span class="sxs-lookup"><span data-stu-id="17845-110">On the **Mobile Device Details** page, under **Mobile devices**, select the mobile device, select **Wipe Data**![Wipe Device](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png), and then select **Block**.</span></span>
5. <span data-ttu-id="17845-111">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="17845-111">Select **Save**.</span></span>
   > [!TIP]
   > <span data-ttu-id="17845-112">Убедитесь, что вы удалите или отключите пользователя из локальной Enterprise Service.</span><span class="sxs-lookup"><span data-stu-id="17845-112">Be sure you remove or disable the user from your on-premises Blackberry Enterprise Service.</span></span> <span data-ttu-id="17845-113">Вы также должны отключить любые устройства Blackberry для пользователя.</span><span class="sxs-lookup"><span data-stu-id="17845-113">You should also disable any Blackberry devices for the user.</span></span> <span data-ttu-id="17845-114">Обратитесь к руководству по администрированию облачных служб Blackberry Business, если вам нужны конкретные действия по отключению пользователя.</span><span class="sxs-lookup"><span data-stu-id="17845-114">Refer to the Blackberry Business Cloud Services Administration Guide if you need specific steps on how to disable the user.</span></span>
