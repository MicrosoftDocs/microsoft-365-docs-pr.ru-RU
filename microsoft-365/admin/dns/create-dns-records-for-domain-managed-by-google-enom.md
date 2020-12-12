---
title: Создание записей DNS, когда доменом управляет Google (eNom)
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
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 3c490fbf-7833-4e43-be34-ed0dc3cce5e3
description: Узнайте, как получить доступ к eNom и создать DNS на странице "Домены Google".
ms.openlocfilehash: 3294be667653c568fbbd1a911bcfab9b6ea7788b
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656859"
---
# <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a>Создание записей DNS, когда доменом управляет Google (eNom)

 Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**. 
  
Чтобы перенести почтовые учетные записи в Корпорацию Майкрософт, необходимо создать запись DNS у регистратора доменных имен.
  
Если вы приобрели домен через Google при регистрации учетной записи **Google Apps for Work,** ваши записи DNS управляются Google, но зарегистрированы в eNom. 
  
Вы можете получить доступ к eNom и создать DNS на странице **"Домены** Google". Просто выполните действия, описанные в этой статье. 
  
## <a name="create-the-dns-record"></a>Создание DNS-записи

1. В консоли [администратора Google](https://www.google.com/work/apps/business)выберите **"Вход".**
    
    ![Google-Apps-Configure-1-1-0](../../media/37a6e9f6-319e-4c02-aa18-d8d06df7953d.png)
  
2. Введите доменное имя и выберите **"Перейти".**
    
    ![Google-Apps-Configure-1-1-1](../../media/2caf8dcb-4d40-4cfa-bc40-d634e454e699.png)
  
3. В нижней части страницы выберите **"Дополнительные элементы управления".**
    
    ![Google-Apps-Configure-1-2-0](../../media/1518ff78-035b-423e-85a3-c16d7faa0968.png)
  
4. Выберите раздел **Домены**.
    
    ![Google-Apps-Configure-1-2-1](../../media/c2972c06-9bca-43bd-9876-2cee63043bf1.png)
  
5. На странице **"Домены"** выберите **"Добавить или удалить домены".**
    
    ![Google-Apps-Configure-1-2-2](../../media/07b8068f-9a05-40aa-a041-fc495c729a18.png)
  
6. На странице **"Домены"** выберите **дополнительные параметры DNS.**
    
    > [!NOTE]
    > Если вы не приобрели доменное имя у Google при регистрации учетной записи **Google Apps for Work**, элемент **Дополнительные настройки DNS** не отображается на вашей странице **Домены**. В этом случае, чтобы добраться до параметров DNS и выполнить это и последующие действия, вам нужно перейти непосредственно на веб-сайт узла домена. Дополнительные [сведения см.](https://support.google.com/a/answer/54693?hl=en) в параметрах домена Access для G Suite. 
  
    ![Google-Apps-eNom-Configure-1-3](../../media/b244b29c-e479-40be-b380-4ffa0f74b421.png)
  
7. На странице **"Дополнительные параметры DNS"** выберите **"Войти в консоль DNS".** Запомните **учетное имя** и **пароль**. Они вам понадобится на следующем шаге. 
    
    ![Google-Apps-eNom-Configure-1-4](../../media/056a2767-462f-4847-acee-d01e3f773add.png)
  
8. Используя значения параметров **Учетное имя** и **Пароль** со страницы **Дополнительные настройки DNS**, войдите в **диспетчер доменов** Google. 
    
    ![Google-Apps-eNom-Configure-1-5](../../media/08b74652-8cdb-4560-a5fd-0899f86deee8.png)
  
9. На странице domain_name _, в разделе ***_Host* Records,** выберите "Изменить". 
    
    ![Google-Apps-eNom-Configure-1-6](../../media/d54fec18-b9d1-4796-8397-0393c964eade.png)
  
10. В разделе **"Записи хоста"** выберите **"Добавить новые".**
    
    ![Google-Apps-eNom-Configure-1-7](../../media/3562806a-4328-4e60-a717-0566841204cf.png)
  
11. В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.
    
    |**HOST (УЗЕЛ)**|**TXT VALUE**|**ТИП ЗАПИСИ**|
    |:-----|:-----|:-----|
    |@  <br/> ||TXT  <br/> |

    > [!NOTE]
    > This is an example. Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы. 
  
    [Как его найти?](../get-help-with-domains/information-for-dns-records.md)
  
12. Нажмите **Сохранить**.
    
    ![Google-Apps-eNom-Configure-1-9](../../media/7a6f7b45-8f79-487b-afe4-05949c2c04e8.png)
  
13. Выберите **"Сохранить изменения"**.
    
    ![Google-Apps-Configure-1-11](../../media/7f321236-33fb-4a7d-9d03-26605e9e558c.png)
  
> [!NOTE]
>  Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
