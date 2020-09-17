---
title: Установка Microsoft Project или Microsoft Visio на настольных устройствах, управляемых Майкрософт
description: Сведения об установке Microsoft Project или Microsoft Visio на настольных устройствах, управляемых Майкрософт
keywords: Управляемый Майкрософт Настольный компьютер, Microsoft 365, Microsoft Project, Microsoft Visio
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
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="50e39-104">Установка Microsoft Project или Microsoft Visio на настольных устройствах, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="50e39-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="50e39-105">Microsoft Project и Microsoft Visio требуют определенных действий для установки на настольных устройствах, управляемых Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="50e39-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="50e39-106">В этом разделе документируется предварительные требования и процесс установки для этих приложений.</span><span class="sxs-lookup"><span data-stu-id="50e39-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="50e39-107">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="50e39-107">Prerequisites</span></span>

<span data-ttu-id="50e39-108">Администраторы должны убедиться, что они отвечают следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="50e39-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="50e39-109">**Количество лицензий** — правильная сумма лицензий Microsoft Project и Microsoft Visio должна быть доступна для пользователей.</span><span class="sxs-lookup"><span data-stu-id="50e39-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="50e39-110">На компьютере, управляемом Майкрософт, в настоящее время поддерживается только 64 – разрядная версия этих приложений.</span><span class="sxs-lookup"><span data-stu-id="50e39-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="50e39-111">**Названия лицензий** — для этих приложений должны быть указаны следующие названия лицензий:</span><span class="sxs-lookup"><span data-stu-id="50e39-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="50e39-112">**Microsoft Project** — Project Online профессиональный или Project Online премиум</span><span class="sxs-lookup"><span data-stu-id="50e39-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="50e39-113">**Microsoft Visio** — Visio Online (план 2)</span><span class="sxs-lookup"><span data-stu-id="50e39-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="50e39-114">**Корпоративный портал** — корпоративный портал должен быть доступен в вашем клиенте, чтобы пользователи могли устанавливать эти приложения.</span><span class="sxs-lookup"><span data-stu-id="50e39-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="50e39-115">Если корпоративный портал не развернут в вашем клиенте, ознакомьтесь со статьей [Корпоративный портал](company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="50e39-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="50e39-116">Развертывание Project и Visio для настольных устройств, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="50e39-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="50e39-117">На рабочем столе Майкрософт вы добавите Microsoft Project и Microsoft Visio как два приложения Win32 в Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="50e39-117">Microsoft Managed Desktop will add Microsoft Project and Microsoft Visio as two Win32 Applications in Microsoft Intune.</span></span> <span data-ttu-id="50e39-118">Кроме того, мы создадим две группы в Azure Active Directory, которые будут назначены соответствующему приложению с намерением "доступно".</span><span class="sxs-lookup"><span data-stu-id="50e39-118">We will also create two groups in Azure Active Directory which will be assigned to the corresponding application with the "Available" intent.</span></span> 

<span data-ttu-id="50e39-119">**Развертывание проекта и Visio** Добавьте пользователя в соответствующую группу, и приложение станет доступным на портале компании.</span><span class="sxs-lookup"><span data-stu-id="50e39-119">**To deploy Project and Visio** Add the user to the appropriate group and the application will become available in the Company Portal.</span></span> <span data-ttu-id="50e39-120">Синхронизация может занять несколько минут, но пользователи могут установить приложения с корпоративного портала.</span><span class="sxs-lookup"><span data-stu-id="50e39-120">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

<span data-ttu-id="50e39-121">Имя группы Azure AD</span><span class="sxs-lookup"><span data-stu-id="50e39-121">Azure AD Group name</span></span> | <span data-ttu-id="50e39-122">Назначение пользователей</span><span class="sxs-lookup"><span data-stu-id="50e39-122">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="50e39-123">Современный рабочее место — Office — Project_Install</span><span class="sxs-lookup"><span data-stu-id="50e39-123">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="50e39-124">Пользователи, которым необходим проект</span><span class="sxs-lookup"><span data-stu-id="50e39-124">Users needing Project</span></span>
<span data-ttu-id="50e39-125">Современный рабочее место — Office — Visio_Install</span><span class="sxs-lookup"><span data-stu-id="50e39-125">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="50e39-126">Пользователи, которым требуется Visio</span><span class="sxs-lookup"><span data-stu-id="50e39-126">Users needing Visio</span></span>

## <a name="communicate-changes"></a><span data-ttu-id="50e39-127">Сообщить об изменениях</span><span class="sxs-lookup"><span data-stu-id="50e39-127">Communicate changes</span></span>
<span data-ttu-id="50e39-128">ИТ администраторам важно, чтобы пользователи могли узнать, как установить Project и Visio.</span><span class="sxs-lookup"><span data-stu-id="50e39-128">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="50e39-129">К ним относятся:</span><span class="sxs-lookup"><span data-stu-id="50e39-129">This includes:</span></span> 
- <span data-ttu-id="50e39-130">Уведомление пользователей о доступности этих приложений.</span><span class="sxs-lookup"><span data-stu-id="50e39-130">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="50e39-131">Инструкции по установке этих приложений с корпоративного портала.</span><span class="sxs-lookup"><span data-stu-id="50e39-131">Instructions on how to install these applications from the Company Portal.</span></span>
