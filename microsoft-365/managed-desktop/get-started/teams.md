---
title: Microsoft Teams
description: Как Teams устанавливается на устройства и обновляется после этого
keywords: Microsoft Managed Desktop, Microsoft 365, служба, документация, приложения, бизнес-приложения, бизнес-приложения
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: ea2ef7637a8d360e3b598aec4852425d977ae4ec
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950943"
---
# <a name="microsoft-teams"></a><span data-ttu-id="9becd-104">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9becd-104">Microsoft Teams</span></span>

<span data-ttu-id="9becd-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) — это [приложение для](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) обмена сообщениями для вашей организации, которое также предоставляет рабочее пространство для совместной работы и общения в режиме реального времени, собраний, общего доступа к файлам и приложениям.</span><span class="sxs-lookup"><span data-stu-id="9becd-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) is a [messaging app](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) for your organization that also provides a workspace for real-time collaboration and communication, meetings, and file and app sharing.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="9becd-106">Начальное развертывание</span><span class="sxs-lookup"><span data-stu-id="9becd-106">Initial deployment</span></span>

<span data-ttu-id="9becd-107">Большинство поставщиков оборудования пока не включают Teams в свои образы, поэтому компьютеры, управляемые Майкрософт, развертывают Teams на ваших устройствах с помощью Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="9becd-107">Most hardware vendors don't yet include Teams as a part of their images, so Microsoft Managed Desktop deploys Teams to your devices by using Microsoft Intune.</span></span> <span data-ttu-id="9becd-108">На всех управляемых устройствах установлен пакет [Microsoft MSI Teams,](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) благодаря которому все пользователи, во время которых вход на устройство, готовы к использованию Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9becd-108">All managed devices have the [Teams .msi package](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) installed, ensuring that all users who sign in to a device have Microsoft Teams ready to use.</span></span> <span data-ttu-id="9becd-109">После завершения установки пакета Teams автоматически запускается и добавляет ярлык на рабочий стол.</span><span class="sxs-lookup"><span data-stu-id="9becd-109">When the package first finishes installing, Teams automatically starts and adds a shortcut to the desktop.</span></span>

### <a name="microsoft-intune-changes"></a><span data-ttu-id="9becd-110">Изменения Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="9becd-110">Microsoft Intune changes</span></span>

<span data-ttu-id="9becd-111">Компьютеры, управляемые Майкрософт, добавляют два приложения в организацию Azure AD для Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9becd-111">Microsoft Managed Desktop adds two applications to your Azure AD organization for Microsoft Teams.</span></span> <span data-ttu-id="9becd-112">Они развертываются в 64- или 32-битных клиентах, если это необходимо для устройства:</span><span class="sxs-lookup"><span data-stu-id="9becd-112">They are deployed to either 64-bit or 32-bit clients as appropriate for the device:</span></span>  

- <span data-ttu-id="9becd-113">Современное рабочее место — teams Machine Wide Installer x64</span><span class="sxs-lookup"><span data-stu-id="9becd-113">Modern Workplace – Teams Machine Wide Installer x64</span></span>  
- <span data-ttu-id="9becd-114">Современное рабочее место — teams Machine Wide Installer x32</span><span class="sxs-lookup"><span data-stu-id="9becd-114">Modern Workplace – Teams Machine Wide Installer x32</span></span>

## <a name="updates"></a><span data-ttu-id="9becd-115">Обновления</span><span class="sxs-lookup"><span data-stu-id="9becd-115">Updates</span></span>

<span data-ttu-id="9becd-116">Teams следует отдельному пути обновления от приложений Microsoft 365 для предприятий, а клиент для настольных ПК обновляется автоматически.</span><span class="sxs-lookup"><span data-stu-id="9becd-116">Teams follows a separate update path from Microsoft 365 Apps for enterprise and the desktop client updates itself automatically.</span></span> <span data-ttu-id="9becd-117">Teams проверяет наличие обновлений каждые несколько часов, скачивает их, а затем ждет, пока компьютер не будет в бездействии, прежде чем автоматически установить обновление.</span><span class="sxs-lookup"><span data-stu-id="9becd-117">Teams checks for updates every few hours, downloads them, and then waits for the computer to be idle before silently installing the update.</span></span>  

<span data-ttu-id="9becd-118">Группа продуктов Teams не позволяет администраторам управлять обновлениями, поэтому на компьютере, управляемом Майкрософт, используется стандартный канал [автоматического обновления.](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)</span><span class="sxs-lookup"><span data-stu-id="9becd-118">The Teams product group doesn't allow admins to control updates, so Microsoft Managed Desktop uses the [standard automatic update channel](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).</span></span>

### <a name="manually-updating-teams"></a><span data-ttu-id="9becd-119">Обновление Teams вручную</span><span class="sxs-lookup"><span data-stu-id="9becd-119">Manually updating Teams</span></span>

<span data-ttu-id="9becd-120">Отдельные пользователи также могут скачивать обновления, выбрав пункт "Проверить обновления" в выпадаемом меню "Профиль" в верхней    правой части \*\*\*\*   приложения.</span><span class="sxs-lookup"><span data-stu-id="9becd-120">Individual users can also download updates by selecting **Check for updates** on the **Profile** drop-down menu at the top right of the app.</span></span> <span data-ttu-id="9becd-121">Если обновление доступно, оно будет загружено и установлено автоматически, когда компьютер находится в простое.</span><span class="sxs-lookup"><span data-stu-id="9becd-121">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

## <a name="delivery-optimization-of-updates"></a><span data-ttu-id="9becd-122">Оптимизация доставки обновлений</span><span class="sxs-lookup"><span data-stu-id="9becd-122">Delivery optimization of updates</span></span>

<span data-ttu-id="9becd-123">Оптимизация доставки для обновлений Teams включена по умолчанию и не требует действий от администраторов или пользователей.</span><span class="sxs-lookup"><span data-stu-id="9becd-123">Delivery optimization for Teams updates is turned on by default and requires no action from admins or users.</span></span> 