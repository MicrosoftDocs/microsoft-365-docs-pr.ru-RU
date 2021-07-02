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
ms.openlocfilehash: 50e4e8ef912a8f19f379bba29b328a5a27358b5c
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256907"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a>Использование Microsoft Teams классов с Canvas

> [!IMPORTANT]
> Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска. Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.

Microsoft Teams классов — это приложение Обучение Tools Interoperability (LTI), которое помогает преподавателям и учащимся легко перемещаться между Обучение системой управления (LMS) и Teams. Пользователи могут получать доступ к группам классов, связанным с их курсом непосредственно из LMS.

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
