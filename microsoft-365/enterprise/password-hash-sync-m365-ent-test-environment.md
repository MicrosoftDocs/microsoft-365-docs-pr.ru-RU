---
title: Синхронизация хэшей паролей для тестовой среды Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: Сводка. Настройте и продемонстрируйте синхронизацию хэшей паролей и вход для тестовой среды Microsoft 365.
ms.openlocfilehash: 2d5fbd3ed2a2afb994fc36f5ba3a15a8c55a274e
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819392"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Синхронизация хэшей паролей для тестовой среды Microsoft 365

*Это руководство по лаборатории тестирования можно использовать для тестовых сред Microsoft 365 корпоративный и Office 365 корпоративный.*

Во многих организациях используются Azure AD Connect и синхронизация хэша паролей в целях синхронизации набора учетных записей в своем локальном лесу доменных служб Active Directory (AD DS) с набором учетных записей в клиенте Azure AD для подписки на Microsoft 365. В этой статье описывается добавление синхронизации хэша паролей в тестовую среду Microsoft 365, в результате чего получается следующая конфигурация:
  
![Тестовая среда смоделированной организации с синхронизацией хэша паролей](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
Настройка этой тестовой среды состоит из двух следующих этапов:
  
1. Создание тестовой среды "имитация предприятия Microsoft 365".
2. Установка и настройка Azure AD Connect на виртуальной машине APP1.
    
> [!TIP]
> Перейдите в раздел [Руководства по лаборатории тестирования Microsoft 365 корпоративный](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), чтобы просмотреть схему всех статей, относящихся к данной теме.
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a>Этап 1. Создание тестовой среды "имитация предприятия" для Microsoft 365.

Следуйте инструкциям в статье о [базовой конфигурации "имитация предприятия" для Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Вот получившаяся конфигурация.
  
![Базовая конфигурация "имитация предприятия"](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
Конфигурация состоит из следующих компонентов: 
  
- Пробные или платные подписки на Microsoft 365 E5 или Office 365 E5.
- Упрощенная интрасеть организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в виртуальной сети Azure. DC1 — контроллер домена для testlab.\<your public domain name> Домен AD DS.

## <a name="phase-2-create-and-register-the-testlab-domain"></a>Этап 2. Создание и регистрация домена testlab

На этом этапе создается и добавляется в подписку публичный домен DNS.

Сначала обратитесь к своему поставщику услуг регистрации общедоступных записей DNS, чтобы создать новое имя общедоступного домена DNS на основе текущего доменного имени и добавить его в подписку. Рекомендуем использовать имя **testlab.**\<your public domain>. Например, если имя вашего общедоступного домена — **<span>contoso</span>.com**, добавьте имя **<span>testlab</span>.contoso.com**.
  
Затем добавьте домен **testlab.**\<your public domain> в пробную или платную подписку на Microsoft 365 или Office 365, пройдя процесс регистрации домена. Он включает добавление дополнительных записей DNS к домену **testlab.**\<your public domain> . Дополнительные сведения см. в статье [Добавление домена в Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain). 

Ниже показана итоговая конфигурация.
  
![Регистрация доменного имени testlab](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
Конфигурация состоит из следующих компонентов:

- Пробные или платные подписки на Microsoft 365 E5 или Office 365 E5 с зарегистрированным доменом DNS testlab.\<your public domain name> -
- Упрощенная интрасеть организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети, входящей в виртуальную сеть Azure.

Обратите внимание, как домен testlab.\<your public domain name> в настоящее время:

- поддерживается общедоступными DNS-записями;
- зарегистрирован в подписках на Microsoft 365;
- является доменом AD DS в имитации интрасети.
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a>Этап 3. Установка Azure AD Connect на APP1

На этом этапе устанавливается и настраивается инструмент Azure AD Connect на APP1, а затем проверяется его работа.
  
Сначала выполняется установка и настройка Azure AD Connect на APP1.

1. На [портале Azure](https://portal.azure.com) выполните вход с помощью учетной записи глобального администратора и подключитесь к виртуальной машине APP1 с помощью учетной записи TESTLAB\\User1.
    
2. На рабочем столе APP1 откройте командную строку Windows PowerShell с правами администратора и выполните указанные ниже команды, чтобы отключить усиленную безопасность Internet Explorer.
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. На панели задач выберите **Internet Explorer** и перейдите по адресу [https://aka.ms/aadconnect](https://aka.ms/aadconnect).
    
4. На странице Microsoft Azure Active Directory Connect нажмите **Скачать**, а затем **Запустить**.
    
5. На странице **Добро пожаловать в Azure AD Connect** установите флажок **Принимаю** и нажмите кнопку **Продолжить**.
    
6. На странице **Стандартные параметры** выберите **Использовать стандартные параметры**.
    
7. На странице **Подключение к Azure AD** введите имя своей учетной записи глобального администратора в поле **Имя пользователя**, введите пароль в поле **Пароль** и нажмите кнопку **Далее**.
    
8. На странице **Подключение к AD DS** введите **TESTLAB\\User1** в поле **Имя пользователя** и пароль в поле **Пароль**, а затем нажмите кнопку **Далее**.
    
9. На странице **Готово к настройке** нажмите **Установить**.
    
10. На странице **Настройка завершена** нажмите **Выход**.
    
11. В браузере Internet Explorer перейдите в Центр администрирования Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)).
    
12. На панели навигации слева выберите элементы **Пользователи > Активные пользователи**.
    
    Обратите внимание на учетную запись **User1**. Эта учетная запись находится на домене AD DS TESTLAB. Это доказывает, что синхронизация службы каталогов выполнена успешно.
    
13. Щелкните учетную запись **User1** и выберите **Лицензии и приложения**.
    
14. В разделе **Лицензии продуктов** выберите свое расположение (при необходимости), отключите лицензию на **Office 365 E5** и включите лицензию на **Microsoft 365 E5**. 

15. Нажмите **Сохранить** в нижней части страницы, а затем нажмите кнопку **Закрыть**.
    
Затем проверьте возможность входа в вашу подписку с использованием учетной записи <strong>user1@testlab.</strong>\<your domain name> на имя пользователя учетной записи User1.

1. Находясь в APP1, выйдите и повторно войдите, используя другую учетную запись.

2. При появлении запроса имени пользователя и пароля, укажите <strong>user1@testlab.</strong>\<your domain name> и пароль пользователя User1. Должен осуществиться успешный вход в качестве пользователя User1. 
 
Обратите внимание, что хотя у пользователя User1 есть разрешения администратора для домена AD DS TESTLAB, он не является глобальным администратором. Следовательно, значок **Администратор** не будет отображаться. 

Ниже показана итоговая конфигурация.

![Тестовая среда "имитация предприятия с синхронизацией хэшей паролей"](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

Конфигурация состоит из следующих компонентов: 
  
- Пробные или платные подписки на Microsoft 365 E5 или Office 365 E5 с зарегистрированным доменом DNS TESTLAB.\<your domain name> -
- Упрощенная интрасеть организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети, входящей в виртуальную сеть Azure. Azure AD Connect работает на APP1 для периодической синхронизации домена AD DS TESTLAB с клиентом Azure AD, связанным с подпиской на Microsoft 365.
- Учетная запись User1 на домене AD DS TESTLAB синхронизирована с клиентом Azure AD.

## <a name="next-step"></a>Следующее действие

Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.

## <a name="see-also"></a>См. также

[Руководства по лаборатории тестирования для Microsoft 365 корпоративный](m365-enterprise-test-lab-guides.md)

[Развертывание Microsoft 365 корпоративный](deploy-microsoft-365-enterprise.md)

[Документация по Microsoft 365 корпоративный](https://docs.microsoft.com/microsoft-365-enterprise/)


