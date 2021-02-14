---
title: Установка Microsoft Project или Microsoft Visio на управляемых Майкрософт настольных устройствах
description: Сведения об установке Microsoft Project или Microsoft Visio на устройствах, управляемых Майкрософт
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c04bcdf846bafaa7838ef5932c8de595f5035992
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950536"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="ef3f2-104">Установка Microsoft Project или Microsoft Visio на управляемых Майкрософт настольных устройствах</span><span class="sxs-lookup"><span data-stu-id="ef3f2-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="ef3f2-105">Microsoft Project и Microsoft Visio требуют установки определенных действий на настольных устройствах, управляемых Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ef3f2-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="ef3f2-106">В этом разделе документироваться необходимые условия и процесс установки для этих приложений.</span><span class="sxs-lookup"><span data-stu-id="ef3f2-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ef3f2-107">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="ef3f2-107">Prerequisites</span></span>

<span data-ttu-id="ef3f2-108">Администраторы должны убедиться, что они соответствуют указанным условиям.</span><span class="sxs-lookup"><span data-stu-id="ef3f2-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="ef3f2-109">**Количество лицензий** — для пользователей должно быть доступно правильное количество лицензий Microsoft Project и Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="ef3f2-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="ef3f2-110">В настоящее время на компьютере, управляемом Майкрософт, поддерживаются только 64-битные версии этих приложений.</span><span class="sxs-lookup"><span data-stu-id="ef3f2-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="ef3f2-111">**Имена лицензий—** соответствующие имена лицензий для этих приложений:</span><span class="sxs-lookup"><span data-stu-id="ef3f2-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="ef3f2-112">**Microsoft Project** — Project Online профессиональный или Project Online премиум</span><span class="sxs-lookup"><span data-stu-id="ef3f2-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="ef3f2-113">**Microsoft Visio** — Visio Online (план 2)</span><span class="sxs-lookup"><span data-stu-id="ef3f2-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="ef3f2-114">**Портал компании** — портал компании должен быть доступен в клиенте, чтобы пользователи установили эти приложения.</span><span class="sxs-lookup"><span data-stu-id="ef3f2-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="ef3f2-115">Если портал компании не развернут в клиенте, см. ["Портал компании".](company-portal.md)</span><span class="sxs-lookup"><span data-stu-id="ef3f2-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="ef3f2-116">Развертывание Project и Visio для настольных устройств, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ef3f2-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="ef3f2-117">Microsoft Managed Desktop добавит Microsoft Project и Microsoft Visio в качестве двух приложений Win32 в Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="ef3f2-117">Microsoft Managed Desktop will add Microsoft Project and Microsoft Visio as two Win32 Applications in Microsoft Intune.</span></span> <span data-ttu-id="ef3f2-118">Мы также создадим две группы в Azure Active Directory, которые будут назначены соответствующему приложению с намерением "Доступно".</span><span class="sxs-lookup"><span data-stu-id="ef3f2-118">We will also create two groups in Azure Active Directory which will be assigned to the corresponding application with the "Available" intent.</span></span> 

<span data-ttu-id="ef3f2-119">**Развертывание Project и Visio** Добавьте пользователя в соответствующую группу, и приложение станет доступным на портале компании.</span><span class="sxs-lookup"><span data-stu-id="ef3f2-119">**To deploy Project and Visio** Add the user to the appropriate group and the application will become available in the Company Portal.</span></span> <span data-ttu-id="ef3f2-120">Синхронизация может занять несколько минут, но пользователи смогут устанавливать приложения с портала компании.</span><span class="sxs-lookup"><span data-stu-id="ef3f2-120">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

<span data-ttu-id="ef3f2-121">Имя группы Azure AD</span><span class="sxs-lookup"><span data-stu-id="ef3f2-121">Azure AD Group name</span></span> | <span data-ttu-id="ef3f2-122">Каких пользователей назначить?</span><span class="sxs-lookup"><span data-stu-id="ef3f2-122">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="ef3f2-123">Современный workplace-Office-Project_Install</span><span class="sxs-lookup"><span data-stu-id="ef3f2-123">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="ef3f2-124">Пользователям нужен Project</span><span class="sxs-lookup"><span data-stu-id="ef3f2-124">Users needing Project</span></span>
<span data-ttu-id="ef3f2-125">Современный workplace-Office-Visio_Install</span><span class="sxs-lookup"><span data-stu-id="ef3f2-125">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="ef3f2-126">Пользователям требуется Visio</span><span class="sxs-lookup"><span data-stu-id="ef3f2-126">Users needing Visio</span></span>

## <a name="communicate-changes"></a><span data-ttu-id="ef3f2-127">Сообщить об изменениях</span><span class="sxs-lookup"><span data-stu-id="ef3f2-127">Communicate changes</span></span>
<span data-ttu-id="ef3f2-128">ИТ-администраторам важно дать своим пользователям знать, как установить Project и Visio.</span><span class="sxs-lookup"><span data-stu-id="ef3f2-128">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="ef3f2-129">К ним относятся:</span><span class="sxs-lookup"><span data-stu-id="ef3f2-129">This includes:</span></span> 
- <span data-ttu-id="ef3f2-130">Уведомление пользователей о том, что эти приложения им доступны.</span><span class="sxs-lookup"><span data-stu-id="ef3f2-130">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="ef3f2-131">Инструкции по установке этих приложений с портала компании.</span><span class="sxs-lookup"><span data-stu-id="ef3f2-131">Instructions on how to install these applications from the Company Portal.</span></span>
