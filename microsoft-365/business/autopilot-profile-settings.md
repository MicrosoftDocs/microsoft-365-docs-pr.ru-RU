---
title: Сведения о параметрах профиля AutoPilot
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: Профили AutoPilot помогают управлять установкой Windows на устройствах пользователей. Профили содержат по умолчанию и необязательные параметры, такие как пропустить установку Кортаны.
ms.openlocfilehash: 86f8718131f0a0b93e18e65e39e02e7d65aded1a
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578514"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="685b0-104">Сведения о параметрах профиля AutoPilot</span><span class="sxs-lookup"><span data-stu-id="685b0-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="685b0-105">Параметры профилей AutoPilot</span><span class="sxs-lookup"><span data-stu-id="685b0-105">AutoPilot profile settings</span></span>

<span data-ttu-id="685b0-106">Вы можете использовать профили АвтоПилота для управления Windows установлен на устройствах пользователей.</span><span class="sxs-lookup"><span data-stu-id="685b0-106">You can use AutoPilot profiles to control how Windows is installed on user devices.</span></span> <span data-ttu-id="685b0-107">Эти профили содержат описанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="685b0-107">The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="685b0-108">**Автоматически задаваемы функции по умолчанию AutoPilot:**</span><span class="sxs-lookup"><span data-stu-id="685b0-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="685b0-109">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="685b0-109">**Setting**</span></span>|<span data-ttu-id="685b0-110">**Описание**</span><span class="sxs-lookup"><span data-stu-id="685b0-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="685b0-111">Пропустить регистрацию кортаны, OneDrive и OEM</span><span class="sxs-lookup"><span data-stu-id="685b0-111">Skip Cortana, OneDrive, and OEM registration</span></span>  <br/> |<span data-ttu-id="685b0-112">Пропускает установку потребительских приложений, таких как Кортана и личные OneDrive.</span><span class="sxs-lookup"><span data-stu-id="685b0-112">Skips the installation of consumer apps like Cortana and personal OneDrive.</span></span> <span data-ttu-id="685b0-113">Пользователь устройства может установить их позже, если пользователь является локальным администратором на устройстве.</span><span class="sxs-lookup"><span data-stu-id="685b0-113">The device user can install these later as long as the user is a local admin on the device.</span></span> <span data-ttu-id="685b0-114">Оригинальная регистрация производителя пропускается, так как устройство будет управляться Microsoft 365 бизнес премиум.</span><span class="sxs-lookup"><span data-stu-id="685b0-114">The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="685b0-115">Интерфейс входа с фирменной символикой компании</span><span class="sxs-lookup"><span data-stu-id="685b0-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="685b0-116">Если в вашей компании есть страница Добавить брендинг [Microsoft 365,](../admin/setup/customize-sign-in-page.md)пользователь устройства получит этот опыт при входе.</span><span class="sxs-lookup"><span data-stu-id="685b0-116">If your company has a [Add your company branding to Microsoft 365 Sign In page](../admin/setup/customize-sign-in-page.md), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="685b0-117">Автоматическая регистрация в службе управления мобильными устройствами с использованием настроенных учетных записей AAD</span><span class="sxs-lookup"><span data-stu-id="685b0-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="685b0-118">Идентификатор пользователя будет управляться Azure Active Directory, и пользователи будут Windows и Microsoft 365 с Microsoft 365 бизнес премиум учетными данными.</span><span class="sxs-lookup"><span data-stu-id="685b0-118">The user identity will be managed by Azure Active Directory, and users will sign in to Windows and Microsoft 365 with their Microsoft 365 Business Premium credentials.</span></span>  <br/> |
   
 <span data-ttu-id="685b0-119">**Дополнительные параметры**</span><span class="sxs-lookup"><span data-stu-id="685b0-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="685b0-120">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="685b0-120">**Setting**</span></span>|<span data-ttu-id="685b0-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="685b0-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="685b0-122">Пропустить параметры конфиденциальности (по умолчанию выключен)</span><span class="sxs-lookup"><span data-stu-id="685b0-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="685b0-123">Если для этого параметра установить значение **Вкл.**, пользователь устройства не увидит условия лицензии для устройства и Windows при первом входе.</span><span class="sxs-lookup"><span data-stu-id="685b0-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="685b0-124">Не разрешать пользователю становиться локальным администратором</span><span class="sxs-lookup"><span data-stu-id="685b0-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="685b0-125">Если для этого параметра установить значение **Вкл.**, пользователь устройства не сможет устанавливать личные приложения, такие как Кортана.</span><span class="sxs-lookup"><span data-stu-id="685b0-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span><br/> |
