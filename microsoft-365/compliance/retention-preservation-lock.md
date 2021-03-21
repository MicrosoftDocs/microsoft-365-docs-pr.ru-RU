---
title: Использование блокировки для сохранения в целях ограничения изменений в политиках хранения и политиках меток хранения.
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Используйте блокировку для сохранения совместно с политиками хранения и политиками меток хранения, чтобы обеспечить соответствие нормативным требованиям и защититься от недобросовестных администраторов.
ms.openlocfilehash: 72f667b970b4257a3a540fb74a121c620892b56d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922533"
---
# <a name="use-preservation-lock-to-restrict-changes-to-retention-policies-and-retention-label-policies"></a>Использование блокировки для сохранения в целях ограничения изменений в политиках хранения и политиках меток хранения.

>*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Функция блокировки для сохранения блокирует политику хранения или политику метки хранения, чтобы никто, в том числе глобальный администратор, не мог отключить политику, удалить ее или сделать менее строгой. Эта конфигурация может потребоваться для соблюдения нормативных требований и помогает защититься от недобросовестных администраторов.

Когда политика хранения заблокирована:

- Никто не может отключить или удалить политику
- Расположения можно добавлять, но не удалять
- Вы можете продлить срок хранения, но не уменьшить его

Когда политика меток хранения заблокирована:

- Никто не может отключить или удалить политику
- Расположения можно добавлять, но не удалять
- Метки можно добавлять, но не удалять

Таким образом, действие заблокированной политики может быть продлено или расширено, но его нельзя сократить или отключить.

> [!IMPORTANT]
> Прежде чем заблокировать политику хранения или политику метки хранения, важно обдумать последствия этого действия и подтвердить, что оно необходимо для вашей организации. Например, это может потребоваться для соблюдения нормативных требований. Администраторы не смогут отключить или удалить эти политики после применения блокировки для сохранения.

Настройте блокировку для сохранения после создания [политики хранения](create-retention-policies.md) или политики меток хранения, которую вы [публикуете](create-apply-retention-labels.md) или которая [применяется автоматически](apply-retention-labels-automatically.md). 

> [!NOTE]
> Блокировка политики меток не запрещает администратору сократить период хранения в метке, включенной в заблокированную политику. Это требование с другими ограничениями можно выполнить при настройке метки для маркировки элементов в качестве [нормативных записей](records-management.md#records).

## <a name="how-to-lock-a-retention-policy-or-retention-label-policy"></a>Порядок блокировки политики хранения или политики метки хранения

Если вам нужно применять блокировку для сохранения, необходимо использовать Windows PowerShell. Так как администраторы не могут отключить или удалить политику хранения после применения этой блокировки, ее включение в пользовательском интерфейсе сделано недоступным, чтобы исключить случайную настройку.

Все политики хранения с любыми настройками поддерживают блокировку для сохранения.

1. [Подключение к Центру безопасности и соответствия требованиям Windows PowerShell](/powershell/exchange/connect-to-scc-powershell).

2. Найдите название политики, которую вы хотите заблокировать, выполнив команду [Get-RetentionCompliancePolicy](/powershell/module/exchange/get-retentioncompliancepolicy). Например:
    
   ![Список политик хранения в PowerShell](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

3. Чтобы применить блокировку для сохранения к политике, выполните командлет [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) с именем политики и параметром *RestrictiveRetention*, которому присвоено значение true:
    
    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" –RestrictiveRetention $true
    ```
    
    Например,
    
    ![Параметр RestrictiveRetention в PowerShell](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
     При появлении запроса прочтите и подтвердите ограничения, связанные с настройкой, путем ввода **Y**:
    
   ![Запрос подтверждения блокировки политики хранения в PowerShell](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

Теперь к политике применена блокировка для сохранения. Чтобы подтвердить действие, выполните команду `Get-RetentionCompliancePolicy` еще раз, при этом укажите имя политики и ее параметры.

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

Вы увидите, что параметру **RestrictiveRetention** присвоено значение **True**. Например:

![Заблокированная политика с отображением всех параметров в PowerShell](../media/retention-policy-preservation-lock-locked-policy.PNG)

## <a name="see-also"></a>См. также

[Вспомогательные ресурсы для соблюдения нормативных требований к управлению данными и записями](retention-regulatory-requirements.md)