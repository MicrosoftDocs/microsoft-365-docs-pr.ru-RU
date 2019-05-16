---
title: Автоматическая установка и удаление Office на устройствах с Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: cbc6bfe5-565a-4fb8-95f0-b06e7b74ac46
description: 'Установка или удаление Office на устройствах с Windows 10 из центра администрирования Microsoft 365 бизнес. '
ms.openlocfilehash: 1e962f51882ddfd97da566858a0a1e6fb56ecbb8
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "34071967"
---
# <a name="automatically-install-or-uninstall-office-on-windows-10-devices"></a><span data-ttu-id="650d2-103">Автоматическая установка и удаление Office на устройствах с Windows 10</span><span class="sxs-lookup"><span data-stu-id="650d2-103">Automatically install or uninstall Office on Windows 10 devices</span></span>

![Баннер, который указывает https://aka.ms/aboutM365previewна.](media/m365admincenterchanging.png)

<span data-ttu-id="650d2-105">Из центра администрирования Office 365 бизнес вы можете легко и быстро установить Office на компьютерах с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="650d2-105">You can quickly and easily install Office to Windows 10 PCs from the Microsoft 365 Business admin center.</span></span>
  
<span data-ttu-id="650d2-106">Прежде чем начать, прочитайте статью [Подготовка к установке Office для клиентов](prepare-for-office-client-deployment.md), чтобы понять, как это работает с ранее установленными приложениями Office.</span><span class="sxs-lookup"><span data-stu-id="650d2-106">To understand how this works with previously installed Office apps, read [Prepare for Office client installation](prepare-for-office-client-deployment.md) before you get started.</span></span> 
  
## <a name="manage-office-deployments"></a><span data-ttu-id="650d2-107">Управление развертываниями Office</span><span class="sxs-lookup"><span data-stu-id="650d2-107">Manage Office deployments</span></span>

1. <span data-ttu-id="650d2-108">Войдите в [центр администрирования](https://aka.ms/bcsportal) с учетными данными глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="650d2-108">Sign in to the [admin center](https://aka.ms/bcsportal) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="650d2-109">На карточке **Устройства** выберите **Управление развертыванием Office**.</span><span class="sxs-lookup"><span data-stu-id="650d2-109">On the **Devices** card, choose **Manage Office Deployment**.</span></span>
      <span data-ttu-id="650d2-110">Если вы не видите карточки **действий устройства** , на **домашней** странице центра администрирования нажмите **добавить** (+), чтобы добавить ее на домашнюю страницу администрирования.</span><span class="sxs-lookup"><span data-stu-id="650d2-110">If you do not see the **Device actions** card, in the admin center **Home** page, click **Add** (+) to add it to your admin home.</span></span>
    
    ![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
3. <span data-ttu-id="650d2-112">На панели **Управление развертыванием Office** нажмите кнопку **Добавить группу** и выберите группы, которые хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="650d2-112">On the **Manage Office deployment** pane that opens, choose **Add a group**, then select the groups you want use.</span></span>
    
4. <span data-ttu-id="650d2-113">Выбрав группу или группы, в раскрывающемся списке **Действие развертывания** выберите одно из действий: **Установить Office как можно быстрее** или **Удалить Office**.</span><span class="sxs-lookup"><span data-stu-id="650d2-113">After you have added the group or groups you want to use, from the **Deployment Action** drop-down, select either **Install Office as soon as possible** or **Uninstall Office**.</span></span>
    
    ![In the Manage Office deployment pane, choose either Install Office as soon as possible, or Uninstall Office.](media/00f24a61-1848-40c0-b037-78d726c7d757.png)
  
5. <span data-ttu-id="650d2-115">Choose **Next** \> review the settings and then choose **Confirm**.</span><span class="sxs-lookup"><span data-stu-id="650d2-115">Choose **Next** \> review the settings and then choose **Confirm**.</span></span>
    
<span data-ttu-id="650d2-116">32-разрядная версия Office будет автоматически установлена на устройствах пользователей, входящих в указанные вами группы, или удалена с них.</span><span class="sxs-lookup"><span data-stu-id="650d2-116">A 32-bit Office will be automatically installed, or uninstalled in the devices owned by users specified by the group or groups you used.</span></span>
  
<span data-ttu-id="650d2-117">Для проверки откройте диспетчер задач на компьютере, выбранном для установки Office, и найдите процесс "Microsoft Office нажми и работай".</span><span class="sxs-lookup"><span data-stu-id="650d2-117">To verify you can open the Task Manager on a computer that was selected for an Office install and look for Microsoft Office Click-to-Run process.</span></span>
  


