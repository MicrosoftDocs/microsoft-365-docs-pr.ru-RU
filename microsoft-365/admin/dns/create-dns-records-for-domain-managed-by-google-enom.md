---
title: Создание записей DNS при управлении доменом с помощью Google (eNom Central)
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 3c490fbf-7833-4e43-be34-ed0dc3cce5e3
description: Узнайте, как получить доступ к eNom Central и создать DNS через страницу Google Domains.
ms.openlocfilehash: 6c6698f3d11f42cd0298bdb66710ec3c62bac5ca
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400260"
---
# <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a>Создание записей DNS при управлении доменом с помощью Google (eNom Central)

 Если вы не нашли то, что вы ищете, обратитесь к разделу **[вопросы и ответы по доменам](../setup/domains-faq.md)**. 
  
Чтобы перенести учетные записи почты в корпорацию Майкрософт, необходимо создать запись DNS у регистратора доменных имен.
  
Если вы приобрели свой домен с помощью Google при регистрации учетной записи **Google Apps for work** , ваши записи DNS будут управляться Google, но зарегистрированы в eNom Central. 
  
Вы можете получить доступ к eNom Central и создать DNS через страницу Google **Domains** . Просто выполните действия, описанные в этой статье. 
  
## <a name="create-the-dns-record"></a>Создание DNS-записи

1. В [консоли администратора Google](https://www.google.com/work/apps/business)нажмите кнопку **войти**.
    
    ![Google-Apps-Configure-1-1-0](../../media/37a6e9f6-319e-4c02-aa18-d8d06df7953d.png)
  
2. Введите имя домена, а затем нажмите кнопку **Перейти**.
    
    ![Google-Apps-Configure-1-1-1](../../media/2caf8dcb-4d40-4cfa-bc40-d634e454e699.png)
  
3. В нижней части страницы выберите пункт **Дополнительные элементы управления**.
    
    ![Google-Apps-Configure-1-2-0](../../media/1518ff78-035b-423e-85a3-c16d7faa0968.png)
  
4. Выберите раздел **Домены**.
    
    ![Google-Apps-Configure-1-2-1](../../media/c2972c06-9bca-43bd-9876-2cee63043bf1.png)
  
5. На странице **домены** выберите **Добавить или удалить домены**.
    
    ![Google-Apps-Configure-1-2-2](../../media/07b8068f-9a05-40aa-a041-fc495c729a18.png)
  
6. На странице **домены** выберите пункт **Дополнительные параметры DNS**.
    
    > [!NOTE]
    > Если вы не приобрели доменное имя у Google при регистрации учетной записи **Google Apps for Work**, элемент **Дополнительные настройки DNS** не отображается на вашей странице **Домены**. В этом случае, чтобы добраться до параметров DNS и выполнить это и последующие действия, вам нужно перейти непосредственно на веб-сайт узла домена. Для получения дополнительных сведений ознакомьтесь со статьей [доступ к параметрам домена G Suite](https://support.google.com/a/answer/54693?hl=en) . 
  
    ![Google — Apps — eNom Central – configure – 1-3](../../media/b244b29c-e479-40be-b380-4ffa0f74b421.png)
  
7. На странице **Advanced DNS (дополнительные параметры DNS** ) выберите пункт **Вход в консоль DNS**. Запомните **учетное имя** и **пароль**. Они вам понадобится на следующем шаге. 
    
    ![Google — Apps — eNom Central – configure – 1-4](../../media/056a2767-462f-4847-acee-d01e3f773add.png)
  
8. Используя значения параметров **Учетное имя** и **Пароль** со страницы **Дополнительные настройки DNS**, войдите в **диспетчер доменов** Google. 
    
    ![Google — Apps — eNom Central – configure – 1-5](../../media/08b74652-8cdb-4560-a5fd-0899f86deee8.png)
  
9. На странице " ***domain_name*** " в разделе **записи узла** нажмите кнопку **изменить**.
    
    ![Google — Apps — eNom Central – configure – 1-6](../../media/d54fec18-b9d1-4796-8397-0393c964eade.png)
  
10. В разделе **записи узла** нажмите кнопку **Добавить новый**.
    
    ![Google — Apps — eNom Central – configure – 1-7](../../media/3562806a-4328-4e60-a717-0566841204cf.png)
  
11. В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.
    
    |**HOST (УЗЕЛ)**|**TXT VALUE**|**ТИП ЗАПИСИ**|
    |:-----|:-----|:-----|
    |@  <br/> ||TXT  <br/> |

    > [!NOTE]
    > This is an example. Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы. 
  
    [Как его найти?](../get-help-with-domains/information-for-dns-records.md)
  
12. Нажмите кнопку **Сохранить**.
    
    ![Google — Apps — eNom Central – configure – 1-9](../../media/7a6f7b45-8f79-487b-afe4-05949c2c04e8.png)
  
13. Нажмите кнопку **сохранить изменения**.
    
    ![Google-Apps-Configure-1-11](../../media/7f321236-33fb-4a7d-9d03-26605e9e558c.png)
  
> [!NOTE]
>  Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
