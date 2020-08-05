---
title: Включение управления устройствами с Windows 10, подключенными к домену, в Microsoft 365 для бизнеса
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
description: Сведения о том, как включить Microsoft 365 для защиты локальных подключенных к Active Directory устройств с Windows 10 в всего несколько этапов.
ms.openlocfilehash: 6275c6c4be9cd9631ab095f8b0e1b39683022bb2
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560850"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Управление устройствами с Windows 10, подключенными к домену, с помощью Microsoft 365 Business Premium

Если ваша организация использует локальную службу Windows Server Active Directory, вы можете настроить Microsoft 365 Business Premium для защиты устройств Windows 10, сохраняя доступ к локальным ресурсам, требующим локальной проверки подлинности.
Чтобы настроить эту защиту, можно внедрить **гибридные подключенные устройства Azure AD**. Эти устройства присоединяются как к локальной службе Active Directory, так и к Azure Active Directory.

В этом видеоролике описаны действия, которые необходимо выполнить для наиболее распространенного сценария, который также содержит подробные инструкции.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a>Прежде чем приступить к работе, убедитесь, что выполнены следующие действия:
- Синхронизация пользователей с Azure AD с помощью Azure AD Connect.
- Выполните синхронизацию подразделения Azure AD Connect (OU).
- Убедитесь, что у всех пользователей домена, которые вы синхронизируете, есть лицензии на Microsoft 365 Business Premium.

В этой статье приведены инструкции по [синхронизации пользователей домена с корпорацией Майкрософт](manage-domain-users.md) .

## <a name="1-verify-mdm-authority-in-intune"></a>1. Проверка полномочий MDM в Intune

Перейдите к [диспетчеру конечной точки](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) и на странице Microsoft Intune выберите **Регистрация устройств**, а затем на странице **обзора** убедитесь, что **центр управления MDM** является **Intune**.

- Если для **MDM Authority** задано значение **None (нет**), щелкните **центр MDM** , чтобы задать для него значение **Intune**.
- Если в качестве **шлюза** **MDM** используется **Microsoft Office 365**, перейдите на страницу  >  **Регистрация устройств** и воспользуйтесь диалоговым окном **Добавление центра MDM** справа для добавления центра **Intune MDM** (диалоговое окно **Add MDM Authority** доступно только в том случае, если для шлюза **MDM** установлено значение Microsoft Office 365).

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Убедитесь, что служба Azure AD включена для присоединения компьютеров

- Перейдите в центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> и выберите **Azure Active Directory** (выберите Показать все, если Azure Active Directory не отображается) в списке **центры администрирования** . 
- В **центре администрирования Azure Active Directory**откройте **Azure Active Directory** , выберите пункт **устройства** и затем **Параметры устройства**.
- Проверка того, что**пользователи могут присоединяться к устройствам для Azure AD** . 
    1. Чтобы включить всех пользователей, задайте значение **ALL**.
    2. Чтобы включить определенных пользователей, установите **флажок** разрешить определенную группу пользователей.
        - Добавьте в [группу безопасности](../admin/create-groups/create-groups.md)требуемых пользователей домена, синхронизированных в Azure AD.
        - Выберите **пункт Выбрать группы** , чтобы включить область пользователя MDM для этой группы безопасности.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. Убедитесь, что служба Azure AD включена для MDM

- Перейдите в центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> и выберите пункт выбрать **конечную точку манажемен**t (выберите **Показать все** , если **Диспетчер конечных точек** не отображается).
- В **центре администрирования Microsoft Endpoint Manager**перейдите к разделу **устройства**, подаче заявки на  >  **Windows**  >  **регистрацию Windows Windows**для  >  **автоматической регистрации**.
- Убедитесь, что область пользователя MDM включена.

    1. Чтобы зарегистрировать все компьютеры, установите для параметра **ALL** значение автоматическая регистрация всех пользовательских компьютеров, присоединенных к Azure AD и новым компьютерам, когда пользователи добавляют рабочую учетную запись в Windows.
    2. Установите значение **, чтобы** зарегистрировать компьютеры определенной группы пользователей.
        -  Добавьте в [группу безопасности](../admin/create-groups/create-groups.md)требуемых пользователей домена, синхронизированных в Azure AD.
        -  Выберите **пункт Выбрать группы** , чтобы включить область пользователя MDM для этой группы безопасности.

## <a name="4-create-the-required-resources"></a>4. создание необходимых ресурсов 

Выполнение необходимых задач для [настройки гибридного объединения Azure AD](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) было упрощено с помощью командлета [Initialize – секмгмсибирддевицеенроллмент](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) , найденного в модуле [секмгмт](https://www.powershellgallery.com/packages/SecMgmt) PowerShell. При вызове этого командлета будет создана и настроена необходимая точка подключения службы и групповая политика.

Вы можете установить этот модуль, вызвав следующий экземпляр PowerShell:

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> Рекомендуется установить этот модуль на Windows Server, на котором выполняется Azure AD Connect.

Для создания необходимой точки подключения службы и групповой политики необходимо вызвать командлет [Initialize – секмгмсибирддевицеенроллмент](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) . При выполнении этой задачи вам потребуются учетные данные глобального администратора Microsoft 365 Бизнес Premium. Когда вы будете готовы создать ресурсы, вызовите следующую команду:

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

Первая команда устанавливает подключение к Microsoft Cloud и при появлении соответствующего запроса укажите учетные данные глобального администратора Microsoft 365 Business Premium.

## <a name="5-link-the-group-policy"></a>5. Связывание групповой политики

1. В консоли управления групповыми политиками щелкните правой кнопкой мыши расположение, в котором нужно связать политику, и выберите пункт *связать существующий объект групповой политики...* в контекстном меню.
2. Выберите политику, созданную на предыдущем шаге, а затем нажмите кнопку **ОК**.

## <a name="get-the-latest-administrative-templates"></a>Получение последних административных шаблонов

Если вы не видите политику **включения автоматической регистрации MDM с использованием учетных данных Azure AD по умолчанию**, возможно, у вас нет ADMX, установленного для Windows 10, версии 1803, версии 1809 или версии 1903. Чтобы устранить эту проблему, выполните указанные ниже действия (Примечание: последние версии MDM. ADMX совместимы с предыдущими).

1.  Загрузка: [Административные шаблоны (ADMX) для Windows 10 май 2019 обновление (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).
2.  Установите пакет на основном контроллере домена (PDC).
3.  Навигация в зависимости от версии папки: **C:\Program Files (x86) \Microsoft Group полици\виндовс 10 май 2019 обновление (1903) v3**.
4.  Переименуйте папку " **определения политик** " в указанном выше пути в **Папка PolicyDefinitions**.
5.  Скопируйте папку **Папка PolicyDefinitions** в **к:\виндовс\сисвол\домаин\полиЦиес**. 
    -   Если вы планируете использовать централизованное хранилище политик для всего домена, добавьте в него содержимое папка PolicyDefinitions.
6.  Чтобы политика была доступна, перезапустите основной контроллер домена. Эта процедура будет работать и для всех последующих версий.

На этом шаге вы увидите, что политика **включает автоматическую регистрацию MDM, используя доступные учетные данные Azure AD по умолчанию** .
