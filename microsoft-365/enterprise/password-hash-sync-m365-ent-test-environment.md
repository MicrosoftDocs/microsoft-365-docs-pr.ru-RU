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
ms.assetid: ''
description: Сводка. Настройте и продемонстрируйте синхронизацию хэшей паролей и вход для тестовой среды Microsoft 365.
ms.openlocfilehash: 7b1ba549a9ac9d3faec8b717a0f76cca1200352b
ms.sourcegitcommit: 87eff6e8a08cec3cb0464a3b765434717584a4a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/26/2020
ms.locfileid: "44371444"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Синхронизация хэшей паролей для тестовой среды Microsoft 365

*Это руководство по лаборатории тестирования можно использовать для тестовых сред Microsoft 365 корпоративный и Office 365 корпоративный.*

Во многих организациях используются Azure AD Connect и синхронизация хэша паролей в целях синхронизации набора учетных записей в своем локальном лесу доменных служб Active Directory (AD DS) с набором учетных записей в клиенте Azure AD для подписки на Microsoft 365. В этой статье описывается добавление синхронизации хэша паролей в тестовую среду Microsoft 365, в результате чего получается следующая конфигурация:
  
![Тестовая среда смоделированной организации с синхронизацией хэша паролей](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
Настройка этой тестовой среды состоит из двух следующих этапов:
  
1. Создание тестовой среды "имитация предприятия Microsoft 365".
2. Установка и настройка Azure AD Connect на виртуальной машине APP1.
    
> [!TIP]
> Щелкните [здесь](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a>Этап 1. Создание тестовой среды "имитация предприятия" для Microsoft 365.

Следуйте инструкциям в статье о [базовой конфигурации "имитация предприятия" для Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Вот получившаяся конфигурация.
  
![Базовая конфигурация "имитация предприятия"](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
Конфигурация состоит из следующих компонентов: 
  
- Пробные или платные подписки на Microsoft 365 E5 или Office 365 E5.
- Упрощенная интрасеть организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в виртуальной сети Azure. DC1 — контроллер домена для домена testlab.\<имя вашего общедоступного домена> AD DS. Этап 2. Создание и регистрация домена testlab

## <a name="phase-2-create-and-register-the-testlab-domain"></a>На этом этапе создается и добавляется в подписку публичный домен DNS.

First, work with your public DNS registration provider to create a new public DNS domain name based on your current domain name and add it to your subscription.

Сначала под руководством регистратора создайте новое имя публичного домена DNS на основе текущего имени домена и добавьте его в свою подписку. Рекомендуем использовать имя **testlab.**\<ваш публичный домен>. Например, если имя вашего публичного домена — **<span>contoso</span>.com**, добавьте имя **<span>testlab</span>.contoso.com**.
  
Он включает добавление записей DNS к домену **testlab.**\<общедоступный домен>. Дополнительные сведения см. в статье [Добавление домена в Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain). Ниже показана итоговая конфигурация. Регистрация доменного имени testlab Конфигурация состоит из следующих компонентов: 

Пробные или платные подписки на Microsoft 365 E5 или Office 365 E5 с зарегистрированным доменом DNS testlab.\<имя общедоступного домена>.
  
![Упрощенная интрасеть организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети, входящей в виртуальную сеть Azure.](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
Обратите внимание, что testlab.\<имя вашего публичного домена> теперь:

- поддерживается общедоступными DNS-записями; зарегистрирован в подписках на Microsoft 365;
- является доменом AD DS в имитации интрасети.

При появлении запроса имени пользователя и пароля, укажите <strong>user1@testlab.</strong>\<имя вашего домена> и пароль пользователя User1. Должен произойти успешный вход в качестве пользователя User1.

- Сначала выполняется установка и настройка Azure AD Connect на APP1.
- На [портале Azure](https://portal.azure.com) выполните вход с помощью учетной записи глобального администратора и подключитесь к виртуальной машине APP1 с помощью учетной записи TESTLAB\\User1.
- На рабочем столе APP1 откройте командную строку Windows PowerShell с правами администратора и выполните указанные ниже команды, чтобы отключить усиленную безопасность Internet Explorer.
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a>На панели задач выберите **Internet Explorer** и перейдите по адресу [https://aka.ms/aadconnect](https://aka.ms/aadconnect).

На странице Microsoft Azure Active Directory Connect нажмите **Скачать**, а затем **Запустить**.
  
На странице **Добро пожаловать в Azure AD Connect** установите флажок **Принимаю** и нажмите кнопку **Продолжить**.

1. На странице **Стандартные параметры** выберите **Использовать стандартные параметры**.
    
2. На странице **Подключение к Azure AD** введите имя своей учетной записи глобального администратора в поле **Имя пользователя**, введите пароль в поле **Пароль** и нажмите кнопку **Далее**.
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. На странице **Подключение к AD DS** введите **TESTLAB\\User1** в поле **Имя пользователя** и пароль в поле **Пароль**, а затем нажмите кнопку **Далее**.
    
4. На странице **Готово к настройке** нажмите **Установить**.
    
5. На странице **Настройка завершена** нажмите **Выход**.
    
6. В браузере Internet Explorer перейдите в Центр администрирования Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)).
    
7. На панели навигации слева выберите элементы **Пользователи > Активные пользователи**.
    
8. Обратите внимание на учетную запись **User1**.
    
9. Эта учетная запись находится на домене AD DS TESTLAB. Это доказывает, что синхронизация службы каталогов выполнена успешно.
    
10. Щелкните учетную запись **User1** и выберите **Лицензии и приложения**.
    
11. В разделе **Лицензии продуктов** выберите свое расположение (при необходимости), отключите лицензию на **Office 365 E5** и включите лицензию на **Microsoft 365 E5**.
    
12. Нажмите **Сохранить** в нижней части страницы, а затем нажмите кнопку **Закрыть**.
    
    Затем проверьте возможность входа в вашу подписку с использованием учетной записи <strong>user1@testlab.</strong>\<имя вашего домена> на имя пользователя User1. Находясь в APP1, выйдите и повторно войдите, используя другую учетную запись.
    
13. When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your domain name> and the User1 password.
    
14. You should successfully sign in as User1. 

15. Обратите внимание, что хотя у пользователя User1 есть разрешения администратора для домена AD DS TESTLAB, он не является глобальным администратором.
    
Следовательно, значок **Администратор** не будет отображаться. Ниже показана итоговая конфигурация.

1. Тестовая среда "имитация предприятия с синхронизацией хэшей паролей"

2. Конфигурация состоит из следующих компонентов: Пробные или платные подписки на Microsoft 365 E5 или Office 365 E5 с зарегистрированным доменом DNS TESTLAB.\<доменное имя>. Упрощенная интрасеть организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети, входящей в виртуальную сеть Azure. 
 
Azure AD Connect работает на APP1 для периодической синхронизации домена AD DS TESTLAB с клиентом Azure AD, связанным с подпиской на Microsoft 365. Учетная запись User1 на домене AD DS TESTLAB синхронизирована с клиентом Azure AD. 

Следующее действие

![Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

См. также 
  
- [Руководства по лаборатории тестирования для Microsoft 365 корпоративный](m365-enterprise-test-lab-guides.md) [Развертывание Microsoft 365 корпоративный](deploy-microsoft-365-enterprise.md)
- [Документация по Microsoft 365 корпоративный](https://docs.microsoft.com/microsoft-365-enterprise/) Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription periodically.
- The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.

## <a name="next-step"></a>Next step

Explore additional <bpt id="p1">[</bpt>identity<ept id="p1">](m365-enterprise-test-lab-guides.md#identity)</ept> features and capabilities in your test environment.

## <a name="see-also"></a>See also

<bpt id="p1">[</bpt>Microsoft 365 Enterprise Test Lab Guides<ept id="p1">](m365-enterprise-test-lab-guides.md)</ept>

<bpt id="p1">[</bpt>Deploy Microsoft 365 Enterprise<ept id="p1">](deploy-microsoft-365-enterprise.md)</ept>

<bpt id="p1">[</bpt>Microsoft 365 Enterprise documentation<ept id="p1">](https://docs.microsoft.com/microsoft-365-enterprise/)</ept>


