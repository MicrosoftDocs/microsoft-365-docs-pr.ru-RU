---
title: Настройка Microsoft Azure AD Rights Management для предыдущей версии шифрования сообщений Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: Предыдущая версия шифрования сообщений Office 365 зависит от Microsoft Azure Rights Management (ранее известной как Windows Azure Active Directory Rights Management).
ms.openlocfilehash: be0fad248465927ee7cc59b31a36e65ce5c053db
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601486"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-office-365-message-encryption"></a>Настройка Microsoft Azure AD Rights Management для предыдущей версии шифрования сообщений Office 365

В этом разделе описываются действия, которые необходимо выполнить, чтобы активировать и затем настроить Azure Rights Management (RMS), часть Azure Information Protection для использования с предыдущей версией Office 365 Message encryption (OME).

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a>Эта статья относится только к предыдущей версии OME
Если вы еще не переместили организацию Office 365 в новые возможности OME, но вы уже развернули OME, то сведения, приведенные в этой статье, применимы к вашей организации. Корпорация Майкрософт рекомендует создавать план для перехода на новые возможности OME, как только она будет приемлема для вашей организации. Инструкции приведены в разделе [Настройка новых возможностей шифрования сообщений Office 365](set-up-new-message-encryption-capabilities.md). Если вы хотите узнать больше о том, как новые возможности работают первыми, ознакомьтесь со статьей [Office 365 Message Encryption](ome.md). В оставшейся части этой статьи рассматривается поведение OME перед выпуском новых возможностей OME.

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a>Необходимые условия для использования предыдущей версии Office 365 шифрования сообщений
<a name="warmprereqs"> </a>

Шифрование сообщений Office 365 (OME), в том числе IRM, зависит от управления правами Azure (Azure RMS). Azure RMS — это технология защиты, используемая службой Azure Information Protection. Чтобы использовать OME, ваша организация Office 365 должна включать подписку на Exchange Online или Exchange Online Protection, которая, в свою очередь, включает подписку на Azure Rights Management.
  
- Если вы не знаете, что включает подписка, ознакомьтесь со статьей описание службы Exchange Online для [политики сообщений, восстановления и соответствия требованиям](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx).

- Если у вас нет подписки Azure RMS для Exchange Online или Exchange Online Protection, вы должны приобрести подписку и активировать ее первым.

    Сведения о приобретении подписки на Azure Rights Management можно найти в статье [Управление правами Azure](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT). В следующем разделе приводятся сведения об активации службы управления правами Azure.

- Если у вас есть служба управления правами Azure, но она не настроена для Exchange Online или Exchange Online Protection, в этой статье описывается активация службы управления правами Azure, а затем описывается лучший способ настройки OME для работы с управлением правами Azure.

- Если вы уже настроили OME для работы с управлением правами Azure для Exchange Online или Exchange Online Protection, в зависимости от того, как вы настроили ее, вы можете сразу приступить к использованию OME и новых возможностей. В этой статье объясняется, как определить, правильно ли настроен OME, что делать, если требуется изменить настройку, а что произойдет, если вы отказаться от изменения настроек. Например, чтобы использовать новые возможности, необходимо использовать Azure RMS с OME. Вы не можете использовать новые возможности с локальной службой управления правами Active Directory.

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a>Активация службы управления правами Azure для предыдущей версии OME в Office 365

Необходимо активировать управление правами Azure, чтобы пользователи в организации могли применять защиту информации к отправляемым им сообщениям, а также открывать сообщения и файлы, защищенные службой управления правами Azure. Инструкции см в разделе [Активация службы управления правами Azure](https://go.microsoft.com/fwlink/p/?LinkId=525775). После завершения активации вернитесь сюда и продолжайте выполнение задач, описанных в этой статье.
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>Настройка предыдущей версии OME для использования Azure RMS путем импорта доверенных доменов публикации (TPD)

TPD — это XML-файл, который содержит сведения о параметрах управления правами организации. Например, TPD содержит сведения о сертификате лицензиара сервера (лицензиар), используемом для подписи и шифрования сертификатов и лицензий, URL-адресов, используемых для лицензирования и публикации, и т. д. Вы импортируете TPD в организацию Office 365 с помощью Windows PowerShell.
  
> [!IMPORTANT]
> Ранее вы можете импортировать TPD из службы управления правами Active Directory (AD RMS) в организацию Office 365. Тем не менее, это предотвратит использование новых возможностей OME и не рекомендуется. Если ваша организация Office 365 в данный момент настроена таким образом, корпорация Майкрософт рекомендует создать план для миграции из локальной службы управления правами Active Directory в облачную службу Azure Information Protection. Дополнительные сведения см. [в статье миграция из AD RMS в Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms). Вы не сможете использовать новые возможности OME, пока миграция не будет завершена в Azure Information Protection.
  
 **Импорт TPD из службы управления правами Azure**
  
1. [Подключитесь к Exchange Online с помощью удаленной оболочки PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).

2. Выберите URL-адрес для общего доступа к ключам, соответствующий географическому расположению организации Office 365:

|**Location**|**URL-адрес расположения для общего доступа к ключам**|
|:-----|:-----|
|Северная Америка  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Европейский Союз  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Азия  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Южная Америка  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Office 365 для государственных организаций (облако сообщества госучреждений)  <br/> Это расположение для общего доступа к ключам RMS зарезервировано для клиентов, которые приобрели Office 365 для государственных учреждений.  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
   
3. Настройте расположение для общего доступа к ключам, выполнив командлет [Set – IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) следующим образом: 
    
  ```powershell
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
  ```

    Например, чтобы настроить расположение для общего доступа к ключам, если ваша организация находится в Северной Америке:

  ```powershell
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
  ```

4. Выполните командлет [Import – RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) с параметром – рмсонлине, чтобы импортировать TPD из службы управления правами Azure: 

  ```powershell
  Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
  ```

    Где *тпднаме* — это имя, которое вы хотите использовать для TPD. Например, "Contoso Северная Америка TPD". 

5. Чтобы убедиться, что ваша организация Office 365 успешно настроена на использование службы управления правами Azure, запустите командлет [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) с параметром-рмсонлине следующим образом: 

  ```powershell
  Test-IRMConfiguration -RMSOnline
  ```

    Помимо прочего, этот командлет проверяет возможность подключения к службе управления правами Azure, загружает TPD и проверяет его допустимость.

6. Выполните командлет [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) , как показано ниже, чтобы отключить доступ к шаблонам управления правами Azure в Outlook в Интернете и Outlook: 

  ```powershell
  Set-IRMConfiguration -ClientAccessServerEnabled $false
  ```

7. Выполните командлет [Set – IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) , как показано ниже, чтобы включить управление правами Azure для облачной организации электронной почты и настроить его для использования службы управления правами Azure для шифрования сообщений Office 365: 

  ```powershell
  Set-IRMConfiguration -InternalLicensingEnabled $true
  ```

8. Чтобы убедиться, что вы успешно импортировали TPD и включили управление правами Azure, используйте командлет Test-IRMConfiguration для проверки функции управления правами Azure. Дополнительные сведения: "Пример 1" в разделе [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx).

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>В предыдущей версии OME настроено управление правами Active Directory, а не Azure Information Protection, что делать?
<a name="importTPDs"> </a>

Вы можете продолжать использовать существующие правила обработки почты для шифрования сообщений Office 365 с помощью управления правами Active Directory, но вы не можете настраивать или использовать новые возможности OME. Вместо этого необходимо выполнить миграцию в Azure Information Protection. Сведения о миграции и том, что это означает для вашей организации, можно узнать [в статье Миграция с AD RMS на Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms).
  
## <a name="next-steps"></a>Дальнейшие действия
<a name="importTPDs"> </a>

После завершения настройки управления правами Azure, если вы хотите включить новые возможности OME, ознакомьтесь со статьей [Настройка новых возможностей шифрования сообщений Office 365, созданных на основе Azure Information Protection.](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)
  
После настройки организации для использования новых возможностей OME вы можете [определить правила обработки почты для защиты сообщений электронной почты с помощью новых возможностей OME](define-mail-flow-rules-to-encrypt-email.md).
  
## <a name="related-topics"></a>Статьи по теме
<a name="importTPDs"> </a>

[Шифрование в Office 365](encryption.md)
  
[Техническая справка по шифрованию в Office 365](technical-reference-details-about-encryption.md)
  
[Управление правами Azure](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
