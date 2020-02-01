---
title: Критерии выхода инфраструктуры управления мобильными устройствами
description: Microsoft 365 Enterprise включает управление мобильными устройствами с помощью Microsoft Intune. Ознакомьтесь с требованиями и необходимыми условиями, настройте Intune, используя ресурс Azure Active Directory, регистрацию устройств iOS, macOS, Android и Windows, развертывание приложений, создание профиля, использование политики соответствия и включение условного доступа для мобильных устройств Управление устройствами с помощью Microsoft 365 корпоративный.
keywords: Microsoft 365, Microsoft 365 корпоративный, документация по Microsoft 365, управление мобильными устройствами, Intune
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/03/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: daf7bcf6525f30b7b52065e4f6bf2ff335f4ea4b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600886"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a><span data-ttu-id="c5fb5-105">Критерии выхода инфраструктуры управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="c5fb5-105">Mobile device management infrastructure exit criteria</span></span>

![Этап 5. Управление мобильными устройствами](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

<span data-ttu-id="c5fb5-107">*Это относится к версиям Microsoft 365 корпоративный для E3 и "# $"*</span><span class="sxs-lookup"><span data-stu-id="c5fb5-107">*This applies to the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="c5fb5-108">Убедитесь, что ваша конфигурация соответствует следующим требованиям для инфраструктуры управления мобильными устройствами.</span><span class="sxs-lookup"><span data-stu-id="c5fb5-108">Ensure that your configuration meets the following requirements for mobile device management infrastructure.</span></span>

- <span data-ttu-id="c5fb5-109">Настроена Intune, в том числе создание пользователей и групп Azure Active Directory (Azure AD) для применения правил вашей организации к устройствам.</span><span class="sxs-lookup"><span data-stu-id="c5fb5-109">Intune is set up, including the creation of Azure Active Directory (Azure AD) users and groups to apply your organization's rules for devices.</span></span>
- <span data-ttu-id="c5fb5-110">Ваши устройства зарегистрированы в Intune, чтобы они могли получать политики, которые вы создаете.</span><span class="sxs-lookup"><span data-stu-id="c5fb5-110">You have enrolled devices in Intune so that the devices can receive the policies you create.</span></span>
- <span data-ttu-id="c5fb5-111">На устройства добавляются приложения, чтобы пользователи могли получать доступ к облачным службам Microsoft 365 организации, таким как Exchange Online и SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="c5fb5-111">Apps are added to devices so your users get access to your organization's Microsoft 365 cloud services, such as Exchange Online and SharePoint Online.</span></span>
- <span data-ttu-id="c5fb5-112">Настройка и применение функций и параметров для устройств выполняется с указанием создаваемых вами групп и пользователей Azure AD. Такая настройка может предусматривать включение антивирусной программы и ограничение работы определенных приложений.</span><span class="sxs-lookup"><span data-stu-id="c5fb5-112">Features and settings are configured and applied to your devices using the Azure AD users and groups you create, which might include enabling anti-virus and restricting specific apps.</span></span>
- <span data-ttu-id="c5fb5-113">Политики соответствия требованиям зависят от того, требуется ли брандмауэр или длина пароля на устройстве.</span><span class="sxs-lookup"><span data-stu-id="c5fb5-113">Compliance policies are in place to require a firewall or a password length on a device.</span></span> <span data-ttu-id="c5fb5-114">Если устройство не соответствует требованиям, условный доступ блокирует доступ к данным вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c5fb5-114">If devices aren't compliant, Conditional Access blocks access to your organization's data.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="c5fb5-115">Результаты и дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="c5fb5-115">Results and next steps</span></span>

<span data-ttu-id="c5fb5-116">Ваши устройства зарегистрированы в Intune и настроены с соответствующими политиками.</span><span class="sxs-lookup"><span data-stu-id="c5fb5-116">Your devices are enrolled in Intune and configured with the appropriate policies.</span></span>

|||
|:-------|:-----|
|![Этап 6. Защита данных](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| <span data-ttu-id="c5fb5-118">Если вы подписаны на стадии комплексного развертывания Microsoft 365 Enterprise, следующий этап — [Защита информации](infoprotect-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="c5fb5-118">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [information protection](infoprotect-infrastructure.md).</span></span> |
