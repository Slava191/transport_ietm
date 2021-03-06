---
title: Регламентные работы 
icon: 'fas fa-wrench'
description: 'Список регламентных работ, их описание и период выполнения'
---

# Регламентные работы

Операция|Периодичность|Описание 
--- | --- | ---
Просмотр логов систем, сетевого оборудования, системы резервного копирования |	ежедневно |	Для просмотра логов используется принцип централизации, то есть настройка сбора логов всех систем в единое место. Такую роль выполняет система мониторинга, которая выдает предупреждения, в том числе на основе лога Windows, syslog, может читать текстовые файлы. В случае обнаружения проблемы, она с соответствующим приоритетом ставится в очередь задач системного администратора, по данному направлению. При необходимости ему даются рекомендации по устранению проблемы. 
Анализ сетевого траффика	| ежедневно |	Позволяет проверить корректность настроенных Вами ограничений, обнаружить возможные изъяны, или даже бреши в безопасности, оценить реальные нагрузки на каналы передачи данных. Регулярные проверки по этому направлению дают много пищи для размышлений. К тому же обычно руководство достаточно внезапно просит представить отчет, о посещаемых пользователями ресурсах Интернет.Плановая перезагрузка	ежемесячно	Во время перезагрузок от «утечек» очищается оперативная память, чистятся логи и завершаются зависшие фоновые задания. Если не делать плановые перезагрузки Windows, то система может зависнуть.
Анализ потребленных ресурсов |	ежемесячно |	Задача заключается в просмотре отчетов по потребляемым ресурсам, анализе тенденций и нахождении потенциально критических точек. Отчеты можно получать из разных мест: система мониторинга, средства анализа на серверах или системах хранения данных. 
Принудительная установка обновлений через WindowsUpdate |	ежемесячно |	Автоматическая установка обновлений на серверах очень нежелательна, потому что после обновления нужна перезагрузка сервера, а после чего - распаковка скачанных обновлений. Это занимает значительное время, которое недопустимо терять в рабочий день. Кроме того, иногда обновления бывают «проблемными» и приводят к неработоспособности различных служб. Приходится откатывать такие обновления, а это тоже занимает время и получается простой сервера.
Проверка открытых портов |	Раз в 2 месяца |	Данная проверка позволяет контролировать безопасность сети клиента на предмет открытых ненужных портов.
Обновление сертификатов и CRL (cписки SSL-сертификатов, отозванных центром выдачи) |	Раз в пол года |	Просроченный сертификат или список отозванных сертификатов может привести к временной недоступности сервисов или даже к остановке их работы, а автоматический перевыпуск по ряду причин не всегда возможен.
