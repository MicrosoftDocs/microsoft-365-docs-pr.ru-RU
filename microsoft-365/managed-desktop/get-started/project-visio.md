---
title: Установка Microsoft Project или microsoft Visio на компьютеры, управляемые Майкрософт устройствах
description: Сведения об установке Microsoft Project или microsoft Visio на компьютеры, управляемые Майкрософт устройствах
keywords: компьютеры, управляемые Майкрософт, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9fd46410877012d92e847ba7ff8b60cd5acceb1e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925543"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="fb05f-104">Установка Microsoft Project или microsoft Visio на компьютеры, управляемые Майкрософт устройствах</span><span class="sxs-lookup"><span data-stu-id="fb05f-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="fb05f-105">Microsoft Project и microsoft Visio требуются определенные действия, которые необходимо установить на компьютеры, управляемые Майкрософт устройствах.</span><span class="sxs-lookup"><span data-stu-id="fb05f-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="fb05f-106">В этом разделе документироваться необходимые условия и процесс установки для этих приложений.</span><span class="sxs-lookup"><span data-stu-id="fb05f-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fb05f-107">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="fb05f-107">Prerequisites</span></span>

<span data-ttu-id="fb05f-108">Администраторы должны убедиться, что они соответствуют этим требованиям:</span><span class="sxs-lookup"><span data-stu-id="fb05f-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="fb05f-109">**Количество лицензий** — необходимое количество Microsoft Project лицензий и Visio microsoft должны быть доступны для пользователей.</span><span class="sxs-lookup"><span data-stu-id="fb05f-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="fb05f-110">компьютеры, управляемые Майкрософт в настоящее время поддерживает только 64-битные версии этих приложений.</span><span class="sxs-lookup"><span data-stu-id="fb05f-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="fb05f-111">**Имена лицензий** . Соответствующие имена лицензий для этих приложений:</span><span class="sxs-lookup"><span data-stu-id="fb05f-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="fb05f-112">**Microsoft Project** - Project Online профессиональный или Project Online расширенный</span><span class="sxs-lookup"><span data-stu-id="fb05f-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="fb05f-113">**Microsoft Visio** - Visio Online Plan 2</span><span class="sxs-lookup"><span data-stu-id="fb05f-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="fb05f-114">**Корпоративный портал** . Корпоративный портал клиент должен быть доступен пользователям для установки этих приложений.</span><span class="sxs-lookup"><span data-stu-id="fb05f-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="fb05f-115">Если Корпоративный портал не развернут в клиенте, см. Корпоративный портал [.](company-portal.md)</span><span class="sxs-lookup"><span data-stu-id="fb05f-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="fb05f-116">Развертывание Project и Visio для компьютеры, управляемые Майкрософт устройств</span><span class="sxs-lookup"><span data-stu-id="fb05f-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="fb05f-117">компьютеры, управляемые Майкрософт добавит Microsoft Project Microsoft Visio в качестве двух приложений Win32 в Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="fb05f-117">Microsoft Managed Desktop will add Microsoft Project and Microsoft Visio as two Win32 Applications in Microsoft Intune.</span></span> <span data-ttu-id="fb05f-118">Мы также создадим две группы в Azure Active Directory, которые будут назначены соответствующему приложению с намерением "Доступно".</span><span class="sxs-lookup"><span data-stu-id="fb05f-118">We will also create two groups in Azure Active Directory which will be assigned to the corresponding application with the "Available" intent.</span></span> 

<span data-ttu-id="fb05f-119">**Развертывание Project и Visio** Добавьте пользователя в соответствующую группу, и приложение станет доступным в Корпоративный портал.</span><span class="sxs-lookup"><span data-stu-id="fb05f-119">**To deploy Project and Visio** Add the user to the appropriate group and the application will become available in the Company Portal.</span></span> <span data-ttu-id="fb05f-120">Синхронизация может занять несколько минут, но затем пользователи могут установить приложения из Корпоративный портал.</span><span class="sxs-lookup"><span data-stu-id="fb05f-120">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

<span data-ttu-id="fb05f-121">Имя группы Azure AD</span><span class="sxs-lookup"><span data-stu-id="fb05f-121">Azure AD Group name</span></span> | <span data-ttu-id="fb05f-122">Какие пользователи назначать?</span><span class="sxs-lookup"><span data-stu-id="fb05f-122">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="fb05f-123">Современные рабочие Office-Project_Install</span><span class="sxs-lookup"><span data-stu-id="fb05f-123">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="fb05f-124">Пользователям, Project</span><span class="sxs-lookup"><span data-stu-id="fb05f-124">Users needing Project</span></span>
<span data-ttu-id="fb05f-125">Современные рабочие Office-Visio_Install</span><span class="sxs-lookup"><span data-stu-id="fb05f-125">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="fb05f-126">Пользователи, нуждающиеся в Visio</span><span class="sxs-lookup"><span data-stu-id="fb05f-126">Users needing Visio</span></span>

## <a name="communicate-changes"></a><span data-ttu-id="fb05f-127">Связывать изменения</span><span class="sxs-lookup"><span data-stu-id="fb05f-127">Communicate changes</span></span>
<span data-ttu-id="fb05f-128">ИТ-администраторы должны знать, как установить Project и Visio.</span><span class="sxs-lookup"><span data-stu-id="fb05f-128">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="fb05f-129">К ним относятся:</span><span class="sxs-lookup"><span data-stu-id="fb05f-129">This includes:</span></span> 
- <span data-ttu-id="fb05f-130">Уведомление пользователей о том, когда эти приложения доступны для них.</span><span class="sxs-lookup"><span data-stu-id="fb05f-130">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="fb05f-131">Инструкции по установке этих приложений из Корпоративный портал.</span><span class="sxs-lookup"><span data-stu-id="fb05f-131">Instructions on how to install these applications from the Company Portal.</span></span>
