---
title: Регистрация Microsoft Defender для конечной точки для macOS-устройств в Jamf Pro
description: Регистрация Microsoft Defender для конечной точки для macOS-устройств в Jamf Pro
keywords: Microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e832493159649cb6721320da53c25f57855baa4f
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861651"
---
# <a name="enroll-microsoft-defender-for-endpoint-on-macos-devices-into-jamf-pro"></a><span data-ttu-id="03577-104">Регистрация Microsoft Defender для конечной точки на устройствах macOS в Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="03577-104">Enroll Microsoft Defender for Endpoint on macOS devices into Jamf Pro</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="03577-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="03577-105">**Applies to:**</span></span>
- [<span data-ttu-id="03577-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="03577-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="03577-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="03577-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="03577-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="03577-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="03577-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="03577-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="enroll-macos-devices"></a><span data-ttu-id="03577-110">Регистрация устройств macOS</span><span class="sxs-lookup"><span data-stu-id="03577-110">Enroll macOS devices</span></span>

<span data-ttu-id="03577-111">Существует несколько методов регистрации в JamF.</span><span class="sxs-lookup"><span data-stu-id="03577-111">There are multiple methods of getting enrolled to JamF.</span></span>

<span data-ttu-id="03577-112">В этой статье вы сможете использовать два метода:</span><span class="sxs-lookup"><span data-stu-id="03577-112">This article will guide you on two methods:</span></span>

- [<span data-ttu-id="03577-113">Метод 1. Приглашения на регистрацию</span><span class="sxs-lookup"><span data-stu-id="03577-113">Method 1:  Enrollment Invitations</span></span>](#enrollment-method-1-enrollment-invitations)
- [<span data-ttu-id="03577-114">Метод 2. Предварительная регистрация</span><span class="sxs-lookup"><span data-stu-id="03577-114">Method 2:  Prestage Enrollments</span></span>](#enrollment-method-2-prestage-enrollments)

<span data-ttu-id="03577-115">Полный список см. в [списке О регистрации на компьютере.](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html)</span><span class="sxs-lookup"><span data-stu-id="03577-115">For a complete list, see [About Computer Enrollment](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html).</span></span>


## <a name="enrollment-method-1-enrollment-invitations"></a><span data-ttu-id="03577-116">Метод регистрации 1. Приглашения на регистрацию</span><span class="sxs-lookup"><span data-stu-id="03577-116">Enrollment Method 1: Enrollment Invitations</span></span>

1. <span data-ttu-id="03577-117">В панели мониторинга Jamf Pro перейдите к **приглашениям для регистрации.**</span><span class="sxs-lookup"><span data-stu-id="03577-117">In the Jamf Pro dashboard, navigate to **Enrollment invitations**.</span></span>

    ![Изображение параметров конфигурации1](images/a347307458d6a9bbfa88df7dbe15398f.png)

2. <span data-ttu-id="03577-119">Выберите **+ Новый**.</span><span class="sxs-lookup"><span data-stu-id="03577-119">Select **+ New**.</span></span>

    ![Крупный план описания логотипа, созданного автоматически](images/b6c7ad56d50f497c38fc14c1e315456c.png)

3. <span data-ttu-id="03577-121">В **указать получателей для** приглашения > **по** адресам электронной почты введите адрес электронной почты (es) получателей.</span><span class="sxs-lookup"><span data-stu-id="03577-121">In **Specify Recipients for the Invitation** > under **Email Addresses** enter the e-mail address(es) of the recipients.</span></span>

    ![Изображение параметров конфигурации2](images/718b9d609f9f77c8b13ba88c4c0abe5d.png)

    ![Изображение параметров конфигурации3](images/ae3597247b6bc7c5347cf56ab1e820c0.png)

    <span data-ttu-id="03577-124">Например: janedoe@contoso.com</span><span class="sxs-lookup"><span data-stu-id="03577-124">For example: janedoe@contoso.com</span></span>

    ![Изображение параметров конфигурации4](images/4922c0fcdde4c7f73242b13bf5e35c19.png)

4. <span data-ttu-id="03577-126">Настройка сообщения для приглашения.</span><span class="sxs-lookup"><span data-stu-id="03577-126">Configure the message for the invitation.</span></span>

    ![Изображение параметров конфигурации5](images/ce580aec080512d44a37ff8e82e5c2ac.png)

    ![Изображение параметров конфигурации6](images/5856b765a6ce677caacb130ca36b1a62.png)

    ![Изображение параметров конфигурации7](images/3ced5383a6be788486d89d407d042f28.png)

    ![Изображение параметров конфигурации8](images/54be9c6ed5b24cebe628dc3cd9ca4089.png)

## <a name="enrollment-method-2-prestage-enrollments"></a><span data-ttu-id="03577-131">Метод регистрации 2. Предварительная регистрация</span><span class="sxs-lookup"><span data-stu-id="03577-131">Enrollment Method 2: Prestage Enrollments</span></span>

1. <span data-ttu-id="03577-132">В панели мониторинга Jamf Pro перейдите к **предварительной регистрации.**</span><span class="sxs-lookup"><span data-stu-id="03577-132">In the Jamf Pro dashboard, navigate to **Prestage enrollments**.</span></span>

    ![Изображение параметров конфигурации9](images/6fd0cb2bbb0e60a623829c91fd0826ab.png)

2. <span data-ttu-id="03577-134">Следуйте инструкциям в [записях предварительного выполнения](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html)компьютера.</span><span class="sxs-lookup"><span data-stu-id="03577-134">Follow the instructions in [Computer PreStage Enrollments](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html).</span></span>

## <a name="enroll-macos-device"></a><span data-ttu-id="03577-135">Регистрация устройства macOS</span><span class="sxs-lookup"><span data-stu-id="03577-135">Enroll macOS device</span></span>

1. <span data-ttu-id="03577-136">Выберите **Продолжить** и установить сертификат ЦС из окна **"Параметры системы".**</span><span class="sxs-lookup"><span data-stu-id="03577-136">Select **Continue** and install the CA certificate from a **System Preferences** window.</span></span>

    ![Изображение регистрации Jamf Pro1](images/jamfpro-ca-certificate.png)

2. <span data-ttu-id="03577-138">После установки сертификата CA вернись в окно браузера и выберите **Продолжить** и установить профиль MDM.</span><span class="sxs-lookup"><span data-stu-id="03577-138">Once CA certificate is installed, return to the browser window and select **Continue** and install the MDM profile.</span></span> 

    ![Изображение регистрации Jamf Pro2](images/jamfpro-install-mdm-profile.png)

3. <span data-ttu-id="03577-140">Выберите **Разрешить** скачивание из JAMF.</span><span class="sxs-lookup"><span data-stu-id="03577-140">Select **Allow** to downloads from JAMF.</span></span>

    ![Изображение регистрации Jamf Pro3](images/jamfpro-download.png)

4. <span data-ttu-id="03577-142">Выберите **Продолжить** работу с установкой профиля MDM.</span><span class="sxs-lookup"><span data-stu-id="03577-142">Select **Continue** to proceed with the MDM Profile installation.</span></span> 

    ![Изображение jamf Pro enrollment4](images/jamfpro-install-mdm.png)

5. <span data-ttu-id="03577-144">Выберите **Продолжить** установку профиля MDM.</span><span class="sxs-lookup"><span data-stu-id="03577-144">Select **Continue** to install the MDM Profile.</span></span>

    ![Изображение jamf Pro enrollment5](images/jamfpro-mdm-unverified.png)

6. <span data-ttu-id="03577-146">Выберите **Продолжить**  для завершения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="03577-146">Select **Continue**  to complete the configuration.</span></span> 

    ![Изображение jamf Pro enrollment6](images/jamfpro-mdm-profile.png)
