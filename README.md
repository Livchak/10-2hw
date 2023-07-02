# Домашнее задание к занятию "`10-02hw`" - `Ливчак Сергей`

---

### Задание 1

`В чём различие между SMP- и MPP-системами?`

1. `Заполните здесь этапы выполнения, если требуется ....`
Эти системы построения класетра отличаются средством внутринней организации коммуникации между узлами.
SMP система представляет из себя единую систему связанную коммуникационной системой с общей памятью и общими средствами ввода вывода. Пример тому современные процессоры по сравнению с одноядерными старыми. У каждого ядра есть своя кеш память, все ядра связаны между собой шиной данных (пример Intel QuickPath Interconnect ), общая оперативная память и система ввода данных. MPP это кластер огранизованный на отдельных вычислительных узлах (со своими - CPU, RAM, сеть, кеш и устройство ввода вывода) объединенные сетью обмена сообщениями. Задачи на таком кластере выполняются параллельно (к примеру обработать большой массив данных) Примером тому система организованная Стенфордским университетом по исследованиям в области био медицины Folding@home. Каждый желающй мог загрузить приложение на свой домашний компьютер и поучаствовать в обработке массива данных.

---

### Задание 2

`В чём отличие сильно связанных и слабо связанных систем?`

1. У этих систем разные системы памяти и как следствие разные системы коммуникации. У слабо связанных система система коммуникации представляет из себя систему передачи сообщений, а в сильно связанной полноценная межпроцесорная коммуникация. Также можно отметить что в слабо связанных системах нет конфликта помяти из-за отсутствия общей памяти. В сильно связанных системах узлы имеют высокую доступность памяти, что повышает производительность приложений чуствительных к обмену данных с памятью и снижает устойчивость к выходу из строя отдельных компонентов или узлов. Слабо связанные системы призваны быть устойчивыми, легко масштабируемыми и выход из строя одного из узлов скорее приведёт к незавершению выполнения конкретной задачи которую можно назначить другому узлу сети. Цели у этих систем разные - сильно связанные больше подходят для выполнения задач в реальном времени, тогда как слабо связанная может насчитывать куда большее число узлов и быть доступнее одновременно.

---

### Задание 3

`Какие преимущества отличают кластерные системы от обычных серверов?`

1. Кластерные системы это структура вычислительных систем куда могут включаться как сильно связанные так и слабо связанные системы с обеспечением беспребойности работы путём избыточности. Легкость масштабируемости без ограничений(приложения должны поддерживать такую масштабируемость) и как следствие производительность.

---

### Задание 4

`Приведите примеры типов современных кластерных систем.`

1. Кластеры высокой производительности HPC-кластеры, на них производится моделирование, научные рассчёты...
2. Отказоустойчивые кластеры, устойчивость которых достигается путём избыточности (Linux HA, red hat cluster suite, VMware vSphere)
3. Кластеры с балансировкой нагрузки, сетевая, транспортная и прикладная балансировка. SDN-контроллеры(маршрутизация), TCP/UDP (распределение между несколькими серверами), Nginx
4. Системы распределительных вычислений. это MPP.  Распреленные вычисления массива данных, часто использут в научных приложениях где нужно обработать большой массив данных.

---

### Задание 5

`Где используют сервис Kafka, rabitMQ?`

1. Kafka это система потоковой обработки сообщений в реальном времени между серверными приложениями. Систему можно встретить в системах мониторинга, аналитики, обработки событий и машинного обучения.
К примеру в банковской сфере - обработка фин. транзакций, социальные сети - обратобка сообщений в twiiter в режиме реального времени, аналитика (данные о пользовательских взаимодействиях)
2. rabitMQ система очереди сообщений для обмена данными в асинхронном режиме с обеспечением гарантии доставки, распределённая обработка задач на нескольких серверах где требуется координация и согласованность действий. Так же удобно использовать в для интеграции сервисов и приложений, огранизовывать маршрутизацию между ними и реализовывать систему подписки.
