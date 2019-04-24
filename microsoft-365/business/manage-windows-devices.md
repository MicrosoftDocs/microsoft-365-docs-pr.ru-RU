---
title: Включение управления подключенными к домену устройств с Windows 10 в Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Сведения о том, как включить Microsoft 365 для защиты локальных подключенных устройств AD к Windows 10.
ms.openlocfilehash: d61b3bf6be50d6b21e7b883774567bb63995e60e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278084"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="45977-103">Включение управления подключенными к домену устройств с Windows 10 в Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="45977-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="45977-104">Если ваша организация использует локальную службу Windows Server Active Directory, вы можете настроить Microsoft 365 бизнес для защиты устройств с Windows 10, сохраняя доступ к локальным ресурсам, требующим локальной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="45977-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="45977-105">Это можно сделать с помощью первой синхронизации Active Directory с Azure Active Directory, а затем зарегистрировать устройства Windows 10 с помощью Azure AD и зарегистрировать их для управления мобильными устройствами в Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="45977-105">You can set this up by first synchronizing your Active Directory with Azure Active Directory, followed by registering the Windows 10 devices with Azure AD and enrolling them for mobile device management by Microsoft 365 Business.</span></span>
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="45977-106">Настройка устройств, присоединенных к домену, для управления с помощью Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="45977-106">Set up domain-joined devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="45977-107">Чтобы настроить устройства, присоединенные к домену организации, для использования возможностей, предоставляемых Azure Active Directory, в дополнение к локальной службе Active Directory, можно внедрить **гибридные подключенные устройства Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="45977-107">To set up your organization's domain-joined devices to benefit from the capabilities provided by Azure Active Directory in addition to on-premises Active Directory, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="45977-108">Это устройства, которые присоединяются к локальному каталогу Active Directory и вашей службе Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="45977-108">These are devices that are joined both to your on-premises Active Directory and your Azure Active Directory.</span></span> <span data-ttu-id="45977-109">Гибридные подключенные устройства Azure AD можно защищать и управлять ими с помощью Microsoft 365 Business..</span><span class="sxs-lookup"><span data-stu-id="45977-109">Hybrid Azure AD joined devices can be protected and managed by Microsoft 365 Business..</span></span> 
  
<span data-ttu-id="45977-110">Выполните приведенные ниже действия, чтобы сделать гибридную службу Windows 10 Devices (Windows 10) присоединенной и управляемой Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="45977-110">Complete the steps below to make your Windows 10 devices Hybrid Azure AD joined and managed by Microsoft 365 Business.</span></span>
  
1. <span data-ttu-id="45977-111">Чтобы синхронизировать пользователей, группы и контакты из локальной службы Active Directory с Azure Active Directory, запустите мастер синхронизации каталогов и Azure Active Directory Connect, как описано в статье [Настройка синхронизации каталогов для Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span><span class="sxs-lookup"><span data-stu-id="45977-111">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure Active Directory Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="45977-112">Эти действия одинаковы для Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="45977-112">The steps are exactly the same for Microsoft 365 Business.</span></span> 
  
2. <span data-ttu-id="45977-113">Прежде чем выполнить шаг 3, чтобы включить гибридные устройства с Windows 10 для гибридной службы Azure AD, необходимо убедиться, что выполняются следующие предварительные требования:</span><span class="sxs-lookup"><span data-stu-id="45977-113">Before you complete step 3 to enable Windows 10 devices to be Hybrid Azure AD joined, you need to make sure that you meet the following prerequisites:</span></span>
    
   - <span data-ttu-id="45977-114">Вы используете последнюю версию Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="45977-114">You are running the latest version of Azure AD connect.</span></span>
    
   - <span data-ttu-id="45977-115">Azure AD Connect синхронизирует все объекты компьютеров устройств, которые вы хотите объединить в гибридную службу Azure AD.</span><span class="sxs-lookup"><span data-stu-id="45977-115">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined.</span></span> <span data-ttu-id="45977-116">Если объекты компьютера принадлежат определенным подразделениям (OU), убедитесь, что эти подразделения настроены для синхронизации в Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="45977-116">If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>
    
3. <span data-ttu-id="45977-117">Регистрация существующих устройств с Windows 10, присоединенных к домену, в гибридное подключение Azure AD и регистрация их для управления мобильными устройствами в Intune (Microsoft 365 бизнес):</span><span class="sxs-lookup"><span data-stu-id="45977-117">Register existing domain-joined Windows 10 devices to be hybrid Azure AD Joined and enroll them for mobile device management by Intune (Microsoft 365 Business):</span></span>
    
4. <span data-ttu-id="45977-118">Выполните пошаговые инструкции по [настройке подключенных устройств гибридной службы Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=872870).</span><span class="sxs-lookup"><span data-stu-id="45977-118">Follow the step by step instructions in [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870).</span></span> <span data-ttu-id="45977-119">Это позволит синхронизировать локальную службу Active Directory с компьютерами с Windows 10 и подготовить их к работе в облаке.</span><span class="sxs-lookup"><span data-stu-id="45977-119">This will enable the synchronization of your on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
5. <span data-ttu-id="45977-120">Чтобы зарегистрировать устройство Windows 10 для управления мобильными устройствами, ознакомьтесь с инструкциями в статье [Регистрация устройства Windows 10 с помощью Intune с помощью групповой политики](https://go.microsoft.com/fwlink/p/?linkid=872871) .</span><span class="sxs-lookup"><span data-stu-id="45977-120">In order to enroll a Windows 10 device for mobile device management, see [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for instructions.</span></span> <span data-ttu-id="45977-121">Вы можете настроить групповую политику на уровне локального компьютера или для массовых операций, вы можете создать этот параметр групповой политики на сервере контроллера домена.</span><span class="sxs-lookup"><span data-stu-id="45977-121">You can set the Group Policy at a local computer level or for bulk operations, you can create this group policy setting on your domain controller server.</span></span> 
    

