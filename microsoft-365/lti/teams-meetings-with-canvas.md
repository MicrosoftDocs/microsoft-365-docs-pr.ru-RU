---
title: Использование Microsoft Teams собраний с Canvas
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
description: Интеграция Microsoft Teams собраний с Canvas
ms.openlocfilehash: 7e13052cb029fef369f6386c2039785e40acc4ff
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409096"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a>Использование Microsoft Teams собраний с Canvas

> [!IMPORTANT]
> Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска. Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.

Microsoft Teams собрания — это приложение Обучение средства взаимодействия (LTI), которое помогает преподавателям и учащимся легко перемещаться между Обучение системой управления (LMS) и Teams. Пользователи могут получать доступ к группам классов, связанным с их курсом непосредственно из LMS.

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365 Admin

Перед управлением интеграцией Microsoft Teams в Instructure Canvas важно, чтобы приложение **Microsoft-Teams-Sync-for-Canvas** Azure было одобрено администратором Microsoft Office 365 учреждения в клиенте Microsoft Azure, прежде чем завершить установку администрирования Canvas.

1. Во входе в Canvas.

2. Выберите **ссылку Администратор** в глобальной навигации, а затем выберите учетную запись.

3. В навигации администратора выберите **ссылку Параметры,** а затем вкладку **Интеграции.**

4. Введите имя клиента Майкрософт и атрибут входа.

   Атрибут входа будет использоваться для связи пользователя Canvas с Azure Active Directory пользователем.

5. Выберите **обновление Параметры** один раз.

6. Чтобы утвердить доступ к приложению **Microsoft-Teams-Sync-for-Canvas** Azure, выберите ссылку на доступ к **клиенту Grant.** Вы будете перенаправлены в конечную точку согласия администратора платформы администрирования Майкрософт.

   ![permissions](media/permissions.png)

7. Выберите **Accept**.

8. Включи Microsoft Teams синхронизацию, включив очки.

   ![teams-sync](media/teams-sync.png)

## <a name="canvas-admin"></a>Администрирование Canvas

Настройка интеграции Microsoft Teams LTI 1.3.

В качестве администратора Canvas необходимо добавить приложение LTI Microsoft Teams собраний в вашей среде. Обратите внимание на ID клиента LTI для приложения.

 - Microsoft Teams - 170000000000703

1. Access **Admin settings**  >  **Apps**.

2. Выберите **+ Приложение,** чтобы добавить Teams приложения LTI.

   ![внешние приложения](media/external-apps.png)

3. Выберите **по client ID** для типа конфигурации.

   ![добавление приложения](media/add-app.png)

4. Введите предоставленный клиентский ID и выберите **Отправить**.

   Вы заметите имя приложения Microsoft Teams собраний LTI для client ID для подтверждения.

5. Нажмите кнопку **Установить**.

   Приложение Microsoft Teams собраний LTI будет добавлено в список внешних приложений.
   
## <a name="enable-for-canvas-courses"></a>Включить курсы canvas

Чтобы использовать LTI в течение курса, инструктор курса Canvas должен включить синхронизацию интеграций. Каждый курс должен быть включен инструктором для создания соответствующего Teams; глобального механизма создания Teams нет. Это разработано с осторожностью, чтобы предотвратить нежелательные Teams создания.

Обратитесь к преподавателям в [документацию для](https://support.microsoft.com/en-us/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) включения LTI для каждого курса и завершения установки интеграции.
