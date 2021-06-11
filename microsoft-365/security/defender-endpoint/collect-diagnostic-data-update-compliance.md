---
title: Сбор диагностических данных для обновления соответствия требованиям и Защитник Windows антивирусная программа в Microsoft Defender
description: Используйте средство для сбора данных для устранения неполадок с обновлением соответствия требованиям при использовании добавления антивирусная программа в Microsoft Defender оценки
keywords: устранение неполадок, ошибка, исправление, обновление соответствия требованиям, oms, монитор, отчет, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 9fbe2b624bec6bbe17bcf6bc8d3f842ba1e43ad7
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903736"
---
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-antivirus-assessment"></a>Сбор диагностических данных о соответствии требованиям для антивирусная программа в Microsoft Defender оценки


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

В этой статье описывается сбор диагностических данных, которые могут использоваться группами поддержки Майкрософт и инженерными группами для устранения проблем, с которыми вы можете столкнуться при использовании раздела антивирусная программа в Microsoft Defender оценки в надстройки Update Compliance.

Перед попыткой этого процесса убедитесь, что вы читали отчеты антивирусная программа в Microsoft Defender устранения неполадок, [](troubleshoot-reporting.md)выполнили все необходимые условия и предприняли любые другие предложенные действия по устранению неполадок.

По крайней мере на двух устройствах, которые не сообщают или не отображаются в соответствии с обновлением, .cab диагностический файл, предприняв следующие действия:

1. Откройте версию командной подсказки на уровне администратора следующим образом:
        
    а. Откройте меню **Пуск.**

    б. Введите **cmd**. Щелкните правой кнопкой мыши **командную подсказку** и выберите **Выполнить в качестве администратора.**

    в. Укажите учетные данные администратора или одобрить запрос.
        
2. Перейдите к Защитник Windows каталогу. По умолчанию это значение равно `C:\Program Files\Windows Defender`.

3. Введите следующую команду и нажмите **кнопку Ввод**
        
    ```Dos
    mpcmdrun -getfiles
    ```
    
4. Будет .cab файл, содержащий различные диагностические журналы. Расположение файла будет указано в выходе в командной подсказке. По умолчанию расположение `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` является .

5. Скопируйте .cab файлы в расположение, к нему можно получить доступ с помощью службы поддержки Майкрософт. Примером может быть защищенная паролем папка OneDrive которую вы можете поделиться с нами.

6. Отправьте сообщение электронной почты <a href="mailto:ucsupport@microsoft.com?subject=MDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">с</a>помощью шаблона поддержки обновления и заполните шаблон следующими сведениями:
  
    ```
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
    
    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a>См. также

- [Устранение Защитник Windows антивирусная программа в Microsoft Defender отчетов](troubleshoot-reporting.md)