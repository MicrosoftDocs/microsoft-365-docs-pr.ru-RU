---
title: Настройка устройств с Windows для пользователей Microsoft 365 Business Premium
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: Узнайте, как настроить устройства Windows, работающие под управлением Windows 10 профессиональная для пользователей Microsoft 365 Business Premium, обеспечивающие централизованное управление и контроль безопасности.
ms.openlocfilehash: efe81a5547496f502232e1db2f3f092165475641
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635459"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a>Настройка устройств с Windows для пользователей Microsoft 365 Business Premium

## <a name="prerequisites-for-setting-up-windows-devices-for-microsoft-365-business-premium-users"></a>Необходимые условия для настройки устройств с Windows для пользователей Microsoft 365 Business Premium

Перед настройкой устройств с Windows для пользователей Microsoft 365 Business Premium убедитесь, что все устройства Windows работают под управлением Windows 10 Pro версии 1703 (обновления). Windows 10 профессиональная является необходимым условием для развертывания Windows 10 Business, который представляет собой набор облачных служб и возможностей управления устройствами, которые дополняют Windows 10 Pro и обеспечивают централизованное управление и управление безопасностью Microsoft 365 бизнес премиум.
  
Если у вас есть устройства с Windows, работающие под управлением Windows 7 Профессиональная, Windows 8 Pro или Windows 8,1 Pro, подписка на Microsoft 365 бизнес премиум дает право на обновление до Windows 10.
  
Дополнительные сведения о переводе устройств с Windows на версию Windows 10 Pro Creators Update приведены в следующей статье: [Обновление устройств с Windows до Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md)
  
Ознакомьтесь со статьей убедитесь, что [устройство подключено к Azure AD](#verify-the-device-is-connected-to-azure-ad) , чтобы проверить, что у вас есть обновление, или чтобы убедиться в том, что обновление работало.

Посмотрите короткое видео о подключении Windows к Microsoft 365.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

Если этот видео помогло вам, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a>Добавление устройств с Windows 10 в каталог Azure AD организации

Когда все устройства с Windows в вашей организации обновлены до версии Windows 10 профессиональная Creators или уже запущены обновление Windows 10 Pro Creators, вы можете присоединить эти устройства к Azure Active Directory вашей организации. После подключения к устройствам они будут автоматически обновлены до Windows 10 Business, которая входит в состав подписки на Microsoft 365 Business Premium.
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a>Для новых (или недавно переведенных) устройств с Windows 10 Pro

Для новых устройств с системой Windows 10 Pro Creators Update и устройств, которые были переведены на эту версию, но для которых еще не выполнена настройка Windows 10, следуйте инструкциям ниже.
  
1. Начните настройку Windows 10 на устройстве и дойдите до страницы **Выбор способа настройки**. 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. В этой статье выберите **Настройка для Организации** , а затем введите имя пользователя и пароль для Microsoft 365 бизнес премиум. 
    
3. Завершите настройку Windows 10 на устройстве.
    
   После завершения этой процедуры пользователь будет добавлен в каталог Azure AD организации. Чтобы проверить, так ли это, ознакомьтесь со статьей [Проверка подключения устройства к Azure AD](#verify-the-device-is-connected-to-azure-ad). 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a>Для устройства, на котором уже установлена и настроена система Windows 10 Pro

 **Подключение пользователей к Azure AD**
  
1. На пользовательском компьютере под управлением Windows 10 Pro версии 1703 (Creators Update) (см. [необходимые условия](pre-requisites-for-data-protection.md)) щелкните логотип Windows, а затем значок параметров.
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. В окне **Параметры** выберите элемент **Учетные записи**.
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. На странице **Ваши данные** выберите **Доступ к учетной записи места работы или учебного заведения** \> **Подключить**.
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. В диалоговом окне **Настроить учетную запись компании или учебного заведения** в разделе **Другие действия** выберите **Присоединить это устройство к Azure Active Directory**.
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. On the **Let's get you signed in** page, enter your work or school account \> **Next**.
  
   On the **Enter password** page, enter your password \> **Sign in**.
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. Убедитесь, что на странице **ваша организация** указана правильная информация, и нажмите кнопку **присоединиться**.
  
   На странице **Готово!** нажмите кнопку **Готово**.
  
   ![On the Make sure this is your organization screen, click Join](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
Если вы добавляете файлы в OneDrive для бизнеса, синхронизируйте их в обратном направлении. Если для переноса профилей и файлов использовалось стороннее средство, также синхронизируйте их с новым профилем.
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a>Проверка подключения устройства к Azure AD

Чтобы проверить состояние синхронизации, на странице **Доступ к учетной записи места работы или учебного заведения** окна **Параметры** щелкните в области **Подключен к** _ \<organization name\> _, чтобы появились кнопки **Сведения** и **Отключить**. Чтобы узнать состояние синхронизации, нажмите кнопку **Сведения**. 
  
На странице состояния синхронизации нажмите кнопку "Синхронизировать", чтобы получить сведения о последних политиках мобильных устройств на компьютере.
  
Чтобы начать работу с учетной записью Microsoft 365 бизнес премиум, перейдите к кнопке **Пуск** Windows, щелкните правой кнопкой мыши текущий рисунок учетной записи, а затем **Переключить учетную запись**. Войдите, используя адрес электронной почты и пароль организации.
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-device-is-upgraded-to-windows-10-business"></a>Проверка перевода устройства на Windows 10 для бизнеса

Убедитесь, что ваши устройства с Windows 10, подключенные к Azure AD, были обновлены до Windows 10 бизнес в рамках своей подписки на Microsoft 365 Business Premium.
  
1. Выберите **Параметры** \> **Система** \> **Сведения**.
    
2. Убедитесь, что в поле **Выпуск** указано **Windows 10 для бизнеса**.
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a>Дальнейшие действия

Чтобы настроить мобильные устройства, ознакомьтесь со статьей [Настройка мобильных устройств для пользователей Microsoft 365 Business Premium](set-up-mobile-devices.md), чтобы задать защиту устройств или политики защиты приложений, приведенные в [статье Manage Microsoft 365 для бизнеса](manage.md).
  
## <a name="for-more-on-setting-up-and-using-microsoft-365-business-premium"></a>Дополнительные сведения о настройке и использовании Microsoft 365 Business Premium

[Обучающие видеоролики Microsoft 365 для бизнеса](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
