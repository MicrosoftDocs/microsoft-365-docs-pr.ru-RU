---
title: Изменение доменных имен для microsoft namecheap
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
ms.assetid: 84f467f6-28cf-40f0-94d0-a2a27ddfc2e7
description: 'Узнайте, как настроить собственный домен Майкрософт с помощью Namecheap, если вы хотите, чтобы корпорация Майкрософт управляет вашими записями DNS. '
ms.openlocfilehash: 0dec28c99bd49d3ba558e11afac8142c7df96591
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657988"
---
# <a name="change-nameservers-to-set-up-microsoft-with-namecheap"></a>Изменение доменных имен для microsoft namecheap

 Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.
  
Следуйте этим инструкциям, если вы хотите, чтобы корпорация Майкрософт управляет вашими записями DNS. (При этом вы можете управлять всеми своими записями DNS microsoft [на сайте Namecheap.)](create-dns-records-at-namecheap.md)
  
    
## <a name="add-a-txt-record-for-verification"></a>Добавление записи TXT для проверки

1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте Namecheap по [этой ссылке](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Вам потребуется войти в службу.
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. On the **Landing** page, under **Account,** choose **Domain List** from the drop-down list. 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. На странице **"Список доменов"** найдите имя домена, который нужно изменить, а затем выберите **"Управление".**
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. Выберите **"Расширенные DNS".**
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. В разделе **"ЗАПИСИ HOST"** выберите **"ДОБАВИТЬ НОВУЮ ЗАПИСЬ".**
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. В раскрывающемся списке **Type** (Тип) выберите **TXT Record** (Запись TXT).
    
    > [!NOTE]
    > При **выборе** "ADD NEW RECORD" автоматически появляется выпадайка **"Тип".**
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.
    
    (Выберите значение **TTL** в выпадаемом списке.) 
    
|**Type (Тип)**|**Host (Узел)**|**Value** (Значение)|**TTL** (Срок жизни)|
|:-----|:-----|:-----|:-----|
|TXT  <br/> |@  <br/> |MS=ms *XXXXXXXX*  <br/> **Примечание.** Это пример. Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.           [Как его найти?](../get-help-with-domains/information-for-dns-records.md)          |30 мин  <br/> |
   
   ![Namecheap-BP-Verify-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. Выберите **контрольный знак** "Сохранить изменения". 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.
    
Теперь, когда вы добавили запись на сайте регистратора доменных имен, вы вернемся в корпорацию Майкрософт и запросите поиск записи.
  
Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.
  
1. В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).

    
2. На странице **Domains** (Домены) выберите домен, который нужно проверить. 
    
    
  
3. На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).
    
    
  
4. На странице **Проверка домена** выберите **Проверить**.
    
    
  
> [!NOTE]
>  Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Изменение записей сервера доменных имен

Чтобы завершить настройку домена с помощью Майкрософт, измените записи доменных имен своего домена у регистратора доменных имен, указав на основной и дополнительный серверы имен Майкрософт. Это настраивает Майкрософт для обновления записей DNS домена за вас. Мы добавим все записи, так что электронная почта, Skype для бизнеса online и общедоступный веб-сайт будут работать в вашем домене и вам больше не придется ничего настраивать.
  
> [!CAUTION]
> При изменении записей сервера доменных имен таким образом, чтобы они указывают на серверы доменных имен Майкрософт, это влияет на все службы, связанные с вашим доменом. Например, все сообщения электронной почты, отправленные на ваш домен (например, rob@ *your_domain*  .com), после внести это изменение в корпорацию Майкрософт начнут приходить в корпорацию Майкрософт. 
  
> [!IMPORTANT]
>  После выполнения действий, описанных в этом разделе, в списке должны быть указаны  *только*  следующие четыре сервера имен: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  В приведенной ниже процедуре показано, как удалить из списка все остальные, нежелательные серверы имен, а также как добавить  *правильные*  серверы имен, если их еще нет в данном списке. 
  
1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте Namecheap по [этой ссылке](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Вам потребуется войти в службу.
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. On the **Landing** page, under **Account,** choose **Domain List** from the drop-down list. 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. На странице **"Список доменов"** найдите имя домена, который нужно изменить, а затем выберите **"Управление".**
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. Выберите **домен.**
    
    ![Namecheap-BP-Redelegate-1-1](../../media/59588406-794e-4ae4-8526-35e3111b5791.png)
  
5. Найдите раздел **NAMESERVERS** (Серверы доменных имен), а затем выберите **Custom** (Другое) в раскрывающемся списке **Namecheap Default** (Значения Namecheap по умолчанию). 
    
    ![Namecheap-BP-Redelegate-1-2](../../media/7df56295-fdb3-472f-9442-13f780c2c93e.png)
  
6. В зависимости от того, есть ли на странице, которая отображается сейчас, уже есть или нет, продолжите одну из двух следующих процедур.
    
### <a name="if-there-are-no-nameservers-already-listed"></a>На странице НЕ УКАЗАНЫ серверы доменных имен
<a name="BKMK_ProcedureWithOUT"> </a>

1. Дважды **выберите ADD NAMESERVER,** чтобы добавить две новые строки.
    
    ![Namecheap-BP-Redelegate-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
2. В поля **Nameserver** (Сервер доменных имен) введите (или скопируйте и вставьте) значения из таблицы ниже.
    
|||
|:-----|:-----|
|**Nameserver 1** (Сервер доменных имен 1) <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Nameserver 2** (Сервер доменных имен 2) <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Nameserver 3** (Сервер доменных имен 3) <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Nameserver 4** (Сервер доменных имен 4) <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Namecheap-BP-Redelegate-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
3. Выберите **контрольный знак** "Сохранить". 
    
    ![Namecheap-BP-Redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов. Затем ваша почта Майкрософт и другие службы будут настроены для работы с вашим доменом. 
  
### <a name="if-there-are-nameservers-already-listed"></a>На странице УКАЗАНЫ серверы доменных имен

> [!CAUTION]
> Выполните эти действия,  *только*  если у вас есть серверы доменных имен, отличные от четырех  *правильных*  серверов. (Т. е. удалите  *только*  серверы доменных имен,  *отличные*  от **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** и **ns4.bdm.microsoftonline.com**.) 
  
1. Если в полях **Nameserver** (Сервер доменных имен) указаны другие серверы доменных имен, удалите их: выберите каждый из них и нажмите клавишу **DELETE**. 
    
    ![Namecheap-BP-Redelegate-1-4](../../media/3270603a-c4f4-40b7-acad-733d56e2f53c.png)
  
2. Дважды **выберите ADD NAMESERVER,** чтобы добавить две новые строки. 
    
    ![Namecheap-BP-Redelegate-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
3. В поля **Nameserver** (Сервер доменных имен) введите (или скопируйте и вставьте) значения из таблицы ниже.
 
    
|||
|:-----|:-----|
|**Name Server 1** (Сервер доменных имен 1) <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2** (Сервер доменных имен 2) <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Nameserver 3** (Сервер доменных имен 3) <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Nameserver 4** (Сервер доменных имен 4) <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Namecheap-BP-Redelegate-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
4. Выберите **контрольный знак** "Сохранить". 
    
    ![Namecheap-BP-Redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов. Затем ваша почта Майкрософт и другие службы будут настроены для работы с вашим доменом.
