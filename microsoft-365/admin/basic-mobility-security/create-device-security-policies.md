---
title: Создание политик безопасности устройств в Basic Mobility and Security
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
description: Используйте Basic Mobility и Security для создания политик устройств, которые защищают сведения о вашей организации.
ms.openlocfilehash: 5c8794b53dc11d1cee2fc13c8fbc4933e18dd9a3
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394091"
---
# <a name="create-device-security-policies-in-basic-mobility-and-security"></a>Создание политик безопасности устройств в Basic Mobility and Security

Вы можете использовать Basic Mobility и Security для создания политик устройств, которые помогают защитить сведения организации Microsoft 365 от несанкционированного доступа. Политики можно применить к любому мобильному устройству в организации, где пользователь устройства имеет применимую лицензию Microsoft 365 и зарегистрировал устройство в Basic Mobility and Security.

## <a name="before-you-begin"></a>Прежде чем начать

> [!IMPORTANT]
> Прежде чем создать политику мобильных устройств, необходимо активировать и настроить basic Mobility and Security. Дополнительные сведения см. в обзоре базовой мобильности и безопасности.

- Узнайте о устройствах, приложениях для мобильных устройств и параметрах безопасности, поддерживаемых Basic Mobility и Security. См. [возможности базовой мобильности и безопасности.](capabilities.md)
- Создайте группы безопасности, Microsoft 365 пользователей, для развертывания политик для пользователей и для них, которые могут быть заблокированы для Microsoft 365. Перед развертыванием новой политики организации рекомендуется проверить политику, развернув ее для небольшого количества пользователей. Вы можете создать и использовать группу безопасности, которая включает только себя или Microsoft 365 пользователей, которые могут протестировать политику для вас. Дополнительные данные о группах безопасности см. в [публикации Create, edit или delete a security group.](../email/create-edit-or-delete-a-security-group.md)
- Чтобы создать и развернуть политики базовой мобильности и безопасности в Microsoft 365, необходимо быть глобальным администратором Microsoft 365. Дополнительные сведения см. [в сайте Permissions in the Security & Compliance Center.](../../security/office-365-security/permissions-in-the-security-and-compliance-center.md)
- Перед развертыванием политик дайте организации знать о потенциальных последствиях регистрации устройства в Basic Mobility and Security. В зависимости от того, как настроить политики, некомплиентные устройства могут быть заблокированы для доступа к Microsoft 365, а данные, включая установленные приложения, фотографии и персональные данные на зарегистрированных устройствах, могут быть удалены.

> [!NOTE]
> Политики и правила доступа, созданные в базовой мобильности и безопасности для Microsoft 365 бизнес стандарт для Exchange ActiveSync почтовых ящиков мобильных устройств и правила доступа к устройствам, созданные в центре администрирования Exchange. После регистрации устройства в Basic Mobility and Security for Microsoft 365 бизнес стандарт для Exchange ActiveSync или правила доступа к устройствам, применяемого к устройству, игнорируется любая политика Exchange ActiveSync или правила доступа к устройству. Дополнительные дополнительные Exchange ActiveSync см. [в Exchange ActiveSync в Exchange Online.](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync)

## <a name="step-1-create-a-device-policy-and-deploy-to-a-test-group"></a>Шаг 1. Создание политики устройства и развертывание в тестовой группе

Перед запуском убедитесь, что активированы и настроены основные функции мобильности и безопасности. Инструкции см. в [обзоре базовой мобильности и безопасности.](overview.md)

1. В браузере введите <https://protection.office.com/devicev2> .

2. Нажмите кнопку **Создать политику**.

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Основные параметры политики мобильности и безопасности":::

3. На странице **Параметры политики** укажите требования, которые необходимо применить к мобильным устройствам в организации.

4. **Требуется управление профилем** электронной почты. Если включено, устройства, у них нет профиля электронной почты, управляемые Basic Mobility and Security, считаются не соответствующими требованиям. Устройство не может иметь управляемый профиль электронной почты, если оно неправильно настроено, или если пользователь вручную настроил учетную запись электронной почты на устройстве. Когда вы оставляете **его Не включен** (по умолчанию), этот параметр не оценивается на соответствие требованиям или несоблюдение. Инструкции о том, как пользователи могут быть совместимыми при выборе этого параметра, см. в примере существующей учетной записи [электронной почты.](/intune-user-help/existing-company-email-account-found)

5. На странице Вы хотите применить эту политику **сейчас?** Выберите группы, к которые вы хотите применить эту политику.

6. Выберите **Создать эту политику.**

Политика нажата на устройство каждого пользователя, к следующему входу политики для Microsoft 365 с помощью мобильного устройства. Если раньше пользователи не применяли политику к мобильному устройству после развертывания политики, они получают уведомление на своем устройстве, которое включает действия по регистрации и активации Basic Mobility and Security. Дополнительные сведения см. в [записи мобильного устройства с помощью Basic Mobility and Security.](enroll-your-mobile-device.md) Пока они не завершат регистрацию в службе Intune Basic Mobility and Security, доступ к электронной почте, OneDrive и другим службам ограничен. После завершения регистрации с помощью Корпоративный портал Intune приложения они могут использовать службы, и политика применяется к устройству.

## <a name="step-2-verify-that-your-policy-works"></a>Шаг 2. Убедитесь, что политика работает

После создания политики устройств убедитесь, что политика работает так, как вы ожидаете, прежде чем развернуть ее в организации.

1. В браузере введите [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Выберите **Просмотр списка управляемых устройств.**
3. Проверьте состояние устройств пользователя, к которым применяется политика. Необходимо управлять **состоянием** **устройств.**
4. Вы также можете сделать полное или выборочное удаление на  устройстве, нажав на сброс **или** удаление данных компании из кнопки **Управление** после выбора устройства. Инструкции см. в приложении [Wipe a mobile device in Microsoft 365.

## <a name="step-3-deploy-a-policy-to-your-organization"></a>Шаг 3. Развертывание политики в организации

После создания политики устройства и проверки ее работы необходимо развернуть в организации.

1. Из типа браузера: [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Выберите политику, которая необходимо развернуть, и выберите **Изменить** рядом с **группами, к которые применяются.**
3. Поиск группы для добавления и нажмите кнопку **Выберите**.
4. Выберите **параметр Закрыть** и **Изменить.**
5. Выберите **политику Close** и **Edit.**

Политика оттеснена на мобильное устройство каждого пользователя, к следующему входу политики для Microsoft 365 с мобильного устройства. Если у пользователей не было политики, применяемой к мобильному устройству, они получают уведомление на своем устройстве с шагами для регистрации и активации для Basic Mobility and Security. После завершения регистрации политика применяется к устройству. Дополнительные сведения см. в [записи мобильного устройства с помощью Basic Mobility and Security.](enroll-your-mobile-device.md)

## <a name="step-4-block-email-access-for-unsupported-devices"></a>Шаг 4. Блокировка доступа к электронной почте для неподтверченных устройств

Чтобы защитить сведения организации, необходимо заблокировать доступ к электронной Microsoft 365 для мобильных устройств, которые не поддерживаются базовой мобильностью и безопасностью. Список поддерживаемых устройств см. в [списке поддерживаемых устройств.](../../admin/basic-mobility-security/capabilities.md)

**Чтобы заблокировать доступ к приложениям:**

1. В браузере введите [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Выберите **параметры доступа к устройствам для всей организации.**
3. Чтобы заблокировать неподдермываемую поддержку устройств, выберите **Блок** под Если устройство не поддерживается базовой мобильностью и безопасностью для **Microsoft 365,** а затем выберите **Сохранить**.

   :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Вариант блокировки базовой мобильности и безопасности":::

## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>Этап 5. Выбор групп безопасности, которые будут исключены из проверок условного доступа

Если вы хотите исключить определенных пользователей из проверок условного доступа на мобильных устройствах, и для них создана одна или несколько групп безопасности, добавьте эти группы сюда. В этих группах не будут применяться политики для поддерживаемых мобильных устройств. Это рекомендуемый вариант, если вы больше не хотите использовать базовую мобильность и безопасность в организации.

1. В браузере введите [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Выберите **параметры доступа к устройствам для всей организации.**

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Basic Mobility and Security create a policy option":::

3. Выберите **Добавить,** чтобы добавить группу безопасности с пользователями, которые необходимо исключить из заблокированного доступа к Microsoft 365. Если пользователь добавлен в этот список, он может получить доступ Microsoft 365 электронной почты при использовании неподтверченного устройства.

4. Выберите группу безопасности, используемую в панели **Select group.**

5. Выберите имя и добавьте **сохранить**  >  .

6. На панели **параметров доступа к устройствам** для всей Организации выберите **Сохранить**.

   :::image type="content" source="../../media/basic-mobility-security/bms-8-allow-access.png" alt-text="Базовые возможности мобильности и безопасности позволяют получить доступ":::

## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>Как политики безопасности влияют на разные типы устройств?

При применении политики к устройствам пользователей влияние на каждое устройство несколько различается между типами устройств. Примеры влияния политик см. в следующей таблице.

|**Политика безопасности**|**Android 4 и более поздний**|**Samsung KNOX**|**iOS 6 и более поздний**|**Примечания**|
|:-----|:-----|:-----|:-----|:-----|
|Требовать шифрование резервных копий|Нет|Да|Да|Требуется шифрование резервного копирования в iOS.|
|Блокировать резервное копирование в облаке|Да|Да|Да|Блокировать резервное копирование Google для Android (параметр недоступен), облачное резервное копирование для iOS.|
|Блокировать синхронизацию документов|Нет|Нет|Да|iOS: блокировать документы в облаке|
|Блокировать синхронизацию фотографий |Нет|Нет|Да|iOS (собственный): блокировать Photo Stream.|
|Блокировать снимки экрана |Нет|Да|Да|Блокируется при попытке.|
|Блокировать видеоконференции |Нет|Нет|Да|FaceTime заблокирован на iOS, а не Skype других.|
|Блокировать отправку данных диагностики |Нет|Да|Да|Блокировать отправку отчета о сбое Google для Android.|
|Блокировать доступ к магазину приложений |Нет|Да|Да|Значок магазина приложений отсутствует на главной странице Android, отключен в Windows, отсутствует в iOS.|
|Требовать пароль для магазина приложений |Нет|Нет|Да|iOS: Пароль требуется для покупок в iTunes.|
|Блокировать подключение съемных носителей |Нет|Да|Недоступно|Android: SD-карта серый в настройках, Windows сообщает пользователю, установленные приложения недоступны|
|Блокировать подключение Bluetooth |См. заметки|См. заметки|Да|Мы не можем отключить BlueTooth как параметр на Android. Вместо этого мы отключаем все транзакции, которые требуют BlueTooth: advanced Audio Distribution, Audio/Video Remote Control, устройства без рук, гарнитуры, Телефон доступа к книгам и серийный порт. При использовании этих функций в нижней части страницы появляется небольшое всплывающее сообщение.|

## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>Что происходит при удалении самой политики или удалении пользователя из политики?

При удалении политики или удалении пользователя из группы, в которую была развернута политика, с устройства пользователя могут быть удалены параметры политики, Microsoft 365 профиль электронной почты и кэшировали сообщения электронной почты. В следующей таблице см., что удаляется для различных типов устройств.

|**Что удалено**|**iOS 6 и более поздний**|**Android 4 и более поздний (включая Samsung KNOX)**|
|:-----|:-----|:-----|
|Управляемые профили<sup>электронной почты 1</sup>|Да|Нет|
|Блокировать резервное копирование в облаке|Да|Нет|

<sup>1</sup> Если политика развернута с  управляемым профилем электронной почты, управляемый профиль электронной почты и кэшные сообщения в этом профиле удаляются с устройства пользователя.

Политика удаляется с мобильного устройства для каждого пользователя, политика применяется к следующему времени, когда устройство проверяется с помощью Basic Mobility and Security. Если развернута новая политика, применяемая к этим устройствам пользователей, им будет предложено повторно зарегистрироваться в Basic Mobility and Security.

Вы также можете полностью или выборочно стереть с устройства организационные сведения. Дополнительные сведения см. в [приложении Wipe a mobile device in Basic Mobility and Security.](wipe-mobile-device.md)

## <a name="related-content"></a>См. также:

[Обзор базовой мобильности и безопасности](overview.md) (статья)\
[Возможности базовой мобильности и безопасности](capabilities.md) (статья)