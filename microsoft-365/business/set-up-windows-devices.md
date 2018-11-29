---
title: Настройка устройств с Windows для пользователей Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: 'Узнайте, как настраивать Windows устройств под управлением Windows 10 Pro для пользователей Microsoft 365 для бизнеса. '
ms.openlocfilehash: 482199b175c568bfae420619aa02024303894789
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870652"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-users"></a>Настройка устройств с Windows для пользователей Microsoft 365 Business

## <a name="prerequisites"></a>Необходимые компоненты

Перед настройкой устройств с Windows для пользователей Microsoft 365 Business убедитесь, что на всех устройствах установлена система Windows 10 Pro версии 1703 (обновление Creators Update). Наличие ОС Windows 10 Pro является необходимым условием для развертывания Windows 10 Business  набора облачных служб и функций управления устройствами, который дополняет возможности этой операционной системы и предназначен для централизованного управления средой Windows 365 Business и ее безопасностью.
  
Если у вас есть устройства с Windows под управлением операционной системы Windows 7 Pro, Windows 8 Pro или Windows 8.1 Pro, вы можете перейти на Windows 10 в рамках подписки Microsoft 365 Business.
  
Дополнительные сведения о переводе устройств с Windows на версию Windows 10 Pro Creators Update приведены в следующей статье: [Обновление устройств с Windows до Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md)
  
Чтобы проверить, выполнено ли обновление и работает ли оно, ознакомьтесь со статьей [Проверка перевода устройства на Windows 10 для бизнеса](set-up-windows-devices.md#bkmk_verifywin10). 
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a>Добавление устройств с Windows 10 в каталог Azure AD организации

После перевода всех корпоративных устройств с Windows 10 на версию Windows 10 Pro Creators Update их можно добавить в каталог Azure Active Directory организации. Добавленные устройства автоматически переводятся на версию Windows 10 для бизнеса, которая входит в состав подписки на Microsoft 365 Business.
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a>Для новых (или недавно переведенных) устройств с Windows 10 Pro

Для новых устройств с системой Windows 10 Pro Creators Update и устройств, которые были переведены на эту версию, но для которых еще не выполнена настройка Windows 10, следуйте инструкциям ниже.
  
1. Начните настройку Windows 10 на устройстве и дойдите до страницы **Выбор способа настройки**. 
    
    ![On the How would you like to set up page, choose Set up for an organization](media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. Выберите вариант **Настроить для организации** и введите имя пользователя и пароль для Microsoft 365 Business. 
    
3. Завершите настройку Windows 10 на устройстве.
    
   После завершения этой процедуры пользователь будет добавлен в каталог Azure AD организации. Чтобы проверить, так ли это, ознакомьтесь со статьей [Проверка подключения устройства к Azure AD](set-up-windows-devices.md#bkmk_verifyaad). 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a>Для устройства, на котором уже установлена и настроена система Windows 10 Pro

 **Подключение пользователей к Azure AD**
  
1. На пользовательском компьютере под управлением Windows 10 Pro версии 1703 (Creators Update) (см. [необходимые условия](pre-requisites-for-data-protection.md)) щелкните логотип Windows, а затем значок параметров.
  
   ![In the Start menu, click Windows Settings icon](media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. В окне **Параметры** выберите элемент **Учетные записи**.
  
   ![In Windows Settings, go to Accounts](media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. На странице **Ваши данные** выберите **Доступ к учетной записи места работы или учебного заведения** \> **Подключить**.
  
   ![Choose Connect under Access work or school](media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. В диалоговом окне **Настроить учетную запись компании или учебного заведения** в разделе **Другие действия** выберите **Присоединить это устройство к Azure Active Directory**.
  
   ![Click Join this device to Azure Active Directory](media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. На странице **давайте вы вход** введите свою учетную запись рабочего или школы \> **Далее**.
  
   На странице **Введите пароль** введите пароль \> **Вход**.
  
   ![Enter your work or school email on the Let's get you signed in page](media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. На ** убедитесь, что это организации ** страницы, проверьте правильность информации и нажмите кнопку **присоединиться**.
  
   На странице **Готово!** нажмите кнопку **Готово**.
  
   ![On the Make sure this is your organization screen, click Join](media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
Если вы добавляете файлы в OneDrive для бизнеса, синхронизируйте их в обратном направлении. Если вы используете стороннюю программу для переноса профиля и файлов, синхронизируйте их тоже с новым профилем.
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a>Проверка подключения устройства к Azure AD

Чтобы проверить состояние синхронизации, на странице **Доступ к учетной записи места работы или учебного заведения** окна **Параметры** щелкните в области **Подключен к** _ \<organization name\> _, чтобы появились кнопки **Сведения** и **Отключить**. Чтобы узнать состояние синхронизации, нажмите кнопку **Сведения**. 
  
На странице состояния синхронизации нажмите кнопку "Синхронизировать", чтобы получить сведения о последних политиках мобильных устройств на компьютере.
  
Чтобы начать пользоваться учетной записью Office 365 бизнес, перейдите в **начальное** меню Windows, щелкните правой кнопкой мыши картинку текущей учетной записи и выберите команду **Сменить учетную запись**. Войдите, используя адрес электронной почты и пароль организации.
  
![Click Info button to view synchronization status](media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-device-is-upgraded-to-windows-10-business"></a>Проверка перевода устройства на Windows 10 для бизнеса

Убедитесь, что устройства с Windows 10, добавленные в домен Azure AD, переведены на версию Windows 10 для бизнеса в составе подписки на Microsoft 365 Business.
  
1. Выберите **Параметры** \> **Система** \> **Сведения**.
    
2. Убедитесь, что в поле **Выпуск** указано **Windows 10 для бизнеса**.
    
    ![Verify that Windows edition is Windows 10 Business.](media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a>Дальнейшие действия

Сведения о настройке мобильных устройств см. в статьях [Настройка мобильных устройств для пользователей Microsoft 365 Business](set-up-mobile-devices.md), о настройке защиты и политик защиты устройств  в статье [Управление Microsoft 365 Business](manage.md).
  
