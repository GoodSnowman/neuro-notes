# Система резервного копирования
### Резервное копирование настроено для следующих сервисов:
- postgresql-dev
- postgresql-prod

### Переодичность создания бэкапов:
- для дева - каждый день в 02:00 Мск
- для прода - каждый день в 00:00 Мск

## Процесс создания резервной копии
- Поднимается реплика копируемой базы отдельным сервисом
- Происходит проверка всех необходимых переменных
- Создается бэкап всех существующих баз
- Создается бэкап непосредственно БД приложения (postgres)
- Архивирование бэкапов
- Ротация (Удаляется все старше 7 дней)
- Архив шифруется и отправляется на гугл диск

## Занимаемое место

## Что произойдет при ошибке во время бэкапа
При  возникновении ошибки в процессе создания резервной копии упадет pipeline с выводом сообщения об ошибке в лог. Для самого сервиса БД падение угрозы не несет.

## Ротирование
На сервере хранятся бэкапы за последнюю неделю. На google-disk - уточню

## Инструкция по восстановлению из бэкапа

## Приблизительное время восстановления

## Прочее
