---
title: Поддерживаемые типы файлов при расследовании данных (Предварительная версия)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 055104a5b7f60fe54b421e7236143aa9af08b57f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601436"
---
# <a name="supported-file-types-in-data-investigations-preview"></a>Поддерживаемые типы файлов при расследовании данных (Предварительная версия)

Расследования данных (Предварительная версия) поддерживает многие типы файлов несколькими различными способами, которые описаны в следующей таблице. Этот список не завершен, и мы добавим новые типы файлов, когда мы продолжим проверочное тестирование. В таблице также указано, можно ли просматривать типы файлов в доступных средствах просмотра, когда вы просматриваете доказательства.

| Тип MIME | Класс File | Встроенное средство просмотра | Средство просмотра текста | Средство просмотра примечаний | Извлечение контейнера | Расширения |
| :- | :- | :- | :- | :- | :- | :- |
| application/msword | Документ | Да | Да | Да | Нет | . doc;. dat |
| application/pdf | Документ | Да | Да | Да | Нет | PDF |
| приложение/RTF | Документ | Да | Да | Да | Нет | RTF;. гостей |
| Application/ВНД. МС-ексцел | Документ | Да | Да | Да | Нет | XLS; dat |
| Application/ВНД. МС-ексцел. sheet. binary. макроенаблед. 12 | Производительность и формат открытого документа | Да | Да | Нет | Нет | . xlsb |
| Application/ВНД. МС-ексцел. sheet. макроенаблед. 12 | Документ | Да | Да | Да | Нет | . xlsm |
| Application/ВНД. МС-ексцел. Template. макроенаблед. 12 | Производительность и формат открытого документа | Нет | Да | Нет | Нет | . xltm |
| Application/ВНД. МС-Аутлук | Производительность труда | Нет | Нет | Нет | Нет | . MSG |
| Application/ВНД. МС-Аутлук-ПСТ | Производительность и совместная работа | Нет | Нет | Нет | Да | PST-файл |
| Application/ВНД. МС-поверпоинт | Документ | Да | Да | Да | Нет | PPT; PPS;. Pot |
| Application/ВНД. МС-Ворд. Document. макроенаблед. 12 | Документ | Да | Да | Да | Нет | DOCM |
| Application/ВНД. МС-Ворд. Template. макроенаблед. 12 | Документ | Да | Да | Да | Нет | . dotm |
| Application/ВНД. Oasis. OpenDocument. Text | Документ | Да | Да | Да | Нет | Detection  |
| application/vnd.openxmlformats-officedocument.presentationml.presentation | Документ | Да | Да | Да | Нет | PPTX |
| Application/ВНД. опенксмлформатс-оффицедокумент. PresentationML. показ слайдов | Производительность и формат открытого документа | Да | Да | Да | Нет | . ppsx |
| Application/ВНД. опенксмлформатс-оффицедокумент. PresentationML. Template | Документ | Да | Да | Да | Нет | . potx |
| application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | Документ | Да | Да | Да | Нет | XLSX |
| Application/ВНД. опенксмлформатс-оффицедокумент. SpreadsheetML. Template | Документ | Да | Да | Да | Нет | . xltx |
| application/vnd.openxmlformats-officedocument.wordprocessingml.document | Документ | Да | Да | Да | Нет | DOCX |
| Application/ВНД. опенксмлформатс-оффицедокумент. WordprocessingML. Template | Документ | Да | Да | Да | Нет | . dotx |
| Application/ВНД. Visio | Документ | Да | Да | Да | Нет | . VSD |
| приложение/x-7z-сжатый | Архив/контейнер | Нет | Нет | Нет | Да | .7z |
| приложение/XHTML + XML | Документ | Да | Да | Да | Нет | . XHTML |
| Application/XML | Документ | Да | Да | Да | Нет | . XML |
| приложение/x-Msaccess | Документ | Да | Да | Да | Нет | . mdb |
| Application/x-мспублишер | Документ | Да | Да | Да | Нет | . pub |
| приложение/x-сжатый архив RAR | Архив/контейнер | Нет | Нет | Нет | Да | . rar |
| приложение/ZIP-индекс | Архив/контейнер | Нет | Нет | Нет | Да | ZIP |
| Image/BMP | Изображение | Да | Да | Да | Нет | BMP |
| Image/EMF | Изображение | Да | Да | Да | Нет | EMF |
| image/gif | Документ | Да | Да | Да | Нет | GIF |
| image/jpeg | Изображение | Да | Да | Да | Нет | JPG;. JPEG;. dat;. жпгт |
| image/png | Изображение | Да | Да | Да | Нет | PNG |
| Image/TIFF | Изображение | Да | Да | Да | Нет | TIF |
| Image/ВНД. DWG | Документ | Да | Да | Да | Нет | . DWG;. DXF |
| Image/WMF | Документ | Да | Да | Да | Нет | . WMF |
| message/rfc822 | Производительность и совместная работа | Нет | Нет | Нет | Нет | EML |
| Text/CSV | Документ | Да | Да | Да | Нет | CSV-файл |
| Text/HTML | Документ | Да | Да | Да | Нет | . HTML;. shtml; htm |
| text/plain | Документ | Да | Да | Да | Нет | . txt;. CSS;. Con;. pl;. csv;. dat |
| текст/vCard-Contact | Документ | Да | Да | Да | Нет | . vcf |
||||||||
