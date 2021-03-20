---
title: Microsoft OneDrive
description: Как Microsoft Managed Desktop настраивает OneDrive для зарегистрированных устройств
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation, apps, line-of-business apps, LOB apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a26500c1671afffc7b70d509a4242914631b937c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904844"
---
# <a name="microsoft-onedrive"></a><span data-ttu-id="7045f-104">Microsoft OneDrive</span><span class="sxs-lookup"><span data-stu-id="7045f-104">Microsoft OneDrive</span></span>

<span data-ttu-id="7045f-105">Microsoft Managed Desktop использует [OneDrive для](/onedrive/plan-onedrive-enterprise) бизнеса в качестве облачной службы хранения для всех устройств Microsoft Managed Desktop, чтобы обеспечить максимальное состояние устройств без состояния.</span><span class="sxs-lookup"><span data-stu-id="7045f-105">Microsoft Managed Desktop uses [OneDrive for Business](/onedrive/plan-onedrive-enterprise) as a cloud storage service for all Microsoft Managed Desktop devices to ensure that the devices are as stateless as possible.</span></span> <span data-ttu-id="7045f-106">Пользователь сможет найти свои файлы независимо от того, на какое устройство они впишутся.</span><span class="sxs-lookup"><span data-stu-id="7045f-106">User will be able to find their files no matter which device they sign into.</span></span> <span data-ttu-id="7045f-107">Например, если вы замените устройство Microsoft Managed Desktop на новое, файлы будут автоматически синхронизироваться с новым устройством.</span><span class="sxs-lookup"><span data-stu-id="7045f-107">For example, if you replace a Microsoft Managed Desktop device with a new one, files will automatically sync to the new device.</span></span>

<span data-ttu-id="7045f-108">Мы автоматически настраиваем эти параметры по умолчанию на управляемых устройствах Майкрософт:</span><span class="sxs-lookup"><span data-stu-id="7045f-108">We automatically configure these settings by default on Microsoft Managed Devices:</span></span>

- <span data-ttu-id="7045f-109">OneDrive безмолвно настроена с учетной записью пользователя и автоматически вписалась (без взаимодействия с пользователем) в учетную запись пользователя, которая была использована для входов в Windows.</span><span class="sxs-lookup"><span data-stu-id="7045f-109">OneDrive is silently configured with the user account and automatically signed in (without user interaction) to the user account that was used to sign into Windows.</span></span> <span data-ttu-id="7045f-110">Дополнительные сведения см. в [немого настраивать учетные записи](/onedrive/use-silent-account-configuration) пользователей - OneDrive</span><span class="sxs-lookup"><span data-stu-id="7045f-110">For more information, see [Silently configure user accounts - OneDrive](/onedrive/use-silent-account-configuration)</span></span>

- <span data-ttu-id="7045f-111">Функция Files-On-Demand включена, чтобы пользователи могли получать доступ к файлам из облачного хранилища в OneDrive без необходимости использования дискового пространства.</span><span class="sxs-lookup"><span data-stu-id="7045f-111">The Files-On-Demand feature is enabled so that users can access files from their cloud storage in OneDrive without having to use disk space unnecessarily.</span></span> <span data-ttu-id="7045f-112">Дополнительные сведения см. в [материалах Save disk space with OneDrive Files On-Demand for Windows 10.](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e)</span><span class="sxs-lookup"><span data-stu-id="7045f-112">For more information, see [Save disk space with OneDrive Files On-Demand for Windows 10](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e).</span></span>

- <span data-ttu-id="7045f-113">Функция "Перемещение известных папок" включена безмолвно для архива данных пользователей в облаке, что дает им доступ к своим файлам с любого устройства.</span><span class="sxs-lookup"><span data-stu-id="7045f-113">The Known Folder Move feature is enabled silently to back up users’ data in the cloud, which gives them access to their files from any device.</span></span> <span data-ttu-id="7045f-114">Дополнительные сведения см. в [документе Back up your Documents, Pictures и Desktop folders with OneDrive.](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057)</span><span class="sxs-lookup"><span data-stu-id="7045f-114">For more information, see [Back up your Documents, Pictures, and Desktop folders with OneDrive](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057).</span></span>

- <span data-ttu-id="7045f-115">Пользователи не могут отключить функцию "Перемещение известных папок" или изменить расположение известных папок для обеспечения согласованного работы на устройствах Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="7045f-115">Users cannot disable the Known Folder Move feature or change the location of known folders to ensure a consistent experience across Microsoft Managed Desktop devices.</span></span>

## <a name="user-experience"></a><span data-ttu-id="7045f-116">Взаимодействие с пользователем</span><span class="sxs-lookup"><span data-stu-id="7045f-116">User experience</span></span>

<span data-ttu-id="7045f-117">Когда пользователи microsoft Managed Desktop получают новое устройство, они проходят первый запуск, вводя учетные данные Azure при настройке устройства.</span><span class="sxs-lookup"><span data-stu-id="7045f-117">When Microsoft Managed Desktop users receive a new device, they go through a first-run experience by entering their Azure credentials while setting up the device.</span></span> <span data-ttu-id="7045f-118">После завершения этого процесса они могут получить доступ к рабочему столу и получить доступ к OneDrive.</span><span class="sxs-lookup"><span data-stu-id="7045f-118">After this process is completed, they can access their desktop and have the OneDrive experience.</span></span>

1. <span data-ttu-id="7045f-119">Система сообщает пользователям, что OneDrive был настроен и что они были автоматически подписаны в OneDrive.</span><span class="sxs-lookup"><span data-stu-id="7045f-119">The system tells users that OneDrive has been configured and that they have been automatically signed into OneDrive.</span></span>

:::image type="content" source="media/onedrive-sync.png" alt-text="Чтение уведомлений, в настоящее время синхронизируемая OneDrive, и вы можете редактировать файлы в OneDrive. щелкните здесь, чтобы просмотреть файлы":::

2. <span data-ttu-id="7045f-121">Система сообщает пользователям, что для них настроено перемещение известных папок OneDrive.</span><span class="sxs-lookup"><span data-stu-id="7045f-121">The system tells users that OneDrive Known Folder Move has been configured for them.</span></span>

:::image type="content" source="media/onedrive-folders.png" alt-text="Уведомление, прочитав ИТ-отдел, поддержало важные папки. В настоящее время папки имеются в хранилище OneDrive и доступны на других устройствах.":::

3. <span data-ttu-id="7045f-123">Чтобы предотвратить повторение значков на рабочем столе при сбросе или переостановке устройств, система автоматически удаляет значки Microsoft Edge и Microsoft Teams из синхронизации OneDrive, как показано в этом представлении в Обозревателе файлов.</span><span class="sxs-lookup"><span data-stu-id="7045f-123">To prevent duplicate icons on the desktop when devices are being reset or reimaged, the system automatically removes Microsoft Edge and Microsoft Teams icons from the OneDrive sync, as shown in this view in File Explorer.</span></span>

:::image type="content" source="media/onedrive-teams.png" alt-text="Обозреватель файлов показывает списки Teams и Edge с очищенными флажками и чтение текста наведении, исключаемом из синхронизации.":::


## <a name="onedrive-sync-restrictions"></a><span data-ttu-id="7045f-125">Ограничения синхронизации OneDrive</span><span class="sxs-lookup"><span data-stu-id="7045f-125">OneDrive sync restrictions</span></span>

<span data-ttu-id="7045f-126">Если требуется ограничить синхронизацию OneDrive, рекомендуется управлять доступом с помощью политики условного доступа Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7045f-126">If you need to restrict OneDrive sync, we recommend that you control access with an Azure Active Directory conditional access policy.</span></span> <span data-ttu-id="7045f-127">Дополнительные сведения см. в приложении ["Включить поддержку условного доступа" в приложении синхронизации OneDrive.](/onedrive/enable-conditional-access)</span><span class="sxs-lookup"><span data-stu-id="7045f-127">For more information, see [Enable conditional access support in the OneDrive sync app](/onedrive/enable-conditional-access).</span></span>

<span data-ttu-id="7045f-128">Если вы не можете использовать политику условного доступа Azure AD в организации, ИТ-администратор должен следовать следующим шагам:</span><span class="sxs-lookup"><span data-stu-id="7045f-128">If you can't use an Azure AD conditional access policy in your organization, your IT Admin should follow these steps:</span></span>

1. <span data-ttu-id="7045f-129">Если вы еще не знаете этого, найдите свой ID клиента, как описано в Найти свой ID клиента [Microsoft 365](/onedrive/find-your-office-365-tenant-id).</span><span class="sxs-lookup"><span data-stu-id="7045f-129">If you don't already know it, look up your tenant ID, as described in [Find your Microsoft 365 tenant ID](/onedrive/find-your-office-365-tenant-id).</span></span>
2. <span data-ttu-id="7045f-130">Ворегистрируйтесь в центр администрирования OneDrive и выберите **синхронизацию** в левой области.</span><span class="sxs-lookup"><span data-stu-id="7045f-130">Sign in to the OneDrive admin center, and then select **Sync** in the left pane.</span></span> <span data-ttu-id="7045f-131">Выберите **разрешить синхронизацию только** на ПК, присоединившись к определенным доменам, и добавьте его в список доменов.</span><span class="sxs-lookup"><span data-stu-id="7045f-131">Select the **Allow syncing only on PCs joined to specific domains** check box, and then add the tenant ID to the list of domains.</span></span> <span data-ttu-id="7045f-132">Дополнительные сведения см. в дополнительных сведениях о том, как разрешить синхронизацию только на [компьютерах, присоединившись к определенным доменам.](/onedrive/allow-syncing-only-on-specific-domains)</span><span class="sxs-lookup"><span data-stu-id="7045f-132">For more information, see [Allow syncing only on computers joined to specific domains](/onedrive/allow-syncing-only-on-specific-domains).</span></span>

> [!NOTE]
> <span data-ttu-id="7045f-133">Это руководство применяется только к арендаторам в Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="7045f-133">This guidance applies only to tenants in Microsoft Managed Desktop.</span></span> <span data-ttu-id="7045f-134">В этой статье используются другие параметры, которые не обсуждаются.</span><span class="sxs-lookup"><span data-stu-id="7045f-134">There are other settings in use that aren't discussed in this article.</span></span>