---
title: Поддерживаемые типы файлов в Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Список поддерживаемых типов файлов в Microsoft 365 Advanced eDiscovery, включая типы файлов изображений, поддерживаемые функцией OCR в Advanced eDiscovery.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a552e6cf0d32e77c2a21bc959ae313e6fc53d4eb
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "47817132"
---
# <a name="supported-file-types-in-advanced-ediscovery"></a>Поддерживаемые типы файлов в Advanced eDiscovery

Advanced eDiscovery поддерживает множество типов файлов на различных уровнях. Типы файлов поддержки описаны в следующих таблицах этой статьи. Этот список еще не завершен, и мы добавим новые типы файлов по мере продолжения проверки. В этих таблицах указано, поддерживается ли тип файла для извлечения текста (а также для извлечения текста оптического знака или OCR для файлов изображений), можно просматривать в машинных просмотрах, а также в представлении аннотатов в Advanced eDiscovery.

## <a name="archive--container"></a>Архив или контейнер

| Тип MIME | Идентификация файла | Извлечение метаданных | Извлечение контейнера | Возможные расширения |
|:---- |:---- |:---- |:---- |:---- |
|application/x-7z-compressed | Да | Да | Да | 0,7z |
|application/x-rar-compressed | Да | Да | Да | RAR |
|application/x-tar | Да | Да | Да | .tar |
|application/zip | Да | Да | Да | ZIP |
||||||||

## <a name="audio--video"></a>Аудио и видео

| Тип MIME | Идентификация файла | Извлечение метаданных | Извлечение текста | Native viewer | Annotate viewer | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
| application/mp4 | Да | Да | Нет | Да | Нет | .f4v; .m4a; .m4v; .mp4; .mp4v; .mpeg4; .mpeg4 |
|audio/mpeg | Да | Да | Нет | Да | Нет | MPEG |
|video/3gpp | Да | Да | Нет | Да | Нет | .3gp |
|video/3gpp2 | Да | Да | Нет | Да | Нет | 0,3g2; 0,3gp2 |
|video/quicktime | Да | Да | Нет | Да | Нет | .moov; .mov; .qt |
|video/x-m4v | Да | Да | Нет | Да | Нет | .m4v |
||||||||

## <a name="database"></a>Database

| Тип MIME | Идентификация файла | Извлечение метаданных | Извлечение текста | Native viewer | Annotate viewer | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/x-msaccess | Да | Да | Да | Нет | Нет | .mdb |
||||||||

## <a name="email"></a>Электронная почта

|Тип MIME |Идентификация файла |Извлечение метаданных |Извлечение текста |Native viewer |Annotate viewer | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-outlook | Да | Да | Да | Да | Да | .msg |
|message/rfc822 | Да | Да | Да | Да | Да | EML |
|text/vcard-contact | Да | Да | Да | Да | Да | .vcf |
||||||||

## <a name="email-container"></a>Контейнер электронной почты

| Тип MIME | Идентификация файла | Извлечение метаданных | Извлечение контейнера | Возможные расширения |
|:------| :------| :------| :------| :------|
|application/mbox | Да | Да | Да | .mbox |
|application/vnd.ms-outlook-pst | Да | Да | Да | .pst |
||||||||

## <a name="html"></a>HTML

| Тип MIME | Идентификация файла | Извлечение метаданных | Извлечение текста | Native viewer | Annotate viewer | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/xhtml+xml | Да | Да | Да | Да | Да | .xhtml |
|application/xml | Да | Да | Да | Да | Да | XML |
|text/html | Да | Да | Да | Да | Да | HTM; HTML; .shtml |
||||||||

## <a name="image"></a>Image

|Тип MIME |Идентификация файла |Извлечение метаданных |Извлечение текста OCR |Native viewer |Annotate viewer |Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|image/bmp | Да | Да | Да | Да | Да | BMP |
|image/emf | Да | Да | Да | Да | Да | EMF |
|image/gif | Да | Да | Да | Да | Да | GIF |
|image/jpeg | Да | Да | Да | Да | Да | JPEG; JPG |
|image/png | Да | Да | Да | Да | Да | PNG |
|image/svg+xml | Да | Да | Да | Да | Нет | .svg |
|image/tiff | Да | Да | Да | Да | Да | .tif |
|image/vnd.dwg | Да | Да | Да | Да | Да | DWG; DXF |
|image/wmf | Да | Да | Да | Да | Да | .wmf |
||||||||

## <a name="microsoft-excel"></a>Microsoft Excel

| Тип MIME | Идентификация файла | Извлечение метаданных | Извлечение текста | Native viewer | Annotate viewer | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-excel | Да | Да | Да | Да | Да | DAT; XLS |
|application/vnd.ms-excel.sheet.binary.macroenabled.12 | Да | Да | Да | Да | Нет | .xlsb |
|application/vnd.ms-excel.sheet.macroenabled.12 | Да | Да | Да | Да | Да | .xlsm |
|application/vnd.ms-excel.template.macroenabled.12 | Да | Да | Да | Нет | Нет | .xltm |
|application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | Да | Да | Да | Да | Да | XLSX |
|application/vnd.openxmlformats-officedocument.spreadsheetml.template | Да | Да | Да | Да | Да | XLTX |
||||||||

## <a name="microsoft-onenote"></a>Microsoft OneNote

| Тип MIME | Идентификация файла | Извлечение метаданных | Извлечение текста | Native viewer | Annotate viewer | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/onenote | Да | Да | Да | Да | Нет | .one |
||||||||

## <a name="microsoft-powerpoint"></a>Microsoft PowerPoint

| Тип MIME | Идентификация файла | Извлечение метаданных | Извлечение текста | Native viewer | Annotate viewer | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-powerpoint | Да | Да | Да | Да | Да | POT; PPS; PPT |
|application/vnd.openxmlformats-officedocument.presentationml.presentation | Да | Да | Да | Да | Да | PPTX |
|application/vnd.openxmlformats-officedocument.presentationml.slideshow | Да | Да | Да | Да | Да | PPSX |
|application/vnd.openxmlformats-officedocument.presentationml.template | Да | Да | Да | Да | Да | POTX |
||||||||

## <a name="microsoft-project"></a>Microsoft Project

| Тип MIME | Идентификация файла | Извлечение метаданных | Извлечение текста | Native viewer | Annotate viewer | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-project | Да | Да | Да | Нет | Да | MPP |
||||||||

## <a name="microsoft-publisher"></a>Microsoft Publisher

|Тип MIME | Идентификация файла | Извлечение метаданных | Извлечение текста | Native viewer | Annotate viewer | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/x-mspublisher | Да | Да | Да | Да | Да | .pub |
||||||||

## <a name="microsoft-visio"></a>Microsoft Visio

| Тип MIME | Идентификация файла | Извлечение метаданных | Извлечение текста | Native viewer | Annotate viewer | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-visio.drawing | Да | Да | Да | Да | Нет |  |
|application/vnd.visio | Да | Да | Да | Да | Да | VSD |
||||||||

## <a name="microsoft-word"></a>Microsoft Word

| Тип MIME | Идентификация файла | Извлечение метаданных | Извлечение текста | Native viewer | Annotate viewer | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/msword | Да | Да | Да | Да | Да | DAT; DOC |
| application/rtf | Да | Да | Да | Да | Да | DOC; RTF |
|application/vnd.ms-word.document.macroenabled.12 | Да | Да | Да | Да | Да | DOCM |
|application/vnd.ms-word.template.macroenabled.12 | Да | Да | Да | Да | Да | DOTM |
|application/vnd.openxmlformats-officedocument.wordprocessingml.document | Да | Да | Да | Да | Да | DOCX |
|application/vnd.openxmlformats-officedocument.wordprocessingml.template | Да | Да | Да | Да | Да | DOTX |
||||||||

## <a name="microsoft-works"></a>Microsoft Works

| Тип MIME | Идентификация файла | Извлечение метаданных | Извлечение текста | Native viewer | Annotate viewer | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-works-ss | Да | Да | Нет | Нет | Нет | .wps |
|application/vnd.ms-works-wp | Да | Да | Нет | Нет | Нет | .wps |
||||||||

## <a name="open-document-format"></a>Формат открытого документа

| Тип MIME | Идентификация файла | Извлечение метаданных | Извлечение текста | Native viewer | Annotate viewer | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.oasis.opendocument.text | Да | Да | Да | Да | Да | ODT |
||||||||

## <a name="other"></a>Другое

| Тип MIME | Идентификация файла | Извлечение метаданных | Извлечение текста | Native viewer | Annotate viewer | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/json | Да | Да | Да | Да | Да | Неприменимо |
|application/vnd.ms-graph | Да | Да | Нет | Нет | Нет |  |
|application/winhlp | Да | Да | Нет | Нет | Нет | .hlp |
|application/x-tnef | Да | Да | Нет | Нет | Нет |  |
||||||||

## <a name="plain-text"></a>обычный текст;

| Тип MIME | Идентификация файла | Извлечение метаданных | Извлечение текста | Native viewer | Annotate viewer | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|text/csv | Да | Да | Да | Да | Да | CSV |
|text/plain | Да | Да | Да | Да | Да | .con; .css; .csv; .dat; .pl; .txt |
||||||||

## <a name="portable-document-format"></a>Формат PDF

| Тип MIME | Идентификация файла | Извлечение метаданных | Извлечение текста | Native viewer | Annotate viewer | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/pdf | Да | Да | Да | Да | Да | PDF |
||||||||

## <a name="word-perfect"></a>Word Perfect

| Тип MIME | Идентификация файла | Извлечение метаданных | Извлечение текста | Native viewer | Annotate viewer | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.wordperfect; version=5.0 | Да | Да | Да | Нет | Нет | .wpd |
|application/vnd.wordperfect; version=5.1 | Да | Да | Да | Нет | Нет | .wpd |
|application/vnd.wordperfect; version=6.x | Да | Да | Да | Нет | Нет | .wpd |
||||||||

## <a name="word-pro"></a>Word Pro

| Тип MIME | Идентификация файла | Извлечение метаданных | Извлечение текста | Native viewer | Annotate viewer | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.lotus-wordpro | Да | Да | Нет | Нет | Нет | .lwp |
||||||||
