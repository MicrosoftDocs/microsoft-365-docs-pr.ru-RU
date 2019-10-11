---
title: Настройка многофакторной проверки подлинности
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
description: Настройка многофакторной проверки подлинности для Microsoft 365 бизнес.
ms.openlocfilehash: f015463d3fecbfe88bae90ddea7d98cf11cad693
ms.sourcegitcommit: 255e8194bb5767a9983d54d16e79d628732a1d97
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/11/2019
ms.locfileid: "37454031"
---
# <a name="multi-factor-authentication"></a><span data-ttu-id="f1505-103">многофакторная проверка подлинности;</span><span class="sxs-lookup"><span data-stu-id="f1505-103">Multi-factor authentication</span></span>

<span data-ttu-id="f1505-104">Многофакторная проверка подлинности (MFA) требует от пользователей выполнить вход с помощью второго метода для проверки их подлинности с помощью телефонного вызова или с помощью приложения проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="f1505-104">Multi-factor authentication (MFA) requires users to sign in with a second method to verify their identity with a phone call or with an authenticator app.</span></span>

## <a name="set-up-mfa-in-the-microsoft-365-admin-center"></a><span data-ttu-id="f1505-105">Настройка MFA в центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f1505-105">Set up MFA in the Microsoft 365 admin center</span></span>

<span data-ttu-id="f1505-106">[![Метка, с помощью которой вы узнаете, что центр администрирования изменяется, и вы можете получить дополнительные сведения по адресу aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="f1505-106">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

1. <span data-ttu-id="f1505-107">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) с помощью учетных данных глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="f1505-107">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 
2. <span data-ttu-id="f1505-108">В левой панели навигации выберите пункт **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="f1505-108">On the left nav, choose **Setup**.</span></span>
3. <span data-ttu-id="f1505-109">На странице Настройка выберите **Просмотр** на карточке **Включение многофакторной проверки подлинности (MFA)** .</span><span class="sxs-lookup"><span data-stu-id="f1505-109">On the Setup page, choose **View** on the **Turn on multi-factor authentication (MFA)** card.</span></span>
4. <span data-ttu-id="f1505-110">На странице **включить MFA** нажмите кнопку **начать работу**или **Управляйте** , если вы уже настроили MFA и хотите внести изменения.</span><span class="sxs-lookup"><span data-stu-id="f1505-110">On the **Turn on MFA** page, choose **Get started**, or **Manage** if you have already set up MFA and want to make changes.</span></span> 

  <span data-ttu-id="f1505-111">:::image type="content" source="media/turnonmfa.png" alt-text="Снимок экрана: включение страницы MFA.":::</span><span class="sxs-lookup"><span data-stu-id="f1505-111">:::image type="content" source="media/turnonmfa.png" alt-text="Screenshot of turn on MFA page.":::</span></span>

5. <span data-ttu-id="f1505-112">На панели **безопасности стренгхен** установите флажок **требуется многофакторная проверка подлинности для администраторов**, а затем выберите **создать политику**.</span><span class="sxs-lookup"><span data-stu-id="f1505-112">On the **Strenghen sign-in security** panel, check both or one of **Require multi-factor authentication for admins**, and then choose **Create policy**.</span></span>
