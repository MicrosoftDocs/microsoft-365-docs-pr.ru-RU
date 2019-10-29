---
title: Шаг 2. Защита паролей
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Необходимо обеспечить надежность и управляемость ваших паролей в масштабах организации.
ms.openlocfilehash: 375f4a678e85dccb544ffaf56f648e98609841d9
ms.sourcegitcommit: 2aeafb631aaabc53eea0a8029711eb891e48d249
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2019
ms.locfileid: "37746515"
---
# <a name="step-2-secure-your-passwords"></a>Шаг 2. Защита паролей

![Этап 2. Удостоверения](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a>Запрет слабых паролей

*Это необязательная процедура, применимая к версиям Microsoft 365 корпоративный E3 и E5*

Все ваши пользователи должны применять [Руководство по паролям корпорации Майкрософт](https://www.microsoft.com/research/publication/password-guidance/) для создания своих паролей учетных записей пользователей.

Чтобы запретить пользователям создавать легко подбираемые пароли, применяйте службу защиты паролей Azure AD, в которой используется как глобальный список запрещенных паролей, так и необязательный настраиваемый список запрещенных паролей, указываемый вами. Например, вы можете указать следующие термины, относящиеся к вашей организации:

- Фирменные названия
- Названия продуктов
- Расположения (например, штаб-квартира компании)
- Внутренние термины, относящиеся к компании
- Сокращения с определенным значением в компании

Вы можете запретить слабые пароли в [облачной среде](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) и [локальных доменных службах Active Directory (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).

Промежуточной контрольной точкой в данном разделе служат [критерии выхода](identity-exit-criteria.md#crit-password-prot).

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a>Упрощение процедуры сброса паролей

*Это необязательная процедура, применимая к наборам Microsoft 365 корпоративный E3 и E5*

В этом разделе описывается включение самостоятельного сброса паролей (SSPR), позволяющего пользователям сбрасывать пароли и разблокировать учетные записи. Чтобы получать оповещения о неправильном или несанкционированном использовании, можно использовать подробные отчеты, которые позволяют отслеживать доступ пользователей к системе, а также уведомления. Прежде чем развертывать функцию сброса паролей необходимо включить обратную запись паролей.

См. [инструкции по развертыванию функции сброса паролей](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Руководство по лаборатории тестирования: сброс пароля](password-reset-m365-ent-test-environment.md) |
|||

Промежуточной контрольной точкой в данном разделе служат [критерии завершения](identity-exit-criteria.md#crit-identity-pw-reset).


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a>Упрощение входа пользователей

*Этот этап не является обязательным для гибридных развертываний. Он применяется к версиям E3 и E5 набора Microsoft 365 корпоративный.*

В этом разделе описывается настройка эффективного единого входа в Azure Active Directory в сочетании с синхронизацией хэша паролей (PHS) и сквозной проверкой подлинности (PTA), чтобы разрешить пользователям входить в службы, использующие учетные записи пользователей Azure AD, не вводя свои пароли и (во многих случаях) имена пользователей. Это упрощает доступ пользователей к облачным приложениям, например Office 365, без необходимости в дополнительных локальных компонентах, таких как серверы федерации удостоверений.

Вы настроите простой единый вход для Azure AD с помощью средства Azure AD Connect.

См. [инструкции по настройке простого единого входа для Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).

|||
|:-------|:-----|
|![Руководства для лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Руководство по лаборатории тестирования: простой единый вход Azure AD](single-sign-on-m365-ent-test-environment.md) |
|||

Промежуточной контрольной точкой в данном разделе служат [критерии завершения](identity-exit-criteria.md#crit-identity-sso).


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a>Настройка страницы входа в Office 365

*Этот шаг не является обязательным. Он применяется к версиям E3 и E5 набора Microsoft 365 корпоративный.*

В этом разделе описывается, как помочь пользователям узнавать страницу входа в систему вашей организации, добавив на нее название и логотип компании, а также другие отличительные элементы. 

С помощью Microsoft 365 корпоративный вы можете настроить внешний вид страницы входа и страниц Панели доступа так, чтобы на них отображались логотип вашей компании, цветовые схемы и настраиваемая пользовательская информация. 

Дополнительные сведения см. в статье [Добавление фирменной символики компании на страницу входа в Office 365](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).

Инструкции по настройке см. в статье [Краткое руководство по добавлению фирменной символики организации на страницу входа в Azure Active Directory](https://aka.ms/aadpaddbranding).

Промежуточной контрольной точкой в данном разделе служат [критерии завершения](identity-exit-criteria.md#crit-identity-custom-sign-in).

## <a name="next-step"></a>Следующий шаг

|||
|:-------|:-----|
|![Шаг 3](./media/stepnumbers/Step3.png)| [Защита пользовательских входов и управление ими](identity-secure-user-sign-ins.md) |
