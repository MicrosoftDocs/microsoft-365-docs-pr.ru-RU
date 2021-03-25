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
# <a name="manage-automation-file-uploads"></a><span data-ttu-id="34925-104">Управление загрузкой файлов автоматизации</span><span class="sxs-lookup"><span data-stu-id="34925-104">Manage automation file uploads</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="34925-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="34925-105">**Applies to:**</span></span>
- [<span data-ttu-id="34925-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="34925-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="34925-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="34925-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="34925-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="34925-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="34925-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="34925-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationefileuploads-abovefoldlink)

<span data-ttu-id="34925-110">Включите возможность анализа контента, чтобы некоторые файлы и вложения электронной почты автоматически были загружены в облако для дополнительной проверки в автоматическом расследовании.</span><span class="sxs-lookup"><span data-stu-id="34925-110">Enable the content analysis capability so that certain files and email attachments can automatically be uploaded to the cloud for additional inspection in Automated investigation.</span></span>

<span data-ttu-id="34925-111">Определите файлы и вложения электронной почты, указав имена расширения файлов и имена расширений вложений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="34925-111">Identify the files and email attachments by specifying the file extension names and email attachment extension names.</span></span> 

<span data-ttu-id="34925-112">Например, если вы добавляете  *exe* и bat в качестве имен расширений файлов или вложений, то все файлы или вложения с этими расширениями автоматически будут отправлены в облако для дополнительной проверки во время автоматического расследования.</span><span class="sxs-lookup"><span data-stu-id="34925-112">For example, if you add *exe* and *bat* as file or attachment extension names, then all files or attachments with those extensions will automatically be sent to the cloud for additional inspection during Automated investigation.</span></span> 

## <a name="add-file-extension-names-and-attachment-extension-names"></a><span data-ttu-id="34925-113">Добавление имен расширений файлов и имен расширений вложений.</span><span class="sxs-lookup"><span data-stu-id="34925-113">Add file extension names and attachment extension names.</span></span>

1. <span data-ttu-id="34925-114">В области навигации выберите **загрузку файла "Автоматизация**  >  **параметров".**</span><span class="sxs-lookup"><span data-stu-id="34925-114">In the navigation pane, select **Settings** > **Automation file uploads**.</span></span> 

2. <span data-ttu-id="34925-115">Переключить параметр анализа контента между **"Включите" и** **"Отключение".**</span><span class="sxs-lookup"><span data-stu-id="34925-115">Toggle the content analysis setting between **On** and **Off**.</span></span>

3. <span data-ttu-id="34925-116">Настройка следующих имен расширений и отдельных имен расширений с запятой:</span><span class="sxs-lookup"><span data-stu-id="34925-116">Configure the following extension names and separate extension names with a comma:</span></span>
   - <span data-ttu-id="34925-117">**Имена расширений файлов** . Подозрительные файлы, кроме вложений электронной почты, будут отправлены для дополнительной проверки</span><span class="sxs-lookup"><span data-stu-id="34925-117">**File extension names** -  Suspicious files except email attachments will be submitted for additional inspection</span></span>
  

## <a name="related-topics"></a><span data-ttu-id="34925-118">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="34925-118">Related topics</span></span>
- [<span data-ttu-id="34925-119">Управление исключениями из папки автоматизации</span><span class="sxs-lookup"><span data-stu-id="34925-119">Manage automation folder exclusions</span></span>](manage-automation-folder-exclusions.md)
