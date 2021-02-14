---
title: Настройка Azure Rights Management для предыдущей версии шифрования сообщений
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
description: Предыдущая версия шифрования сообщений Office 365 зависит от службы управления правами Microsoft Azure (прежнее название — Windows Azure Active Directory Rights Management).
ms.openlocfilehash: 879f4ec1db8a8cfe1fe3c8d3b1dd9e1fc68dd687
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165920"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-message-encryption"></a>Настройка azure Rights Management для предыдущей версии шифрования сообщений

В этом разделе описываются действия, которые необходимо предпринять, чтобы активировать и настроить службу Azure Rights Management (RMS), включаемую в Azure Information Protection, для использования с предыдущей версией шифрования сообщений Office 365 (OME).

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a>Эта статья относится только к предыдущей версии OME

Если вы еще не перешли на новые возможности OME, но уже развернули OME, сведения в этой статье применимы к вашей организации. Корпорация Майкрософт рекомендует спланировать переход на новые возможности OME, как только это будет приемлемо для вашей организации. Инструкции см. в настройках новых возможностей шифрования [сообщений Office 365.](set-up-new-message-encryption-capabilities.md) Дополнительные информацию о том, как новые возможности работают [](ome.md)в первую очередь, см. в этой теме. Остальная часть этой статьи относится к поведению OME перед выпуском новых возможностей OME.

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a>Необходимые условия для использования предыдущей версии шифрования сообщений Office 365
<a name="warmprereqs"> </a>

Шифрование сообщений Office 365 (OME), включая IRM, зависит от службы Azure Rights Management (Azure RMS). Azure RMS — это технология защиты, используемая Azure Information Protection. Чтобы использовать OME, ваша организация должна включить подписку exchange Online или Exchange Online Protection, которая, в свою очередь, включает подписку на Azure Rights Management.
  
- Если вы не знаете, что входит в подписку, см. описание службы Exchange Online для политики сообщений, восстановления [и соответствия требованиям.](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx)

- Если у вас есть служба Azure Rights Management, но она не настроена для Exchange Online или Exchange Online Protection, в этой статье описывается, как активировать службу Azure Rights Management, а затем описан лучший способ настроить OME для работы с Azure Rights Management.

- Если вы уже настроили OME для работы с azure Rights Management для Exchange Online или Exchange Online Protection, в зависимости от того, как вы настроили OME, вы можете сразу приступить к использованию OME и его новых возможностей. В этой статье объясняется, как определить, правильно ли настроена настройка OME, что делать, если необходимо изменить настройку, и что произойдет, если вы решите не изменять настройку. Например, чтобы использовать новые возможности, необходимо использовать Azure RMS с OME. Новые возможности нельзя использовать с локальной службой active Directory RMS.

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a>Активация azure Rights Management для предыдущей версии OME в Office 365

Необходимо активировать Службу управления правами Azure, чтобы пользователи в организации могли применять защиту информации к отправляемым ими сообщениям, а также открывать сообщения и файлы, защищенные службой управления правами Azure. Инструкции см. в [инструкциях по активации службы управления правами Azure.](https://go.microsoft.com/fwlink/p/?LinkId=525775) Завершив активацию, вернись сюда и продолжите выполнение задач, которые данная статья.
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>Настройка предыдущей версии OME для использования Azure RMS путем импорта доверенных доменов публикации (TPD)

TPD — это XML-файл, содержащий сведения о параметрах управления правами организации. Например, TPD содержит сведения о сертификате лицензирования сервера (SLC), используемом для подписи и шифрования сертификатов и лицензий, URL-адресах, используемых для лицензирования и публикации, и т. д. Вы импортируете TPD в свою организацию с помощью Windows PowerShell.
  
> [!IMPORTANT]
> Ранее можно было импортировать TPD из службы управления правами Active Directory (AD RMS) в организацию. Однако это не позволит вам использовать новые возможности OME и не рекомендуется. Если в настоящее время ваша организация настроена таким образом, Корпорация Майкрософт рекомендует создать план перехода с локальной службы active Directory RMS на облачную службу Azure Information Protection. Дополнительные сведения см. в переходе [с AD RMS на Azure Information Protection.](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) Вы не сможете использовать новые возможности OME, пока не завершите миграцию в Azure Information Protection.
  
 **Импорт TPD из Azure RMS**
  
1. [Подключение к Exchange Online с помощью удаленной powerShell.](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)

2. Выберите URL-адрес общего доступа по ключам, соответствующий географическому расположению вашей организации:

|**Location**|**URL-адрес расположения для общего доступа к ключам**|
|:-----|:-----|
|Северная Америка  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Европейский Союз  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Азия  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Южная Америка  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Office 365 для государственных организаций (облако сообщества госучреждений)  <br/> Это расположение для общего доступа к ключам RMS зарезервировано для клиентов, которые приобрели Office 365 для государственных номеров.  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
  
3. Настройте расположение для общего доступа [](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) к ключам, задав для этого 24-й и 10-й разделы. 

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
   ```
  
   Например, чтобы настроить расположение общего доступа к ключам, если ваша организация расположена в Северной Америке:

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
   ```

4. [Запустителет Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) с переключателем -RMSOnline, чтобы импортировать TPD из azure Rights Management: 

   ```powershell
   Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
   ```

   Где  *TPDName*  это имя, которое вы хотите использовать для TPD. Например, "Contoso North American TPD". 

5. Чтобы убедиться, что вы успешно настроили свою организацию для использования службы управления правами Azure, выполните с помощью переключателя -RMSOnline с помощью команды [Test-IRMConfiguration:](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx)

   ```powershell
   Test-IRMConfiguration -RMSOnline
   ```

   Помимо прочего, этот cmdlet проверяет возможность подключения к службе управления правами Azure, скачивает TPD и проверяет его действительность.

6. Чтобы [отключить](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) доступ к шаблонам управления правами Azure в Outlook в Интернете и Outlook, выполните этот запуск следующим образом: 

   ```powershell
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

7. Чтобы [](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) включить Службу управления правами Azure для облачной организации электронной почты и настроить ее на использование службы Azure Rights Management для шифрования сообщений Office 365, выполните этот запуск следующим образом:

   ```powershell
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```

8. Чтобы убедиться, что вы успешно импортировали TPD и включили azure Rights Management, используйте Test-IRMConfiguration для проверки функций Azure Rights Management. Подробные сведения см. в примере 1 в [test-IRMConfiguration.](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx)

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>У меня установлена предыдущая версия OME с управлением правами Active Directory, а не Azure Information Protection, что мне делать?
<a name="importTPDs"> </a>

Вы можете продолжать использовать существующие правила потока почты шифрования сообщений Office 365 с управлением правами Active Directory, но не можете настроить или использовать новые возможности OME. Вместо этого необходимо перейти на Azure Information Protection. Сведения о миграции и о том, что это означает для вашей организации, см. в сведениях о переходе с [AD RMS на Azure Information Protection.](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms)
  
## <a name="next-steps"></a>Дальнейшие действия
<a name="importTPDs"> </a>

Если вы хотите включить новые возможности OME, по завершению настройки azure Rights Management, см. сведения о настройке новых возможностей шифрования сообщений [Office 365,](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities) построенных на основе Azure Information Protection.
  
После того как вы настроите свою организацию для использования новых возможностей OME, вы можете определить правила потока почты для защиты сообщений электронной почты с помощью новых возможностей [OME.](define-mail-flow-rules-to-encrypt-email.md)
  
## <a name="related-topics"></a>Статьи по теме
<a name="importTPDs"> </a>

[Шифрование в Office 365](encryption.md)
  
[Техническая справка по шифрованию в Office 365](technical-reference-details-about-encryption.md)
  
[Управление правами Azure](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
