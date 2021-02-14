---
title: Управление устройствами с Windows 10, которые присоединились к домену, с помощью Microsoft 365 для бизнеса
f1.keywords:
- CSH
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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Узнайте, как включить Microsoft 365 для защиты локальных устройств с Windows 10, которые присоединились к Active Directory, всего за несколько шагов.
ms.openlocfilehash: 6275c6c4be9cd9631ab095f8b0e1b39683022bb2
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560850"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Управление устройствами с Windows 10, которые присоединились к домену, с помощью Microsoft 365 бизнес премиум

Если в вашей организации используется локальная служба Windows Server Active Directory, вы можете настроить Microsoft 365 бизнес премиум для защиты устройств с Windows 10, сохранив при этом доступ к локальным ресурсам, которые требуют локальной проверки подлинности.
Чтобы настроить эту защиту, можно реализовать гибридные устройства, **присоединимые к Azure AD.** Эти устройства присоединяются к локальной службе Active Directory и Azure Active Directory.

В этом видео описаны действия по его настройкам для наиболее распространенных сценариев, которые также подробно описаны в последующих действиях.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a>Перед началом работы выполните следующие действия:
- Синхронизация пользователей с Azure AD с помощью Azure AD Connect.
- Завершите синхронизацию подразделения Azure AD Connect.
- Убедитесь, что все синхронизированные пользователи домена имеют лицензии на Microsoft 365 бизнес премиум.

См. действия по синхронизации [пользователей домена с Корпорацией](manage-domain-users.md) Майкрософт.

## <a name="1-verify-mdm-authority-in-intune"></a>1. Проверка MDM Authority в Intune

Перейдите [в Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) и на странице Microsoft Intune  выберите регистрацию **устройств,** а затем на странице "Обзор" убедитесь, что в **MDM** есть **Intune.**

- Если **полномочия MDM не**  **установлены,** щелкните его, чтобы установить для него **intune.**
- Если для **MDM** установлено право **Microsoft Office 365,** перейдите на сайт "Регистрация устройств" и используйте диалоговое окно "Добавление полномочий MDM" справа для добавления полномочий Intune MDM (диалоговое окно "Добавление полномочий MDM" доступно, только если для управления  >   **MDM** установлено Microsoft Office 365).   

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Убедитесь, что azure AD включен для присоединения к компьютерам

- Перейдите в Центр администрирования и выберите <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **Azure Active Directory** (выберите "Показать все", если Azure Active Directory не отображается) в списке центров **администрирования.** 
- В Центре **администрирования Azure Active Directory** перейдите в **Azure Active Directory,** выберите **"Устройства",** а затем **параметры устройства.**
- Проверка **того, что пользователи могут присоединять устройства к Azure AD,** включена 
    1. Чтобы включить всех пользователей, установите **для** них все.
    2. Чтобы включить определенных пользователей, установите **"Выбрано",** чтобы включить определенную группу пользователей.
        - Добавьте нужных пользователей домена, синхронизированных в Azure AD, в [группу безопасности.](../admin/create-groups/create-groups.md)
        - Выберите **"Выбрать группы",** чтобы включить область пользователей MDM для этой группы безопасности.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. Убедитесь, что Azure AD включен для MDM

- Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Endpoint Managemen** t (select **Show all** if **Endpoint Manager** is not visible)
- В Центре **администрирования Microsoft Endpoint Manager** перейдите на **устройства с** автоматической регистрацией  >    >  **Windows.**  >  
- Убедитесь, что область пользователя MDM включена.

    1. Чтобы зарегистрировать все компьютеры, установите для этого все, чтобы автоматически зарегистрировать все компьютеры пользователей, которые присоединились к Azure AD, и новые компьютеры при добавлении пользователями учетной записи в Windows. 
    2. Установите для **некоторых** зарегистрировать компьютеры определенной группы пользователей.
        -  Добавьте нужных пользователей домена, синхронизированных в Azure AD, в [группу безопасности.](../admin/create-groups/create-groups.md)
        -  Выберите **"Выбрать группы",** чтобы включить область пользователей MDM для этой группы безопасности.

## <a name="4-create-the-required-resources"></a>4. Создайте необходимые ресурсы 

Выполнение необходимых задач для настройки гибридного пользования [Azure AD](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) было упрощено с помощью командлета [Initialize-SecMgmtHybirdDeviceEnrollment,](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) найденного в модуле [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell. При вызове этого cmdlet он создаст и настроит необходимую точку подключения службы и групповую политику.

Чтобы установить этот модуль, вы можете с помощью экземпляра PowerShell:

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> Рекомендуется установить этот модуль на windows Server с Azure AD Connect.

Чтобы создать необходимую точку подключения службы и групповую политику, вы вызываете [cmdlet Initialize-SecMgmtHybirdDeviceEnrollment.](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) При выполнении этой задачи вам потребуется учетные данные глобального администратора Microsoft 365 бизнес премиум. Когда вы будете готовы создать ресурсы, вы можете вызвать следующее:

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

Первая команда установит подключение к Облаку Майкрософт, и при запросе укажите учетные данные глобального администратора Microsoft 365 бизнес премиум.

## <a name="5-link-the-group-policy"></a>5. Связывать групповую политику

1. В консоли управления групповыми политиками (GPMC) щелкните правой кнопкой мыши расположение, в котором нужно связать политику, и выберите ссылку на существующий *GPO...* в контекстное меню.
2. Выберите политику, созданную на этапе выше, и нажмите кнопку **"ОК".**

## <a name="get-the-latest-administrative-templates"></a>Получить последние административные шаблоны

Если вы не видите политику "Включить автоматическую регистрацию **в MDM** с использованием учетных данных Azure AD по умолчанию", возможно, У вас нет ADMX, установленной для Windows 10 версии 1803, версии 1809 или версии 1903. Чтобы устранить проблему, выполните следующие действия (обратите внимание: последняя версия MDM.admx совместима с обратной совместимость):

1.  Download: [Administrative Templates (.admx) for Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).
2.  Установите пакет на основном контроллере домена (PDC).
3.  Перейдите в зависимости от версии папки: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.
4.  Переименуем папку **"Определения политик"** в вышеуказанном пути в **PolicyDefinitions.**
5.  **Скопируйте папку PolicyDefinitions** **в папку C:\Windows\SYSVOL\domain\Policies.** 
    -   Если вы планируете использовать центральное хранилище политик для всего домена, добавьте в нее содержимое policyDefinitions.
6.  Перезапустите основной контроллер домена, чтобы политика была доступна. Эта процедура также будет работать для любой будущей версии.

На этом этапе вы сможете увидеть политику "Включить автоматическую регистрацию **в MDM"** с помощью учетных данных Azure AD по умолчанию.
