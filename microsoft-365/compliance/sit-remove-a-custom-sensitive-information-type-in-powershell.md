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
# <a name="remove-a-custom-sensitive-information-type-using-powershell"></a>Удаление настраиваемого типа конфиденциальной информации с помощью PowerShell



В PowerShell центра соответствия требованиям пользовательские типы конфиденциальных данных можно удалить двумя способами.

- **Удалите отдельные настраиваемые типы** конфиденциальной информации. Используйте метод, задокументированный в Модифицировать настраиваемый тип конфиденциальной информации [с помощью PowerShell.](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell) Экспортируем настраиваемый пакет правил, содержащий настраиваемый тип конфиденциальной информации, удаляем тип конфиденциальной информации из XML-файла и импортируем обновленный XML-файл обратно в существующий пользовательский пакет правил.

- **Удаление пакета настраиваемых правил и всех пользовательских типов конфиденциальных данных, содержащихся в нем**. Этот метод описан в текущем разделе.

> [!NOTE]
> Перед удалением пользовательского типа конфиденциальной информации убедитесь, что политики защиты от потери данных и правила потока обработки почты Exchange (также называемые правилами транспорта) не ссылаются на этот тип.

1. [Подключение к центру соответствия требованиям PowerShell](/powershell/exchange/exchange-online-powershell)

2. Чтобы удалить пакет настраиваемых правил, используйте командлет [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage):

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
   ```

   Для определения пакета правил можно использовать значение Name (для любого языка) или значение `RulePack id` (GUID).

   В этом примере удаляется пакет правил под названием "Employee ID Custom Rule Pack".

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

   Дополнительные сведения о синтаксисе и параметрах см. в статье [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage).

3. Чтобы убедиться в успешном удалении пользовательского типа конфиденциальных данных, выполните одно из указанных ниже действий.

   - Выполните командлет [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) и убедитесь в отсутствии пакета правил:

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - Выполните командлет [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype), чтобы убедиться в отсутствии типов конфиденциальных данных в удаленном пакете правил:

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     Для пользовательских типов конфиденциальных данных значение свойства Publisher будет отличаться от "Корпорация Майкрософт".

   - Замените \<Name\> значением Name типа конфиденциальных данных (например, Employee ID) и запустите командлет [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype), чтобы убедиться в отсутствии типа конфиденциальных данных:

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="more-information"></a>Дополнительные сведения

- [Сведения о защите от потери данных](dlp-learn-about-dlp.md)

- [Определения объектов типов конфиденциальной информации](sensitive-information-type-entity-definitions.md)

- [Сведения, для обнаружения которых используются функции защиты от потери данных](what-the-dlp-functions-look-for.md)
