---
title: Использование Microsoft Teams классов с Canvas
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sovaish
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Интеграция Microsoft Teams классов с Canvas
ms.openlocfilehash: e8ab45de84fe8325f6d5b349deb96aa831d54e36
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454689"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a>Использование Microsoft Teams классов с Canvas

Microsoft Teams классов — это приложение Обучение Tools Interoperability (LTI), которое помогает преподавателям и учащимся легко перемещаться между Обучение системой управления (LMS) и Teams. Пользователи могут получать доступ к группам классов, связанным с их курсом непосредственно из LMS.

## <a name="prerequisites-before-deployment"></a>Необходимые условия перед развертыванием

> [!NOTE]
> Текущий класс Teams LTI поддерживает синхронизацию пользователей Canvas с Microsoft Azure Active Directory (AAD) в ограниченной области. 
> - Клиент должен иметь точное соответствие между полем Canvas (email, user ID или SIS ID) и upN в Microsoft AAD. Мы работаем над расширением гибкости функций синхронизации, но пока все пользователи Canvas, не совпадающие с upN в AAD, не будут добавлены в класс Teams, синхронизированный с Canvas. 
> - Только один клиент Майкрософт может использоваться для сопоставления пользователей между Canvas и Microsoft.
> - Чтобы избежать дублирования групп, необходимо отключить SDS перед использованием Teams класса LTI.

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365 Admin

Перед управлением интеграцией Microsoft Teams в Instructure Canvas важно, чтобы приложение **Microsoft-Teams-Sync-for-Canvas** Azure было одобрено администратором Microsoft Office 365 учреждения в клиенте Microsoft Azure, прежде чем завершить установку администрирования Canvas.

1. Во входе в Canvas.

2. Выберите **ссылку Администратор** в глобальной навигации, а затем выберите учетную запись.

3. В навигации администратора выберите **ссылку Параметры,** а затем вкладку **Интеграции.**

4. Включение Microsoft Teams синхронизации, включив очки.

   ![teams-sync](media/teams-sync.png)

5. Введите имя клиента Майкрософт и атрибут входа.

   Атрибут входа будет использоваться для связи пользователя Canvas с Azure Active Directory пользователем.

6. Выберите **обновление Параметры** один раз.

7. Чтобы утвердить доступ к приложению **Microsoft-Teams-Sync-for-Canvas** Azure, выберите ссылку на доступ к **клиенту Grant.** Вы будете перенаправлены в конечную точку согласия администратора платформы администрирования Майкрософт.

   ![permissions](media/permissions.png)

8. Выберите **Accept**.

## <a name="canvas-admin"></a>Администрирование Canvas

Настройка интеграции Microsoft Teams LTI 1.3.

В качестве администратора Canvas необходимо добавить приложение LTI Microsoft Teams классов в вашей среде. Обратите внимание на ID клиента LTI для приложения.

 - Microsoft Teams - 170000000000570

1. Access **Admin settings**  >  **Apps**.

2. Выберите **+ Приложение,** чтобы добавить Teams приложения LTI.

   ![внешние приложения](media/external-apps.png)

3. Выберите **по client ID** для типа конфигурации.

   ![добавление приложения](media/add-app.png)

4. Введите предоставленный клиентский ID и выберите **Отправить**.

   Вы заметите имя приложения Microsoft Teams классов LTI для client ID для подтверждения.

5. Нажмите кнопку **Установить**.

   Приложение Microsoft Teams классов LTI будет добавлено в список внешних приложений.
   
## <a name="enabling-the-lti-app-for-canvas-courses"></a>Включение приложения LTI для курсов Canvas

Чтобы использовать приложение LTI в течение курса, инструктор курса Canvas должен включить синхронизацию интеграций. Каждый курс должен быть включен инструктором для создания соответствующей группы; глобального механизма создания групп нет. Эта мера разработана в качестве меры предосторожности для предотвращения создания нежелательных групп.

Обратитесь к преподавателям в документацию [для](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) включения приложения LTI для каждого курса и завершения установки интеграции.
