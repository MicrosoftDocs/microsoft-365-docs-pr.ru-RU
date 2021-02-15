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
description: Развернете пакет конфигурации на устройстве инфраструктуры виртуальных рабочих стола (VDI), чтобы они были размещены в службе защиты от потери данных Конечной точки Microsoft 365.
ms.openlocfilehash: ce5ad0ba6af3e18a6f6c53e1860fc47a77c38770
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769450"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)

**Область применения:**
- [Предотвращение потери данных конечной точки Microsoft 365 (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)

- Устройства инфраструктуры виртуальных рабочих стола (VDI)

>[!WARNING]
> Поддержка защиты от потери данных конечной точки Microsoft 365 для виртуального рабочего стола Windows поддерживает сценарии с одним сеансом. Сценарии с несколькими сеансами на виртуальном рабочем столе Windows в настоящее время не поддерживаются.

## <a name="onboard-vdi-devices"></a>Ветвь устройств VDI

Microsoft 365 Endpoint data loss prevention supports non-persistent VDI session onboarding. 

>[!Note]
>Чтобы взламыть несохраняемые сеансы VDI, устройства VDI должны быть в Windows 10 1809 или выше.

При подборе VDIs могут возникнуть проблемы. В этом сценарии типичные проблемы:

- Мгновенное раннее подмавка кратковременных сеансов, которые должны быть переназначения в службу защиты от потери данных конечной точки Microsoft 365 перед фактической подготовкаю.
- Имя устройства обычно используется повторно для новых сеансов.

Устройства VDI могут отображаться в Центре соответствия требованиям Microsoft 365 как:

- Одна запись для каждого устройства.  
Обратите внимание, что  в этом случае при создания сеанса необходимо настроить одно и то же имя устройства, например с использованием файла ответов, не от имени которого установлено.
- Несколько записей для каждого устройства — по одной для каждого сеанса.

Далее приводится руководство по входоубору устройств VDI и выделены этапы для одной и нескольких записей.

>[!WARNING]
> В средах с низкой конфигурацией ресурсов процедура загрузки VDI может замедлить веху защиты от потери данных в Конечной точке Microsoft 365. 

1.  Откройте ZIP-файл пакета конфигурации ** VDI (DeviceCompliancePackage.zip), который вы скачали из мастера подбора службы.

2.  В области навигации выберите **"Параметры** устройства для входящего  >  в  >  **нее".**

3. В поле **"Метод развертывания"** выберите сценарии взбора VDI для **постоянных конечных точек.**

5. Щелкните **"Скачать пакет"** и сохраните ZIP-файл.

6. Скопируйте файлы из папки DeviceCompliancePackage, извлеченной из ZIP-файла, в изображение `golden/master` по `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` пути. 

7. Если вы не реализуете одну запись для каждого устройства, скопируйте DeviceComplianceOnboardingScript.cmd.

8. Если вы реализуете одну запись для каждого устройства, скопируйте и Onboard-NonPersistentMachine.ps1 DeviceComplianceOnboardingScript.cmd.
    
    > [!NOTE]
    > Если вы не видите папку, она может `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` быть скрыта. Необходимо выбрать параметр "Показать скрытые **файлы и папки"** в проводнике.

9. Откройте окно редактора локальных групповых политик и перейдите к скриптам запуска параметров  >  **конфигурации**  >    >  компьютера.

   > [!NOTE]
   > Групповая политика домена также может использоваться для въехающих несохраняющихся устройств VDI.

4. В зависимости от метода, который вы хотите реализовать, выполните следующие действия.

   **Для одной записи для каждого устройства**
   
   Откройте **вкладку "Сценарии PowerShell",** а затем нажмите кнопку **"Добавить"** (проводник Windows откроется прямо по пути, в который ранее был скопирован сценарий вкладки). Перейдите к сценарию входить в `Onboard-NonPersistentMachine.ps1` PowerShell.
   
   **Для нескольких записей для каждого устройства:**
   
   Перейдите **на вкладку** "Сценарии" и нажмите кнопку **"Добавить"** (проводник Windows откроется непосредственно по пути, куда ранее был скопирован сценарий вкладки). Перейдите к сценарию onboarding `DeviceComplianceOnboardingScript.cmd` Bash.

5. Протестировать решение:

   1. Создайте пул с одним устройством.
      
   1. Во время logon на устройстве.
      
   1. Выйдите из устройства.

   1. Во время этого действия во время устройства вы сможете работать с другим пользователем.
      
   1. **Для одной записи для каждого устройства:** проверьте только одну запись в Центре безопасности Microsoft Defender.<br>
      **Для нескольких записей для каждого устройства:** проверьте несколько записей в Центре безопасности Microsoft Defender.

6. Щелкните **список "Устройства"** в области навигации.

7. Используйте функцию поиска, введите имя устройства и выберите **"Устройство"** в качестве типа поиска.

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>Обновление образов инфраструктуры виртуальных рабочих стола (VDI) без сохраняемого сохраняемого рабочего стола
Рекомендуется использовать средства автономного обслуживания для исправления эталовых и эталовых образов.<br>
Например, вы можете использовать команды ниже, чтобы установить обновление, пока образ остается в автономном режиме:

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

Дополнительные сведения о командах DISM и автономном обслуживании см. в статьях ниже:
- [Изменение образа Windows с помощью DISM](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [Параметры управления Command-Line DISM](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [Уменьшение размера хранения компонентов в автономном образе Windows](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

Если автономное обслуживание не является вариантом для несохраняемой среды VDI, необходимо предпринять следующие действия для обеспечения согласованности и безопасности датчиков:

1. После загрузки образа для онлайн-обслуживания или исправления запустите сценарий отключения, чтобы отключить датчик защиты от потери данных конечной точки Microsoft 365. Дополнительные сведения см. в [подключеных устройствах с помощью локального сценария.](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)

2. Убедитесь, что датчик остановлен, выдав приведенную ниже команду в окне CMD:

   ```console
   sc query sense
   ```

3. Обслуживание изображения по мере необходимости.

4. Запустите команды ниже с помощью PsExec.exe (которые можно скачать для очистки содержимого киберпамяти, которое может быть скоплено датчиком после https://download.sysinternals.com/files/PSTools.zip) загрузки:

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. Повторно запечатывка золотого/основному изображению, как обычно.

## <a name="related-topics"></a>Связанные статьи
- [Ветвь устройств с Windows 10 с помощью групповой политики](dlp-configure-endpoints-gp.md)
- [Ветвь устройств с Windows 10 с помощью Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Подключение устройств Windows 10 с помощью средств управления мобильными устройствами](dlp-configure-endpoints-mdm.md)
- [Подключение устройств Windows 10 с помощью локального сценария](dlp-configure-endpoints-script.md)
- [Устранение неполадок с подсетями Advanced Threat Protection в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
