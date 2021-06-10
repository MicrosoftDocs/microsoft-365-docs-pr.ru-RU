---
title: Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)
description: Развертывание пакета конфигурации на устройстве виртуальной инфраструктуры настольных компьютеров (VDI), чтобы они были размещены в службе Microsoft Defender для конечных точек.
keywords: настройка устройства виртуальной инфраструктуры настольных компьютеров, vdi, управления устройствами, настройки Microsoft Defender для конечных точек, конечных точек
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
ms.topic: article
ms.date: 04/16/2020
ms.technology: mde
ms.openlocfilehash: d09967a18848365702f52f65a7f0624d2b2ae3d6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843214"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Устройства виртуальной инфраструктуры настольных компьютеров (VDI)
- Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configvdi-abovefoldlink)

## <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)

Defender for Endpoint поддерживает непродержку сеанса VDI в бортовом окантовке. 


При висячих VDIs могут возникнуть связанные проблемы. Для этого сценария характерны следующие задачи:

- Мгновенный ранний сеанс, который должен быть переназначелен в Defender для конечной точки до фактического обеспечения.
- Имя устройства обычно используется повторно для новых сеансов.

Устройства VDI могут отображаться на портале Defender для конечных точек так же:

- Одна запись для каждого устройства.

  > [!NOTE]
  > В этом случае одно и *то же* имя устройства необходимо настроить после создания сеанса, например с помощью неавтоматного файла ответа.

- Несколько записей для каждого устройства — по одной для каждого сеанса.

В следующих действиях вы сможете пройти через входные устройства VDI и выделить действия для одиночных и нескольких записей.

>[!WARNING]
> В средах с низкой конфигурацией ресурсов процедура загрузки VDI может замедлить загрузку датчика Defender для конечной точки. 


### <a name="for-windows-10-or-windows-server-2019"></a>Для Windows 10 или Windows Server 2019

1.  Откройте пакет конфигурации VDI .zip *(WindowsDefenderATPOnboardingPackage.zip), который* вы скачали из мастера бортового обслуживания. Вы также можете получить пакет из [Центр безопасности в Microsoft Defender:](https://securitycenter.windows.com/)

    1.  В области навигации выберите **Параметры**  >  **onboarding**.

    1. Выберите Windows 10 в качестве операционной системы.

    1.  В поле **методов развертывания** выберите **скрипты ВДИ для неустанных конечных точек.**

    1. Нажмите **кнопку Загрузка** пакета и сохраните .zip файл.

2. Скопируйте файлы из папки WindowsDefenderATPOnboardingPackage, извлеченной из файла .zip в образ под `golden/master` `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` путем. 

    1. Если вы не реализуете одну запись для каждого устройства, скопируйте WindowsDefenderATPOnboardingScript.cmd.

    1. Если вы реализуете одну запись для каждого устройства, скопируйте как Onboard-NonPersistentMachine.ps1, так и WindowsDefenderATPOnboardingScript.cmd.
    
    > [!NOTE]
    > Если папку не видно, она может `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` быть скрыта. Вам потребуется выбрать параметр Показать скрытые файлы **и папки** из File Explorer.

3. Откройте окно редактора локальной групповой политики и перейдите к запуску  >  **Windows Параметры**  >    >  **конфигурации компьютера.**

   > [!NOTE]
   > Политика группы домена также может использоваться для использования на бортовых устройствах СДВ.

4. В зависимости от метода, который вы хотите реализовать, выполните следующие действия:

   - Для одной записи для каждого устройства:
   
     Выберите **вкладку PowerShell Scripts,** а затем нажмите кнопку **Добавить** (Windows Explorer откроется непосредственно в пути, на котором вы скопировали сценарий для вкладки ранее). Перейдите к сценарию onboarding `Onboard-NonPersistentMachine.ps1` PowerShell. Нет необходимости указывать другой файл, так как он будет активируется автоматически.
   
   - Для нескольких записей для каждого устройства:
   
     Выберите **вкладку Scripts,** а затем нажмите кнопку **Добавить** (Windows Explorer откроется непосредственно в пути, где вы скопировали сценарий на борту ранее). Перейдите к сценарию висят `WindowsDefenderATPOnboardingScript.cmd` баш.

5. Проверьте свое решение:

   1. Создайте пул с одним устройством.
      
   1. Logon to device.
      
   1. Вход с устройства.

   1. Logon для устройства с другим пользователем.
      
   1. В зависимости от метода, который вы хотите реализовать, выполните следующие действия:
   
      - Для одной записи для каждого устройства: 
    
        Проверьте только одну запись в Центр безопасности в Microsoft Defender.

      - Для нескольких записей для каждого устройства: 
       
        Проверьте несколько записей в Центр безопасности в Microsoft Defender.

6. Щелкните **список Устройств** на области навигации.

7. Используйте функцию поиска, введите имя устройства и выберите **Устройство** в качестве типа поиска.


## <a name="for-downlevel-skus"></a>Для downlevel SKUs

> [!NOTE]
> Следующий реестр актуален только в том случае, если цель состоит в достижении "Единой записи для каждого устройства".

1. Установите значение реестра:

    ```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    или с помощью командной строки:

    ```console
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. Следуйте [за процессом бортовой обработки сервера.](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016) 



## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>Обновление нестандартных изображений виртуальной инфраструктуры настольных компьютеров (VDI)
В качестве наилучшей практики рекомендуется использовать средства автономного обслуживания для исправления золотых и мастер-изображений.<br>
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

1. После загрузки мастер-изображения для онлайн-обслуживания или исправления запустите сценарий offboarding, чтобы отключить датчик Defender для конечной точки. Дополнительные сведения см. в [таблице Offboard devices с помощью локального скрипта.](configure-endpoints-script.md#offboard-devices-using-a-local-script)

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

## <a name="related-topics"></a>Статьи по теме
- [Onboard Windows 10 с помощью групповой политики](configure-endpoints-gp.md)
- [На борту Windows 10 устройства с Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Подключение устройств Windows 10 с помощью средств управления мобильными устройствами](configure-endpoints-mdm.md)
- [Подключение устройств Windows 10 с помощью локального сценария](configure-endpoints-script.md)
- [Устранение неполадок в Microsoft Defender для проблем с бортовой точкой конечной точки](troubleshoot-onboarding.md)
