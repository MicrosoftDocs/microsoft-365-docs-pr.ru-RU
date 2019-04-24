---
title: Критерии выхода инфраструктуры управления мобильными устройствами
description: Microsoft 365 Enterprise включает управление мобильными устройствами с помощью Microsoft Intune. Ознакомьтесь с требованиями и необходимыми условиями, настройте Intune, используя ресурс Azure Active Directory, регистрацию устройств iOS, macOS, Android и Windows, развертывание приложений, создание профиля, использование политики соответствия и включение условного доступа для мобильных устройств Управление устройствами с помощью Microsoft 365 корпоративный.
keywords: Microsoft 365, Microsoft 365 корпоративный, документация по Microsoft 365, управление мобильными устройствами, Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: 14f216fe352d9108fe69028731f4c94dfb9d19f7
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291236"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a><span data-ttu-id="71f12-105">Критерии выхода инфраструктуры управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="71f12-105">Mobile device management infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

<span data-ttu-id="71f12-106">*Это относится к версиям Microsoft 365 корпоративный для E3 и "# $"*</span><span class="sxs-lookup"><span data-stu-id="71f12-106">*This applies to the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="71f12-107">Убедитесь, что ваша конфигурация соответствует следующим требованиям для инфраструктуры управления мобильными устройствами.</span><span class="sxs-lookup"><span data-stu-id="71f12-107">Ensure that your configuration meets the following requirements for mobile device management infrastructure.</span></span>

- <span data-ttu-id="71f12-108">Настройка Intune, в том числе для создания групп и пользователей Azure AD, выполняется для применения правил организации к устройствам.</span><span class="sxs-lookup"><span data-stu-id="71f12-108">Intune is set up, including the creation of Azure AD users and groups to apply your organization's rules for devices.</span></span>
- <span data-ttu-id="71f12-109">Ваши устройства зарегистрированы в Intune, чтобы они могли получать политики, которые вы создаете.</span><span class="sxs-lookup"><span data-stu-id="71f12-109">You have enrolled devices in Intune so that the devices can receive the policies you create.</span></span>
- <span data-ttu-id="71f12-110">На устройства добавляются приложения, чтобы пользователи могли получать доступ к облачным службам Microsoft 365 организации, таким как Exchange Online и SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="71f12-110">Apps are added to devices so your users get access to your organization's Microsoft 365 cloud services, such as Exchange Online and SharePoint Online.</span></span>
- <span data-ttu-id="71f12-111">Настройка и применение функций и параметров для устройств выполняется с указанием создаваемых вами групп и пользователей Azure AD. Такая настройка может предусматривать включение антивирусной программы и ограничение работы определенных приложений.</span><span class="sxs-lookup"><span data-stu-id="71f12-111">Features and settings are configured and applied to your devices using the Azure AD users and groups you create, which might include enabling anti-virus and restricting specific apps.</span></span>
- <span data-ttu-id="71f12-p102">Настроены политики соответствия требованиям для проверки наличия брандмауэра или длины пароля на устройстве. Если устройство не соответствует требованиям, политика условного доступа блокирует доступ к данным организации.</span><span class="sxs-lookup"><span data-stu-id="71f12-p102">Compliance policies are in place to require a firewall or a password length on a device. If devices aren't compliant, conditional access blocks access to your organization's data.</span></span>



## <a name="results-and-next-steps"></a><span data-ttu-id="71f12-114">Результаты и дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="71f12-114">Results and next steps</span></span>

<span data-ttu-id="71f12-115">Ваши устройства зарегистрированы в Intune и настроены с соответствующими политиками.</span><span class="sxs-lookup"><span data-stu-id="71f12-115">Your devices are enrolled in Intune and configured with the appropriate policies.</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| <span data-ttu-id="71f12-116">Если вы подписаны на стадии комплексного развертывания Microsoft 365 Enterprise, следующий этап — [Защита информации](infoprotect-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="71f12-116">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [information protection](infoprotect-infrastructure.md).</span></span> |
