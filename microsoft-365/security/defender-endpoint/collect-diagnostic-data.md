---
title: Сбор диагностических данных антивируса Microsoft Defender
description: Используйте средство для сбора данных для устранения неполадок антивируса Microsoft Defender
keywords: устранение неполадок, ошибка, исправление, обновление соответствия требованиям, oms, монитор, отчет, Microsoft Defender av, объект групповой политики, параметр, диагностические данные
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/29/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3b7c07bace86a2a4651e5c951c6e0b7d954f0982
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691094"
---
# <a name="collect-microsoft-defender-av-diagnostic-data"></a>Сбор диагностических данных Microsoft Defender AV

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

В этой статье описывается сбор диагностических данных, которые могут использоваться группами поддержки Майкрософт и инженерными группами для устранения неполадок, с которыми вы можете столкнуться при использовании AV Microsoft Defender.

> [!NOTE]
> В рамках процесса расследования или ответа можно собрать пакет исследований с устройства. Вот как: [сбор пакета исследований с устройств.](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)

По крайней мере на двух устройствах, столкнующихся с одной и той же проблемой, получите диагностический файл .cab, предприняв следующие действия:

1. Откройте версию командной подсказки на уровне администратора следующим образом:

    а. Откройте меню **Пуск.**

    б. Введите **cmd**. Щелкните правой кнопкой мыши **командный запрос** и нажмите **кнопку Выполнить в качестве администратора.**

    в. Ввод учетных данных администратора или утверждение запроса.

2. Перейдите к каталогу Microsoft Defender. По умолчанию это значение равно `C:\Program Files\Windows Defender`.

> [!NOTE]
> Если вы работаете с [обновленной версией платформы Защитника Майкрософт,](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)запустите ее в `MpCmdRun` следующем расположении: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` .

3. Введите следующую команду и нажмите **кнопку Ввод**  

    ```Dos
    mpcmdrun.exe -GetFiles
    ```
  
4. Создается файл .cab, содержащий различные диагностические журналы. Расположение файла будет указано в выходе в командной подсказке. По умолчанию расположение `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab` является .

> [!NOTE]
> Чтобы перенаправить файл кабины на другой путь или долю UNC, используйте следующую команду: `mpcmdrun.exe -GetFiles -SupportLogLocation <path>`  <br/>Дополнительные сведения см. в [раздел Перенаправление диагностических данных в раздел UNC.](#redirect-diagnostic-data-to-a-unc-share)

5. Скопируйте эти файлы .cab в расположение, к нему можно получить доступ с помощью службы поддержки Майкрософт. Примером может быть защищенная паролем папка OneDrive, которую вы можете поделиться с нами.

> [!NOTE]
>Если у вас возникла проблема с соответствием требованиям обновления, отправьте сообщение электронной почты с помощью шаблона поддержки обновления и заполните шаблон следующими сведениями: <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a"></a>
>```
> I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
> I have provided at least 2 support .cab files at the following location:  
> <accessible share, including access details such as password>
>
>    My OMS workspace ID is:
>
>    Please contact me at:

## <a name="redirect-diagnostic-data-to-a-unc-share"></a>Перенаправление диагностических данных на долю UNC
Для сбора диагностических данных в центральном репозитории можно указать параметр SupportLogLocation.

```Dos
mpcmdrun.exe -GetFiles -SupportLogLocation <path>
```

Копирует диагностические данные в указанный путь. Если путь не указан, диагностические данные будут скопированы в расположение, указанное в конфигурации расположения журнала поддержки.

Когда используется параметр SupportLogLocation, в пути назначения будет создана структура папок, как по следующим параметрам:

```Dos
<path>\<MMDD>\MpSupport-<hostname>-<HHMM>.cab
```

| поле  | Описание   |
|:----|:----|
| path | Путь, указанный в командной строке или извлеченный из конфигурации
| MMDD | Месяц и день сбора диагностических данных (например, 0530)
| имя хозяйского имени | Имя хозяина устройства, на котором собирались диагностические данные
| HHMM | Часы и минуты при сборе диагностических данных (например, 1422)

> [!NOTE]
> При использовании файла убедитесь, что учетная запись, используемая для сбора диагностического пакета, имеет доступ к файлу записи.  

## <a name="specify-location-where-diagnostic-data-is-created"></a>Укажите расположение, где создаются диагностические данные

Вы также можете указать, где будет создан диагностический файл .cab с помощью объекта групповой политики (GPO). 

1. Откройте редактор локальной групповой политики и найдите GPO SupportLogLocation по: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\SupportLogLocation`
   
1. Выберите **Определение пути каталога для копирования файлов журнала поддержки.**

    ![Снимок экрана редактора локальной групповой политики](images/GPO1-SupportLogLocationDefender.png)  
        
     ![Снимок экрана определения пути для параметра файлов журналов](images/GPO2-SupportLogLocationGPPage.png)  
3. В редакторе политики выберите **Включено**.
       
4. Укажите путь каталога, в котором необходимо скопировать файлы журнала поддержки в поле **Параметры.**
     ![Снимок экрана настраиваемого параметра путь к каталогам с включенной поддержкой](images/GPO3-SupportLogLocationGPPageEnabledExample.png) 
5. Выберите **ОК** или **Применить**.

## <a name="see-also"></a>См. также

- [Устранение неполадок в антивирусной отчетности Microsoft Defender](troubleshoot-reporting.md)