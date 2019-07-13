---
title: Сведения о клиенте Azure Active Directory
description: В этом разделе описываются изменения, внесенные в учетную запись AAD при регистрации на компьютере, управляемом Майкрософт
keywords: Настольные компьютеры, управляемые корпорацией Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: 6b2b30d8dedba1086bfa9268fb0fdbce20367c20
ms.sourcegitcommit: dd426c686b52cf79325f11022b2d99bc45285577
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2019
ms.locfileid: "35643950"
---
# <a name="azure-active-directory-tenant-details"></a><span data-ttu-id="fe4c5-104">Сведения о клиенте Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="fe4c5-104">Azure Active Directory tenant details</span></span>
<span data-ttu-id="fe4c5-105">{Гори сведения об учетных записях, вызовах API, доступах и т. д.}</span><span class="sxs-lookup"><span data-stu-id="fe4c5-105">{gory details about accounts, API calls, perms, etc., etc.}</span></span>


## <a name="data-transmitted-to-and-from-your-aad-account"></a><span data-ttu-id="fe4c5-106">Данные, передаваемые в учетную запись AAD и получаемые от нее</span><span class="sxs-lookup"><span data-stu-id="fe4c5-106">Data transmitted to and from your AAD account</span></span>


<span data-ttu-id="fe4c5-107">Данные, отправляемые в учетную запись Майкрософт:</span><span class="sxs-lookup"><span data-stu-id="fe4c5-107">Data sent to your account from Microsoft:</span></span>

- <span data-ttu-id="fe4c5-108">Имена групп</span><span class="sxs-lookup"><span data-stu-id="fe4c5-108">Group names</span></span>
- <span data-ttu-id="fe4c5-109">Настройка политики безопасности</span><span class="sxs-lookup"><span data-stu-id="fe4c5-109">Security policy configuration</span></span>
- <span data-ttu-id="fe4c5-110">Заказы на устройства</span><span class="sxs-lookup"><span data-stu-id="fe4c5-110">Device orders</span></span>
- <span data-ttu-id="fe4c5-111">Учетные записи пользователей (мсадмин, MSTest, мваас_сок_ро, мваас_вдгсок)</span><span class="sxs-lookup"><span data-stu-id="fe4c5-111">User accounts (msadmin, mstest, mwaas_soc_ro, mwaas_wdgsoc)</span></span>
- <span data-ttu-id="fe4c5-112">Назначение лицензии для учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="fe4c5-112">E5 License assignment to the user accounts</span></span>
- <span data-ttu-id="fe4c5-113">Политики обновления Windows для звонков обновления</span><span class="sxs-lookup"><span data-stu-id="fe4c5-113">Windows update policies for update rings</span></span>

<span data-ttu-id="fe4c5-114">Данные, отправляемые в корпорацию Майкрософт из вашей учетной записи:</span><span class="sxs-lookup"><span data-stu-id="fe4c5-114">Data sent to Microsoft from your account:</span></span>

- <span data-ttu-id="fe4c5-115">Данные об обновлениях, использовании и надежности устройств</span><span class="sxs-lookup"><span data-stu-id="fe4c5-115">Device update, usage and reliability data</span></span>
- <span data-ttu-id="fe4c5-116">Данные о развертывании и надежности приложений</span><span class="sxs-lookup"><span data-stu-id="fe4c5-116">App deployment and reliability data</span></span>
- <span data-ttu-id="fe4c5-117">Данные о развертывании политик обновления и безопасности</span><span class="sxs-lookup"><span data-stu-id="fe4c5-117">Update and security policy deployment data</span></span>
- <span data-ttu-id="fe4c5-118">Пользователи, назначенные устройствам</span><span class="sxs-lookup"><span data-stu-id="fe4c5-118">Users assigned to devices</span></span>  

<span data-ttu-id="fe4c5-119">Данные, передаваемые из учетной записи, хранятся в базах данных Azure SQL в клиенте Майкрософт, размещенном в США.</span><span class="sxs-lookup"><span data-stu-id="fe4c5-119">Data transmitted from your account is stored in Azure SQL databases in the Microsoft tenant hosted in the USA.</span></span> <span data-ttu-id="fe4c5-120">Данные хранятся и обрабатываются в соответствии с политиками, описанными в статье {Microsoft Azure Security}.</span><span class="sxs-lookup"><span data-stu-id="fe4c5-120">Data is stored and handled in accordance the policies described in {Microsoft Azure security}.</span></span> 

## <a name="api-permissions-and-calls"></a><span data-ttu-id="fe4c5-121">Разрешения и вызовы API</span><span class="sxs-lookup"><span data-stu-id="fe4c5-121">API permissions and calls</span></span>

<span data-ttu-id="fe4c5-122">**Во время регистрации:**</span><span class="sxs-lookup"><span data-stu-id="fe4c5-122">**During enrollment:**</span></span>

<span data-ttu-id="fe4c5-123">Разрешения API:</span><span class="sxs-lookup"><span data-stu-id="fe4c5-123">API permissions:</span></span>
- <span data-ttu-id="fe4c5-124">DeviceManagementServiceConfig.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="fe4c5-124">DeviceManagementServiceConfig.ReadWrite.All</span></span>
- <span data-ttu-id="fe4c5-125">Directory.AccessAsUser.All</span><span class="sxs-lookup"><span data-stu-id="fe4c5-125">Directory.AccessAsUser.All</span></span>
- <span data-ttu-id="fe4c5-126">User.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="fe4c5-126">User.ReadWrite.All</span></span>
- <span data-ttu-id="fe4c5-127">DeviceManagementConfiguration.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="fe4c5-127">DeviceManagementConfiguration.ReadWrite.All</span></span>
- <span data-ttu-id="fe4c5-128">DeviceManagementManagedDevices.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="fe4c5-128">DeviceManagementManagedDevices.ReadWrite.All</span></span>
- <span data-ttu-id="fe4c5-129">Group.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="fe4c5-129">Group.ReadWrite.All</span></span>

<span data-ttu-id="fe4c5-130">Вызовов API:</span><span class="sxs-lookup"><span data-stu-id="fe4c5-130">API calls:</span></span>
- <span data-ttu-id="fe4c5-131">POST/Организатион/{организатионид}/сетмобиледевицеманажементаусорити</span><span class="sxs-lookup"><span data-stu-id="fe4c5-131">POST /organization/{organizationId}/setMobileDeviceManagementAuthority</span></span>
- <span data-ttu-id="fe4c5-132">GET/POST/Директориролес/{ИД}/мемберс</span><span class="sxs-lookup"><span data-stu-id="fe4c5-132">GET/POST /directoryRoles/{id}/members</span></span>
- <span data-ttu-id="fe4c5-133">GET/POST/Users</span><span class="sxs-lookup"><span data-stu-id="fe4c5-133">GET/POST /users</span></span>
- <span data-ttu-id="fe4c5-134">GET/POST/граупс</span><span class="sxs-lookup"><span data-stu-id="fe4c5-134">GET/POST /groups</span></span>
- <span data-ttu-id="fe4c5-135">Исправление/граупс/{ИД}</span><span class="sxs-lookup"><span data-stu-id="fe4c5-135">PATCH /groups/{id}</span></span>
- <span data-ttu-id="fe4c5-136">GET/POST/Девицеманажемент/девицеконфигуратионс</span><span class="sxs-lookup"><span data-stu-id="fe4c5-136">GET/POST /deviceManagement/deviceConfigurations</span></span>
- <span data-ttu-id="fe4c5-137">ПОЛУЧЕНИЕ/Девицеманажемент/детектедаппс</span><span class="sxs-lookup"><span data-stu-id="fe4c5-137">GET /deviceManagement/detectedApps</span></span>

<span data-ttu-id="fe4c5-138">**После регистрации в обычном управлении:**</span><span class="sxs-lookup"><span data-stu-id="fe4c5-138">**After enrollment, during ordinary management:**</span></span>

<span data-ttu-id="fe4c5-139">Разрешения API:</span><span class="sxs-lookup"><span data-stu-id="fe4c5-139">API permissions:</span></span>
- <span data-ttu-id="fe4c5-140">DeviceManagementManagedDevices.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="fe4c5-140">DeviceManagementManagedDevices.ReadWrite.All</span></span>
- <span data-ttu-id="fe4c5-141">DeviceManagementApps.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="fe4c5-141">DeviceManagementApps.ReadWrite.All</span></span>
- <span data-ttu-id="fe4c5-142">DeviceManagementConfiguration.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="fe4c5-142">DeviceManagementConfiguration.ReadWrite.All</span></span>
- <span data-ttu-id="fe4c5-143">Reports.Read.All</span><span class="sxs-lookup"><span data-stu-id="fe4c5-143">Reports.Read.All</span></span>
- <span data-ttu-id="fe4c5-144">User.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="fe4c5-144">User.ReadWrite.All</span></span>
- <span data-ttu-id="fe4c5-145">Group.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="fe4c5-145">Group.ReadWrite.All</span></span>
- <span data-ttu-id="fe4c5-146">Directory.AccessAsUser.All</span><span class="sxs-lookup"><span data-stu-id="fe4c5-146">Directory.AccessAsUser.All</span></span>

<span data-ttu-id="fe4c5-147">Вызовов API:</span><span class="sxs-lookup"><span data-stu-id="fe4c5-147">API calls:</span></span>
- <span data-ttu-id="fe4c5-148">GET/POST/Директориролес/{ИД}/мемберс</span><span class="sxs-lookup"><span data-stu-id="fe4c5-148">GET/POST /directoryRoles/{id}/members</span></span>
- <span data-ttu-id="fe4c5-149">GET/PATCH/POST/Users</span><span class="sxs-lookup"><span data-stu-id="fe4c5-149">GET/PATCH/POST /users</span></span>
- <span data-ttu-id="fe4c5-150">GET/POST/граупс</span><span class="sxs-lookup"><span data-stu-id="fe4c5-150">GET/POST /groups</span></span>
- <span data-ttu-id="fe4c5-151">Исправление/граупс/{ИД}</span><span class="sxs-lookup"><span data-stu-id="fe4c5-151">PATCH /groups/{id}</span></span>
- <span data-ttu-id="fe4c5-152">GET/POST/Девицеманажемент/девицеконфигуратионс</span><span class="sxs-lookup"><span data-stu-id="fe4c5-152">GET/POST /deviceManagement/deviceConfigurations</span></span>
- <span data-ttu-id="fe4c5-153">GET/POST/Девицеаппманажемент/мобилеаппс</span><span class="sxs-lookup"><span data-stu-id="fe4c5-153">GET/POST /deviceAppManagement/mobileApps</span></span>
- <span data-ttu-id="fe4c5-154">ПОЛУЧЕНИЕ/Девицеманажемент/детектедаппс</span><span class="sxs-lookup"><span data-stu-id="fe4c5-154">GET /deviceManagement/detectedApps</span></span>
- <span data-ttu-id="fe4c5-155">ПОЛУЧЕНИЕ/девицес</span><span class="sxs-lookup"><span data-stu-id="fe4c5-155">GET /devices</span></span>
- <span data-ttu-id="fe4c5-156">POST/усерс/{ИД | userPrincipalName}/Ассигнлиценсе</span><span class="sxs-lookup"><span data-stu-id="fe4c5-156">POST /users/{id | userPrincipalName}/assignLicense</span></span>
- <span data-ttu-id="fe4c5-157">ПОЛУЧЕНИЕ/Субскрибедскус</span><span class="sxs-lookup"><span data-stu-id="fe4c5-157">GET /subscribedSkus</span></span>

## <a name="accounts-used-by-microsoft-managed-desktop"></a><span data-ttu-id="fe4c5-158">Учетные записи, используемые корпорацией Майкрософт для настольных компьютеров</span><span class="sxs-lookup"><span data-stu-id="fe4c5-158">Accounts used by Microsoft Managed Desktop</span></span>





| <span data-ttu-id="fe4c5-159">Учетная запись</span><span class="sxs-lookup"><span data-stu-id="fe4c5-159">Account</span></span> | <span data-ttu-id="fe4c5-160">Описание</span><span class="sxs-lookup"><span data-stu-id="fe4c5-160">Description</span></span>  | <span data-ttu-id="fe4c5-161">условный доступ;</span><span class="sxs-lookup"><span data-stu-id="fe4c5-161">Conditional access</span></span>  | <span data-ttu-id="fe4c5-162">многофакторная проверка подлинности;</span><span class="sxs-lookup"><span data-stu-id="fe4c5-162">Multi-factor authentication</span></span>  | <span data-ttu-id="fe4c5-163">Почему это нормально</span><span class="sxs-lookup"><span data-stu-id="fe4c5-163">Why this is OK</span></span> |
|---------|---------|---------|---------|--------------|
| <span data-ttu-id="fe4c5-164">мсадмин @ \* онммикрософт. com</span><span class="sxs-lookup"><span data-stu-id="fe4c5-164">msadmin@\*onmmicrosoft.com</span></span> | <span data-ttu-id="fe4c5-165">Ограниченная учетная запись службы с правами администратора, используемая в качестве Microsoft Intune и администратором пользователей {что это такое?}</span><span class="sxs-lookup"><span data-stu-id="fe4c5-165">Limited service account with administrator privileges, used as a Microsoft Intune and User administrator {what's this?}</span></span> <span data-ttu-id="fe4c5-166">для определения и настройки клиента для современных настольных устройств Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fe4c5-166">to define and configure the tenant for Microsoft Modern Desktop devices.</span></span><span data-ttu-id="fe4c5-167">Не имеет разрешений для интерактивного входа; выполняет операции только через службу.</span><span class="sxs-lookup"><span data-stu-id="fe4c5-167">  Does not have interactive login permissions; performs operations only through the service.</span></span>  | <span data-ttu-id="fe4c5-168">Исключено, так как он не исходит из сети</span><span class="sxs-lookup"><span data-stu-id="fe4c5-168">Excluded, because it doesn't originate in your network</span></span>        | <span data-ttu-id="fe4c5-169">Исключено из-за отсутствия интерактивного входа</span><span class="sxs-lookup"><span data-stu-id="fe4c5-169">Excluded because there is no interactive logon</span></span>        | <span data-ttu-id="fe4c5-170">Пароль, хранящийся в Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="fe4c5-170">Password stored in Azure Key Vault</span></span> |
| <span data-ttu-id="fe4c5-171">MSTest @ \* онммикрософт. com</span><span class="sxs-lookup"><span data-stu-id="fe4c5-171">mstest@\*onmmicrosoft.com</span></span>     |         |         |         |
| <span data-ttu-id="fe4c5-172">мссуппорт @ \* онммикрософт. com</span><span class="sxs-lookup"><span data-stu-id="fe4c5-172">mssupport@\*onmmicrosoft.com</span></span>     |         |         |         |
| <span data-ttu-id="fe4c5-173">мсадмининт @ \* онммикрософт. com</span><span class="sxs-lookup"><span data-stu-id="fe4c5-173">msadminint@\*onmmicrosoft.com</span></span>     |         |         |         |
