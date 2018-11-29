---
title: Мобильное устройство управления инфраструктуры выходные условия
description: Microsoft 365 Enterprise включает в себя управление мобильными устройствами, с помощью Microsoft Intune. Просмотрите требования и предварительные условия, Настройка Intune, с помощью ресурса Azure Active Directory, регистрация операций ввода-вывода, macOS, Android и Windows устройств, развертывание приложений, создание Настройка профиля, с помощью политики соответствия требованиям и включения условного доступа для мобильных устройств Управление устройствами с Microsoft 365 для предприятия.
keywords: Документация Microsoft 365 365 Майкрософт, Microsoft 365 Enterprise, управление мобильными устройствами Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/10/2018
ms.topic: article
audience: ITPro
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
ms.custom: microsoft-intune
ms.openlocfilehash: b511052698f42a07df5fc25aeaad7fc7f00c2a6e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870610"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a><span data-ttu-id="42ddf-105">Мобильное устройство управления инфраструктуры выходные условия</span><span class="sxs-lookup"><span data-stu-id="42ddf-105">Mobile device management infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

<span data-ttu-id="42ddf-106">*Это относится к E3 и E5 версий Microsoft 365 для предприятия*</span><span class="sxs-lookup"><span data-stu-id="42ddf-106">*This applies to the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="42ddf-107">Перед переходом к следующему этапу процесса развертывания, убедитесь, что конфигурации соответствует следующим требованиям для инфраструктуры управления мобильного устройства.</span><span class="sxs-lookup"><span data-stu-id="42ddf-107">Before you move on to the next phase in the deployment process, ensure that your configuration meets the following requirements for mobile device management infrastructure.</span></span>

- <span data-ttu-id="42ddf-108">Настройка Intune, в том числе для создания групп и пользователей Azure AD, выполняется для применения правил организации к устройствам.</span><span class="sxs-lookup"><span data-stu-id="42ddf-108">Intune is set up, including the creation of Azure AD users and groups to apply your organization's rules for devices.</span></span>
- <span data-ttu-id="42ddf-109">Ваши устройства зарегистрированы в Intune, чтобы они могли получать политики, которые вы создаете.</span><span class="sxs-lookup"><span data-stu-id="42ddf-109">You have enrolled devices in Intune so that the devices can receive the policies you create.</span></span>
- <span data-ttu-id="42ddf-110">На устройства добавляются приложения, чтобы пользователи могли получать доступ к облачным службам Microsoft 365 организации, таким как Exchange Online и SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="42ddf-110">Apps are added to devices so your users get access to your organization's Microsoft 365 cloud services, such as Exchange Online and SharePoint Online.</span></span>
- <span data-ttu-id="42ddf-111">Настройка и применение функций и параметров для устройств выполняется с указанием создаваемых вами групп и пользователей Azure AD. Такая настройка может предусматривать включение антивирусной программы и ограничение работы определенных приложений.</span><span class="sxs-lookup"><span data-stu-id="42ddf-111">Features and settings are configured and applied to your devices using the Azure AD users and groups you create, which might include enabling anti-virus and restricting specific apps.</span></span>
- <span data-ttu-id="42ddf-p102">Настроены политики соответствия требованиям для проверки наличия брандмауэра или длины пароля на устройстве. Если устройство не соответствует требованиям, политика условного доступа блокирует доступ к данным организации.</span><span class="sxs-lookup"><span data-stu-id="42ddf-p102">Compliance policies are in place to require a firewall or a password length on a device. If devices aren't compliant, conditional access blocks access to your organization's data.</span></span>

## <a name="next-phase"></a><span data-ttu-id="42ddf-114">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="42ddf-114">Next phase</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| <span data-ttu-id="42ddf-115">На следующий этап процесса-сквозного развертывания для Microsoft 365 корпоративный — [Защита информации](infoprotect-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="42ddf-115">Your next phase in the end-to-end deployment process for Microsoft 365 Enterprise is [information protection](infoprotect-infrastructure.md).</span></span> |
