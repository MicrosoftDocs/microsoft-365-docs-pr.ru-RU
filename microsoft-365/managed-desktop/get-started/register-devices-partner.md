---
title: Этапы регистрации устройств для партнеров
description: Как партнеры могут регистрировать устройства, чтобы управлять ими с помощью Microsoft Managed Desktop
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
ms.openlocfilehash: 227786fdcf1e490be1e3ce74bbc1be1c5f21acfe
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689237"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="1d6a1-103">Этапы регистрации устройств для партнеров</span><span class="sxs-lookup"><span data-stu-id="1d6a1-103">Steps for Partners to register devices</span></span>


<span data-ttu-id="1d6a1-104">В этой статье описываются действия, которые необходимо предпринять партнерам для регистрации устройств.</span><span class="sxs-lookup"><span data-stu-id="1d6a1-104">This article describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="1d6a1-105">Процесс самостоятельной регистрации устройств задокументирован на [устройствах Register в Microsoft Managed Desktop.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="1d6a1-105">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="1d6a1-106">Подготовка к регистрации</span><span class="sxs-lookup"><span data-stu-id="1d6a1-106">Prepare for registration</span></span> 
<span data-ttu-id="1d6a1-107">Прежде чем завершить регистрацию для клиента, сначала необходимо установить отношения с ними в [Центре партнеров.](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="1d6a1-107">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="1d6a1-108">Дополнительные [сведения об](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) этом процессе см. в документации по согласию.</span><span class="sxs-lookup"><span data-stu-id="1d6a1-108">See the [consent documentation](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) for more details on that process.</span></span> <span data-ttu-id="1d6a1-109">Любой партнер CSP может добавлять устройства от имени любого клиента, если клиент соглашается.</span><span class="sxs-lookup"><span data-stu-id="1d6a1-109">Any CSP partner can add devices on behalf of any customer, as long as the customer consents.</span></span> <span data-ttu-id="1d6a1-110">Вы также можете узнать больше о партнерских отношениях и разрешениях автопилота в [справке Центра партнеров.](/partner-center/customers_revoke_admin_privileges#windows-autopilot)</span><span class="sxs-lookup"><span data-stu-id="1d6a1-110">You can also learn more about partner relationships and Autopilot permissions at [Partner Center help](/partner-center/customers_revoke_admin_privileges#windows-autopilot).</span></span>


> [!NOTE]
> <span data-ttu-id="1d6a1-111">Эта документация только для партнеров и OEMs.</span><span class="sxs-lookup"><span data-stu-id="1d6a1-111">This documentation is only for Partners and OEMs.</span></span> <span data-ttu-id="1d6a1-112">Процесс саморегистрации задокументирован на [устройствах Register в Microsoft Managed Desktop самостоятельно.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="1d6a1-112">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>


## <a name="register-devices-by-using-partner-center"></a><span data-ttu-id="1d6a1-113">Регистрация устройств с помощью Центра партнеров</span><span class="sxs-lookup"><span data-stu-id="1d6a1-113">Register devices by using Partner Center</span></span>

<span data-ttu-id="1d6a1-114">После того как вы установили отношения с клиентами, вы можете использовать Центр партнеров для добавления устройств в Автопилот для любого из клиентов, с которые у вас есть отношения, следуя следующим шагам:</span><span class="sxs-lookup"><span data-stu-id="1d6a1-114">Once you have established the relationship with your customers, you can use Partner Center to add devices to Autopilot for any of the customers that you have a relationship with by following these steps:</span></span>

1. <span data-ttu-id="1d6a1-115">Перейдите в [Центр партнеров](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="1d6a1-115">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="1d6a1-116">Выберите **клиентов** из меню Центра партнеров, а затем выберите клиента, устройства которого вы хотите управлять.</span><span class="sxs-lookup"><span data-stu-id="1d6a1-116">Select **Customers** from the Partner Center menu and then select the customer whose devices you want to manage.</span></span>
3. <span data-ttu-id="1d6a1-117">На странице детализации клиента выберите **Устройства**.</span><span class="sxs-lookup"><span data-stu-id="1d6a1-117">On the customer's detail page, select **Devices**.</span></span>
4. <span data-ttu-id="1d6a1-118">В **статье Применение профилей к** устройствам выберите Добавить **устройства.**</span><span class="sxs-lookup"><span data-stu-id="1d6a1-118">Under **Apply profiles** to devices, select **Add devices**.</span></span>
5. <span data-ttu-id="1d6a1-119">Введите соответствующий групповой тег для выбранного профиля устройства (как показано в следующей таблице), а затем выберите **Просмотр** для отправки списка клиента (в формате файлов csv) в Центр партнеров.</span><span class="sxs-lookup"><span data-stu-id="1d6a1-119">Enter the appropriate Group Tag for the device profile you've selected (as shown in the following table) and then select **Browse** to upload the customer's list (in .csv file format) to Partner Center.</span></span>

|[<span data-ttu-id="1d6a1-120">Профиль устройства</span><span class="sxs-lookup"><span data-stu-id="1d6a1-120">Device profile</span></span>](../service-description/profiles.md)  |<span data-ttu-id="1d6a1-121">Тег группы</span><span class="sxs-lookup"><span data-stu-id="1d6a1-121">Group Tag</span></span>  |
|---------|---------|
|<span data-ttu-id="1d6a1-122">Конфиденциальные данные</span><span class="sxs-lookup"><span data-stu-id="1d6a1-122">Sensitive data</span></span>     |<span data-ttu-id="1d6a1-123">**Microsoft365Managed \_ SensitiveData**</span><span class="sxs-lookup"><span data-stu-id="1d6a1-123">**Microsoft365Managed\_SensitiveData**</span></span>    |
|<span data-ttu-id="1d6a1-124">Power user</span><span class="sxs-lookup"><span data-stu-id="1d6a1-124">Power user</span></span>     | <span data-ttu-id="1d6a1-125">**Microsoft365Managed \_ PowerUser**</span><span class="sxs-lookup"><span data-stu-id="1d6a1-125">**Microsoft365Managed\_PowerUser**</span></span>          |
|<span data-ttu-id="1d6a1-126">Стандартный</span><span class="sxs-lookup"><span data-stu-id="1d6a1-126">Standard</span></span>     | <span data-ttu-id="1d6a1-127">**Стандарт Microsoft365Managed \_**</span><span class="sxs-lookup"><span data-stu-id="1d6a1-127">**Microsoft365Managed\_Standard**</span></span>        |

> [!IMPORTANT]
> <span data-ttu-id="1d6a1-128">Имя группы должно точно соответствовать тем, которые указаны в таблице, включая капитализацию и специальные символы.</span><span class="sxs-lookup"><span data-stu-id="1d6a1-128">The Group Name must match those listed in the table exactly, including capitalization and special characters.</span></span> <span data-ttu-id="1d6a1-129">Это позволит вновь зарегистрированным устройствам быть назначены с профилем Microsoft Managed Desktop Autopilot.</span><span class="sxs-lookup"><span data-stu-id="1d6a1-129">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>

>[!NOTE]
> <span data-ttu-id="1d6a1-130">Вы должны были получить этот файл CSV с покупкой устройства.</span><span class="sxs-lookup"><span data-stu-id="1d6a1-130">You should have received this .csv file with your device purchase.</span></span> <span data-ttu-id="1d6a1-131">Если вы не получили файл CSV, вы можете создать его самостоятельно, следуя шагам в добавлении устройств в [Windows Autopilot.](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)</span><span class="sxs-lookup"><span data-stu-id="1d6a1-131">If you didn't receive a .csv file, you can create one yourself by following the steps in [Adding devices to Windows Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell).</span></span> <span data-ttu-id="1d6a1-132">Сценарий Windows PowerShell отличается от сценария, используемого для портала [администрирования microsoft Managed Desktop.](./register-devices-self.md#obtain-the-hardware-hash)</span><span class="sxs-lookup"><span data-stu-id="1d6a1-132">The Windows PowerShell script is different from the one used for the [Microsoft Managed Desktop Admin portal](./register-devices-self.md#obtain-the-hardware-hash).</span></span> <span data-ttu-id="1d6a1-133">Партнеры должны использовать [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) для регистрации устройств для устройств Microsoft Managed Desktop в Центре партнеров.</span><span class="sxs-lookup"><span data-stu-id="1d6a1-133">Partners should use [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to register devices for Microsoft Managed Desktop devices in Partner Center.</span></span>

<span data-ttu-id="1d6a1-134">Если вы получаете сообщение об ошибке при попытке загрузить файл .csv, проверьте формат файла.</span><span class="sxs-lookup"><span data-stu-id="1d6a1-134">If you get an error message while trying to upload the .csv file, check the format of the file.</span></span> <span data-ttu-id="1d6a1-135">Убедитесь, что порядок столбца совпадает с тем, что описано в профилей [Автопилота Windows](/partner-center/autopilot#add-devices-to-a-customers-account)на новых устройствах, чтобы настроить пользовательские возможности.</span><span class="sxs-lookup"><span data-stu-id="1d6a1-135">Make sure the column order matches what is described in [Use Windows Autopilot profiles on new devices to customize a customer's out-of-box experience](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span> <span data-ttu-id="1d6a1-136">Для создания списка устройств можно также использовать пример файла CSV, предоставленного по ссылке рядом с **Добавлением** устройств.</span><span class="sxs-lookup"><span data-stu-id="1d6a1-136">You can also use the sample .csv file provided from the link next to **Add devices** to create a device list.</span></span> 

<span data-ttu-id="1d6a1-137">Дополнительные сведения об автопилоте в сценариях партнеров см. в добавлении [устройств к учетной записи клиента.](/partner-center/autopilot#add-devices-to-a-customers-account)</span><span class="sxs-lookup"><span data-stu-id="1d6a1-137">For more information about Autopilot in Partner scenarios, see [Add devices to a customer’s account](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span>


## <a name="register-devices-by-using-the-oem-api"></a><span data-ttu-id="1d6a1-138">Регистрация устройств с помощью API OEM</span><span class="sxs-lookup"><span data-stu-id="1d6a1-138">Register devices by using the OEM API</span></span>

<span data-ttu-id="1d6a1-139">Прежде чем завершить регистрацию для клиента, сначала необходимо установить с ним связь.</span><span class="sxs-lookup"><span data-stu-id="1d6a1-139">Before completing registration for a customer, you must first establish a relationship with them.</span></span> <span data-ttu-id="1d6a1-140">У вас должна быть уникальная ссылка, которая будет предоставляться соответствующим клиентам.</span><span class="sxs-lookup"><span data-stu-id="1d6a1-140">You should have a unique link to provide to your respective customers.</span></span> <span data-ttu-id="1d6a1-141">Узнайте, [как установить связь OEM.](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)</span><span class="sxs-lookup"><span data-stu-id="1d6a1-141">See [How to establish OEM relationship](/windows/deployment/windows-autopilot/registration-auth#oem-authorization).</span></span>

<span data-ttu-id="1d6a1-142">После того как вы установили связь, вы можете начать регистрацию устройств для клиентов с помощью соответствующего группового тега для каждого выбранного ими профиля устройства:</span><span class="sxs-lookup"><span data-stu-id="1d6a1-142">Once you've established the relationship, you can start registering devices for customers using the appropriate Group Tag for each device profile they've selected:</span></span>


|<span data-ttu-id="1d6a1-143">Профиль устройства</span><span class="sxs-lookup"><span data-stu-id="1d6a1-143">Device profile</span></span>  |<span data-ttu-id="1d6a1-144">Тег группы</span><span class="sxs-lookup"><span data-stu-id="1d6a1-144">Group Tag</span></span>  |
|---------|---------|
|<span data-ttu-id="1d6a1-145">Конфиденциальные данные</span><span class="sxs-lookup"><span data-stu-id="1d6a1-145">Sensitive data</span></span>     | <span data-ttu-id="1d6a1-146">**Microsoft365Managed \_ SensitiveData**</span><span class="sxs-lookup"><span data-stu-id="1d6a1-146">**Microsoft365Managed\_SensitiveData**</span></span>     |
|<span data-ttu-id="1d6a1-147">Power user</span><span class="sxs-lookup"><span data-stu-id="1d6a1-147">Power user</span></span>     | <span data-ttu-id="1d6a1-148">**Microsoft365Managed \_ PowerUser**</span><span class="sxs-lookup"><span data-stu-id="1d6a1-148">**Microsoft365Managed\_PowerUser**</span></span>          |
|<span data-ttu-id="1d6a1-149">Стандартный</span><span class="sxs-lookup"><span data-stu-id="1d6a1-149">Standard</span></span>     | <span data-ttu-id="1d6a1-150">**Стандарт Microsoft365Managed \_**</span><span class="sxs-lookup"><span data-stu-id="1d6a1-150">**Microsoft365Managed\_Standard**</span></span>      |

> [!IMPORTANT]
> <span data-ttu-id="1d6a1-151">Теги группы должны точно соответствовать тем, которые указаны в таблице, включая капитализацию и специальные символы.</span><span class="sxs-lookup"><span data-stu-id="1d6a1-151">The Group Tags must match those listed in the table exactly, including capitalization and special characters.</span></span> <span data-ttu-id="1d6a1-152">Это позволит вновь зарегистрированным устройствам быть назначены с профилем Microsoft Managed Desktop Autopilot.</span><span class="sxs-lookup"><span data-stu-id="1d6a1-152">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>