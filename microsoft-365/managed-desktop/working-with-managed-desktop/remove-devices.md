---
title: Удаление устройств
description: Удаление устройств из компьютеры, управляемые Майкрософт управления
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: fa1cb7307fddd815a2a9249c5a98739d21bd2418
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893930"
---
# <a name="remove-devices"></a><span data-ttu-id="5f846-103">Удаление устройств</span><span class="sxs-lookup"><span data-stu-id="5f846-103">Remove devices</span></span>

<span data-ttu-id="5f846-104">Вы можете удалить устройства из компьютеры, управляемые Майкрософт с помощью портала Admin.</span><span class="sxs-lookup"><span data-stu-id="5f846-104">You can remove devices from Microsoft Managed Desktop management by using the Admin portal.</span></span> <span data-ttu-id="5f846-105">Это действие является постоянным, но вы можете зарегистрировать их компьютеры, управляемые Майкрософт, следуя шагам [регистрации.](../get-started/register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="5f846-105">This action is permanent, but you can register them with Microsoft Managed Desktop again by following the [registration steps](../get-started/register-devices-self.md).</span></span>

<span data-ttu-id="5f846-106">При удаляемом устройстве происходит следующее:</span><span class="sxs-lookup"><span data-stu-id="5f846-106">When you remove a device, all of the following occur:</span></span>

- <span data-ttu-id="5f846-107">Мы удаляем устройство из автопилота.</span><span class="sxs-lookup"><span data-stu-id="5f846-107">We remove the device from Autopilot.</span></span>
- <span data-ttu-id="5f846-108">Мы удаляем устройство из всех групп устройств "Modern Workplace".</span><span class="sxs-lookup"><span data-stu-id="5f846-108">We remove the device from  all "Modern Workplace" device groups.</span></span>
- <span data-ttu-id="5f846-109">Мы удаляем устройство из лезвия **Devices** на портале Admin.</span><span class="sxs-lookup"><span data-stu-id="5f846-109">We remove the device from the **Devices** blade in the Admin portal.</span></span>

<span data-ttu-id="5f846-110">При удалите устройство, у вас есть возможность также удалить его из Azure Active Directory (Azure AD) и Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="5f846-110">When you remove a device, you have the option to also remove it from Azure Active Directory (Azure AD) and Microsoft Intune.</span></span>
 
> [!CAUTION]
> <span data-ttu-id="5f846-111">Удаление объектов, связанных с устройством, из Azure AD и Microsoft Intune является постоянным.</span><span class="sxs-lookup"><span data-stu-id="5f846-111">Removing the objects related to a device from Azure AD and Microsoft Intune is permanent.</span></span> <span data-ttu-id="5f846-112">Если удалить объекты, вы не сможете просматривать или управлять устройствами с порталов Intune и Azure.</span><span class="sxs-lookup"><span data-stu-id="5f846-112">If you remove the objects, you won't be able to view or manage the devices from the Intune and Azure portals.</span></span> <span data-ttu-id="5f846-113">Устройства не смогут получить доступ к корпоративным ресурсам своей компании.</span><span class="sxs-lookup"><span data-stu-id="5f846-113">The devices won't be able to access their company's corporate resources.</span></span> <span data-ttu-id="5f846-114">Данные компании могут быть удалены из них, если устройства попытаются войти после удаления.</span><span class="sxs-lookup"><span data-stu-id="5f846-114">Company data might be deleted from them if the devices try to sign in after they're deleted.</span></span>

1. <span data-ttu-id="5f846-115">В [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)выберите **Устройства** в левой области навигации.</span><span class="sxs-lookup"><span data-stu-id="5f846-115">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span>
2. <span data-ttu-id="5f846-116">Посмотрите раздел **компьютеры, управляемые Майкрософт** меню и выберите **Устройства**.</span><span class="sxs-lookup"><span data-stu-id="5f846-116">Look for the **Microsoft Managed Desktop** section of the menu and select **Devices**.</span></span>
3. <span data-ttu-id="5f846-117">В рабочей компьютеры, управляемые Майкрософт Устройства выберите устройства, которые необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="5f846-117">In the Microsoft Managed Desktop Devices workspace, select the devices you want to delete.</span></span>
4. <span data-ttu-id="5f846-118">Выберите **действия устройства,** а затем выберите **Удаление устройства,** которое открывает флайер для удаления устройств.</span><span class="sxs-lookup"><span data-stu-id="5f846-118">Select **Device actions**, and then select **Delete Device** which opens a fly-in to remove the devices.</span></span>
5. <span data-ttu-id="5f846-119">Во время влета просмотрите выбранные устройства и выберите **Удалить устройства.**</span><span class="sxs-lookup"><span data-stu-id="5f846-119">In the fly-in, review the selected devices and then select **Remove devices**.</span></span> <span data-ttu-id="5f846-120">Если вы хотите одновременно удалить объекты Azure AD и Intune, выберите поле для проверки.</span><span class="sxs-lookup"><span data-stu-id="5f846-120">If you want to also remove the Azure AD and Intune objects at the same time, select the check box.</span></span> <span data-ttu-id="5f846-121">Удаление устройства может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="5f846-121">Device removal can take a few minutes to complete.</span></span>

> [!NOTE]
> <span data-ttu-id="5f846-122">Вы не можете удалить устройства, которые находятся в состоянии **ожидания** регистрации.</span><span class="sxs-lookup"><span data-stu-id="5f846-122">You can't remove devices that are in a **pending** registration state.</span></span>