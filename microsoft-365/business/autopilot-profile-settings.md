---
title: Сведения о параметрах профиля AutoPilot
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
ms.openlocfilehash: 912a24e3d458986a4bcf7dcf903f80211996aca2
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "38321792"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="f4809-104">Сведения о параметрах профиля AutoPilot</span><span class="sxs-lookup"><span data-stu-id="f4809-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="f4809-105">Параметры профиля для автопилота</span><span class="sxs-lookup"><span data-stu-id="f4809-105">AutoPilot profile settings</span></span>

<span data-ttu-id="f4809-106">Вы можете использовать профили автопилота для управления установкой Windows на устройствах пользователей.</span><span class="sxs-lookup"><span data-stu-id="f4809-106">You can use AutoPilot profiles to control how Windows is installed on user devices.</span></span> <span data-ttu-id="f4809-107">Эти профили содержат описанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="f4809-107">The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="f4809-108">**Компоненты автопилота по умолчанию (обязательные), которые устанавливаются автоматически:**</span><span class="sxs-lookup"><span data-stu-id="f4809-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="f4809-109">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="f4809-109">**Setting**</span></span>|<span data-ttu-id="f4809-110">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f4809-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f4809-111">Пропуск регистрации Кортаны, OneDrive и ИВТ</span><span class="sxs-lookup"><span data-stu-id="f4809-111">Skip Cortana, OneDrive, and OEM registration</span></span>  <br/> |<span data-ttu-id="f4809-112">Пропускает установку пользовательских приложений, таких как Кортана и личное хранилище OneDrive.</span><span class="sxs-lookup"><span data-stu-id="f4809-112">Skips the installation of consumer apps like Cortana and personal OneDrive.</span></span> <span data-ttu-id="f4809-113">Пользователь устройства может устанавливать их позже, если пользователь является локальным администратором на устройстве.</span><span class="sxs-lookup"><span data-stu-id="f4809-113">The device user can install these later as long as the user is a local admin on the device.</span></span> <span data-ttu-id="f4809-114">Первоначальная регистрация изготовителя оборудования пропускается, потому что устройством будет управлять Office 365 бизнес.</span><span class="sxs-lookup"><span data-stu-id="f4809-114">The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="f4809-115">Интерфейс входа с фирменной символикой компании</span><span class="sxs-lookup"><span data-stu-id="f4809-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="f4809-116">Если у вашей компании есть [Добавление фирменной символики компании на страницу входа в Office 365](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), то пользователь устройства получит этот интерфейс при входе.</span><span class="sxs-lookup"><span data-stu-id="f4809-116">If your company has a [Add your company branding to Office 365 Sign In page](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="f4809-117">Автоматическая регистрация в службе управления мобильными устройствами с использованием настроенных учетных записей AAD</span><span class="sxs-lookup"><span data-stu-id="f4809-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="f4809-118">Удостоверение пользователя будет управляться Azure Active Directory, и пользователи будут входить в Windows и Office 365 с помощью учетных данных Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="f4809-118">The user identity will be managed by Azure Active Directory, and users will sign in to Windows and Office 365 with their Microsoft 365 Business credentials.</span></span>  <br/> |
   
 <span data-ttu-id="f4809-119">**Дополнительные параметры**</span><span class="sxs-lookup"><span data-stu-id="f4809-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="f4809-120">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="f4809-120">**Setting**</span></span>|<span data-ttu-id="f4809-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f4809-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f4809-122">Пропустить параметры конфиденциальности (по умолчанию выключен)</span><span class="sxs-lookup"><span data-stu-id="f4809-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="f4809-123">Если для этого параметра установить значение **Вкл.**, пользователь устройства не увидит условия лицензии для устройства и Windows при первом входе.</span><span class="sxs-lookup"><span data-stu-id="f4809-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="f4809-124">Не разрешать пользователю становиться локальным администратором</span><span class="sxs-lookup"><span data-stu-id="f4809-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="f4809-125">Если для этого параметра установить значение **Вкл.**, пользователь устройства не сможет устанавливать личные приложения, такие как Кортана.</span><span class="sxs-lookup"><span data-stu-id="f4809-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span><br/> |
   
