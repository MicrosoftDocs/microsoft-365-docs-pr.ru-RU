---
title: Сведения о параметрах профиля AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: Профили автопилот помогают управлять тем, как Windows получает установлены на устройствах пользователей. Профили содержат по умолчанию и необязательные параметры, например пропустить Cortana установки.
ms.openlocfilehash: 5440286f1363780c87ab60514584c4addfeea0b2
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870465"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="db543-104">Сведения о параметрах профиля AutoPilot</span><span class="sxs-lookup"><span data-stu-id="db543-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="db543-105">Параметры профиля AutoPilot</span><span class="sxs-lookup"><span data-stu-id="db543-105">AutoPilot profile settings</span></span>

<span data-ttu-id="db543-p102">Можно управлять как Windows устанавливается на устройствах пользователей с помощью профилей автопилот. Профили содержат следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="db543-p102">You can control how Windows gets installed on user devices by using the AutoPilot profiles. The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="db543-108">**Автопилот компоненты по умолчанию (обязательно), которые устанавливаются автоматически:**</span><span class="sxs-lookup"><span data-stu-id="db543-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="db543-109">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="db543-109">**Setting**</span></span>|<span data-ttu-id="db543-110">**Описание**</span><span class="sxs-lookup"><span data-stu-id="db543-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="db543-111">Пропуск регистрации Кортаны, OneDrive и изготовителя оборудования</span><span class="sxs-lookup"><span data-stu-id="db543-111">Skip Cortana, OneDrive and OEM registration</span></span>  <br/> |<span data-ttu-id="db543-p103">Пропускает установки потребителей приложения как Cortana и личные OneDrive. В частности, пользователь можно установить эти более поздней версии, до тех пор, пока не является локального администратора на устройстве. Исходной регистрации производитель пропущен, поскольку устройство будет осуществляться с Microsoft 365 для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="db543-p103">Skips the installation of consumer apps like Cortana and personal OneDrive. The device user can install these later as long as he or she is a local admin on the device. The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="db543-115">Интерфейс входа с фирменной символикой компании</span><span class="sxs-lookup"><span data-stu-id="db543-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="db543-116">Если у компании есть [Добавить вашей компании фирменной символики в Office 365 страницу входа](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), в частности, пользователь получит этот опыт при входе.</span><span class="sxs-lookup"><span data-stu-id="db543-116">If your company has a [Add your company branding to Office 365 Sign In page](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="db543-117">Автоматическая регистрация в службе управления мобильными устройствами с использованием настроенных учетных записей AAD</span><span class="sxs-lookup"><span data-stu-id="db543-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="db543-118">Удостоверениями пользователей управляет Azure Active Directory. Пользователи входят в Windows и Office 365 со своими учетными данными Office 365 бизнес.</span><span class="sxs-lookup"><span data-stu-id="db543-118">The user identity will be managed by Azure Active directory, and the users will sign into Windows and Office 365 with their Microsoft 365 Business credentials.</span></span>  <br/> |
   
 <span data-ttu-id="db543-119">**Дополнительные параметры**</span><span class="sxs-lookup"><span data-stu-id="db543-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="db543-120">**Настройка**</span><span class="sxs-lookup"><span data-stu-id="db543-120">**Setting**</span></span>|<span data-ttu-id="db543-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="db543-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="db543-122">Пропустить параметры конфиденциальности (по умолчанию выключен)</span><span class="sxs-lookup"><span data-stu-id="db543-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="db543-123">Если для этого параметра установить значение **Вкл.**, пользователь устройства не увидит условия лицензии для устройства и Windows при первом входе.</span><span class="sxs-lookup"><span data-stu-id="db543-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="db543-124">Не разрешать пользователю становиться локальным администратором</span><span class="sxs-lookup"><span data-stu-id="db543-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="db543-125">Если для этого параметра установить значение **Вкл.**, пользователь устройства не сможет устанавливать личные приложения, такие как Кортана.</span><span class="sxs-lookup"><span data-stu-id="db543-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span>  <br/> |
   
