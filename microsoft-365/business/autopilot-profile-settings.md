---
title: Сведения о параметрах профиля AutoPilot
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: Профили автопилота помогают контролировать установку Windows на устройствах пользователей. Профили содержат параметры по умолчанию и необязательные параметры, например пропуск установки Кортаны.
ms.openlocfilehash: 0c706d12ba262856ff40ea3bee57c64234fd77f7
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165848"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="2d857-104">Сведения о параметрах профиля AutoPilot</span><span class="sxs-lookup"><span data-stu-id="2d857-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="2d857-105">Параметры профиля для автопилота</span><span class="sxs-lookup"><span data-stu-id="2d857-105">AutoPilot profile settings</span></span>

<span data-ttu-id="2d857-106">Вы можете использовать профили автопилота для управления установкой Windows на устройствах пользователей.</span><span class="sxs-lookup"><span data-stu-id="2d857-106">You can use AutoPilot profiles to control how Windows is installed on user devices.</span></span> <span data-ttu-id="2d857-107">Эти профили содержат описанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="2d857-107">The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="2d857-108">**Компоненты автопилота по умолчанию (обязательные), которые устанавливаются автоматически:**</span><span class="sxs-lookup"><span data-stu-id="2d857-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="2d857-109">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="2d857-109">**Setting**</span></span>|<span data-ttu-id="2d857-110">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2d857-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2d857-111">Пропуск регистрации Кортаны, OneDrive и ИВТ</span><span class="sxs-lookup"><span data-stu-id="2d857-111">Skip Cortana, OneDrive, and OEM registration</span></span>  <br/> |<span data-ttu-id="2d857-112">Пропускает установку пользовательских приложений, таких как Кортана и личное хранилище OneDrive.</span><span class="sxs-lookup"><span data-stu-id="2d857-112">Skips the installation of consumer apps like Cortana and personal OneDrive.</span></span> <span data-ttu-id="2d857-113">Пользователь устройства может устанавливать их позже, если пользователь является локальным администратором на устройстве.</span><span class="sxs-lookup"><span data-stu-id="2d857-113">The device user can install these later as long as the user is a local admin on the device.</span></span> <span data-ttu-id="2d857-114">Исходная регистрация изготовителя пропускается, так как устройство будет управляться с помощью Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="2d857-114">The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="2d857-115">Интерфейс входа с фирменной символикой компании</span><span class="sxs-lookup"><span data-stu-id="2d857-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="2d857-116">Если у вашей компании есть [возможность добавить фирменную символику компании на страницу входа в Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/customize-sign-in-page), пользователь устройства получит этот интерфейс при входе.</span><span class="sxs-lookup"><span data-stu-id="2d857-116">If your company has a [Add your company branding to Microsoft 365 Sign In page](https://docs.microsoft.com/microsoft-365/admin/setup/customize-sign-in-page), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="2d857-117">Автоматическая регистрация в службе управления мобильными устройствами с использованием настроенных учетных записей AAD</span><span class="sxs-lookup"><span data-stu-id="2d857-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="2d857-118">Удостоверение пользователя будет управляться Azure Active Directory, и пользователи будут входить в Windows и Microsoft 365 с помощью учетных данных Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="2d857-118">The user identity will be managed by Azure Active Directory, and users will sign in to Windows and Microsoft 365 with their Microsoft 365 Business Premium credentials.</span></span>  <br/> |
   
 <span data-ttu-id="2d857-119">**Дополнительные параметры**</span><span class="sxs-lookup"><span data-stu-id="2d857-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="2d857-120">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="2d857-120">**Setting**</span></span>|<span data-ttu-id="2d857-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2d857-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2d857-122">Пропустить параметры конфиденциальности (по умолчанию выключен)</span><span class="sxs-lookup"><span data-stu-id="2d857-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="2d857-123">Если для этого параметра установить значение **Вкл.**, пользователь устройства не увидит условия лицензии для устройства и Windows при первом входе.</span><span class="sxs-lookup"><span data-stu-id="2d857-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="2d857-124">Не разрешать пользователю становиться локальным администратором</span><span class="sxs-lookup"><span data-stu-id="2d857-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="2d857-125">Если для этого параметра установить значение **Вкл.**, пользователь устройства не сможет устанавливать личные приложения, такие как Кортана.</span><span class="sxs-lookup"><span data-stu-id="2d857-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span><br/> |
   
