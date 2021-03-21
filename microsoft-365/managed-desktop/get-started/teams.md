---
title: Microsoft Teams
description: Как Teams устанавливается на устройствах и обновляется после этого
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation, apps, line-of-business apps, LOB apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: 01a3adc7829bbb94f36649f69ba6ef15dbe6b3c2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920660"
---
# <a name="microsoft-teams"></a><span data-ttu-id="afdd1-104">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="afdd1-104">Microsoft Teams</span></span>

<span data-ttu-id="afdd1-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) — это [приложение для](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) обмена сообщениями для организации, которое также предоставляет рабочее пространство для совместной работы и общения в режиме реального времени, собраний, обмена файлами и приложениями.</span><span class="sxs-lookup"><span data-stu-id="afdd1-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) is a [messaging app](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) for your organization that also provides a workspace for real-time collaboration and communication, meetings, and file and app sharing.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="afdd1-106">Начальное развертывание</span><span class="sxs-lookup"><span data-stu-id="afdd1-106">Initial deployment</span></span>

<span data-ttu-id="afdd1-107">Большинство поставщиков оборудования еще не включают Teams в свои изображения, поэтому Microsoft Managed Desktop развертывает Teams на устройствах с помощью Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="afdd1-107">Most hardware vendors don't yet include Teams as a part of their images, so Microsoft Managed Desktop deploys Teams to your devices by using Microsoft Intune.</span></span> <span data-ttu-id="afdd1-108">На всех управляемых устройствах установлен [пакет Teams.msi,](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) обеспечивающий готовность всех пользователей, входивших на устройство, к использованию Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="afdd1-108">All managed devices have the [Teams .msi package](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) installed, ensuring that all users who sign in to a device have Microsoft Teams ready to use.</span></span> <span data-ttu-id="afdd1-109">После первого завершения установки пакета Teams автоматически запускает и добавляет ярлык на рабочий стол.</span><span class="sxs-lookup"><span data-stu-id="afdd1-109">When the package first finishes installing, Teams automatically starts and adds a shortcut to the desktop.</span></span>

### <a name="microsoft-intune-changes"></a><span data-ttu-id="afdd1-110">Изменения Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="afdd1-110">Microsoft Intune changes</span></span>

<span data-ttu-id="afdd1-111">Microsoft Managed Desktop добавляет два приложения в организацию Azure AD для Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="afdd1-111">Microsoft Managed Desktop adds two applications to your Azure AD organization for Microsoft Teams.</span></span> <span data-ttu-id="afdd1-112">Они развертываются для 64-битных или 32-битных клиентов, соответствующих устройству:</span><span class="sxs-lookup"><span data-stu-id="afdd1-112">They are deployed to either 64-bit or 32-bit clients as appropriate for the device:</span></span>  

- <span data-ttu-id="afdd1-113">Modern Workplace — Teams Machine Wide Installer x64</span><span class="sxs-lookup"><span data-stu-id="afdd1-113">Modern Workplace – Teams Machine Wide Installer x64</span></span>  
- <span data-ttu-id="afdd1-114">Modern Workplace — Teams Machine Wide Installer x32</span><span class="sxs-lookup"><span data-stu-id="afdd1-114">Modern Workplace – Teams Machine Wide Installer x32</span></span>

## <a name="updates"></a><span data-ttu-id="afdd1-115">Обновления</span><span class="sxs-lookup"><span data-stu-id="afdd1-115">Updates</span></span>

<span data-ttu-id="afdd1-116">Teams следует отдельному пути обновления от Microsoft 365 Apps для предприятия, и клиент настольных компьютеров обновляется автоматически.</span><span class="sxs-lookup"><span data-stu-id="afdd1-116">Teams follows a separate update path from Microsoft 365 Apps for enterprise and the desktop client updates itself automatically.</span></span> <span data-ttu-id="afdd1-117">Команды проверяют обновления каждые несколько часов, загружают их, а затем ждут, пока компьютер не будет простаивать, прежде чем безмолвно установить обновление.</span><span class="sxs-lookup"><span data-stu-id="afdd1-117">Teams checks for updates every few hours, downloads them, and then waits for the computer to be idle before silently installing the update.</span></span>  

<span data-ttu-id="afdd1-118">Группа продуктов Teams не позволяет администраторам управлять обновлениями, поэтому Microsoft Managed Desktop использует стандартный канал [автоматического обновления.](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)</span><span class="sxs-lookup"><span data-stu-id="afdd1-118">The Teams product group doesn't allow admins to control updates, so Microsoft Managed Desktop uses the [standard automatic update channel](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).</span></span>

### <a name="manually-updating-teams"></a><span data-ttu-id="afdd1-119">Ручное обновление Teams</span><span class="sxs-lookup"><span data-stu-id="afdd1-119">Manually updating Teams</span></span>

<span data-ttu-id="afdd1-120">Отдельные пользователи также могут скачивать обновления, выбрав **пункт Проверка** обновлений в выпадаемом меню Profile в правом верхнем    \*\*\*\*   справа от приложения.</span><span class="sxs-lookup"><span data-stu-id="afdd1-120">Individual users can also download updates by selecting **Check for updates** on the **Profile** drop-down menu at the top right of the app.</span></span> <span data-ttu-id="afdd1-121">Если обновление доступно, оно будет скачивано и тихо установлено, когда компьютер простаивает.</span><span class="sxs-lookup"><span data-stu-id="afdd1-121">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

## <a name="delivery-optimization-of-updates"></a><span data-ttu-id="afdd1-122">Оптимизация доставки обновлений</span><span class="sxs-lookup"><span data-stu-id="afdd1-122">Delivery optimization of updates</span></span>

<span data-ttu-id="afdd1-123">Оптимизация доставки обновлений Teams включена по умолчанию и не требует действий от администраторов или пользователей.</span><span class="sxs-lookup"><span data-stu-id="afdd1-123">Delivery optimization for Teams updates is turned on by default and requires no action from admins or users.</span></span>