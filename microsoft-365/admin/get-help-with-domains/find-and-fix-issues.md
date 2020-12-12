---
title: Поиск и устранение неполадок после добавления домена и записей DNS
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Узнайте, как отслеживать любые проблемы, которые могут возникнуть при настройке пользовательского домена, убедившись, что записи DNS настроены правильно.
ms.openlocfilehash: d2935a7fcc134f7f6d2dd06a5b4e0e0a8761ad8a
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658523"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a>Поиск и устранение неполадок после добавления домена и записей DNS

 Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**. 
  
Настройка домена для работы с Microsoft 365 может быть сложной задачей. С DNS-системой необходимо работать, и настройка DNS для вашего домена влияет на важные бизнес-действия, такие как электронная почта!

> [!NOTE]
> Вы можете проверить, нет ли проблем с доменом, проверив его состояние. Перейдите **в "Настройка**  >  **доменов"** и просмотреть уведомления в столбце **"Состояние".** Если вы видите проблему, выберите дополнительные действия (три точки), а затем выберите **"Проверить состояние".** В открываемой области описываются все проблемы, которые произошли с вашим доменом.
  
## <a name="whats-going-on"></a>Почему?

- [Не можете проверить домен?](#cant-verify-your-domain)
    
- [Outlook не работает?](#outlook-isnt-working)
    
- [Все сообщения электронной почты переключились на Microsoft 365, и вы хотите, чтобы ваша электронная почта переключилась?](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [Не можете подтвердить состояние некоммерческой или учебной учетной записи?](#cant-confirm-non-profit-or-school-account-status)

- [Службы не работают с вашим доменом?](#services-not-working-with-your-domain)
    
- [Не работает доступ к веб-сайту?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>Не удается проверить свой домен?
<a name="BKMK_verify"> </a>

Вот несколько причин, по которым может не удаваться проверить домен:
  
1. **Проверочная запись неправильная.** Убедитесь, что вы скопировали и вставили точное значение в проверочную запись TXT на узле DNS. Часто пользователи забывают указать "MS =". Эта часть тоже нужна! 
    
2. **Запись не была сохранена.** На некоторых узлах DNS необходимо выполнить дополнительное действие для сохранения файла зоны (в котором хранится запись DNS), чтобы он обновился в Интернете. Убедитесь, что вы сохранили изменения, чтобы Microsoft 365 видел и проверял запись. 
    
3. **Запись не обновилась в Интернете.** Обычно новая запись становится доступна через несколько минут, но иногда ее обновление может занять до нескольких часов. 
    
## <a name="outlook-isnt-working"></a>Не работает Outlook?
<a name="BKMK_OutlookBroken"> </a>

Если вы настроили свою запись MX и другие записи DNS для домена правильно, но почта не работает, мы поможем [устранить неполадки с Outlook](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a>Все сообщения электронной почты переключились на Microsoft 365, и вы хотите, чтобы ваша электронная почта переключилась?
<a name="BKMK_EmailSwitched"> </a>

При добавлении домена в Microsoft 365 обычно запись MX вашего домена обновляется (вами или Microsoft 365) так, чтобы она была направлена на Microsoft 365, а Вся электронная почта, отправленная на этот домен, начиналась с Microsoft 365. Перед изменением записи MX убедитесь, что вы создали почтовые ящики в Microsoft 365 для всех, у кого есть электронная почта в вашем домене.
  
Что делать, если вы не хотите перемещать электронную почту для всех в вашем домене в Microsoft 365? Вы можете предпринять действия для [пилотного проекта Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)с несколькими адресами электронной почты.
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>Не можете подтвердить состояние некоммерческой или учебной учетной записи?
<a name="BKMK_validateAcct"> </a>

Существует несколько сценариев, когда вам нужно просто проверить домен вашей организации и не настроить службы. Например, чтобы доказать Microsoft 365, что ваша организация имеет право на подписку на учебное заведения.
  
Инструкции по проверке домена [Microsoft 365,](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) чтобы подтвердить право собственности, статус некоммерческой организации или образования или активировать Yammer, чтобы убедиться, что вы выполнили все необходимые действия. Он немного отличается для каждой ситуации. 
  
## <a name="services-not-working-with-your-domain"></a>Службы не работают с вашим доменом?
<a name="BKMK_Test"> </a>

Мы поможем вам выявить проблемы с настройкой DNS для домена. The domains troubleshooter in Microsoft 365 will show you any records that need fixing, and exactly what the records need to be set to. 

> [!TIP]
> DNS настроена правильно, но почта не работает в Outlook на рабочем столе? Ознакомьтесь с различными сценариями потока почты, которые вы можете использовать в [Microsoft 365,](https://docs.microsoft.com/exchange/mail-flow-best-practices/mail-flow-best-practices) чтобы убедиться, что у вас все настроено правильно для вашей компании. Дополнительную помощь по устранению неполадок с электронной почтой можно найти здесь: [Устранение неполадок в Outlook](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues). 
  
## <a name="accessing-your-website-isnt-working"></a>Ваш веб-сайт недоступен?
<a name="BKMK_Website"> </a>

Если вы устранили все неполадки DNS, но у вас по-прежнему возникают проблемы, попробуйте одно из указанных ниже действий.
  
- Пользователи не могут войти на ваш веб-сайт в www.mydomain.com: [Диагностика неполадок веб-сайта](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
    
- You can't update your A record or CNAME record to point to your website: [Update custom DNS records in Microsoft 365](../dns/add-or-edit-custom-dns-records.md)

## <a name="related-content"></a>Связанные материалы

[Устранение неполадок: аудит данных при изменении проверенного домена](https://docs.microsoft.com/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain)

    
