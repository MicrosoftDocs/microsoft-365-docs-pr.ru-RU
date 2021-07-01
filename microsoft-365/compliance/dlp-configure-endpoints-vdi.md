---
title: Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Развертывание пакета конфигурации на устройстве виртуальной инфраструктуры настольных компьютеров (VDI), чтобы они были Microsoft 365 службу предотвращения потери данных конечной точки.
ms.openlocfilehash: 64d9bfed3d1d5600b5843c697e894577f83527fe
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226879"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)

**Область применения:**
- [Microsoft 365 Предотвращение потери конечных данных (DLP)](./endpoint-dlp-learn-about.md)

- Устройства виртуальной инфраструктуры настольных компьютеров (VDI)

> [!WARNING]
> Microsoft 365 Поддержка предотвращения потери данных конечной точки для Windows Virtual Desktop поддерживает сценарии одного сеанса. Сценарии нескольких сеансов на Windows в настоящее время не поддерживаются.

## <a name="onboard-vdi-devices"></a>На борту устройств VDI

Microsoft 365 Предотвращение потери данных конечной точки поддерживает непродержку сеанса VDI на борту.

> [!NOTE]
> Чтобы на борту нестойких сеансов VDI устройства VDI должны быть Windows 10 1809 или выше.

При висячих VDIs могут возникнуть связанные проблемы. Для этого сценария характерны следующие задачи:

- Мгновенный ранний сеанс, который необходимо использовать для Microsoft 365 предотвращения потери данных конечной точки перед фактической подготовкаю.
- Имя устройства обычно используется повторно для новых сеансов.

Устройства VDI могут отображаться в центре Microsoft 365 соответствия требованиям как таковые:

- Одна запись для каждого устройства.
Обратите внимание, что  в этом случае при создания сеанса необходимо настроить одно и то же имя устройства, например с помощью неавтоматного файла ответа.
- Несколько записей для каждого устройства — по одной для каждого сеанса.

В следующих действиях вы сможете пройти через входные устройства VDI и выделить действия для одиночных и нескольких записей.

> [!WARNING]
> В средах с низкими конфигурациями ресурсов процедура загрузки VDI может замедлить Microsoft 365 предотвращения потери данных конечной точки.

1. Откройте пакет конфигурации VDI .zip *(DeviceCompliancePackage.zip), который* вы скачали из мастера бортового обслуживания.

2. В области навигации выберите **Параметры**  >  **бортового**  >  устройства.

3. В поле **методов развертывания** выберите **скрипты ВДИ для неустанных конечных точек.**

4. Нажмите **кнопку Загрузка** пакета и сохраните .zip файл.

5. Скопируйте файлы из папки DeviceCompliancePackage, извлеченной из файла .zip в образ `golden/master` под пути `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` .

6. Если вы не реализуете одну запись для каждого устройства, скопируйте DeviceComplianceOnboardingScript.cmd.

7. Если вы реализуете одну запись для каждого устройства, скопируйте как Onboard-NonPersistentMachine.ps1, так и deviceComplianceOnboardingScript.cmd.

    > [!NOTE]
    > Если папку не видно, она может `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` быть скрыта. Вам потребуется выбрать параметр Показать скрытые файлы **и папки** из File Explorer.

8. Откройте окно редактора локальной групповой политики и перейдите к запуску  >  **Windows Параметры**  >    >  **конфигурации компьютера.**

   > [!NOTE]
   > Политика группы домена также может использоваться для использования на бортовых устройствах СДВ.

9. В зависимости от метода, который вы хотите реализовать, выполните следующие действия:

   **Для одной записи для каждого устройства**

   Выберите **вкладку PowerShell Scripts,** а затем нажмите кнопку **Добавить** (Windows Explorer откроется непосредственно в пути, на котором вы скопировали сценарий для вкладки ранее). Перейдите к сценарию onboarding `Onboard-NonPersistentMachine.ps1` PowerShell.

   **Для нескольких записей для каждого устройства:**

   Выберите **вкладку Scripts,** а затем нажмите кнопку **Добавить** (Windows Explorer откроется непосредственно в пути, где вы скопировали сценарий на борту ранее). Перейдите к сценарию висят `DeviceComplianceOnboardingScript.cmd` баш.

10. Проверьте свое решение:
    1. Создайте пул с одним устройством.
    1. Logon to device.
    1. Вход с устройства.
    1. Logon для устройства с другим пользователем.
    1. **Для одной записи для каждого устройства:** проверьте только одну запись в Центр безопасности в Microsoft Defender.
       **Для нескольких записей для каждого устройства:** Проверьте несколько записей в Центр безопасности в Microsoft Defender.

11. Щелкните **список Устройств** на области навигации.

12. Используйте функцию поиска, введите имя устройства и выберите **Устройство** в качестве типа поиска.

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>Обновление нестандартных изображений виртуальной инфраструктуры настольных компьютеров (VDI)

В качестве наилучшей практики рекомендуется использовать средства автономного обслуживания для исправления золотых и мастер-изображений.

Например, вы можете использовать ниже команд для установки обновления, пока изображение остается в автономном режиме:

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing"
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

Дополнительные сведения о командах DISM и автономном обслуживании см. в статьях ниже:

- [Изменение Windows с помощью DISM](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [Параметры управления изображениями DISM Command-Line](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [Уменьшение размера магазина компонентов в автономном Windows изображении](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

Если автономное обслуживание не является жизнеспособным вариантом для среды нестойких VDI, необходимо предпринять следующие действия для обеспечения согласованности и безопасности датчиков:

1. После загрузки мастер-изображения для онлайн-обслуживания или исправления запустите сценарий offboarding, чтобы отключить датчик предотвращения потери Microsoft 365 конечных точек. Дополнительные сведения см. в [таблице Offboard devices с помощью локального скрипта.](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)

2. Убедитесь, что датчик остановлен, запуская команду ниже в окне CMD:

   ```console
   sc query sense
   ```

3. Обслуживание изображения по мере необходимости.

4. Запустите ниже команд с помощью PsExec.exe (которые можно скачать для очистки содержимого кибер-папки, которые датчик, возможно, https://download.sysinternals.com/files/PSTools.zip) накопил после загрузки:

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. Повторно запечатыть золотое/мастер-изображение, как обычно.

## <a name="related-topics"></a>Похожие темы

- [Onboard Windows 10 с помощью групповой политики](dlp-configure-endpoints-gp.md)
- [На борту Windows 10 устройства с Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Подключение устройств Windows 10 с помощью средств управления мобильными устройствами](dlp-configure-endpoints-mdm.md)
- [Подключение устройств Windows 10 с помощью локального сценария](dlp-configure-endpoints-script.md)
- [Устранение неполадок с бортовой защитой расширенных угроз Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
