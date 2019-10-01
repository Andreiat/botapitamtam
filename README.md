# tamtam_api_lite
Попытка создать набор простых инструментов для написания ботов на базе API мессенджера TamTam. Набор содержит базовый функционал взаимодействия бота с пользователями и предназначен для начинающих программистов. Синтаксис комманд позволяет легко их модифицировать или создавать на их базе новые комманды используя официальную документацию https://dev.tamtam.chat/ .

Примеры реализации ботов с использованем библиотеки:   

https://github.com/registriren/filelink

https://github.com/registriren/yatranslate
  

Библиотека находится в стадии разработки, поэтому возможны изменения синтаксиса, которые приведут к неработоспособности вашего кода, проверяйте перед применением изменений на своей системе.

Чат для обсуждения вопросов, связанных с работой библиотеки https://tt.me/botapitamtam

Принцип взаимодействия с библиотекой:
- 
1. Методы, которые начинаются с get_ получают события, произошедшие с ботом (написанные или пересланные сообщения, результат нажатия кнопок, вложения и т.д.).
2. Методы, которые начинаются с send_ формируют события в боте (отправляют сообщения, генерируют кнопки и т.д.).
3. В основном цикле Вашей программы осуществляем запрос (long polling), происходящих с ботом событий, методом get_updates. Результат помещаем в переменную ( например update = get_updates() ).
4. Результат работы сформированных вами событий так же можно поместить в переменную (например update = send_message(parametry) ).
4. Для получения "тела" события, которое необходимо обработать, передаем переменную update выбранному методу get_ ( например get_text(update) ), работаем с результатом. 
5. Если запрошенное событие не произошло в ответ получим None.

## Описание методов (в разработке, смотрите в основном коде):
- [delete_message](doc/delete_message.md) - удаляет сообщение (контент) по его идентификатору (message_id).
- [get_callback_id](doc/get_callback_id.md) - получает значение callback_id нажатой кнопки.
- [get_chat_id](doc/get_chat_id.md) - получает идентификатор чата (диалога) в которм происходит взаимодействие с ботом.
- [get_link_chat_id](doc/get_link_chat_id.md) - получает идентификатор чата пересланного сообщения.
- [get_link_name](doc/get_link_name.md) - получает имя пользователя пересланного сообщения.
- [get_link_user_id](doc/get_link_user_id.md) - получает идентификатор пользователя пересланного сообщения.
- [get_marker](doc/get_marker.md) - получает маркер (порядковый номер) следующего события.
- [get_members](doc/get_members.md) - получает members.
- [get_message_id](doc/get_message_id.md) - получает идентификатор сообщения.
- [get_name](doc/get_name.md) - получает имя пользователя.
- [get_payload](doc/get_payload.md) - получает payload (присвоенное значение) нажатой кнопки.
- [get_text](doc/get_text.md) - получает значение поля text полученного сообщения (события) .
- [get_update_type](doc/get_update_type.md) - получает тип события, произошедшего в боте.
- [get_updates](doc/get_updates.md) - получение событий, произошедших в боте.
- [get_url](doc/get_url.md) - получает значение поля URL полученного сообщения (события).  
- [get_user_id](doc/get_user_id.md) - получает идентификатор пользователя полученного сообщения.
- [send_answer_callback](doc/send_answer_callback.md) - отправляет уведомление (реакцию) после нажатия кнопки.
- [send_audio](doc/send_audio.md) - отправляет аудиофайл с преобразованием в формат ТамТам.
- [send_buttons](doc/send_buttons.md) - формирует кнопки.
- [send_content](doc/send_content.md) - отправляет любой контент по сормированному attachments.
- [send_file](doc/send_file.md) - отправляет файл.
- [send_forward_message](doc/send_forward_message.md) - пересылает сообщение по его идентификатору.
- [send_mark_seen](doc/send_mark_seen.md) - отправляет уведомление о прочтении ботом сообщения.
- [send_message](doc/send_message.md) - отправляет текстовое сообщение.
- [send_photo](doc/send_photo.md) - отправляет изображение (несколько изображений) из локального файла.
- [send_photo_url](doc/send_photo_url.md) - отправляет изображение из URL.
- [send_reply_message](doc/send_reply_message.md) - формирует ответ на сообщение.
- [send_sending_audio](doc/send_sending_audio.md) - отправляет уведомление об отправке аудио.
- [send_sending_file](doc/send_sending_file.md) - отправляет уведомление об отправке файла.
- [send_sending_photo](doc/send_sending_photo.md) - отправляет уведомление об отправке изображения.
- [send_sending_video](doc/send_sending_video.md) - отправляет уведомление об отправке видео.
- [send_typing_on](doc/send_typing_on.md) - отправляет уведомление о печати сообщения.
- [send_video](doc/send_video.md) - отправляет видео.
- [token_upload_content](doc/token_upload_content.md) - вспомогательная функция получения токена загружаемого изображения.
- [upload_url](doc/upload_url.md) - вспомогательная функция получения URL загружаемого изображения.
