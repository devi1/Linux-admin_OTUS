# Performance Lab

Глянь еще https://youtu.be/gXeaeOAIfvc


Еще хорошая статья по докладу с Хайлоуд++
https://habr.com/ru/post/322562/
Только переписыванием софта (как тут мемкешед переписывали) тебе заниматься не нужно


Но в целом - не представляю, как по 1-2 статьям научиться таким вещам
Нужно разобраться по очереди (в работе или хотя бы в лабе) с каждой из используемых софтин, а затем постепенно усложнять схему (сначала вебсерверы отмасштабировать, потом БД, потом кэши и т.п., на каждом этапе только одно усложнение).


memcache принято менять на redis и на его мультитредовые аналоги ;)
а apache менять на nginx
пока проект мелкий, можно на одном сервере держать
потом придется переносить, через связку redis и репликацию master-slave (она не только в MySQL бывает, репликация ;)

если тебе хватает CPU и памяти, то можно держать на одном сервере, но сразу тренироваться переносить на другой без простоя... или с минимальным простоем


все наверное это знают, и много кто так делает, но все же напишу. Для постоянного изучения и опробации лучше иметь домашний стенд, такой недорого можно собрать на алиэкспресс. На базе китайской материнской платы типа Huanan. Там же к ней продаются серверные процы и память БУ, буквально за 30-35к(сейчас возможно даже дешевле) можно собрать неплохой стенд. К примеру я собрал на базе xeon 2680v2(10 ядер, 20 потоков)+64ГБ reg ecc+nvme накопитель(на него положил диски виртуалок). Для учебных стендов его "за глаза" хватает

--
можно тесты и гонять, думаю
тут сложности две, заодно две возможности прокачаться
- сделать тесты, которые правдоподобно эмулируют тысячи подключений в секунду, например, сложно, но можно
- ну и собсно оптимизацию отточить

Отдельная задача - придумать темы тестов
Можно пробовать построить копии реально работающих сервисов, и тестировать нагрузку на них

можно потрейсить любое приложение, которое достаточно быстро исполняется
пхп какойнибудь потрейсить, там достаточно понятно все

Еще есть анализ коредампов
Похоже на стрейс, но как "снимок памяти в момент проблемы"

