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
# <a name="modify-a-custom-sensitive-information-type-using-powershell"></a><span data-ttu-id="16703-103">Изменение настраиваемого типа конфиденциальной информации с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="16703-103">Modify a custom sensitive information type using PowerShell</span></span>

<span data-ttu-id="16703-104">Чтобы изменить пользовательский тип конфиденциальных данных в PowerShell центра соответствия требованиям, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="16703-104">In Compliance center PowerShell, modifying a custom sensitive information type requires you to:</span></span>

1. <span data-ttu-id="16703-105">Экспортируйте существующий пакет правил, содержащий пользовательский тип конфиденциальных данных в XML-файл (или используйте существующий XML-файл при наличии).</span><span class="sxs-lookup"><span data-stu-id="16703-105">Export the existing rule package that contains the custom sensitive information type to an XML file (or use the existing XML file if you have it).</span></span>

2. <span data-ttu-id="16703-106">Измените пользовательский тип конфиденциальных данных в экспортированном XML-файле.</span><span class="sxs-lookup"><span data-stu-id="16703-106">Modify the custom sensitive information type in the exported XML file.</span></span>

3. <span data-ttu-id="16703-107">Импортируйте обновленный XML-файл обратно в существующий пакет правил.</span><span class="sxs-lookup"><span data-stu-id="16703-107">Import the updated XML file back into the existing rule package.</span></span>

<span data-ttu-id="16703-108">Чтобы подключиться к центру соответствия требованиям PowerShell, см. статью [Подключение к центру соответствия требованиям PowerShell](/powershell/exchange/exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="16703-108">To connect to Compliance Center PowerShell, see [Connect to Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell).</span></span>

### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a><span data-ttu-id="16703-109">Этап 1. Экспорт существующего пакета правил в XML-файл</span><span class="sxs-lookup"><span data-stu-id="16703-109">Step 1: Export the existing rule package to an XML file</span></span>

> [!NOTE]
> <span data-ttu-id="16703-110">Если у вас есть копия XML-файла (например, вы только что создали и импортировали его), вы можете перейти к следующему этапу по изменению XML-файла.</span><span class="sxs-lookup"><span data-stu-id="16703-110">If you have a copy of the XML file (for example, you just created and imported it), you can skip to the next step to modify the XML file.</span></span>

1. <span data-ttu-id="16703-111">Если вы еще не знаете имени пакета настраиваемых правил, выполните командлет [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype), чтобы найти его:</span><span class="sxs-lookup"><span data-stu-id="16703-111">If you don't already know it, run the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to find the name of the custom rule package:</span></span>

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

   > [!NOTE]
   > <span data-ttu-id="16703-p101">Встроенный пакет правил, содержащий встроенные типы конфиденциальной информации, называется пакетом правил Майкрософт. Пакет правил, содержащий настраиваемые типы конфиденциальной информации, созданные в пользовательском интерфейсе центра соответствия требованиям, называется Microsoft.SCCManaged.CustomRulePack.</span><span class="sxs-lookup"><span data-stu-id="16703-p101">The built-in rule package that contains the built-in sensitive information types is named Microsoft Rule Package. The rule package that contains the custom sensitive information types that you created in the Compliance center UI is named Microsoft.SCCManaged.CustomRulePack.</span></span>

2. <span data-ttu-id="16703-114">Чтобы сохранить пакет настраиваемых правил в переменной, используйте командлет [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage):</span><span class="sxs-lookup"><span data-stu-id="16703-114">Use the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet to store the custom rule package to a variable:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
   ```

   <span data-ttu-id="16703-115">Например, если пакет правил называется "Employee ID Custom Rule Pack", выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="16703-115">For example, if the name of the rule package is "Employee ID Custom Rule Pack", run the following cmdlet:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

3. <span data-ttu-id="16703-116">Чтобы экспортировать пакет настраиваемых правил в XML-файл, используйте командлет [Set-Content](/powershell/module/microsoft.powershell.management/set-content).</span><span class="sxs-lookup"><span data-stu-id="16703-116">Use the [Set-Content](/powershell/module/microsoft.powershell.management/set-content) cmdlet to export the custom rule package to an XML file:</span></span>

   ```powershell
   Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

   <span data-ttu-id="16703-117">В этом примере пакет правил экспортируется в файл с именем ExportedRulePackage.xml в папку C:\My Documents.</span><span class="sxs-lookup"><span data-stu-id="16703-117">This example export the rule package to the file named ExportedRulePackage.xml in the C:\My Documents folder.</span></span>

   ```powershell
   Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a><span data-ttu-id="16703-118">Этап 2. Изменение типа конфиденциальных данных в экспортированном XML-файле</span><span class="sxs-lookup"><span data-stu-id="16703-118">Step 2: Modify the sensitive information type in the exported XML file</span></span>

<span data-ttu-id="16703-119">Типы конфиденциальных данных в XML-файле и другие элементы в файле описаны выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="16703-119">Sensitive information types in the XML file and other elements in the file are described earlier in this topic.</span></span>

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a><span data-ttu-id="16703-120">Этап 3. Импорт обновленного XML-файла обратно в существующий пакет правил</span><span class="sxs-lookup"><span data-stu-id="16703-120">Step 3: Import the updated XML file back into the existing rule package</span></span>

<span data-ttu-id="16703-121">Чтобы импортировать обновленный XML-файл обратно в существующий пакет правил, используйте командлет [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage):</span><span class="sxs-lookup"><span data-stu-id="16703-121">To import the updated XML back into the existing rule package, use the [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) cmdlet:</span></span>

```powershell
Set-DlpSensitiveInformationTypeRulePackage -FileData ([Byte[]]$(Get-Content -Path "C:\My Documents\External Sensitive Info Type Rule Collection.xml" -Encoding Byte -ReadCount 0))
```

<span data-ttu-id="16703-122">Дополнительные сведения о синтаксисе и параметрах см. в статье [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage).</span><span class="sxs-lookup"><span data-stu-id="16703-122">For detailed syntax and parameter information, see [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage).</span></span>


## <a name="more-information"></a><span data-ttu-id="16703-123">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="16703-123">More information</span></span>

- [<span data-ttu-id="16703-124">Сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="16703-124">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="16703-125">Определения объектов типов конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="16703-125">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="16703-126">Сведения, для обнаружения которых используются функции защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="16703-126">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
