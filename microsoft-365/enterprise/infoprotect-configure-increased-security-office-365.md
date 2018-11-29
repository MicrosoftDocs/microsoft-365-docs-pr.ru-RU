---
title: Шаг 3. Настройка усиленной защиты для Office 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: В этом разделе рассказывается, как настроить усиленную защиту для Office 365, включая Office 365 Advanced Threat Protection.
ms.openlocfilehash: 0344778b8d8f9940dc6267a39eac2f4cfb261f9a
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870965"
---
# <a name="step-3-configure-increased-security-for-office-365"></a>Шаг 3. Настройка усиленной защиты для Office 365

*Этот шаг — обязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Чтобы защитить вашу подписку на Office 365 и ее данные от вредоносных угроз, выполните инструкции в статье [Настройка клиента Office 365 для повышения безопасности](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355). Кроме того, настройте указанные ниже дополнительные средства обеспечения безопасности.

- Политики управления угрозами в Центре безопасности и соответствия требованиям Office 365
- Дополнительные параметры, используемые во всем клиенте Exchange Online
- Политики общего доступа, используемые во всем клиенте, в Центре администрирования SharePoint
- Параметры в Azure Active Directory

После настройки вы сможете получать сведения о состоянии системы обеспечения безопасности из указанных ниже источников.

- Панель мониторинга и отчеты в Центре безопасности и соответствия требованиям
- [Оценка безопасности Office 365](https://securescore.office.com/)
 
  Для доступа к этой странице необходимо войти в систему в качестве администратора клиента Office 365.

Кроме того, с помощью Cloud App Security или Office 365 Cloud App Security вы можете отслеживать события безопасности и выполнять необходимые действия. Дополнительные сведения см. в статье [Общие сведения о безопасности облачных приложений Office 365](https://support.office.com/article/Overview-of-Office-365-Cloud-App-Security-81f0ee9a-9645-45ab-ba56-de9cbccab475).

Office 365 Advanced Threat Protection — это дополнительная функция защиты. Благодаря ей совместная работа в вашей организации станет более безопасной благодаря указанным ниже средствам.

- Защита ссылок и вложений в электронных письмах. 
- Функции анализа подделок и антифишинга для почты в Exchange Online и файлов в SharePoint Online, OneDrive для бизнеса и Microsoft Teams. 

>[!Note]
>Функция Office 365 Advanced Threat Protection включена в план E5 в Microsoft 365 корпоративный. Если вы используете план E3 в Microsoft 365 корпоративный, вы можете приобрести отдельные лицензии на Advanced Threat Protection.
>

Сведения о том, как включить Office 365 Advanced Threat Protection, см. в разделе [Включение Office 365 Advanced Threat Protection для SharePoint Online, OneDrive для бизнеса и Microsoft Teams](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).

Дополнительные сведения см. в статье [Office 365 ATP для SharePoint, OneDrive и Microsoft Teams](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607).


|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Руководство по лаборатории тестирования: настройка усиленной защиты Office 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

Прежде чем перейти к следующему шагу, проверьте [условия](infoprotect-exit-criteria.md#crit-infoprotect-step4), при выполнении которых можно считать данный шаг завершенным.

## <a name="next-step"></a>Следующий шаг


|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[Настройка управления привилегированным доступом](infoprotect-configure-privileged-access-management.md)|


