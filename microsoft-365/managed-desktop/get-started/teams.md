---
title: Microsoft Teams
description: Как Microsoft Teams устанавливается на устройствах и обновляется позже
keywords: Настольные компьютеры, управляемые корпорацией Майкрософт, Microsoft 365, служба, документация, приложения, бизнес-приложения, бизнес-приложения
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
# <a name="microsoft-teams"></a><span data-ttu-id="bb21c-104">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bb21c-104">Microsoft Teams</span></span>

<span data-ttu-id="bb21c-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) — это [приложение для обмена сообщениями](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) , которое также предоставляет рабочую область для совместной работы и общения в реальном времени, собраний, собраний, а также совместного использования файлов и приложений.</span><span class="sxs-lookup"><span data-stu-id="bb21c-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) is a [messaging app](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) for your organization that also provides a workspace for real-time collaboration and communication, meetings, and file and app sharing.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="bb21c-106">Начальное развертывание</span><span class="sxs-lookup"><span data-stu-id="bb21c-106">Initial deployment</span></span>

<span data-ttu-id="bb21c-107">Большинство производителей оборудования еще не включают в себя Teams в своих изображениях, поэтому управляемый Майкрософт Настольный компьютер развертывает Teams на своих устройствах с помощью Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="bb21c-107">Most hardware vendors don't yet include Teams as a part of their images, so Microsoft Managed Desktop deploys Teams to your devices by using Microsoft Intune.</span></span> <span data-ttu-id="bb21c-108">На всех управляемых устройствах установлен [пакет Teams. msi](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) , что гарантирует, что все пользователи, выполняющие вход на устройство, готовы к использованию Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bb21c-108">All managed devices have the [Teams .msi package](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) installed, ensuring that all users who sign in to a device have Microsoft Teams ready to use.</span></span> <span data-ttu-id="bb21c-109">При первом завершении установки пакета Teams автоматически запускается и добавляется ярлык на Рабочий стол.</span><span class="sxs-lookup"><span data-stu-id="bb21c-109">When the package first finishes installing, Teams automatically starts and adds a shortcut to the desktop.</span></span>

### <a name="microsoft-intune-changes"></a><span data-ttu-id="bb21c-110">Изменения в Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="bb21c-110">Microsoft Intune changes</span></span>

<span data-ttu-id="bb21c-111">Рабочий стол, управляемый Майкрософт, добавляет два приложения в организацию Azure AD для Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bb21c-111">Microsoft Managed Desktop adds two applications to your Azure AD organization for Microsoft Teams.</span></span> <span data-ttu-id="bb21c-112">Они разворачиваются как в 64, так и на клиентах 32, в соответствии с требованиями к устройству:</span><span class="sxs-lookup"><span data-stu-id="bb21c-112">They are deployed to either 64-bit or 32-bit clients as appropriate for the device:</span></span>  

- <span data-ttu-id="bb21c-113">Современная Рабочая область — установщик на уровне компьютера для Teams x64</span><span class="sxs-lookup"><span data-stu-id="bb21c-113">Modern Workplace – Teams Machine Wide Installer x64</span></span>  
- <span data-ttu-id="bb21c-114">Современная Рабочая область — x32 установки для всего компьютера Teams</span><span class="sxs-lookup"><span data-stu-id="bb21c-114">Modern Workplace – Teams Machine Wide Installer x32</span></span>

## <a name="updates"></a><span data-ttu-id="bb21c-115">Обновления</span><span class="sxs-lookup"><span data-stu-id="bb21c-115">Updates</span></span>

<span data-ttu-id="bb21c-116">В Teams следует отдельный путь обновления от приложений Microsoft 365 для предприятий, а клиент для настольных ПК автоматически обновляется.</span><span class="sxs-lookup"><span data-stu-id="bb21c-116">Teams follows a separate update path from Microsoft 365 Apps for enterprise and the desktop client updates itself automatically.</span></span> <span data-ttu-id="bb21c-117">Teams проверяет наличие обновлений каждые несколько часов, загружает их, а затем ждет, пока компьютер не простаивает, прежде чем устанавливать обновление автоматически.</span><span class="sxs-lookup"><span data-stu-id="bb21c-117">Teams checks for updates every few hours, downloads them, and then waits for the computer to be idle before silently installing the update.</span></span>  

<span data-ttu-id="bb21c-118">Группа продуктов Teams не позволяет администраторам управлять обновлениями, поэтому для управляемого рабочего стола Майкрософт используется [стандартный канал автоматического обновления](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).</span><span class="sxs-lookup"><span data-stu-id="bb21c-118">The Teams product group doesn't allow admins to control updates, so Microsoft Managed Desktop uses the [standard automatic update channel](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).</span></span>

### <a name="manually-updating-teams"></a><span data-ttu-id="bb21c-119">Ручное обновление Teams</span><span class="sxs-lookup"><span data-stu-id="bb21c-119">Manually updating Teams</span></span>

<span data-ttu-id="bb21c-120">Отдельные пользователи также могут скачивать обновления, выбрав пункт **проверить наличие обновлений**   в раскрывающемся меню **Профили**   в правом верхнем углу приложения.</span><span class="sxs-lookup"><span data-stu-id="bb21c-120">Individual users can also download updates by selecting **Check for updates** on the **Profile** drop-down menu at the top right of the app.</span></span> <span data-ttu-id="bb21c-121">Если обновление доступно, оно будет загружено и автоматически установлено, когда компьютер простаивает.</span><span class="sxs-lookup"><span data-stu-id="bb21c-121">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

## <a name="delivery-optimization-of-updates"></a><span data-ttu-id="bb21c-122">Оптимизация доставки обновлений</span><span class="sxs-lookup"><span data-stu-id="bb21c-122">Delivery optimization of updates</span></span>

<span data-ttu-id="bb21c-123">Оптимизация доставки для Teams включена по умолчанию и не требует никаких действий от администраторов и пользователей.</span><span class="sxs-lookup"><span data-stu-id="bb21c-123">Delivery optimization for Teams updates is turned on by default and requires no action from admins or users.</span></span> 