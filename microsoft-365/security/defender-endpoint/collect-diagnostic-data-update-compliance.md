---
title: Сбор диагностических данных для обновления соответствия требованиям и Защитник Windows антивируса Microsoft Defender
description: Используйте средство для сбора данных для устранения неполадок с обновлением соответствия требованиям при использовании добавления в добавленную в Microsoft Defender антивирусную оценку
keywords: устранение неполадок, ошибка, исправление, обновление соответствия требованиям, oms, монитор, отчет, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f2b3060d7f0d9daf0f923c674f2fe45ba976fdfc
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764739"
---
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-av-assessment"></a>Сбор диагностических данных об обновлении соответствия требованиям для оценки av Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

В этой статье описывается, как собирать диагностические данные, которые могут использоваться группами поддержки Майкрософт и инженерными группами для устранения проблем, с которыми вы можете столкнуться при использовании раздела Оценки автозаполнения защитника Майкрософт в надстройки "Соответствие требованиям обновления".

Перед началом этого процесса убедитесь, что вы прочитали отчеты об устранении неполадок антивируса [Microsoft Defender,](troubleshoot-reporting.md)выполнили все необходимые условия и предприняли любые другие предложенные действия по устранению неполадок.

По крайней мере на двух устройствах, которые не сообщают или не отображаются в соответствии с обновлением, получите диагностический файл .cab, предприняв следующие действия:

1. Откройте версию командной подсказки на уровне администратора следующим образом:
        
    а. Откройте меню **Пуск.**

    б. Введите **cmd**. Щелкните правой кнопкой мыши **командный запрос** и нажмите **кнопку Выполнить в качестве администратора.**

    в. Ввод учетных данных администратора или утверждение запроса.
        
2. Перейдите к Защитник Windows каталогу. По умолчанию это значение равно `C:\Program Files\Windows Defender`.

3. Введите следующую команду и нажмите **кнопку Ввод**
        
    ```Dos
    mpcmdrun -getfiles
    ```
    
4. Создается файл .cab, содержащий различные диагностические журналы. Расположение файла будет указано в выходе в командной подсказке. По умолчанию расположение `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` является .

5. Скопируйте эти файлы .cab в расположение, к нему можно получить доступ с помощью службы поддержки Майкрософт. Примером может быть защищенная паролем папка OneDrive, которую вы можете поделиться с нами.

6. Отправьте сообщение электронной почты <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">с</a>помощью шаблона поддержки обновления и заполните шаблон следующими сведениями:
  
    ```
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
    
    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a>См. также

- [Устранение неполадок Защитник Windows антивирусной отчетности Microsoft Defender](troubleshoot-reporting.md)