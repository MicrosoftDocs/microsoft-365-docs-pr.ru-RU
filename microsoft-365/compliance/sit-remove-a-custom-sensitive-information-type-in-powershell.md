---
title: Удаление настраиваемого типа конфиденциальной информации с помощью PowerShell
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
description: Узнайте, как удалить настраиваемый тип конфиденциальной информации с помощью PowerShell
ms.openlocfilehash: 9365eeff6100b16c94b9fa09b06dc51b272b60a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322954"
---
# <a name="remove-a-custom-sensitive-information-type-using-powershell"></a><span data-ttu-id="5b37c-103">Удаление настраиваемого типа конфиденциальной информации с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="5b37c-103">Remove a custom sensitive information type using PowerShell</span></span>



<span data-ttu-id="5b37c-104">В PowerShell центра соответствия требованиям пользовательские типы конфиденциальных данных можно удалить двумя способами.</span><span class="sxs-lookup"><span data-stu-id="5b37c-104">In Compliance center PowerShell, there are two methods to remove custom sensitive information types:</span></span>

- <span data-ttu-id="5b37c-105">**Удалите отдельные настраиваемые типы** конфиденциальной информации. Используйте метод, задокументированный в Модифицировать настраиваемый тип конфиденциальной информации [с помощью PowerShell.](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell)</span><span class="sxs-lookup"><span data-stu-id="5b37c-105">**Remove individual custom sensitive information types**: Use the method documented in [Modify a custom sensitive information type using PowerShell](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell).</span></span> <span data-ttu-id="5b37c-106">Экспортируем настраиваемый пакет правил, содержащий настраиваемый тип конфиденциальной информации, удаляем тип конфиденциальной информации из XML-файла и импортируем обновленный XML-файл обратно в существующий пользовательский пакет правил.</span><span class="sxs-lookup"><span data-stu-id="5b37c-106">You export the custom rule package that contains the custom sensitive information type, remove the sensitive information type from the XML file, and import the updated XML file back into the existing custom rule package.</span></span>

- <span data-ttu-id="5b37c-107">**Удаление пакета настраиваемых правил и всех пользовательских типов конфиденциальных данных, содержащихся в нем**. Этот метод описан в текущем разделе.</span><span class="sxs-lookup"><span data-stu-id="5b37c-107">**Remove a custom rule package and all custom sensitive information types that it contains**: This method is documented in this section.</span></span>

> [!NOTE]
> <span data-ttu-id="5b37c-108">Перед удалением пользовательского типа конфиденциальной информации убедитесь, что политики защиты от потери данных и правила потока обработки почты Exchange (также называемые правилами транспорта) не ссылаются на этот тип.</span><span class="sxs-lookup"><span data-stu-id="5b37c-108">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. [<span data-ttu-id="5b37c-109">Подключение к центру соответствия требованиям PowerShell</span><span class="sxs-lookup"><span data-stu-id="5b37c-109">Connect to Compliance center PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

2. <span data-ttu-id="5b37c-110">Чтобы удалить пакет настраиваемых правил, используйте командлет [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage):</span><span class="sxs-lookup"><span data-stu-id="5b37c-110">To remove a custom rule package, use the [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) cmdlet:</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
   ```

   <span data-ttu-id="5b37c-111">Для определения пакета правил можно использовать значение Name (для любого языка) или значение `RulePack id` (GUID).</span><span class="sxs-lookup"><span data-stu-id="5b37c-111">You can use the Name value (for any language) or the `RulePack id` (GUID) value to identify the rule package.</span></span>

   <span data-ttu-id="5b37c-112">В этом примере удаляется пакет правил под названием "Employee ID Custom Rule Pack".</span><span class="sxs-lookup"><span data-stu-id="5b37c-112">This example removes the rule package named "Employee ID Custom Rule Pack".</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

   <span data-ttu-id="5b37c-113">Дополнительные сведения о синтаксисе и параметрах см. в статье [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage).</span><span class="sxs-lookup"><span data-stu-id="5b37c-113">For detailed syntax and parameter information, see [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage).</span></span>

3. <span data-ttu-id="5b37c-114">Чтобы убедиться в успешном удалении пользовательского типа конфиденциальных данных, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="5b37c-114">To verify that you've successfully removed a custom sensitive information type, do any of the following steps:</span></span>

   - <span data-ttu-id="5b37c-115">Выполните командлет [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) и убедитесь в отсутствии пакета правил:</span><span class="sxs-lookup"><span data-stu-id="5b37c-115">Run the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet and verify the rule package is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - <span data-ttu-id="5b37c-116">Выполните командлет [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype), чтобы убедиться в отсутствии типов конфиденциальных данных в удаленном пакете правил:</span><span class="sxs-lookup"><span data-stu-id="5b37c-116">Run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information types in the removed rule package are no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     <span data-ttu-id="5b37c-117">Для пользовательских типов конфиденциальных данных значение свойства Publisher будет отличаться от "Корпорация Майкрософт".</span><span class="sxs-lookup"><span data-stu-id="5b37c-117">For custom sensitive information types, the Publisher property value will be something other than Microsoft Corporation.</span></span>

   - <span data-ttu-id="5b37c-118">Замените \<Name\> значением Name типа конфиденциальных данных (например, Employee ID) и запустите командлет [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype), чтобы убедиться в отсутствии типа конфиденциальных данных:</span><span class="sxs-lookup"><span data-stu-id="5b37c-118">Replace \<Name\> with the Name value of the sensitive information type (for example, Employee ID) and run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information type is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="more-information"></a><span data-ttu-id="5b37c-119">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="5b37c-119">More information</span></span>

- [<span data-ttu-id="5b37c-120">Сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="5b37c-120">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="5b37c-121">Определения объектов типов конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="5b37c-121">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="5b37c-122">Сведения, для обнаружения которых используются функции защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="5b37c-122">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
