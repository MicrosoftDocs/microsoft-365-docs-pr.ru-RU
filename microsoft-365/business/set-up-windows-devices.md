---
title: Настройка Windows устройств для Microsoft 365 бизнес премиум пользователей
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
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
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: Узнайте, как настроить устройства Windows, работающие Windows 10 Pro для Microsoft 365 бизнес премиум пользователей, включив централизованные элементы управления и управления безопасностью.
ms.openlocfilehash: 3e268d81ff6fb7113b7e0b0fe5d0545ff5c72b1e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244783"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a>Настройка Windows устройств для Microsoft 365 бизнес премиум пользователей

## <a name="prerequisites-for-setting-up-windows-devices-for-microsoft-365-business-premium-users"></a>Необходимые условия для настройки Windows устройств для Microsoft 365 бизнес премиум пользователей

Прежде чем настроить Windows для Microsoft 365 бизнес премиум пользователей, убедитесь, что все Windows работают Windows 10 Pro версии 1703 (Creators Update). Windows 10 Pro является обязательным условием для развертывания Windows 10 для бизнеса, который представляет собой набор облачных служб и возможностей управления устройствами, которые дополняют Windows 10 Pro и обеспечивают централизованное управление и управление безопасностью Microsoft 365 бизнес премиум.
  
Если у вас Windows устройств с Windows 7 Pro, Windows 8 Профессиональная или Windows 8.1 Профессиональная, ваша Microsoft 365 бизнес премиум подписка дает вам право на Windows 10 обновления.
  
Дополнительные сведения о переводе устройств с Windows на версию Windows 10 Pro Creators Update приведены в следующей статье: [Обновление устройств с Windows до Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md)
  
Проверьте, подключено ли устройство к [Azure AD,](#verify-the-device-is-connected-to-azure-ad) чтобы убедиться, что обновление обновлено, или убедиться, что обновление сработало.

Просмотрите короткое видео о подключении Windows к Microsoft 365.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

Если это видео помогло вам, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](../business-video/index.yml).
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a>Добавление устройств с Windows 10 в каталог Azure AD организации

Если все Windows в организации были обновлены до Windows 10 Pro Creators Update или уже запущены Windows 10 Pro Creators Update, вы можете присоединиться к этим устройствам в Azure Active Directory. После того как устройства будут соединены, они будут автоматически обновлены до Windows 10 для бизнеса, что является частью Microsoft 365 бизнес премиум подписки.
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a>Для новых (или недавно переведенных) устройств с Windows 10 Pro

Для новых устройств с системой Windows 10 Pro Creators Update и устройств, которые были переведены на эту версию, но для которых еще не выполнена настройка Windows 10, следуйте инструкциям ниже.
  
1. Начните настройку Windows 10 на устройстве и дойдите до страницы **Выбор способа настройки**. 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. Здесь выберите **Настройка для организации,** а затем введите имя пользователя и пароль для Microsoft 365 бизнес премиум. 
    
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
  
6. На странице **Убедитесь, что это** ваша страница организации, убедитесь, что информация верна, и выберите **Присоединиться**.
  
   На странице **Готово!** страница, chosse **Готово**.
  
   ![На экране Убедитесь, что это ваш экран организации, выберите Присоединиться](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
Если вы добавляете файлы в OneDrive для бизнеса, синхронизируйте их в обратном направлении. Если для переноса профилей и файлов используется сторонний инструмент, синхронизируйте их с новым профилем.
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a>Проверка подключения устройства к Azure AD

Чтобы проверить состояние синхронизации, на странице **Access work** или school **в Параметры** выберите область Подключенная к **_** _, чтобы выставить кнопки \<organization name\> **Info** и **Disconnect**. Выберите **Info,** чтобы получить состояние синхронизации. 
  
На странице **Состояние синхронизации** выберите **Синхронизация,** чтобы получить последние политики управления мобильными устройствами на компьютере.
  
Чтобы начать использовать учетную запись Microsoft 365 бизнес премиум, перейдите  Windows кнопку Начните, щелкните правой кнопкой мыши текущую учетную запись, а затем **переключите учетную запись**. Войдите, используя адрес электронной почты и пароль организации.
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-pc-is-upgraded-to-windows-10-business"></a>Убедитесь, что компьютер обновлен до Windows 10 для бизнеса

Убедитесь, что ваши Windows 10 Azure AD обновляются до Windows 10 для бизнеса в рамках Microsoft 365 бизнес премиум подписки.
  
1. Выберите **Параметры** \> **Система** \> **Сведения**.
    
2. Убедитесь, что в поле **Выпуск** указано **Windows 10 для бизнеса**.
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a>Дальнейшие действия

Чтобы настроить мобильные устройства, см. в Microsoft 365 бизнес премиум настройка мобильных устройств [для](set-up-mobile-devices.md)пользователей, чтобы установить политики защиты устройств или приложений, см. в Microsoft 365 [для бизнеса.](manage.md)
  
## <a name="for-more-on-setting-up-and-using-microsoft-365-business-premium"></a>Дополнительные для настройки и использования Microsoft 365 бизнес премиум

[Обучающие видеоролики по Microsoft 365 для бизнеса](../business-video/index.yml)
