---
title: Управление загрузкой файлов автоматизации
description: Включить анализ контента и настроить расширения файлов и вложений электронной почты, которые будут отправлены для анализа
keywords: автоматизация, файл, отправка, контент, анализ, файл, расширение, электронная почта, вложение
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
ms.technology: mde
ms.openlocfilehash: 72405ad7500bf5d672f66ea64634e60c29ad1704
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076910"
---
# <a name="manage-automation-file-uploads"></a>Управление загрузкой файлов автоматизации

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationefileuploads-abovefoldlink)

Включите возможность анализа контента, чтобы некоторые файлы и вложения электронной почты автоматически были загружены в облако для дополнительной проверки в автоматическом расследовании.

Определите файлы и вложения электронной почты, указав имена расширения файлов и имена расширений вложений электронной почты. 

Например, если вы добавляете  *exe* и bat в качестве имен расширений файлов или вложений, то все файлы или вложения с этими расширениями автоматически будут отправлены в облако для дополнительной проверки во время автоматического расследования. 

## <a name="add-file-extension-names-and-attachment-extension-names"></a>Добавление имен расширений файлов и имен расширений вложений.

1. В области навигации выберите **загрузку файла "Автоматизация**  >  **параметров".** 

2. Переключить параметр анализа контента между **"Включите" и** **"Отключение".**

3. Настройка следующих имен расширений и отдельных имен расширений с запятой:
   - **Имена расширений файлов** . Подозрительные файлы, кроме вложений электронной почты, будут отправлены для дополнительной проверки
  

## <a name="related-topics"></a>Статьи по теме
- [Управление исключениями из папки автоматизации](manage-automation-folder-exclusions.md)
