---
title: Управление привилегированным доступом для тестовой среды Microsoft 365 для предприятий
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: Ent_TLGs
description: Используйте это руководство по лаборатории тестирования, чтобы включить управление привилегированным доступом в тестовой среде Microsoft 365 для предприятий.
ms.openlocfilehash: e9684ebd2aa147049dadfbda9408257ff801aff0
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126421"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a>Управление привилегированным доступом для тестовой среды Microsoft 365 для предприятий

*Это руководство по лаборатории тестирования можно использовать для тестовых сред Microsoft 365 для предприятий и Office 365 корпоративный.*

В этой статье описывается настройка управления привилегированным доступом для повышения безопасности в тестовой среде Microsoft 365 для предприятий.

Настройка управления доступом с использованием priviledged состоит из трех этапов:
- [Этап 1. Создание тестовой среды Microsoft 365 для предприятий](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Этап 2. Настройка управления привилегированным доступом](#phase-2-configure-privileged-access-management)
- [Этап 3. Проверка необходимости утверждения для задач с повышенными привилегиями](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Чтобы получить визуальную карту всех статей в руководстве по лаборатории тестирования Microsoft 365 для предприятий, перейдите в стек руководств по лаборатории тестирования [Microsoft 365 для предприятий.](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Этап 1. Создание тестовой среды Microsoft 365 для предприятий

Если вы хотите настроить управление привилегированным доступом облегченным способом с минимальными требованиями, следуйте инструкциям в базовой конфигурации [облегченного доступа.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Если вы хотите настроить управление привилегированным доступом в имитированном предприятии, следуйте инструкциям в сквозной [проверке подлинности.](pass-through-auth-m365-ent-test-environment.md)
  
>[!NOTE]
>Для тестирования управления привилегированным доступом не требуется тестовая среда имитации предприятия, которая включает имитированную интрасеть, подключенную к Интернету, и синхронизацию каталогов для леса доменных служб Active Directory. Он предоставляется здесь в качестве варианта, чтобы вы могли протестировать управление привилегированным доступом и поэкспериментировать с ним в среде, которая представляет типичную организацию.

## <a name="phase-2-configure-privileged-access-management"></a>Этап 2. Настройка управления привилегированным доступом

На этом этапе настройте группу утвержденных и встройте управление привилегированным доступом для тестовой среды Microsoft 365 для предприятий. Дополнительные сведения и обзор управления привилегированным доступом см. в руководстве [по управлению привилегированным доступом.](../compliance/privileged-access-management-overview.md)

Чтобы настроить и использовать привилегированный доступ в организации, выполните следующие действия.

#### <a name="step-1-create-an-approvers-group"></a>[Шаг 1. Создание группы утвержденного](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

Прежде чем приступить к использованию привилегированного доступа, определите, кто будет иметь полномочия на утверждение входящих запросов на доступ к задачам с повышенными привилегиями. Все пользователи, которые являются частью группы "Утверждение", могут утверждать запросы на доступ. Чтобы использовать привилегированный доступ, необходимо создать группу безопасности с включенной поддержкой почты в Microsoft 365. В тестовой среде назовите новую группу безопасности "Privileged Access Approvers" и добавьте "Пользователь 3", ранее созданную на предыдущих шагах руководства по лаборатории тестирования.

#### <a name="step-2-enable-privileged-access"></a>[Шаг 2. Включить привилегированный доступ](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

Привилегированный доступ должен быть явно включен в Microsoft 365 с группой утвержденных по умолчанию и должен включать набор системных учетных записей, которые необходимо исключить из управления привилегированным доступом управления доступом. Не забудьте включить привилегированный доступ в организации перед началом этапа 3 этого руководства.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Этап 3. Проверка необходимости утверждения для задач с повышенными привилегиями

На этом этапе убедитесь, что политика привилегированного доступа работает и что пользователям требуется утверждение для выполнения определенных задач с повышенными привилегиями.

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>Проверка возможности выполнения задачи, НЕ определенной в политике привилегированного доступа

Сначала подключите к Exchange Management PowerShell с учетными данными пользователя, настроенного в качестве глобального администратора в тестовой среде, и попытайтесь создать новое правило журнала. Задача [New-JournalRule](/powershell/module/exchange/new-journalrule) в настоящее время не определена в политике привилегированного доступа для организации.

1. На локальном компьютере откройте удаленный модуль PowerShell для Exchange Online в модуле **Microsoft Corporation** Microsoft Exchange Online  >  **Remote PowerShell с** помощью учетной записи глобального администратора для тестовой среды.

1. В Exchange Management PowerShell создайте новое правило журнала для своей организации:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. Вы должны увидеть, что новое правило журнала успешно создано в Exchange Management PowerShell.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Создание новой политики привилегированного доступа для New-JournalRule задачи

>[!NOTE]
>Если вы еще не выполнили шаги 1 и 2 из этапа 2 этого руководства, обязательно выполните действия, чтобы создать группу утвержденного с именем "Privilege Access Approvers", чтобы включить привилегированный доступ в тестовой среде.

1. Во sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.

2. В Центре администрирования перейдите **к** параметрам безопасности  >  **&**  >  **конфиденциальности привилегированного доступа.**

3. Выберите **"Управление политиками и запросами доступа".**

4. Выберите **"Настроить политики",** а затем выберите **"Добавить политику".**

5. В полях в выпадаемом поле выберите или введите следующие значения:

    **Тип политики**: Задача

    **Область политики**: Exchange

    **Имя политики:** новое правило журнала

    **Тип утверждения:** вручную

    **Группа утверждения:**"Утверждение привилегированного доступа"

6. Выберите **"Создать"** и **"Закрыть".** Для полной настройки и включения политики может потребоваться несколько минут. Убедитесь, что у вас должно быть время для полной включения политики, прежде чем тестировать требование утверждения на следующем этапе.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Требование проверки утверждения для New-JournalRule, определенной в политике привилегированного доступа

1. На локальном компьютере откройте удаленный модуль PowerShell для Exchange Online в модуле **Microsoft Corporation** Microsoft Exchange Online  >  **Remote PowerShell с** помощью учетной записи глобального администратора для тестовой среды.

2. В Exchange Management PowerShell создайте новое правило журнала для своей организации:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. Просмотр ошибки "Недостаточно разрешений" в Exchange Management PowerShell:

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Запрос доступа для создания нового правила журнала с помощью New-JournalRule задачи

1. Во sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.

2. В Центре администрирования перейдите **к** параметрам безопасности  >  **&**  >  **конфиденциальности привилегированного доступа.**

3. Выберите **"Управление политиками и запросами доступа".**

4. Выберите **новый запрос.** В полях в выпадаемом поле выберите соответствующие значения для вашей организации:

    **Тип запроса**: Задача

    **Область запроса**: Exchange

    **Запрос :** новое правило журнала

    **Продолжительность (часы)**: 2

    **Комментарии:** запрос разрешения на создание нового правила журнала

5. Выберите **"Сохранить"** и **"Закрыть".** Ваш запрос будет отправлен группе утвержденного по электронной почте.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Утверждение запроса на привилегированный доступ для создания нового правила журнала

1. Во sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).

2. В Центре администрирования перейдите **к** параметрам безопасности  >  **&**  >  **конфиденциальности привилегированного доступа.**

3. Выберите **"Управление политиками и запросами доступа".**

4. Выберите ожидающее запрос,  а затем выберите "Утвердить", чтобы предоставить доступ к учетной записи глобального администратора для создания нового правила журнала. Учетная запись глобального администратора (запрашивающий пользователь) получит по электронной почте подтверждение об утверждении.

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Тестирование создания нового правила журнала с привилегированным доступом, утвержденным для New-JournalRule задачи

1. На локальном компьютере откройте удаленный модуль PowerShell для Exchange Online в модуле **Microsoft Corporation** Microsoft Exchange Online  >  **Remote PowerShell с** помощью учетной записи глобального администратора для тестовой среды.

1. В Exchange Management PowerShell создайте новое правило журнала для своей организации:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. Вы должны увидеть, что новое правило журнала успешно создано в Exchange Management PowerShell.

## <a name="next-step"></a>Следующий этап

Изучите [дополнительные функции](m365-enterprise-test-lab-guides.md#information-protection) и возможности защиты информации в тестовой среде.

## <a name="see-also"></a>См. также

[Руководства по лаборатории тестирования для Microsoft 365 для предприятий](m365-enterprise-test-lab-guides.md)

[Обзор Microsoft 365 для предприятий](microsoft-365-overview.md)

[Документация по Microsoft 365 для предприятий](/microsoft-365-enterprise/)
