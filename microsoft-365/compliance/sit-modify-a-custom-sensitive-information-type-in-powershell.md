---
title: Изменение настраиваемого типа конфиденциальной информации с помощью PowerShell
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Узнайте, как изменить настраиваемую конфиденциальную информацию с помощью PowerShell.
ms.openlocfilehash: 9f8a9ef119e632c695113320ab86a3bdfef8a197
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322959"
---
# <a name="modify-a-custom-sensitive-information-type-using-powershell"></a>Изменение настраиваемого типа конфиденциальной информации с помощью PowerShell

Чтобы изменить пользовательский тип конфиденциальных данных в PowerShell центра соответствия требованиям, необходимо выполнить следующие действия.

1. Экспортируйте существующий пакет правил, содержащий пользовательский тип конфиденциальных данных в XML-файл (или используйте существующий XML-файл при наличии).

2. Измените пользовательский тип конфиденциальных данных в экспортированном XML-файле.

3. Импортируйте обновленный XML-файл обратно в существующий пакет правил.

Чтобы подключиться к центру соответствия требованиям PowerShell, см. статью [Подключение к центру соответствия требованиям PowerShell](/powershell/exchange/exchange-online-powershell).

### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a>Этап 1. Экспорт существующего пакета правил в XML-файл

> [!NOTE]
> Если у вас есть копия XML-файла (например, вы только что создали и импортировали его), вы можете перейти к следующему этапу по изменению XML-файла.

1. Если вы еще не знаете имени пакета настраиваемых правил, выполните командлет [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype), чтобы найти его:

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

   > [!NOTE]
   > Встроенный пакет правил, содержащий встроенные типы конфиденциальной информации, называется пакетом правил Майкрософт. Пакет правил, содержащий настраиваемые типы конфиденциальной информации, созданные в пользовательском интерфейсе центра соответствия требованиям, называется Microsoft.SCCManaged.CustomRulePack.

2. Чтобы сохранить пакет настраиваемых правил в переменной, используйте командлет [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage):

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
   ```

   Например, если пакет правил называется "Employee ID Custom Rule Pack", выполните следующий командлет:

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

3. Чтобы экспортировать пакет настраиваемых правил в XML-файл, используйте командлет [Set-Content](/powershell/module/microsoft.powershell.management/set-content).

   ```powershell
   Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

   В этом примере пакет правил экспортируется в файл с именем ExportedRulePackage.xml в папку C:\My Documents.

   ```powershell
   Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a>Этап 2. Изменение типа конфиденциальных данных в экспортированном XML-файле

Типы конфиденциальных данных в XML-файле и другие элементы в файле описаны выше в этой статье.

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a>Этап 3. Импорт обновленного XML-файла обратно в существующий пакет правил

Чтобы импортировать обновленный XML-файл обратно в существующий пакет правил, используйте командлет [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage):

```powershell
Set-DlpSensitiveInformationTypeRulePackage -FileData ([Byte[]]$(Get-Content -Path "C:\My Documents\External Sensitive Info Type Rule Collection.xml" -Encoding Byte -ReadCount 0))
```

Дополнительные сведения о синтаксисе и параметрах см. в статье [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage).


## <a name="more-information"></a>Дополнительные сведения

- [Сведения о защите от потери данных](dlp-learn-about-dlp.md)

- [Определения объектов типов конфиденциальной информации](sensitive-information-type-entity-definitions.md)

- [Сведения, для обнаружения которых используются функции защиты от потери данных](what-the-dlp-functions-look-for.md)
