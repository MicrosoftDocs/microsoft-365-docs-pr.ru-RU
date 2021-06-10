---
title: Настройка управления правами Azure для предыдущей версии шифрования сообщений
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
description: Предыдущая версия шифрование сообщений Office 365 зависит от Microsoft Azure управления правами (ранее Windows Azure Active Directory управления правами).
ms.openlocfilehash: 978a8027c79de574b80aeedabcbbd51fa6f9e2a0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919495"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-message-encryption"></a>Настройка управления правами Azure для предыдущей версии шифрования сообщений

В этом разделе описываются действия, которые необходимо выполнять, чтобы активировать и затем настроить Azure Rights Management (RMS), часть Azure Information Protection, для использования в предыдущей версии шифрование сообщений Office 365 (OME).

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a>Эта статья применяется только к предыдущей версии OME

Если вы еще не перевели организацию в новые возможности OME, но уже развернули OME, то сведения в этой статье применимы к вашей организации. Корпорация Майкрософт рекомендует вам спланировать переход на новые возможности OME, как только это будет разумно для вашей организации. Инструкции см. в [инструкции Настройка новых шифрование сообщений Office 365 возможностей.](set-up-new-message-encryption-capabilities.md) Подробнее о работе новых возможностей см. в [шифрование сообщений Office 365.](ome.md) Остальная часть этой статьи относится к поведению OME перед выпуском новых возможностей OME.

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a>Необходимые условия для использования предыдущей версии шифрование сообщений Office 365
<a name="warmprereqs"> </a>

шифрование сообщений Office 365 (OME), включая IRM, зависит от управления правами Azure (Azure RMS). Azure RMS — это технология защиты, используемая Azure Information Protection. Чтобы использовать OME, организация должна включить подписку Exchange Online или Exchange Online Protection, которая, в свою очередь, включает подписку На управление правами Azure.
  
- Если вы не уверены в том, что включает подписка, см. Exchange Online службы [политики,](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)восстановления и соответствия требованиям.

- Если у вас есть управление правами Azure, но оно не настроено для Exchange Online или Exchange Online Protection, в этой статье рассказывается, как активировать управление правами Azure, а затем описывается лучший способ настроить OME для работы с Управление правами Azure.

- Если вы уже настроили OME для работы с Azure Rights Management для Exchange Online или Exchange Online Protection, в зависимости от того, как вы его настроили, вы можете быть готовы сразу же начать использовать OME и его новые возможности. В этой статье рассказывается, как определить, правильно ли настроен OME, что делать, если необходимо изменить настройку, и что произойдет, если вы решите не менять установку. Например, для использования новых возможностей необходимо использовать Azure RMS с OME. Новые возможности нельзя использовать с локальной службой active Directory RMS.

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a>Активируйте управление правами Azure для предыдущей версии OME в Office 365

Необходимо активировать управление правами Azure, чтобы пользователи в организации могли применять защиту информации к отправляемым сообщениям и открывать сообщения и файлы, защищенные службой управления правами Azure. Инструкции см. в [инструкции "Активация управления правами Azure".](/azure/information-protection/activate-service) После завершения активации возвращайся сюда и продолжай выполнять задачи в этой статье.
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>Настройка предыдущей версии OME для использования Azure RMS путем импорта доверенных доменов публикации (TPDs)

TPD — это XML-файл, содержащий сведения о параметрах управления правами организации. Например, TPD содержит сведения о сертификате лицензирования сервера (SLC), используемом для подписания и шифрования сертификатов и лицензий, URL-адресах, используемых для лицензирования и публикации и т. д. Вы импортируете TPD в организацию с помощью Windows PowerShell.
  
> [!IMPORTANT]
> Ранее можно было импортировать TPD из службы управления правами active Directory (AD RMS) в вашу организацию. Однако это не позволит вам использовать новые возможности OME и не рекомендуется. Если ваша организация настроена таким образом, корпорация Майкрософт рекомендует создать план переноса из локальной службы Active Directory RMS в облачную защиту информации Azure. Дополнительные сведения см. в дополнительных сведениях о переносе из [AD RMS в Azure Information Protection.](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) Вы не сможете использовать новые возможности OME, пока не завершите миграцию в Azure Information Protection.
  
 **Импорт TPD из Azure RMS**
  
1. [Подключение использовать Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Выберите URL-адрес обмена ключами, соответствующий географическому расположению организации:

|**Location**|**URL-адрес расположения для общего доступа к ключам**|
|:-----|:-----|
|Северная Америка  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Европейский Союз  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Азия  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Южная Америка  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Office 365 для государственных организаций (облако сообщества госучреждений)  <br/> Это расположение обмена ключами RMS зарезервировано для клиентов, которые приобрели Office 365 для государственных skUs.  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
  
3. Настройка расположения совместного доступа к ключам, задав кодлет [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) следующим образом: 

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
   ```
  
   Например, чтобы настроить расположение обмена ключами, если ваша организация расположена в Северной Америке:

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
   ```

4. Запустите [комлет Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain) с переключателем -RMSOnline для импорта TPD из Azure Rights Management: 

   ```powershell
   Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
   ```

   Где  *TPDName*  — это имя, которое необходимо использовать для TPD. Например, "Contoso North American TPD". 

5. Чтобы убедиться, что ваша организация успешно настроена на использование службы управления правами Azure, выполните команды [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) с переключателем -RMSOnline следующим образом:

   ```powershell
   Test-IRMConfiguration -RMSOnline
   ```

   Помимо прочего, этот комдлет проверяет подключение к службе управления правами Azure, скачивает TPD и проверяет его подлинность.

6. Выполните команды [set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) следующим образом, чтобы отключить шаблоны управления правами Azure из доступных Outlook в Интернете и Outlook: 

   ```powershell
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

7. Выполните команды [set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) следующим образом, чтобы включить Управление правами Azure для облачной организации электронной почты и настроить ее для использования Azure Rights Management для шифрование сообщений Office 365:

   ```powershell
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```

8. Чтобы убедиться, что вы успешно импортировали TPD и включили Управление правами Azure, используйте Test-IRMConfiguration для тестирования функций управления правами Azure. Подробнее см. в материале "Пример 1" [в Test-IRMConfiguration.](/powershell/module/exchange/test-irmconfiguration)

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>У меня есть предыдущая версия OME, настроенная с управлением правами Active Directory, а не Azure Information Protection, что мне делать?
<a name="importTPDs"> </a>

Вы можете продолжать использовать существующие правила потока шифрование сообщений Office 365 с помощью Active Directory Rights Management, но вы не можете настроить или использовать новые возможности OME. Вместо этого необходимо перейти на Azure Information Protection. Сведения о миграции и о том, что это означает для вашей организации, см. в см. в руб. Миграция из [AD RMS в Azure Information Protection.](/information-protection/deploy-use/prepare-environment-adrms)
  
## <a name="next-steps"></a>Дальнейшие действия
<a name="importTPDs"> </a>

Как только вы завершите установку управления правами Azure, если вы хотите включить новые возможности OME, см. в шифрование сообщений Office 365 возможности, построенные на вершине [Azure Information Protection.](./set-up-new-message-encryption-capabilities.md)
  
После того как вы настроите организацию для использования новых возможностей OME, вы будете готовы определить правила потока почты для защиты сообщений электронной почты с помощью новых [возможностей OME.](define-mail-flow-rules-to-encrypt-email.md)
  
## <a name="related-topics"></a>Статьи по теме
<a name="importTPDs"> </a>

[Шифрование в Office 365](encryption.md)
  
[Техническая справка по шифрованию в Office 365](technical-reference-details-about-encryption.md)
  
[Управление правами Azure](/information-protection/understand-explore/what-is-azure-rms)