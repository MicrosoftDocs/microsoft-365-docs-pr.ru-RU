---
title: Включить доступ к Windows 10 с помощью Microsoft 365 для бизнеса
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
description: Узнайте, как Microsoft 365 защитить локальные устройства с Windows 10 active-Directory.
ms.openlocfilehash: 9cc7ca01cec667465e9114083fecdc56ef4e7ce7
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393386"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Включить устройства с Windows 10 с помощью Microsoft 365 бизнес премиум

Если организация использует Windows Server Active Directory локально, вы можете настроить Microsoft 365 бизнес премиум для защиты Windows 10 устройств, сохраняя при этом доступ к локальным ресурсам, которые требуют локальной проверки подлинности.
Чтобы настроить эту защиту, можно реализовать устройства **hybrid Azure AD.** Эти устройства присоединяются как к локальному Active Directory, так и к Azure Active Directory.

## <a name="watch-configure-hybrid-azure-active-directory-join"></a>Watch: Настройка гибридной Azure Active Directory присоединиться

В этом видео описываются действия по настройкам этого сценария для наиболее распространенных сценариев, которые также описаны в последующих действиях.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  
## <a name="before-you-begin"></a>Прежде чем начать

- Синхронизация пользователей с Azure AD с azure AD Подключение.
- Выполните синхронизацию Подключение Azure AD.
- Убедитесь, что все синхронизированные пользователи домена имеют лицензии на Microsoft 365 бизнес премиум.

См. [в этой записи Синхронизация](manage-domain-users.md) действий пользователей домена с Microsoft.

## <a name="1-verify-mdm-authority-in-intune"></a>1. Проверка управления MDM в Intune

Перейдите [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) и на странице Microsoft Intune, выберите регистрацию **устройства,** а затем на странице **Обзор** убедитесь, что **полномочия MDM** **intune**.

- Если **полномочия MDM нет,** нажмите кнопку **MDM,** чтобы настроить его **на Intune**. 
- Если полномочия **MDM** **Microsoft Office 365,** перейдите на устройства Для регистрации устройств и используйте диалоговое окно Add MDM authority справа для добавления полномочий  >   **Intune MDM** (диалоговое окно **Add MDM Authority** доступно только в том случае, если для управления **MDM** установлено Microsoft Office 365). 

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Проверка включения Azure AD для присоединения к компьютерам

- Перейдите в центр администрирования и выберите Azure Active Directory (выберите Показать все, если Azure Active Directory не отображается) в <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> списке **центров администрирования.**  
- В центре **Azure Active Directory администрирования** перейдите **в Azure Active Directory,** выберите **параметры Устройств** и **устройств.**
- Проверка **того, что пользователи могут присоединяться к устройствам в Azure AD,** включена 
    1. Чтобы включить всех пользователей, установите **все**.
    2. Чтобы включить определенных пользователей, **установите выбранный,** чтобы включить определенную группу пользователей.
        - Добавьте нужных пользователей домена, синхронизированных в Azure AD, в [группу безопасности.](../admin/create-groups/create-groups.md)
        - Выберите **выберите группы,** чтобы включить область пользовательского интерфейса MDM для этой группы безопасности.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. Проверка включения Azure AD для MDM

- Перейдите в центр администрирования и выберите <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> выберите **endpoint Managemen** t (выберите **Показать** все, **если** Endpoint Manager не отображается)
- В центре **Microsoft Endpoint Manager администрирования** перейдите к **устройствам** Windows  >    >  **Windows**  >  **регистрации.**
- Проверка включенной пользовательской области MDM.

    1. Чтобы зарегистрироваться на всех  компьютерах, установите для всех автоматически зачислить все пользовательские компьютеры, которые присоединяются к Azure AD и новым компьютерам, когда пользователи добавляют учетную запись в Windows.
    2. Установите для **некоторых** для регистрации компьютеров определенной группы пользователей.
        -  Добавьте нужных пользователей домена, синхронизированных в Azure AD, в [группу безопасности.](../admin/create-groups/create-groups.md)
        -  Выберите **выберите группы,** чтобы включить область пользовательского интерфейса MDM для этой группы безопасности.

## <a name="4-create-the-required-resources"></a>4. Создание необходимых ресурсов 

Выполнение необходимых задач по настройке гибридного присоединяния [Azure AD](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) было упрощено с помощью командлета [Initialize-SecMgmtHybirdDeviceEnrollment,](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) найденного в модуле [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell. При вызове этого комлета создается и настраивается необходимая точка подключения к службе и политика группы.

Этот модуль можно установить, созовав следующее из экземпляра PowerShell:

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> Рекомендуется установить этот модуль на сервере Windows Azure AD Подключение.

Чтобы создать требуемую точку подключения к службе и групповую политику, необходимо вызвать групповую группу [Initialize-SecMgmtHybirdDeviceEnrollment.](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) При выполнении этой задачи Microsoft 365 бизнес премиум глобальные учетные данные администратора. Когда вы будете готовы создать ресурсы, привяйте следующие ссылки:

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

Первая команда установит подключение к облаку Майкрософт, а когда вам будет предложено, укажите Microsoft 365 бизнес премиум учетные данные администратора.

## <a name="5-link-the-group-policy"></a>5. Ссылка групповой политики

1. В консоли управления групповой политикой (GPMC) щелкните правой кнопкой мыши по расположению, где необходимо связать политику, и выберите Ссылку существующего *GPO...* из контекстного меню.
2. Выберите политику, созданную на вышеуказанной шаге, а затем нажмите **кнопку ОК**.

## <a name="get-the-latest-administrative-templates"></a>Получить последние административные шаблоны

Если вы не видите политику Включить автоматическую регистрацию **MDM** с помощью учетных данных Azure AD по умолчанию, это может быть из-за того, что у вас нет установки ADMX для Windows 10 версии 1803 или более поздней версии. Чтобы устранить проблему, выполните следующие действия (Примечание: последняя версия MDM.admx совместима с обратной совместимость):

1. Загрузка: [Административные шаблоны (.admx) для Windows 10 2020 обновления (20H2).](https://www.microsoft.com/download/102157)
2. Установите пакет на контроллер домена.
3. Перейдите в зависимости от версии административных шаблонов в папку: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 октябрь 2020 г. Обновление (20H2)**.
4. Переименовать **папку Определения политики** в вышеуказанном пути в **PolicyDefinitions**.
5. Скопируйте **папку PolicyDefinitions** в свою долю SYSVOL по умолчанию, расположенную в **C:\Windows\SYSVOL\domain\Policies**.
   - Если вы планируете использовать центральный магазин политик для всего домена, добавьте туда содержимое PolicyDefinitions.
6. Если у вас есть несколько контроллеров домена, подождите, пока SYSVOL будет реплицировать доступные политики. Эта процедура будет работать и для любой будущей версии административных шаблонов.

На этом этапе вы сможете увидеть политику Включить автоматическую регистрацию **MDM** с помощью доступных учетных данных Azure AD по умолчанию.

## <a name="related-content"></a>См. также:

[Синхронизация пользователей домена с Microsoft 365](manage-domain-users.md) (статья)\
[Создание группы в центре администрирования](../admin/create-groups/create-groups.md) (статья)\
[Руководство. Настройка гибридного Azure Active Directory для управляемых доменов](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) (статья)