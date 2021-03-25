---
title: Предварительные требования к удостоверениям и доступу к устройствам для облачного применения в тестовой среде Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Создание среды Microsoft 365 для тестирования удостоверений и доступа к устройствам с предварительными требованиями для облачной проверки подлинности.
ms.openlocfilehash: 927aa032e4181206b3a744da7076b696ac5cf4d4
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199553"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a><span data-ttu-id="82f5d-103">Предварительные требования к удостоверениям и доступу к устройствам для облачного применения в тестовой среде Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="82f5d-103">Identity and device access prerequisites for cloud only in your Microsoft 365 test environment</span></span>

<span data-ttu-id="82f5d-104">*Это руководство по тестовой лаборатории можно использовать только для Microsoft 365 для корпоративных тестовых сред.*</span><span class="sxs-lookup"><span data-stu-id="82f5d-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="82f5d-105">[Конфигурации удостоверений](../security/office-365-security/microsoft-365-policies-configurations.md) и доступа к устройствам — это набор рекомендуемых конфигураций и политики условного доступа для защиты доступа ко всем службам, интегрированным с Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="82f5d-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of recommended configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="82f5d-106">В этой статье описано, как настроить тестовую среду Microsoft 365, соответствующую требованиям [предварительной настройки облачной среды](../security/office-365-security/identity-access-prerequisites.md#prerequisites) для удостоверений и доступа к устройствам.</span><span class="sxs-lookup"><span data-stu-id="82f5d-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [cloud only prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="82f5d-107">Настройка этой тестовой среды состоит из восьми следующих этапов:</span><span class="sxs-lookup"><span data-stu-id="82f5d-107">There are eight phases to setting up this test environment:</span></span>

1. <span data-ttu-id="82f5d-108">Создание простой тестовой среды</span><span class="sxs-lookup"><span data-stu-id="82f5d-108">Build out your lightweight test environment</span></span>
2. <span data-ttu-id="82f5d-109">Настройка именованных расположений</span><span class="sxs-lookup"><span data-stu-id="82f5d-109">Configure named locations</span></span>
3. <span data-ttu-id="82f5d-110">Настройка самостоятельного сброса пароля</span><span class="sxs-lookup"><span data-stu-id="82f5d-110">Configure self-service password reset</span></span>
4. <span data-ttu-id="82f5d-111">Настройка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="82f5d-111">Configure multifactor authentication</span></span>
5. <span data-ttu-id="82f5d-112">Включить автоматическую регистрацию устройств на компьютерах Windows, присоединив к домену</span><span class="sxs-lookup"><span data-stu-id="82f5d-112">Enable automatic device registration of domain-joined Windows computers</span></span>
6. <span data-ttu-id="82f5d-113">Настройка защиты паролей Azure AD</span><span class="sxs-lookup"><span data-stu-id="82f5d-113">Configure Azure AD password protection</span></span> 
7. <span data-ttu-id="82f5d-114">Включение защиты идентификации Azure AD</span><span class="sxs-lookup"><span data-stu-id="82f5d-114">Enable Azure AD Identity Protection</span></span>
8. <span data-ttu-id="82f5d-115">Включение современной проверки подлинности для Exchange Online и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="82f5d-115">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a><span data-ttu-id="82f5d-116">Этап 1. Создание упрощенной тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="82f5d-116">Phase 1: Build out your lightweight Microsoft 365 test environment</span></span>

<span data-ttu-id="82f5d-117">Следуйте инструкциям в статье [Простая базовая конфигурация](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="82f5d-117">Follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
<span data-ttu-id="82f5d-118">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="82f5d-118">Here is the resulting configuration.</span></span>

![Простая среда тестирования Microsoft 365 корпоративный](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 
## <a name="phase-2-configure-named-locations"></a><span data-ttu-id="82f5d-120">Этап 2. Настройка именованных расположений</span><span class="sxs-lookup"><span data-stu-id="82f5d-120">Phase 2: Configure named locations</span></span>

<span data-ttu-id="82f5d-121">Сначала определите общедоступные IP-адреса или диапазоны адресов, используемые в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="82f5d-121">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="82f5d-122">Затем выполните инструкции из статьи [Настройка именованных расположений в Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) для добавления адресов или диапазонов адресов в качестве именованных расположений.</span><span class="sxs-lookup"><span data-stu-id="82f5d-122">Next, follow the instructions in [Configure named locations in Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-3-configure-self-service-password-reset"></a><span data-ttu-id="82f5d-123">Этап 3. Настройка сброса пароля самообслуживки</span><span class="sxs-lookup"><span data-stu-id="82f5d-123">Phase 3: Configure self-service password reset</span></span>

<span data-ttu-id="82f5d-124">Выполните инструкции [этапа 3 руководства по лаборатории тестирования для сброса пароля](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="82f5d-124">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="82f5d-125">При включении сброса пароля для учетных записей в определенной группе Azure AD добавьте эти учетные записи в группу **Сброс пароля**:</span><span class="sxs-lookup"><span data-stu-id="82f5d-125">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="82f5d-126">Пользователь 2</span><span class="sxs-lookup"><span data-stu-id="82f5d-126">User 2</span></span>
- <span data-ttu-id="82f5d-127">Пользователь 3</span><span class="sxs-lookup"><span data-stu-id="82f5d-127">User 3</span></span>
- <span data-ttu-id="82f5d-128">Пользователь 4</span><span class="sxs-lookup"><span data-stu-id="82f5d-128">User 4</span></span>
- <span data-ttu-id="82f5d-129">Пользователь 5</span><span class="sxs-lookup"><span data-stu-id="82f5d-129">User 5</span></span>

<span data-ttu-id="82f5d-130">Проверьте сброс паролей только для учетной записи "Пользователь 2".</span><span class="sxs-lookup"><span data-stu-id="82f5d-130">Test password reset only for the User 2 account.</span></span>

## <a name="phase-4-configure-multi-factor-authentication"></a><span data-ttu-id="82f5d-131">Этап 4. Настройка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="82f5d-131">Phase 4: Configure multi-factor authentication</span></span>

<span data-ttu-id="82f5d-132">Выполните инструкции [этапа 2 руководства по лаборатории тестирования для многофакторной проверки подлинности](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) для следующих учетных записей пользователей:</span><span class="sxs-lookup"><span data-stu-id="82f5d-132">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="82f5d-133">Пользователь 2</span><span class="sxs-lookup"><span data-stu-id="82f5d-133">User 2</span></span>
- <span data-ttu-id="82f5d-134">Пользователь 3</span><span class="sxs-lookup"><span data-stu-id="82f5d-134">User 3</span></span>
- <span data-ttu-id="82f5d-135">Пользователь 4</span><span class="sxs-lookup"><span data-stu-id="82f5d-135">User 4</span></span>
- <span data-ttu-id="82f5d-136">Пользователь 5</span><span class="sxs-lookup"><span data-stu-id="82f5d-136">User 5</span></span>

<span data-ttu-id="82f5d-137">Протестируйте многофакторную проверку подлинности только для учетной записи "Пользователь 2".</span><span class="sxs-lookup"><span data-stu-id="82f5d-137">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-5-enable-automatic-device-registration-of-domain-joined-windows-computers"></a><span data-ttu-id="82f5d-138">Этап 5. Включить автоматическую регистрацию устройств на компьютерах Windows, присоединив к домену</span><span class="sxs-lookup"><span data-stu-id="82f5d-138">Phase 5: Enable automatic device registration of domain-joined Windows computers</span></span> 

<span data-ttu-id="82f5d-139">Следуйте [этим инструкциям,](/azure/active-directory/devices/hybrid-azuread-join-plan) чтобы включить автоматическую регистрацию устройств на компьютерах Windows, присоединив к домену.</span><span class="sxs-lookup"><span data-stu-id="82f5d-139">Follow [these instructions](/azure/active-directory/devices/hybrid-azuread-join-plan) to enable automatic device registration of domain-joined Windows computers.</span></span>

## <a name="phase-6-configure-azure-ad-password-protection"></a><span data-ttu-id="82f5d-140">Этап 6. Настройка защиты паролей Azure AD</span><span class="sxs-lookup"><span data-stu-id="82f5d-140">Phase 6: Configure Azure AD password protection</span></span> 

<span data-ttu-id="82f5d-141">Следуйте [этим инструкциям,](/azure/active-directory/authentication/concept-password-ban-bad) чтобы заблокировать известные слабые пароли и их варианты.</span><span class="sxs-lookup"><span data-stu-id="82f5d-141">Follow [these instructions](/azure/active-directory/authentication/concept-password-ban-bad) to block known weak passwords and their variants.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="82f5d-142">Этап 7. Включение защиты идентификации Azure AD</span><span class="sxs-lookup"><span data-stu-id="82f5d-142">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="82f5d-143">Выполните инструкции [этапа 2 руководства по лаборатории тестирования для защиты идентификации Azure AD](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="82f5d-143">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="82f5d-144">Этап 8. Включение современной проверки подлинности для Exchange Online и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="82f5d-144">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="82f5d-145">Для Exchange Online выполните [эти инструкции](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span><span class="sxs-lookup"><span data-stu-id="82f5d-145">For Exchange Online, follow [these instructions](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="82f5d-146">Для Skype для бизнеса Online:</span><span class="sxs-lookup"><span data-stu-id="82f5d-146">For Skype for Business Online:</span></span>

1. <span data-ttu-id="82f5d-147">Подключитесь к [Skype для бизнеса Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="82f5d-147">Connect to [Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="82f5d-148">Выполните указанную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="82f5d-148">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="82f5d-149">Проверьте успешность изменения с помощью указанной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="82f5d-149">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="82f5d-150">Результатом является тестовая среда, которая соответствует [](../security/office-365-security/identity-access-prerequisites.md#prerequisites) требованиям конфигурации для удостоверений и доступа к устройствам только для облачной среды.</span><span class="sxs-lookup"><span data-stu-id="82f5d-150">The result is a test environment that meets the requirements of the [cloud-only prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="82f5d-151">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="82f5d-151">Next step</span></span>

<span data-ttu-id="82f5d-152">См. статью [Основные политики доступа для удостоверений и устройств](../security/office-365-security/identity-access-policies.md), чтобы настроить политики, созданные на основе предварительных требований, и защитить удостоверения и устройства.</span><span class="sxs-lookup"><span data-stu-id="82f5d-152">Use [Common identity and device access policies](../security/office-365-security/identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="82f5d-153">См. также</span><span class="sxs-lookup"><span data-stu-id="82f5d-153">See also</span></span>

[<span data-ttu-id="82f5d-154">Руководства по лаборатории тестирования для дополнительного удостоверения</span><span class="sxs-lookup"><span data-stu-id="82f5d-154">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="82f5d-155">Дорожная карта удостоверений</span><span class="sxs-lookup"><span data-stu-id="82f5d-155">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="82f5d-156">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="82f5d-156">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="82f5d-157">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="82f5d-157">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="82f5d-158">Документация по Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="82f5d-158">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)
