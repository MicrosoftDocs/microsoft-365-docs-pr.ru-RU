---
title: Зачем нужна запись CNAME в Office 365 для MSOID?
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NOINDEX
description: Дополнительные данные о записи CNAME "MSOID" в Office 365, которая направляет вас на лучший сервер для процессов проверки подлинности, поэтому вы получите более быстрый ответ.
monikerRange: o365-21vianet
ms.openlocfilehash: a1d587abc9db03c9a1f7c5f66711fde3648a0e96
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914310"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a>Зачем нужна запись CNAME в Office 365 для MSOID?

 Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**. 
> [!NOTE]
> Ниже приводится только **Office 365, выполняемый 21Vianet.
  
У вас может возникнуть вопрос: зачем нужно добавлять в Office 365 запись CNAME "MSOID"? Эту запись необходимо добавить для всех личных доменов независимо от вида подписки. Зачем она нужна? Это технический, но важный вопрос. Запись направляет вас на лучший сервер проверки подлинности, позволяющий вам получить самый быстрый отклик.
  
Технические подробности: при запуске клиентского приложения, взаимодействующего с Office 365, например Skype для бизнеса online, Outlook, Windows PowerShell или средства синхронизации Microsoft Azure Active Directory, ваши учетные данные должны пройти проверку подлинности. В Office 365 используется запись CNAME, которая указывает на оптимальную конечную точку проверки подлинности для вашего региона. Это позволяет уменьшить время отклика при проверке подлинности.
  
Если эта запись CNAME не указана для вашего домена, то в приложениях будет использоваться конечная точка по умолчанию, которая находится в США. Это может замедлить проверку. Если же запись CNAME настроена неправильно (например, неверно введен адрес в поле **Указывает на**), то приложения вообще не смогут пройти проверку подлинности.
  
 Если Office 365 управляет записями **DNS** вашего домена, Office 365 настраивает эту запись CNAME для вас. 
  
 **Если вы управляете записями DNS** для вашего домена на вашем DNS-хозяйте, вы создаете эту запись самостоятельно, следуя инструкциям для вашего [DNS-хоста.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
  
Если вы планируете развертывание Office 365 и хотите узнать больше обо всех записях DNS, которые вам может потребоваться добавить или обновить, ознакомьтесь с ними в [справке:](../../enterprise/external-domain-name-system-records.md)записи системы внешних доменных имен для Office 365 .
