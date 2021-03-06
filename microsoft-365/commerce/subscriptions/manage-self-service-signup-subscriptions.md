---
title: Управление подписками на самообслуживку
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
search.appverid: MET150
description: Узнайте, как управлять бесплатными подписками на самообслуживку для вашей организации.
ms.date: 03/17/2021
ms.openlocfilehash: 741c9e0b45f127ffc0753b34982073f90c525d5b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52536074"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>Управление подписками на самообслуживку

## <a name="what-are-self-service-sign-up-subscriptions"></a>Что такое подписки на самообслуживку?

Для регистрации пользователей в вашей организации доступно ограниченное число бесплатных подписок для самостоятельной регистрации. Пользователь может зарегистрироваться только для себя и использовать подписку на самообслуживку. Вы управляете подписками на самообслуживку, блокируя регистрацию пользователей и удаляя бесплатные подписки, на которые подписаны пользователи. Дополнительные сведения о самообслужии и доступных подписках см. в журнале [Using self-service sign up in your organisation.](../../admin/misc/self-service-sign-up.md)

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a>Просмотр списка подписки на самообслуживку

1. В Центре администрирования перейдите на страницу **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ваши продукты</a>.
2. На **вкладке Продукты** выберите значок фильтра, а затем выберите **Бесплатный**. Отображается список всех подписок на регистрацию самообслуживаний.

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>Чем эти подписки отличаются от подписки на покупку самообслуживки?

Подписки на самообслуживку бесплатны и доступны для большего списка продуктов, чем подписки на покупку самообслуживаний. Когда пользователь подписывает подписку на покупку самостоятельной службы, он несет ответственность за ее оплату. Подписки на самообслуживку доступны только для продуктов Power Platform (Power BI, Power Apps и Power Automate), Project и Visio. Дополнительные сведения см. в [faq самообслуживной покупки.](self-service-purchase-faq.yml)

## <a name="block-users-from-signing-up"></a>Блокировка регистрации пользователей

Вы используете комлет [**Set-MsolCompanySettings**](/powershell/module/msonline/set-msolcompanysettings?preserve-view=true&view=azureadps-1.0) с параметром **AllowAdHocSubscriptions,** чтобы определить, могут ли пользователи зарегистрироваться для подписки на самообслуживку. Дополнительные сведения см. в дополнительных сведениях о том, как управлять настройками [самообслуживки?](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="delete-a-self-service-sign-up-subscription"></a>Удаление подписки на самообслуживку

> [!IMPORTANT]
> При удалении подписки на самообслуживку вы блокируете доступ всех пользователей к своим данным и электронной почте и удаляете все данные и электронную почту.

1. В Центре администрирования перейдите на страницу **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ваши продукты</a>.
2. На **вкладке Продукты** выберите значок фильтра, а затем выберите **Бесплатный**.
3. Выберите подписку на самообслуживку, которую необходимо удалить. 
4. На странице сведения о подписке в разделе **Подписки** и параметры оплаты выберите **Удалить подписку.**
5. В области **Удалить подписку** выберите контрольный окне, а затем выберите **подписку Удалить**.

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>У меня есть подписка на самообслуживку, которая блокирует удаление каталогов

Продукты самообслуживления, для регистрации на которые могут зарегистрироваться отдельные пользователи, также создают гостевого пользователя для проверки подлинности в каталоге Azure AD. Чтобы избежать потери данных, эти продукты самообслуживания блокируют удаления каталогов, пока они не будут полностью удалены из каталога. Они могут быть удалены только администратором Azure AD. Дополнительные сведения см. [в публикации Delete a directory in Azure Active Directory.](/azure/active-directory/users-groups-roles/directory-delete-howto)
