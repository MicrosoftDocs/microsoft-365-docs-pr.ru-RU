---
title: Пользовательские типы конфиденциальной информации для защиты от потери данных
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/23/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Обзор пользовательских типов конфиденциальной информации для защиты от потери данных, таких как основной шаблон, расстояние между символами и уровень вероятности.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6934edba6eef03bc9d4bfc5c1c69f127a7d3a0e5
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817968"
---
# <a name="custom-sensitive-information-types"></a>Пользовательские типы конфиденциальной информации

Microsoft 365 содержит множество встроенных типов конфиденциальной информации, готовых к использованию в вашей организации, например для [защиты от потери данных](data-loss-prevention-policies.md) (DLP) или [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security). Встроенные типы конфиденциальной информации помогают определять и защищать номера кредитных карт, номера банковских счетов, номера паспортов и многое другое на основе закономерностей, определенных регулярным выражением (regex) или функцией. Дополнительные сведения см. в статье [Что позволяют искать типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).

Но что если вам нужно обнаруживать и защищать конфиденциальную информацию другого типа, например идентификаторы сотрудников или номера проектов с использованием особого формата в вашей организации? Для этого вы можете создать пользовательский тип конфиденциальной информации.

Основные компоненты пользовательского типа конфиденциальной информации:

- **Основной шаблон**: коды сотрудников, номера проектов и т. д. Как правило, он определяется регулярным выражением (RegEx), но также может представлять собой список ключевых слов.

- **Additional evidence**: Suppose you're looking for a nine-digit employee ID number. Not all nine-digit numbers are employee ID numbers, so you can look for additional text: keywords like "employee", "badge", "ID", or other text patterns based on additional regular expressions. This supporting evidence (also known as _supporting_ or _corroborative_ evidence) increases the likelihood that nine-digit number found in content is really an employee ID number.

- **Character proximity**: It makes sense that the closer the primary pattern and the supporting evidence are to each other, the more likely the detected content is going to be what you're looking for. You can specify the character distance between the primary pattern and the supporting evidence (also known as the _proximity window_) as shown in the following diagram:

    ![Схема подтверждающего признака и интервала вероятности](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- **Confidence level**: The more supporting evidence you have, the higher the likelihood that a match contains the sensitive information you're looking for. You can assign higher levels of confidence for matches that are detected by using more evidence.

  When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policies. When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown in the following diagram:

    ![Пример параметров количества и точности совпадения](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

## <a name="creating-custom-sensitive-information-types"></a>Создание пользовательских типов конфиденциальной информации

Создать пользовательский тип конфиденциальной информации для защиты от потери данных в Центре безопасности и соответствия требованиям можно с помощью нескольких вариантов:

- **С помощью EDM.** (НОВИНКА!) Вы можете настроить пользовательские типы конфиденциальной информации с использованием классификации на основе точного совпадения данных (EDM). Этот метод позволяет создать динамический тип конфиденциальной информации с помощью защищенной базы данных, которую можно периодически обновлять. См. статью [Создание пользовательского типа конфиденциальной информации с помощью классификации на основе точного совпадения данных](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

- **С помощью PowerShell.** Вы можете настроить пользовательские типы конфиденциальной информации с использованием PowerShell. Хотя этот метод сложнее, чем использование пользовательского интерфейса, он предоставляет дополнительные параметры конфигурации. См. статью [Создание пользовательского типа конфиденциальной информации в PowerShell Центра безопасности и соответствия требованиям](create-a-custom-sensitive-information-type-in-scc-powershell.md).

- **С помощью пользовательского интерфейса.** Вы можете настроить пользовательский тип конфиденциальной информации, используя пользовательский интерфейс Центра безопасности и соответствия требованиям. В этом методе можно использовать регулярные выражения, ключевые слова и словари ключевых слов. Дополнительные сведения см. в статье [Создание пользовательского типа конфиденциальной информации](create-a-custom-sensitive-information-type.md).



