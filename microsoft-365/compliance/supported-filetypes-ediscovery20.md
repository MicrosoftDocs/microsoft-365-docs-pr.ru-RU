---
title: Поддерживаемые типы файлов в advanced eDiscovery
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
description: Список поддерживаемых типов файлов в Microsoft 365 Advanced eDiscovery, включая типы файлов изображений, поддерживаемые функциями OCR в advanced eDiscovery.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 719a0474d45825114cf4ea3fbd19082bb8df7622
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599834"
---
# <a name="supported-file-types-in-advanced-ediscovery"></a>Поддерживаемые типы файлов в advanced eDiscovery

Advanced eDiscovery поддерживает многие типы файлов на разных уровнях. Типы файлов поддержки описаны в следующих таблицах в этой статье. Этот список еще не завершен, и мы добавим новые типы файлов по мере продолжения тестирования проверки. В этих таблицах указывается, поддерживается ли тип файла для извлечения текста (и оптического распознавания символов или удаления текста OCR для файлов изображений), просматриваемого в родном зрителье, а также поддержки в просмотрах Аннотации в advanced eDiscovery.

## <a name="archive--container"></a>Архив / Контейнер

| Тип Mime | Идентификация файла | Извлечение метаданных | Извлечение контейнера | Возможные расширения |
|:---- |:---- |:---- |:---- |:---- |
|application/x-7z-compressed | Да | Да | Да | .7z |
|application/x-rar-compressed | Да | Да | Да | .rar |
|application/x-tar | Да | Да | Да | .tar |
|application/zip | Да | Да | Да | ZIP |
||||||||

## <a name="audio--video"></a>Аудио / видео

| Тип Mime | Идентификация файла | Извлечение метаданных | Извлечение текста | Родной зритель | Аннотировать зрителя | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
| application/mp4 | Да | Да | Нет | Да | Нет | .f4v; .m4a; .m4v; .mp4v; .mpeg; .mpeg4 |
|аудио/mpeg | Да | Да | Нет | Да | Нет | .mpeg |
|video/3gpp | Да | Да | Нет | Да | Нет | .3gp |
|видео/3gpp2 | Да | Да | Нет | Да | Нет | .3g2; .3gp2 |
|видео/quicktime | Да | Да | Нет | Да | Нет | .moov; .mov; .qt |
|видео/x-m4v | Да | Да | Нет | Да | Нет | .m4v |
||||||||

## <a name="database"></a>Database

| Тип Mime | Идентификация файла | Извлечение метаданных | Извлечение текста | Родной зритель | Аннотировать зрителя | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/x-msaccess | Да | Да | Да | Нет | Нет | .mdb |
||||||||

## <a name="email"></a>Электронная почта

|Тип Mime |Идентификация файла |Извлечение метаданных |Извлечение текста |Родной зритель |Аннотировать зрителя | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-outlook | Да | Да | Да | Да | Да | .msg |
|message/rfc822 | Да | Да | Да | Да | Да | EML |
|text/vcard-contact | Да | Да | Да | Да | Да | .vcf |
||||||||

## <a name="email-container"></a>Контейнер электронной почты

| Тип Mime | Идентификация файла | Извлечение метаданных | Извлечение контейнера | Возможные расширения |
|:------| :------| :------| :------| :------|
|application/mbox | Да | Да | Да | .mbox |
|application/vnd.ms-outlook-pst | Да | Да | Да | PST |
||||||||

## <a name="html"></a>HTML

| Тип Mime | Идентификация файла | Извлечение метаданных | Извлечение текста | Родной зритель | Аннотировать зрителя | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/xhtml+xml | Да | Да | Да | Да | Да | .xhtml |
|application/xml | Да | Да | Да | Да | Да | .xml |
|text/html | Да | Да | Да | Да | Да | .htm; .html; .shtml |
||||||||

## <a name="image"></a>Image

|Тип Mime |Идентификация файла |Извлечение метаданных |Извлечение текста OCR |Родной зритель |Аннотировать зрителя |Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|image/bmp | Да | Да | Да | Да | Да | BMP |
|image/emf | Да | Да | Да | Да | Да | .emf |
|image/gif | Да | Да | Да | Да | Да | GIF |
|image/jpeg | Да | Да | Да | Да | Да | .jpeg; .jpg |
|image/png | Да | Да | Да | Да | Да | PNG |
|image/svg+xml | Да | Да | Да | Да | Нет | .svg |
|image/tiff | Да | Да | Да | Да | Да | .tif |
|image/vnd.dwg | Да | Да | Да | Да | Да | .dwg; .dxf |
|image/wmf | Да | Да | Да | Да | Да | .wmf |
||||||||

## <a name="microsoft-excel"></a>Microsoft Excel

| Тип Mime | Идентификация файла | Извлечение метаданных | Извлечение текста | Родной зритель | Аннотировать зрителя | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-excel | Да | Да | Да | Да | Да | .dat; .xls |
|application/vnd.ms-excel.sheet.binary.macroenabled.12 | Да | Да | Да | Да | Нет | .xlsb |
|application/vnd.ms-excel.sheet.macroenabled.12 | Да | Да | Да | Да | Да | .xlsm |
|application/vnd.ms-excel.template.macroenabled.12 | Да | Да | Да | Нет | Нет | .xltm |
|application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | Да | Да | Да | Да | Да | .xlsx |
|application/vnd.openxmlformats-officedocument.spreadsheetml.template | Да | Да | Да | Да | Да | .xltx |
||||||||

## <a name="microsoft-onenote"></a>Microsoft OneNote

| Тип Mime | Идентификация файла | Извлечение метаданных | Извлечение текста | Родной зритель | Аннотировать зрителя | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/onenote | Да | Да | Да | Нет | Нет | .one |
||||||||

## <a name="microsoft-powerpoint"></a>Microsoft PowerPoint

| Тип Mime | Идентификация файла | Извлечение метаданных | Извлечение текста | Родной зритель | Аннотировать зрителя | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-powerpoint | Да | Да | Да | Да | Да | .pot; .pps; .ppt |
|application/vnd.openxmlformats-officedocument.presentationml.presentation | Да | Да | Да | Да | Да | PPTX |
|application/vnd.openxmlformats-officedocument.presentationml.slideshow | Да | Да | Да | Да | Да | .ppsx |
|application/vnd.openxmlformats-officedocument.presentationml.template | Да | Да | Да | Да | Да | .potx |
||||||||

## <a name="microsoft-project"></a>Microsoft Project

| Тип Mime | Идентификация файла | Извлечение метаданных | Извлечение текста | Родной зритель | Аннотировать зрителя | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-project | Да | Да | Да | Нет | Да | .mpp |
||||||||

## <a name="microsoft-publisher"></a>Microsoft Publisher

|Тип Mime | Идентификация файла | Извлечение метаданных | Извлечение текста | Родной зритель | Аннотировать зрителя | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/x-mspublisher | Да | Да | Да | Да | Да | .pub |
||||||||

## <a name="microsoft-visio"></a>Microsoft Visio

| Тип Mime | Идентификация файла | Извлечение метаданных | Извлечение текста | Родной зритель | Аннотировать зрителя | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-visio.drawing | Да | Да | Да | Да | Нет |  |
|application/vnd.visio | Да | Да | Да | Да | Да | .vsd |
||||||||

## <a name="microsoft-word"></a>Microsoft Word

| Тип Mime | Идентификация файла | Извлечение метаданных | Извлечение текста | Родной зритель | Аннотировать зрителя | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/msword | Да | Да | Да | Да | Да | .dat; .doc |
| application/rtf | Да | Да | Да | Да | Да | .doc; .rtf |
|application/vnd.ms-word.document.macroenabled.12 | Да | Да | Да | Да | Да | DOCM |
|application/vnd.ms-word.template.macroenabled.12 | Да | Да | Да | Да | Да | .dotm |
|application/vnd.openxmlformats-officedocument.wordprocessingml.document | Да | Да | Да | Да | Да | .docx |
|application/vnd.openxmlformats-officedocument.wordprocessingml.template | Да | Да | Да | Да | Да | .dotx |
||||||||

## <a name="microsoft-works"></a>Microsoft Works

| Тип Mime | Идентификация файла | Извлечение метаданных | Извлечение текста | Родной зритель | Аннотировать зрителя | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-works-ss | Да | Да | Нет | Нет | Нет | .wps |
|application/vnd.ms-works-wp | Да | Да | Нет | Нет | Нет | .wps |
||||||||

## <a name="open-document-format"></a>Формат open document

| Тип Mime | Идентификация файла | Извлечение метаданных | Извлечение текста | Родной зритель | Аннотировать зрителя | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.oasis.opendocument.text | Да | Да | Да | Да | Да | .odt |
||||||||

## <a name="other"></a>Другие

| Тип Mime | Идентификация файла | Извлечение метаданных | Извлечение текста | Родной зритель | Аннотировать зрителя | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/json | Да | Да | Да | Да | Да | Неприменимо |
|application/vnd.ms-graph | Да | Да | Нет | Нет | Нет |  |
|application/winhlp | Да | Да | Нет | Нет | Нет | .hlp |
|application/x-tnef | Да | Да | Нет | Нет | Нет |  |
||||||||

## <a name="plain-text"></a>обычный текст;

| Тип Mime | Идентификация файла | Извлечение метаданных | Извлечение текста | Родной зритель | Аннотировать зрителя | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|text/csv | Да | Да | Да | Да | Да | .csv |
|text/plain | Да | Да | Да | Да | Да | .con; .css; .csv; .dat; .pl; .txt |
||||||||

## <a name="portable-document-format"></a>Формат PDF

| Тип Mime | Идентификация файла | Извлечение метаданных | Извлечение текста | Родной зритель | Аннотировать зрителя | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/pdf | Да | Да | Да | Да | Да | PDF |
||||||||

## <a name="word-perfect"></a>Word Perfect

| Тип Mime | Идентификация файла | Извлечение метаданных | Извлечение текста | Родной зритель | Аннотировать зрителя | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.wordperfect; version=5.0 | Да | Да | Да | Нет | Нет | WPD |
|application/vnd.wordperfect; version=5.1 | Да | Да | Да | Нет | Нет | WPD |
|application/vnd.wordperfect; version=6.x | Да | Да | Да | Нет | Нет | WPD |
||||||||

## <a name="word-pro"></a>Word Pro

| Тип Mime | Идентификация файла | Извлечение метаданных | Извлечение текста | Родной зритель | Аннотировать зрителя | Возможные расширения |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.lotus-wordpro | Да | Да | Нет | Нет | Нет | .lwp |
||||||||
