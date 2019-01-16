---
title: Распространенные удостоверения и устройства для доступа к политики - Microsoft 365 Enterprise | Документация Microsoft
description: Описание рекомендаций Майкрософт по применению политик и конфигураций доступа для удостоверений и устройств.
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: ab8454c27cd57b6bd5cc8df6e1526ee2950ac998
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871074"
---
# <a name="common-identity-and-device-access-policies"></a>Основные политики доступа для удостоверений и устройств
В этой статье описываются общие, рекомендуется политик безопасности доступа к облачные службы, опубликовано включая локальных приложений с Azure AD прокси приложения. 

В этом руководстве содержатся инструкции по развертыванию рекомендуемые политики в среде вновь подготовить к работе. Настройка этих политик в отдельном лабораторной среде позволяет понять и оценка рекомендуемые политики перед поэтапное развертывание вашей подготовки и рабочей среды. Только что подготовленные среда может быть только в облаке или комбинированным.  

## <a name="policy-set"></a>Политика set 

На следующем рисунке показано несколько набора политик. Показано какой уровень защиты каждой политики применяется к и ли политики применяются к ПК или телефоны и планшетные ПК или обе категории устройств. Также указывается, где этих политик.

![Общие политики для настройки удостоверения и устройства доступа](../images/Identity_device_access_policies_byplan.png)


Далее в этой статье описывается, как настроить эти политики. 

Прежде чем отправлять заявки на получение устройств в Intune Software assurance, устройство во временном пользовании целям пользователя рекомендуется использовать многофакторной проверки подлинности. Также необходимо зарегистрировать устройств в Intune до применения политики соответствия устройства.

Чтобы предоставить время для выполнения этих задач, рекомендуется реализации политик базового в том порядке, перечисленные в следующей таблице. Тем не менее политики многофакторной проверкой Подлинности для защиты конфиденциальных и сильно регулируемого могут быть реализованы в любое время.


|Уровень защиты|Политики.|Дополнительные сведения|
|:---------------|:-------|:----------------|
|**Базовый уровень**|[После входа в риска *Средний* или *высокий* требуют многофакторной проверкой Подлинности](#require-mfa-based-on-sign-in-risk)| |
|        |[Блокировать клиенты, не поддерживающие современных проверки подлинности](#block-clients-that-dont-support-modern-authentication)|Клиентов, не использующих современных проверки подлинности может обходить правила условного доступа, поэтому важно для блокировки этих|
|        |[Пользователи высокого риска смену пароля](#high-risk-users-must-change-password)|Заставляет пользователя должен сменить пароль при входе в высокого риска действия в случае обнаружения для своей учетной записи|
|        |[Определение политик защиты от приложения](#define-app-protection-policies)|Одна политика на платформу (операций ввода-вывода, Android, Windows).|
|        |[Требовать одобренных приложений](#require-approved-apps)|Обеспечивает защиту мобильных приложений для телефонов и планшетные ПК|
|        |[Определение политики соответствия устройств](#define-device-compliance-policies)|Одна политика для каждой платформы|
|        |[Требовать спецификации ПК](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Обеспечивает управление Intune ПК|
|**Конфиденциальный**|[После входа в риска *низкий*, *Средний* или *высокий* требуют многофакторной проверкой Подлинности](#require-mfa-based-on-sign-in-risk)| |
|         |[Требовать спецификации ПК *и* мобильных устройств.](#require-compliant-pcs-and-mobile-devices)|Обеспечивает управление Intune для и телефона/планшетные ПК|
|**Строго регулируемый уровень**|[*Всегда* требовать многофакторной проверкой Подлинности](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a>Назначение политик для пользователей
Прежде чем настраивать политики, определяют группы Azure AD, используемой для каждого уровня защиты. Как правило базового защиты применяется ко всем пользователям в организации. Пользователь, который включен для базовой и защите конфиденциальных будут иметь все политики базового применены, а также конфиденциальных политик. Защита накопительным и наиболее строгими политикой. 

Рекомендуется создать группу Azure AD для исключения условного доступа. Добавление этой группы на все правила условного доступа в разделе «Исключить». Это позволяет метод для обеспечения доступа к пользователю во время устранения неполадок access. Рекомендуется в качестве временное решение. Отслеживайте этой группы для изменения и убедитесь, что группа исключения используется только правильно. 

Ниже приведен пример назначение пользователя и исключений.

![Назначение пользователя пример и исключения для правил многофакторной проверкой Подлинности](../images/identity-access-policies-assignment.png)

На рисунке «верхней секретный X группе проекта» назначается политику условного доступа, который требует многофакторной проверкой Подлинности *всегда*. Быть разумное при применении более высокий уровень защиты пользователей. Участники этой группы проекта должны предоставляют следующие способы проверки подлинности при каждом входе в систему, даже в том случае, если они могут не видеть сильно регулируемого содержимого.  

Все группы Azure AD, создаваемого в рамках этих рекомендаций по использованию должен быть создан как группы Office 365. Это особенно важно для развертывания защиты информации Azure (AIP), когда защита документов в SharePoint Online.

![Снимок экрана для создания группы Office 365](../images/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a>Требовать многофакторной проверкой Подлинности на основании входа риска
Перед требованием многофакторной проверкой Подлинности, используйте политику регистрации многофакторной проверкой Подлинности удостоверения защиты для регистрации пользователей для многофакторной проверкой Подлинности. После регистрации пользователей, вы можете принудительно многофакторной проверкой Подлинности для входа. [Предварительные работы](identity-access-prerequisites.md) включает в себя регистрация всем пользователям с многофакторной проверкой Подлинности.

Чтобы создать политику условного доступа, выполните следующие действия. 

1. Перейдите в [Azure портала](https://portal.azure.com)и выполнить вход. После того как вы успешно выполнили вход, вы изучите Azure панели мониторинга.

2. В меню слева выберите **Azure Active Directory**.

3. В разделе **Безопасность** выберите **Условный доступ**.

4. Выберите **Создать политику**.

![Базовая политика условного доступа](./media/secure-email/CA-EXO-policy-1.png)

 Следующих таблицах описаны параметры политики условного доступа для реализации для этой политики.

**Назначения**

|Type|Элемент Property|Значения|Примечания|
|:---|:---------|:-----|:----|
|Пользователи или группы|Включить|Выберите пользователей и группы — выберите определенную группу безопасности, содержащую целевых пользователей|Следует начать с группы безопасности, в которую входят пользователи пилотного проекта|
||Исключить|Исключение группы безопасности, учетных записей служб (удостоверений приложений)|Членство в изменено на основе временные по необходимости|
|Облачные приложения|Включить|Выберите приложения, правила для применения к. Например выберите Office 365 Exchange Online||
|Условия|Настроено|Да|Выполните настройку в соответствии с вашей средой и потребностями|
|Риск при входе|Уровень риска||Просмотрите руководства в следующей таблице|

**Риск при входе**

Примените параметры на основании уровень защиты, который вы используете.

|Свойство|Уровень защиты|Значения|Примечания|
|:---|:---------|:-----|:----|
|Уровень риска|Базовый уровень|Высокий, средний|Выберите оба варианта|
| |Конфиденциальный|High, medium, низкой|Выберите все три варианта|
| |Строго регулируемый уровень| |Не устанавливайте флажок всегда внедрение многофакторной проверкой Подлинности все параметры|

**Средства управления доступом**

|Type|Элемент Property|Значения|Примечания|
|:---|:---------|:-----|:----|
|Предоставить|Предоставление доступа|True|Выбрано|
||Требовать многофакторную идентификацию|True|Check|
||Требовать устройства будут отмечены как соответствующая требованиям|False||
||Требовать гибридного Azure присоединился к AD устройства|False||
||Требовать утвержденных клиентского приложения|False||
||Требовать все выбранные средства управления|True|Выбрано|

> [!NOTE]
> Убедитесь, что этот параметр включен, выбрав **на**. Также рекомендуется использовать средство [что делать, если](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) для проверки политики.



## <a name="block-clients-that-dont-support-modern-authentication"></a>Блокировать клиенты, не поддерживающие современных проверки подлинности
1. Перейдите в [Azure портала](https://portal.azure.com)и выполнить вход. После того как вы успешно выполнили вход, вы изучите Azure панели мониторинга.

2. В меню слева выберите **Azure Active Directory**.

3. В разделе **Безопасность** выберите **Условный доступ**.

4. Выберите **Создать политику**.

Следующих таблицах описаны параметры политики условного доступа для реализации для этой политики.

**Назначения**

|Type|Элемент Property|Значения|Примечания|
|:---|:---------|:-----|:----|
|Пользователи или группы|Включить|Выберите пользователей и группы — выберите определенную группу безопасности, содержащую целевых пользователей|Следует начать с группы безопасности, в которую входят пользователи пилотного проекта|
||Исключить|Исключение группы безопасности, учетных записей служб (удостоверений приложений)|Изменение членства по мере необходимости на временной основе|
|Облачные приложения|Включить|Выберите приложения, правила для применения к. Например выберите Office 365 Exchange Online||
|Условия|Настроено|Да|Настройка клиентского приложения|
|Клиентские приложения|Настроено|Да|Мобильных приложений и настольных клиентов, других клиентских программах (оба флажка)|

**Средства управления доступом**

|Type|Элемент Property|Значения|Примечания|
|:---|:---------|:-----|:----|
|Предоставить|Заблокировать доступ|True|Выбрано|
||Требовать многофакторную идентификацию|False||
||Требовать устройства будут отмечены как соответствующая требованиям|False||
||Требовать гибридного Azure присоединился к AD устройства|False||
||Требовать утвержденных клиентского приложения|False||
||Требовать все выбранные средства управления|True|Выбрано|

> [!NOTE]
> Убедитесь, что этот параметр включен, выбрав **на**. Также рекомендуется использовать средство [что делать, если](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) для проверки политики.



## <a name="high-risk-users-must-change-password"></a>Пользователи высокого риска смену пароля
Убедитесь, что все высокого риска пользователей атаке учетные записи, принудительно выполнить смены пароля при вход в систему, необходимо установить следующие политики.

Выполните вход в систему [портал Microsoft Azure (http://portal.azure.com) ](http://portal.azure.com/) с свои учетные данные администратора, а затем перейдите к **Azure AD защиту > политики пользователя риска**.

**Назначения**

|Type|Элемент Property|Значения|Примечания|
|:---|:---------|:-----|:----|
|Users|Включить|Все пользователи|Выбрано|
||Исключить|Нет||
|Условия|Риск пользователя|Высокий|Выбрано|

**Элементы управления**

| Type | Элемент Property | Значения                  | Примечания |
|:-----|:-----------|:------------------------|:------|
|      | Доступ     | Разрешить доступ            | True  |
|      | Доступ     | Требовать смену пароля | True  |

**Проверки:** неприменимо

> [!NOTE]
> Убедитесь, что этот параметр включен, выбрав **на**. Также рекомендуется использовать средство [что делать, если](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) для тестирования политики

## <a name="define-app-protection-policies"></a>Определение политик защиты от приложения
Политики в отношении защиты приложений определить, какие приложения разрешено и действия, которые необходимо выполнить с данными вашей организации. Создание приложения Intune политик защиты от Azure портала. 

Создайте политику для каждой платформы.
- операций ввода-вывода
- Android,
- Windows 10

Чтобы создать новую политику защиты приложения, выполните вход в портал Microsoft Azure с помощью учетных данных администратора и перейдите на **мобильных приложениях > политики в отношении защиты приложений**. Последовательно выберите пункты **Добавить политику**.

Существует несколько различается защиты приложения параметры политики между iOS и Android (en). Ниже политики — это специально для Android. Используйте это в качестве руководства для других политик.

Рекомендуемые список приложений включает в себя следующее:
- PowerPoint
- Excel
- Word
- Microsoft Teams
- Microsoft SharePoint
- Средство просмотра Microsoft Visio
- OneDrive
- OneNote
- Outlook

В следующих таблицах описываются рекомендуемые параметры:

|Type|Элемент Property|Значения|Примечания|
|:---|:---------|:-----|:----|
|Перемещение данных|Запретить резервное копирование на Android|Да|В iOS это касается iTunes и iCloud|
||Разрешить приложению передавать данные в другие приложения|Приложения, управляемые политикой||
||Разрешить приложению получать данные от других приложений|Приложения, управляемые политикой||
||Запрет команды "Сохранить как"|Да||
||Выбор служб хранения данных, в которые могут быть сохранены данные организации|OneDrive для бизнеса в SharePoint||
||Ограничить вырезание, копирование и вставку данных между приложениями|Политики управляемых приложений с помощью вставки в||
||Ограничить веб-контент, отображаемый в Managed Browser|Нет||
||Шифрование данных приложения|Да|В iOS выберите параметр "Когда устройство заблокировано"|
||Отключать шифрование приложения при включении устройства|Да|Отключите этот параметр, чтобы избежать двойного шифрования|
||Отключить синхронизацию контактов|Нет||
||Отключение печати|Нет||
|Доступ|Требовать ПИН-код для доступа|Да||
||Выберите тип|Числовой||
||Разрешить простой ПИН-код|Нет||
||Длина ПИН-кода|6||
||Разрешить вход с использованием отпечатков пальцев вместо ПИН-кода|Да||
||Отключить приложение ПИН-код при управляемых устройств ПИН-кода|Да||
||Требуются учетные данные организации для access|Нет||
||Перепроверять требования к доступу через (мин)|30||
||Блокировать снимки экрана и Android Assistant|Нет|В iOS этот параметр недоступен|
|Требования к безопасности входа|ПИН-код максимальное число попыток|5|Сброс ПИН-кода|
||Период отсрочки в автономном режиме|720|Заблокировать доступ|
||Интервал в автономном режиме до очистки данных приложения (дн.)|90|Очистка данных|
||Корневой каталог/Jailbroken устройств| |Очистка данных|

Закончив настройку, не забудьте выберите пункт «Создать». Повторите действия, описанные выше и замените выбранной платформы (раскрывающийся список) операций ввода-вывода. При этом создается два политики в отношении приложений, поэтому после создания политики, затем назначать группы к политике и его развертывание.

Чтобы изменить политики и назначения этих политик для пользователей, узнайте, [как для создания и назначения политики в отношении защиты приложений](https://docs.microsoft.com/intune/app-protection-policies). 

## <a name="require-approved-apps"></a>Требовать одобренных приложений
Чтобы сделать обязательным наличие одобренных приложений:

1. Перейдите в [Azure портала](https://portal.azure.com)и выполнить вход. После того как вы успешно выполнили вход, вы изучите Azure панели мониторинга.

2. В меню слева выберите **Azure Active Directory**.

3. В разделе **Безопасность** выберите **Условный доступ**.

4. Выберите **Создать политику**.

5. Введите имя политики, а затем выберите **Пользователей и группы**, к которым нужно ее применить.

6. Выберите **Облачные приложения**.

7. Выберите команду **выбрать приложения**, выберите нужный приложений в списке **облачных приложений** . Например выберите Office 365 Exchange Online. Нажмите кнопку **выбрать** и **сделано**.

8. Выберите **Предоставление** в разделе **Элементы управления доступом**.

9. Нажмите кнопку **предоставить доступ**, выберите **Требовать утверждения клиентского приложения**. Для нескольких элементов управления выберите **Требовать выбранные элементы управления**, а затем выберите команду **выбрать**. 

10. Нажмите кнопку **Создать**.

## <a name="define-device-compliance-policies"></a>Определение политики соответствия устройств

Политики соответствия устройства определить требования, устройств, должна придерживаться пометить следующим требованиям. Создание политики соответствия из портала Azure Intune устройства. 

Создайте политику для каждой платформы.
- Android
- Android enterprise
- операций ввода-вывода
- macOS
- Windows Phone 8.1
- Windows 8.1 и более поздних версий
- Windows 10 и более поздних версий

Для создания политики соответствия устройства, войдите портал Microsoft Azure с помощью учетных данных администратора и перейдите на **Intune > соответствия устройства**. Выберите **Создать политику**.

Для Windows 10 рекомендуются следующие параметры.

**Устройство работоспособности: правила оценки службы аттестации работоспособности Windows**

|Элемент Property|Значения|Примечания|
|:---------|:-----|:----|
|Необходимо использовать BitLocker|Обязательность||
|Требовать безопасного загрузки включить на устройстве|Обязательность||
|Требовать целостность кода|Обязательность||


**Свойства устройства**

|Type|Элемент Property|Значения|Примечания|
|:---|:---------|:-----|:----|
|Версия операционной системы|all|Не настроено||

Для всех развернуты выше политики следует учитывать они должны предназначены для группы пользователей. Это можно сделать, создав политику (при сохранении) или более поздней версии, выбрав **Управление развертывания** в разделе **Политика** (же уровне, что Add).

**Безопасность системы**

|Type|Элемент Property|Значения|Примечания|
|:---|:---------|:-----|:----|
|Password|Требование ввести пароль для разблокировки мобильных устройств|Обязательность||
||Простых паролей|Блок||
||Введите пароль|Устройство по умолчанию||
||Минимальная длина пароля|6||
||Максимальное число минут бездействия, прежде чем пароль|15 |Этот параметр поддерживается для Android версии 4.0 и более или НОКСА 4.0 и выше. Для операций ввода-вывода устройств поддерживается для iOS 8.0 и выше|
||Срок действия пароля (дней)|41||
||Число предыдущих паролей для предотвращения повторного использования|5||
||Требовать пароль при возврате устройства из состояния простоя (Mobile и Holographic)|Обязательность|Доступные для Windows 10 и более поздних версий|
|Шифрование|Шифрование хранения данных на устройстве|Обязательность||
|Безопасность устройств|Брандмауэр|Обязательность||
||Защита от вирусов|Обязательность||
||Антишпионское|Обязательность|Этот параметр требуется решение по обеспечению защита от шпионского по зарегистрирован в центре обеспечения безопасности Windows|
|Защитник|Защитник Windows защиты от вредоносных программ|Обязательность||
||Минимальная версия Защитника Windows защиты от вредоносных программ||Поддерживается только для настольных компьютеров Windows 10. Корпорация Майкрософт рекомендует версий не более 5 за из наиболее поздней версии|
||В актуальном состоянии подписи Защитник Windows защиты от вредоносных программ|Обязательность||
||"Защита в режиме реального времени"|Обязательность|Поддерживается только для настольных компьютеров Windows 10|

**ATP в Защитнике Windows**

|Type|Элемент Property|Значения|Примечания|
|:---|:---------|:-----|:----|
|Правила защиты от угроз дополнительные Защитника Windows|Требовать устройства в или в разделе оценки риска компьютера|Средние||

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Требовать спецификации (но не соответствует спецификации телефоны и планшетные ПК)
Перед добавлением политики требуется совместимый ПК, убедитесь, что регистрация устройств для управления в Intune. Прежде чем отправлять заявки на получение устройств в Intune Software assurance, устройство во временном пользовании целям пользователя рекомендуется использовать многофакторной проверки подлинности. 

Чтобы сделать обязательным наличие спецификации ПК:

1. Перейдите в [Azure портала](https://portal.azure.com)и выполнить вход. После того как вы успешно выполнили вход, вы изучите Azure панели мониторинга.

2. В меню слева выберите **Azure Active Directory**.

3. В разделе **Безопасность** выберите **Условный доступ**.

4. Выберите **Создать политику**.

5. Введите имя политики, а затем выберите **Пользователей и группы**, к которым нужно ее применить.

6. Выберите **Облачные приложения**.

7. Выберите команду **выбрать приложения**, выберите нужный приложений в списке **облачных приложений** . Например выберите Office 365 Exchange Online. Нажмите кнопку **выбрать** и **сделано**.

8. Чтобы сделать обязательным наличие спецификации, но не соответствует спецификации телефоны и планшетные ПК, выберите **условия** и **платформах устройств**. Выберите команду **выбрать платформах устройств** и выберите **Windows** и **macOS**.

9. Выберите **Предоставление** в разделе **Элементы управления доступом**.

10. Нажмите кнопку **предоставить доступ**, выберите **Требовать устройство для помечен как совместимый с**. Для нескольких элементов управления выберите **Требовать все выбранные элементы управления**, а затем выберите команду **выбрать**. 

11. Нажмите кнопку **Создать**.

Целью является требуют спецификации ПК *и* мобильных устройств, не устанавливайте платформ. Это обеспечивает соответствие требованиям для всех устройств. 

## <a name="require-compliant-pcs-and-mobile-devices"></a>Требовать спецификации ПК *и* мобильных устройств.

Чтобы сделать обязательным наличие соответствия для всех устройств:

1. Перейдите в [Azure портала](https://portal.azure.com)и выполнить вход. После того как вы успешно выполнили вход, вы изучите Azure панели мониторинга.

2. В меню слева выберите **Azure Active Directory**.

3. В разделе **Безопасность** выберите **Условный доступ**.

4. Выберите **Создать политику**.

5. Введите имя политики, а затем выберите **Пользователей и группы**, к которым нужно ее применить.

6. Выберите **Облачные приложения**.

7. Выберите команду **выбрать приложения**, выберите нужный приложений в списке **облачных приложений** . Например выберите Office 365 Exchange Online. Нажмите кнопку **выбрать** и **сделано**.

8. Выберите **Предоставление** в разделе **Элементы управления доступом**.

9. Нажмите кнопку **предоставить доступ**, выберите **Требовать устройство для помечен как совместимый с**. Для нескольких элементов управления выберите **Требовать все выбранные элементы управления**, а затем выберите команду **выбрать**. 

10. Нажмите кнопку **Создать**.

При создании этой политики, не устанавливайте флажок платформ. Это приводит к использованию совместимые устройства.




<!---
#### Data loss prevention
The goal for your device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain or enroll their PCs into management with Microsoft Intune or System Center Configuration Manager.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact

For most organizations, it is important to be able to set user expectations around when and for which conditions they will be expected to sign into Office 365 to access their email.  

Users typically benefit from single sign-on (SSO) except during the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users may be asked to MFA whenever a **medium or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Sensitive
This section describes the recommendations for the sensitive tier of data, identity, and device protection. These recommendations are for customers who have a subset of data that must be protected at higher levels or require all data to be protected at these higher levels.

You can apply increased protection to all or specific data sets in your Office 365 environment. For example, you can apply policies to ensure sensitive data is only shared between protected apps to prevent data loss. We recommend protecting identities and devices that access sensitive data with comparable levels of security.

### Conditional access policy settings
#### Identity protection

You can give users single sign-on (SSO) experience as described in earlier sections. You only need to intervene when necessary based on [risk events](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-risk-events).   

* Require MFA on **low or above** risk sessions
* Require secure password change for high risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data loss prevention

The goal for these device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their PCs to an Active Directory Domain or enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 email.

Users typically benefit from single sign-on (SSO) except under the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to MFA whenever a **low or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Highly regulated
This section describes the recommendations for the highly regulated tier of data, identity, and device protection. These recommendations are for customers who may have a very small amount of data that is highly classified, trade secret, or regulated data. Microsoft provides capabilities to help organizations meet these requirements, including added protection for identities and devices.

### Conditional access policy settings
#### Identity protection

For the highly regulated tier Microsoft recommends enforcing MFA for all new sessions.
* Require MFA for all new sessions
* Require secure password change for **high** risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data Loss Prevention
The goal for these device and app management policies is to prevent data loss in the event of a lost or stolen device. This is done by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

For the highly regulated tier, we recommend requiring apps that support Intune App Protection policy running only on Intune compliant or domain-joined devices.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain, **or** enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that devices used to access Office 365 email and files are managed by Intune or company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are Low risk as determined by a third-party MTP like Lookout or SkyCure.|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 files.

* Users configured as highly regulated will be required to re-authenticate with MFA after their session expires.
* When users at risk sign-in they will be asked to change their password after completing MFA.
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to perform MFA whenever they begin a new session.  
  * Users will be required to use email apps that support the Intune App Protection SDK
  * Users will be required to access emails from Intune compliant or AD domain-joined devices.
--->
## <a name="next-steps"></a>Дальнейшие шаги

[Узнайте о рекомендуемых политиках для защиты электронной почты](secure-email-recommended-policies.md)
