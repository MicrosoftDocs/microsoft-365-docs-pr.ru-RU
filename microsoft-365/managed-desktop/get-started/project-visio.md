---
title: Установка Microsoft Project или Microsoft Visio на наСтольных устройствах, управляемых Майкрософт
description: Сведения об установке Microsoft Project или Microsoft Visio на наСтольных устройствах, управляемых Майкрософт
keywords: Управляемый Майкрософт Настольный компьютер, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5c820e36b7b397fe770216ee229e38a1da5b034d
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289000"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="ebd18-104">Установка Microsoft Project или Microsoft Visio на наСтольных устройствах, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ebd18-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="ebd18-105">Microsoft Project и Microsoft Visio требуют определенных действий для установки на наСтольных устройствах, управляемых Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ebd18-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="ebd18-106">В этом разделе документируется предварительные требования и процесс установки для этих приложений.</span><span class="sxs-lookup"><span data-stu-id="ebd18-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ebd18-107">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="ebd18-107">Prerequisites</span></span>

<span data-ttu-id="ebd18-108">Администраторы должны убедиться, что они отвечают следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="ebd18-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="ebd18-109">**Количество лицензий** — правильная сумма лицензий Microsoft Project и Microsoft Visio должна быть доступна для пользователей.</span><span class="sxs-lookup"><span data-stu-id="ebd18-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="ebd18-110">На компьютере, управляемом Майкрософт, в настоящее время поддерживается только 64 – разрядная версия этих приложений.</span><span class="sxs-lookup"><span data-stu-id="ebd18-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="ebd18-111">**Названия лицензий** — для этих приложений должны быть указаны следующие названия лицензий:</span><span class="sxs-lookup"><span data-stu-id="ebd18-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="ebd18-112">**Microsoft Project** — Project Online профессиональный или Project Online премиум</span><span class="sxs-lookup"><span data-stu-id="ebd18-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="ebd18-113">**Microsoft Visio** — Visio Online (план 2)</span><span class="sxs-lookup"><span data-stu-id="ebd18-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="ebd18-114">**Корпоративный портал** — корпоративный портал должен быть доступен в вашем клиенте, чтобы пользователи могли устанавливать эти приложения.</span><span class="sxs-lookup"><span data-stu-id="ebd18-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="ebd18-115">Если корпоративный портал не развернут в вашем клиенте, ознакомьтесь со статьей [Корпоративный портал](company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="ebd18-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="ebd18-116">Развертывание Project и Visio для наСтольных устройств, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ebd18-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="ebd18-117">После того как вы отправите запрос в службу поддержки, на рабочем столе Майкрософт будут созданы три группы Azure AD и три развертывания приложений с помощью Microsoft Intune, чтобы развернуть приложения в клиенте.</span><span class="sxs-lookup"><span data-stu-id="ebd18-117">After you submit your support request, Microsoft Managed Desktop will create three Azure AD groups and three application deployments through Microsoft Intune to deploy the apps to your tenant.</span></span>  

<span data-ttu-id="ebd18-118">**Развертывание проекта и Visio**</span><span class="sxs-lookup"><span data-stu-id="ebd18-118">**To deploy Project and Visio**</span></span>
1. <span data-ttu-id="ebd18-119">**Файловый запрос поддержки** ИТ – администраторам необходимо создать запрос в службу поддержки, чтобы сделать эти приложения доступными для пользователей.</span><span class="sxs-lookup"><span data-stu-id="ebd18-119">**File a support request** IT administrators need to file a support request to make these applications available their users.</span></span> <span data-ttu-id="ebd18-120">Для получения дополнительных сведений о том, как связаться с управляемым рабочим столом Майкрософт, ознакомьтесь со статьей [Поддержка администраторов для компьютеров, управляемых Майкрософт](../working-with-managed-desktop/admin-support.md)</span><span class="sxs-lookup"><span data-stu-id="ebd18-120">For information on contacting Microsoft Managed Desktop, see [Admin support for Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).</span></span>
2. <span data-ttu-id="ebd18-121">**Назначение пользователей новым группам Azure AD** На рабочем столе Майкрософт будут созданы 3 группы Azure AD в клиенте и 3 соответствующие развертывания приложений.</span><span class="sxs-lookup"><span data-stu-id="ebd18-121">**Assign users to new Azure AD groups** Microsoft Managed Desktop will create 3 Azure AD groups in your tenant and 3 corresponding application deployments.</span></span> <span data-ttu-id="ebd18-122">ИТ – администраторы должны назначить пользователей соответствующим группам.</span><span class="sxs-lookup"><span data-stu-id="ebd18-122">IT admins need to assign the users to the appropriate groups.</span></span>

>[!NOTE]
><span data-ttu-id="ebd18-123">Назначьте пользователей только одной из этих групп Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ebd18-123">Assign users to only one of these Azure AD groups.</span></span> 

<span data-ttu-id="ebd18-124">Имя группы Azure AD</span><span class="sxs-lookup"><span data-stu-id="ebd18-124">Azure AD Group name</span></span> | <span data-ttu-id="ebd18-125">Назначение пользователей</span><span class="sxs-lookup"><span data-stu-id="ebd18-125">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="ebd18-126">Microsoft — Office — проект — установка</span><span class="sxs-lookup"><span data-stu-id="ebd18-126">Microsoft-Office-Project-Install</span></span> | <span data-ttu-id="ebd18-127">Пользователям требуется только проект</span><span class="sxs-lookup"><span data-stu-id="ebd18-127">Users needing only Project</span></span>
<span data-ttu-id="ebd18-128">Microsoft — Office — Visio — установка</span><span class="sxs-lookup"><span data-stu-id="ebd18-128">Microsoft-Office-Visio-Install</span></span> | <span data-ttu-id="ebd18-129">Пользователи, которым требуется только Visio</span><span class="sxs-lookup"><span data-stu-id="ebd18-129">Users needing only Visio</span></span>
<span data-ttu-id="ebd18-130">Microsoft — Office — проект и Visio — установка</span><span class="sxs-lookup"><span data-stu-id="ebd18-130">Microsoft-Office-Project and Visio-Install</span></span> | <span data-ttu-id="ebd18-131">Пользователям требуется как проект, так и Visio</span><span class="sxs-lookup"><span data-stu-id="ebd18-131">Users needing both Project and Visio</span></span>

<span data-ttu-id="ebd18-132">После назначения этим группам приложения будут доступны на портале компании.</span><span class="sxs-lookup"><span data-stu-id="ebd18-132">Once assigned to these groups, applications will be available in the Company Portal.</span></span> <span data-ttu-id="ebd18-133">Синхронизация может занять несколько минут, но пользователи могут установить приложения с корпоративного портала.</span><span class="sxs-lookup"><span data-stu-id="ebd18-133">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

## <a name="communicate-changes"></a><span data-ttu-id="ebd18-134">Сообщить об изменениях</span><span class="sxs-lookup"><span data-stu-id="ebd18-134">Communicate changes</span></span>
<span data-ttu-id="ebd18-135">ИТ администраторам важно, чтобы пользователи могли узнать, как установить Project и Visio.</span><span class="sxs-lookup"><span data-stu-id="ebd18-135">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="ebd18-136">Это включает:</span><span class="sxs-lookup"><span data-stu-id="ebd18-136">This includes:</span></span> 
- <span data-ttu-id="ebd18-137">Уведомление пользователей о доступности этих приложений.</span><span class="sxs-lookup"><span data-stu-id="ebd18-137">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="ebd18-138">Инструкции по установке этих приложений с корпоративного портала.</span><span class="sxs-lookup"><span data-stu-id="ebd18-138">Instructions on how to install these applications from the Company Portal.</span></span>

>[!NOTE]
><span data-ttu-id="ebd18-139">Пользователи должны закрыть все приложения Office перед установкой Microsoft Project или Microsoft Visio с корпоративного портала.</span><span class="sxs-lookup"><span data-stu-id="ebd18-139">Users must close all Office applications before installing Microsoft Project or Microsoft Visio from Company Portal.</span></span> 
