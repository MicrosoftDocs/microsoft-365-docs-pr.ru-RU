---
title: Управление привилегированным доступом для Microsoft 365 для корпоративной тестовой среды
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
description: Используйте это руководство по лаборатории тестирования, чтобы включить управление привилегированным доступом Microsoft 365 для корпоративной тестовой среды.
ms.openlocfilehash: e9684ebd2aa147049dadfbda9408257ff801aff0
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126421"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a>Управление привилегированным доступом для Microsoft 365 для корпоративной тестовой среды

*Это руководство по тестовой лаборатории можно использовать как для Microsoft 365, так и для Office 365 корпоративный среды тестирования.*

В этой статье описывается настройка управления привилегированным доступом для повышения безопасности Microsoft 365 для корпоративной тестовой среды.

Настройка управления доступом с priviledged включает три этапа:
- [Этап 1. Создание Microsoft 365 для корпоративной тестовой среды](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Этап 2. Настройка управления привилегированным доступом](#phase-2-configure-privileged-access-management)
- [Этап 3. Убедитесь, что для повышенных и привилегированных задач требуется утверждение](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Чтобы получить визуальную карту для всех статей в стеке руководства по Microsoft 365 для корпоративной лаборатории тестирования, перейдите Microsoft 365 для корпоративного руководства по [лаборатории тестирования.](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Этап 1. Создание Microsoft 365 для корпоративной тестовой среды

Если вы хотите настроить управление привилегированным доступом облегченным способом с минимальными требованиями, следуйте инструкциям в [базовой конфигурации Lightweight.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Если вы хотите настроить управление привилегированным доступом в смоделированном предприятии, следуйте инструкциям в сквозной [проверке подлинности.](pass-through-auth-m365-ent-test-environment.md)
  
>[!NOTE]
>Тестирование управления привилегированным доступом не требует имитации тестовой среды предприятия, которая включает смоделированную интрасеть, подключенную к Интернету, и синхронизацию каталогов для леса служб домена Active Directory. Он предоставляется здесь в качестве параметра, чтобы можно было протестировать управление привилегированным доступом и поэкспериментировать с ним в среде, которая представляет типичную организацию.

## <a name="phase-2-configure-privileged-access-management"></a>Этап 2. Настройка управления привилегированным доступом

На этом этапе настройте группу одобрений и встройте управление привилегированным доступом для Microsoft 365 для корпоративной тестовой среды. Дополнительные сведения и обзор управления привилегированным доступом см. в материале [Privileged access management.](../compliance/privileged-access-management-overview.md)

Чтобы настроить и использовать привилегированный доступ в организации, выполните следующие действия.

#### <a name="step-1-create-an-approvers-group"></a>[Шаг 1. Создание группы утверждения](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

Прежде чем приступить к использованию привилегированного доступа, определите, у кого будет полномочия по утверждению входящих запросов на доступ к повышенным и привилегированным задачам. Все пользователи, которые являются частью группы утверждений, могут утверждать запросы на доступ. Чтобы использовать привилегированный доступ, необходимо создать группу безопасности с поддержкой почты в Microsoft 365. В тестовой среде назовите новую группу безопасности "Утверждения привилегированного доступа" и добавьте "User 3", созданную ранее в предыдущих действиях руководства лаборатории тестирования.

#### <a name="step-2-enable-privileged-access"></a>[Шаг 2. Включить привилегированный доступ](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

Привилегированный доступ должен быть включен Microsoft 365 в группе утверждения по умолчанию, и он должен включать набор учетных записей системы, которые необходимо исключить из управления доступом к привилегированному управлению доступом. Не забудьте включить привилегированный доступ в организации перед началом этапа 3 этого руководства.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Этап 3. Убедитесь, что для повышенных и привилегированных задач требуется утверждение

На этом этапе убедитесь, что политика привилегированного доступа работает и что пользователям требуется утверждение для выполнения определенных повышенных и привилегированных задач.

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>Проверьте возможность выполнения задачи, не определенной в политике привилегированного доступа

Сначала подключите Exchange PowerShell с учетными данными пользователя, настроенного в качестве глобального администратора в тестовой среде, и попробуйте создать новое правило Journal. Задача [New-JournalRule](/powershell/module/exchange/new-journalrule) в настоящее время не определена в политике привилегированного доступа для вашей организации.

1. На локальном компьютере откройте и впишитесь в модуль удаленной Exchange Online PowerShell в **модуле Microsoft Corporation** Microsoft Exchange Online Remote  >  **PowerShell с** помощью учетной записи Глобального администратора для тестовой среды.

1. В Exchange PowerShell создайте новое правило Журнала для организации:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. Просмотр того, что новое правило журнала было успешно создано в Exchange PowerShell.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Создание новой политики привилегированного доступа для New-JournalRule задачи

>[!NOTE]
>Если вы еще не завершили этапы 1 и 2 из этапа 2 этого руководства, выполните действия по созданию группы утверждения с именем "Утверждения доступа к привилегиям", чтобы включить привилегированный доступ в тестовой среде.

1. Вопишитесь в [центр администрирования Microsoft 365 с](https://admin.microsoft.com) помощью учетных данных учетной записи Глобального администратора для тестовой среды.

2. В Центре администрирования перейдите **к** Параметры  >  **безопасности & конфиденциальности.**  >  

3. Выберите **Управление политиками и запросами доступа.**

4. Выберите **Настройка политик,** а затем выберите **Добавить политику.**

5. Из выпадаемого поля выберите или введите следующие значения:

    **Тип политики:** Задача

    **Область действия политики**: Exchange

    **Имя политики:** Новое правило журнала

    **Тип утверждения:** вручную

    **Группа утверждения.** Утверждения привилегированного доступа

6. Нажмите **Создать**, а затем — **Закрыть**. Для полной настройки и включения политики может потребоваться несколько минут. Убедитесь, что у вас будет время, чтобы политика была полностью включена, прежде чем тестировать требование утверждения на следующем шаге.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Проверка требования к утверждению New-JournalRule задачи, определенной в политике привилегированного доступа

1. На локальном компьютере откройте и вопишитесь в модуль удаленной Exchange Online PowerShell в **модуле Microsoft Corporation** Microsoft Exchange Online Remote  >  **PowerShell с** помощью учетной записи Глобального администратора для тестовой среды.

2. В Exchange PowerShell создайте новое правило Журнала для организации:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. Просмотр ошибки "Недостаточные разрешения" в Exchange PowerShell:

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Запрос доступа для создания нового правила журнала с помощью New-JournalRule задачи

1. Вопишитесь в [центр администрирования Microsoft 365](https://admin.microsoft.com) с помощью учетной записи Глобального администратора для тестовой среды.

2. В Центре администрирования перейдите **к** Параметры  >  **безопасности & конфиденциальности.**  >  

3. Выберите **Управление политиками и запросами доступа.**

4. Выберите **новый запрос**. Из выпадаемого поля выберите соответствующие значения для организации:

    **Тип запроса:** Задача

    **Область действия запроса**: Exchange

    **Запрос на**: Новое правило журнала

    **Продолжительность (часы)**: 2

    **Комментарии.** Запрос разрешения на создание нового правила журнала

5. Выберите **Сохранить,** а затем выберите **Закрыть**. Ваш запрос будет отправлен группе одобрения по электронной почте.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Утверждение запроса на привилегированный доступ для создания нового правила журнала

1. Во входе [в центр администрирования Microsoft 365](https://admin.microsoft.com) с использованием учетных данных пользователя 3 в тестовой среде (член группы безопасности "Утверждения привилегированного доступа" в тестовой среде).

2. В Центре администрирования перейдите **к** Параметры  >  **безопасности & конфиденциальности.**  >  

3. Выберите **Управление политиками и запросами доступа.**

4. Выберите ожидающее запрос, а затем **выберите Утверждение,** чтобы предоставить доступ к учетной записи Глобального администратора для создания нового правила журнала. Учетная запись Глобального администратора (запрашивающий пользователь) получит подтверждение электронной почты о том, что одобрение было предоставлено.

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Тестирование создания нового правила журнала с привилегированным доступом, утвержденным для New-JournalRule задачи

1. На локальном компьютере откройте и впишитесь в модуль удаленной Exchange Online PowerShell в **модуле Microsoft Corporation** Microsoft Exchange Online Remote  >  **PowerShell с** помощью учетной записи Глобального администратора для тестовой среды.

1. В Exchange PowerShell создайте новое правило Журнала для организации:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. Просмотр того, что новое правило журнала было успешно создано в Exchange PowerShell.

## <a name="next-step"></a>Следующий этап

Ознакомьтесь [с дополнительными функциями](m365-enterprise-test-lab-guides.md#information-protection) и возможностями защиты информации в тестовой среде.

## <a name="see-also"></a>См. также

[Руководства по лаборатории тестирования для Microsoft 365 для предприятий](m365-enterprise-test-lab-guides.md)

[Обзор Microsoft 365 для предприятий](microsoft-365-overview.md)

[Документация по Microsoft 365 для предприятий](/microsoft-365-enterprise/)
