---
title: Подключенные приложения в Microsoft Defender для конечной точки
ms.reviewer: ''
description: Просмотр подключенных партнерских приложений, которые используют стандартный протокол OAuth 2.0 для проверки подлинности и предоставления маркеров для использования в API конечных токенов Microsoft Defender.
keywords: партнеры, приложения, сторонние подключения, sentinelone, lookout, bitdefender, corrata, morphisec, paloalto, ziften, better mobile
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4b212acdf4bdf8fa53ef00763463190e204fc1ed
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339170"
---
# <a name="connected-applications-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="8b840-104">Подключенные приложения в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="8b840-104">Connected applications in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8b840-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="8b840-105">**Applies to:**</span></span>
- [<span data-ttu-id="8b840-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="8b840-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8b840-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8b840-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="8b840-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="8b840-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8b840-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="8b840-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="8b840-110">Подключенные приложения интегрируются с платформой Defender для конечных точек с помощью API.</span><span class="sxs-lookup"><span data-stu-id="8b840-110">Connected applications integrates with the Defender for Endpoint platform using APIs.</span></span> 

<span data-ttu-id="8b840-111">Приложения используют стандартный протокол OAuth 2.0 для проверки подлинности и предоставления маркеров для использования в API конечных токенов Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="8b840-111">Applications use standard OAuth 2.0 protocol to authenticate and provide tokens for use with Microsoft Defender for Endpoint APIs.</span></span>  <span data-ttu-id="8b840-112">Кроме того, Azure Active Directory (Azure AD) позволяют администраторам клиентов устанавливать явный контроль над доступом к API с помощью соответствующего приложения.</span><span class="sxs-lookup"><span data-stu-id="8b840-112">In addition, Azure Active Directory (Azure AD) applications allow tenant admins to set explicit control over which APIs can be accessed using the corresponding app.</span></span>
 
<span data-ttu-id="8b840-113">Чтобы использовать API [](/microsoft-365/security/defender-endpoint/apis-intro) с подключенным приложением, необходимо следовать этим шагам.</span><span class="sxs-lookup"><span data-stu-id="8b840-113">You'll need to follow [these steps](/microsoft-365/security/defender-endpoint/apis-intro) to use the APIs with the connected application.</span></span>
 
## <a name="access-the-connected-application-page"></a><span data-ttu-id="8b840-114">Доступ к подключенной странице приложения</span><span class="sxs-lookup"><span data-stu-id="8b840-114">Access the connected application page</span></span>
<span data-ttu-id="8b840-115">В левом меню навигации выберите **приложения Endpoints**  >  **Partners и API**  >  **Connected.**</span><span class="sxs-lookup"><span data-stu-id="8b840-115">From the left navigation menu, select **Endpoints** > **Partners and APIs** > **Connected applications**.</span></span>

 
## <a name="view-connected-application-details"></a><span data-ttu-id="8b840-116">Просмотр сведений о подключенных приложениях</span><span class="sxs-lookup"><span data-stu-id="8b840-116">View connected application details</span></span>
<span data-ttu-id="8b840-117">На странице Подключенные приложения содержится информация о приложениях Azure AD, подключенных к Microsoft Defender для конечной точки в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="8b840-117">The Connected applications page provides information about the Azure AD applications connected to Microsoft Defender for Endpoint in your organization.</span></span> <span data-ttu-id="8b840-118">Вы можете просмотреть использование подключенных приложений: последнее просмотрение, количество запросов за последние 24 часа и тенденции запроса за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="8b840-118">You can review the usage of the connected applications: last seen, number of requests in the past 24 hours, and request trends in the last 30 days.</span></span>

![Изображение подключенных приложений](images/connected-apps.png)
 
## <a name="edit-reconfigure-or-delete-a-connected-application"></a><span data-ttu-id="8b840-120">Изменение, перенастройка или удаление подключенного приложения</span><span class="sxs-lookup"><span data-stu-id="8b840-120">Edit, reconfigure, or delete a connected application</span></span>
<span data-ttu-id="8b840-121">Ссылка **"Параметры открытого приложения"** открывает соответствующую страницу управления приложениями Azure AD на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="8b840-121">The **Open application settings** link opens the corresponding Azure AD application management page in the Azure portal.</span></span> <span data-ttu-id="8b840-122">На портале Azure можно управлять разрешениями, перенастройка или удаление подключенных приложений.</span><span class="sxs-lookup"><span data-stu-id="8b840-122">From the Azure portal, you can manage permissions, reconfigure, or delete the connected applications.</span></span>
