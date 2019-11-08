---
title: Защита файлов в командах с помощью меток конфиденциальности
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: Сводка. Используйте метки конфиденциальности, чтобы защитить файлы в команде со строго конфиденциальным уровнем защиты.
ms.openlocfilehash: f52b864087d22e14bb3e9bfe1eb38d088f6f981a
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925861"
---
# <a name="protect-files-in-teams-with-sensitivity-labels"></a><span data-ttu-id="8cd4e-103">Защита файлов в командах с помощью меток конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="8cd4e-103">Protect files in teams with sensitivity labels</span></span>


<span data-ttu-id="8cd4e-104">В отличие от метки конфиденциальности для строго регулируемых данных, которую любой пользователь может применить к любому файлу, команде со строго конфиденциальным уровнем защиты требуется собственная метка или вложенная метка, чтобы файлы, которым она назначена:</span><span class="sxs-lookup"><span data-stu-id="8cd4e-104">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure team needs its own label or sublabel so that assigned files:</span></span>

- <span data-ttu-id="8cd4e-105">шифровались по отдельности;</span><span class="sxs-lookup"><span data-stu-id="8cd4e-105">Are individually encrypted.</span></span>
- <span data-ttu-id="8cd4e-106">содержали настраиваемые разрешения, благодаря которым их смогут открыть только участники команды.</span><span class="sxs-lookup"><span data-stu-id="8cd4e-106">Contain custom permissions so that only members of the Team Group can open it.</span></span>

<span data-ttu-id="8cd4e-107">Чтобы установить этот дополнительный уровень безопасности для файлов, хранящихся на базовом сайте SharePoint команды, необходимо настроить метку конфиденциальности, являющуюся самостоятельной меткой или вложенной меткой для общей метки строго регулируемых данных.</span><span class="sxs-lookup"><span data-stu-id="8cd4e-107">To accomplish this additional level of security for files stored in the Team Site, you must configure a new sensitivity label that is either its own label a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="8cd4e-108">Только участники команды смогут увидеть настроенную метку или вложенную метку в своем списке меток.</span><span class="sxs-lookup"><span data-stu-id="8cd4e-108">Only team members will see the customized label or sublabel in their list of labels.</span></span>

<span data-ttu-id="8cd4e-109">Используйте метку конфиденциальности, если требуется небольшое число меток для общих и отдельных закрытых команд.</span><span class="sxs-lookup"><span data-stu-id="8cd4e-109">Use a sensitivity label when you need a small number of labels for both global use and individual private teams.</span></span> 

<span data-ttu-id="8cd4e-110">Используйте вложенную метку конфиденциальности, если у вас большое число меток или нужно упорядочить метки для команд со строго конфиденциальным уровнем защиты под меткой строго регулируемых данных.</span><span class="sxs-lookup"><span data-stu-id="8cd4e-110">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for private teams under the highly regulated label.</span></span>

<span data-ttu-id="8cd4e-111">Используйте [эти инструкции](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels), чтобы настроить отдельную метку или вложенную метку со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="8cd4e-111">[Use these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="8cd4e-112">Имя метки или вложенной метки содержит название команды</span><span class="sxs-lookup"><span data-stu-id="8cd4e-112">The name of the label contains the name of the team</span></span>
- <span data-ttu-id="8cd4e-113">Шифрование включено</span><span class="sxs-lookup"><span data-stu-id="8cd4e-113">Encryption is enabled</span></span>
- <span data-ttu-id="8cd4e-114">Группа Office 365 для команды получила разрешения на совместное редактирование</span><span class="sxs-lookup"><span data-stu-id="8cd4e-114">The Office 365 group for the team has Co-Author permissions</span></span>

<span data-ttu-id="8cd4e-115">После создания опубликуйте новую метку или вложенную метку для своих пользователей, которые смогут применять ее к файлам локально, прежде чем загружать их в команду, или позже, когда файл будет сохранен в команде.</span><span class="sxs-lookup"><span data-stu-id="8cd4e-115">After creating, publish the new label or sublabel for your users, who can then apply them to files either locally before uploading them to the team or later once the file is stored in the team.</span></span>

<span data-ttu-id="8cd4e-116">Ниже приведена конфигурация команды с особо конфиденциальным уровнем защиты, в которой используются метки конфиденциальности для шифрования файлов и предоставления разрешений.</span><span class="sxs-lookup"><span data-stu-id="8cd4e-116">Here is the configuration of the highly confidential team that uses sensitivity labels for file encryption and permissions.</span></span>

![Базовый уровень защиты для общедоступной команды.](../media/highly-confidential-team-dlp-sensitivity-labels.png)


## <a name="see-also"></a><span data-ttu-id="8cd4e-118">См. также</span><span class="sxs-lookup"><span data-stu-id="8cd4e-118">See Also</span></span>

[<span data-ttu-id="8cd4e-119">Защита файлов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8cd4e-119">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)
  
[<span data-ttu-id="8cd4e-120">Освоение облака и гибридные решения</span><span class="sxs-lookup"><span data-stu-id="8cd4e-120">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
