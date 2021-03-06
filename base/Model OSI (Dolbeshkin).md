# Модель OSI

###Аннотация

В данной работе рассмотрена модель взаимодействия OSI/ISO, ее уровни, а также функции этих уровней. Подробно описаны сеансовый и транспортный уровни OSI. Представлены функции сеансового уровня по управлению диалогом, синхронизации и управления активностью, функции и услуги транспортного уровня, классы сервиса транспортного уровня, классы и процедуры транспортного протокола.


###Оглавление

######Введение
1.	Модель взаимодействия OSI/ISO. Уровни эталонной модели. Функции уровней.   
1.1.	Описание модели   
1.2.	Уровни эталонной модели   
1.3.	Функции уровней    
2.	Сеансовый и транспортный уровни OSI.    
2.1.	Функции сеансового уровня по управлению диалогом, синхронизации и управления активностью    
2.2.	Функции и услуги транспортного уровня   
2.3.	Классы сервиса транспортного уровня   
2.4.	Классы и процедуры транспортного протокола   
Заключение   
Библиографический список   

###Введение

Современные сети построены по многоуровневому принципу. Чтобы организовать связь двух компьютеров, требуется сначала создать свод правил их взаимодействия, определить язык их общения, т.е. определить, что означают посылаемые ими сигналы и т.д. Эти правила и определения называются протоколами. Для работы сетей необходимо запастись множеством различных протоколов: например, управляющих физической связью, установлением связи по сети, доступом к различным ресурсам и т.д. Многоуровневая структура используется с целью упростить и упорядочить это великое множество протоколов и отношений. Она также позволяет составлять сетевые системы из продуктов - модулей программного обеспечения, выпущенных разными производителями.
Стандарт, выработанный ISO, называется Взаимодействие Открытых Систем - Open System Interconnection - OSI. Он описывает структуру самих открытых систем, требования к ним, их взаимодействие. Модель взаимодействия сетевых систем, представленная в этом стандарте, известна под названием ``эталонная модель ISO/OSI''. 
Основная причина создания данной модели - стандартизация используемых протоколов и технологий. Независимость технологий каждого уровня позволяет разработчикам новых приложений и технологий абстрагироваться от реализаций тех протоколов, которые не затрагивают внедряемый или разрабатываемый объект, что в конечном счете экономит время и деньги. 
 
###1. Модель взаимодействия OSI/ISO. Уровни эталонной модели. Функции уровней

####1.1 Описание модели

В настоящее время при анализе сетевого взаимодействия широко используется архитектурный подход, при котором функции, выполняются сетью, представляются иерархическими. Согласно данным представлениям, сетевые системы описываются в контексте Эталонной модели взаимодействия открытых систем (Open System Interconnection (OSI) Reference Model), которую разработала Международная организация по стандартизации (ISO). 

***Сетевая модель OSI*** - базовая эталонная модель взаимодействия открытых систем (сокр. ЭМВОС; 1978 г) - абстрактная сетевая модель  для коммуникаций и разработки сетевых протоколов. Предлагает взгляд на компьютерную сеть с точки зрения измерений. Каждое измерение обслуживает свою часть процесса взаимодействия. Благодаря такой структуре совместная работа сетевого оборудования и программного обеспечения становится гораздо проще и прозрачнее.    
В настоящее время основным используемым стеком протоколов является TCP/IP ,разработанный ещё до принятия модели OSI и вне связи с ней.
Модель OSI/ISO стандартизирует обмен информацией между системами. Если две системы используют один и тот же набор стандартов, то они открыты друг для друга. В реальной сети источниками и приемниками информации являются прикладные процессы, имеющие различную природу. Например, в качестве такого процесса может выступать оператор, обслуживающий банковский терминал или программное обеспечение для управления базой данных, управления техническими процессами на предприятиях. Функции прикладных процессов, которые связаны с обеспечением взаимодействия, называются прикладными объектами. С точки зрения OSI такие объекты являются частями открытых систем. С другой стороны, для осуществления взаимодействия прикладными объектами необходим обмен данными между системами, частями которых эти объекты являются, для чего необходима некая физическая среда (кабели, радиоканал и т.д.).

Таким образом, модель OSI/ISO основана на четырех элементах:    
•	открытых системах;    
•	прикладных объектах, существующих в рамках OSI;    
•	соединениях, которые связывают прикладные объекты и позволяют им обмениваться информацией;    
•	физической среде для такого обмена.

Термин «соединение» в данном контексте имеет широкое толкование. Его следует понимать как кооперацию прикладных объектов, принимающую различные формы. Это может быть и межпроцессорная связь, относящаяся к обмену информацией и синхронизации действий между прикладными процессами; представление данных, относящееся ко всем аспектам создания и поддержания описаний и преобразований данных; управление ресурсами, с помощью которых инициируются прикладные процессы OSI, обеспечение целостности и сохранности данных во время функционирования открытых систем. Модель OSI не ограничивается только передачей информации между системами, но затрагивает вопросы взаимодействия для решения общих задач.
Функции взаимосвязи, образующие открытую систему, в своей совокупности чрезвычайно сложны. Поэтому в модели ISO они структурируются путем разбиения на уровни. При этом каждая открытая система представляется в виде иерархически расположенных подсистем. Подсистемы, выполняющие схожие наборы функций, образуют уровень. 

###1.2 Уровни эталонной модели

В модели OSI/ISO сетевые функции распределены между семью уровнями:    
1.	*Физический* - собственно кабель или физический носитель   
2.	*Канальный* - передача и прием пакетов, определение аппаратных адресов   
3.	*Сетевой* – маршрутизация и ведение учета   
4.	*Транспортный* – обеспечение корректной, сквозной пересылки данных   
5.	*Сеансовый* – аутентификация и проверка полномочий   
6.	*Представление данных* – интерпретация и сжатие данных   
7.	*Прикладной* – предоставление услуг на уровне конечного пользователя: почта, регистрация и т.д.   

###1.3 Функции уровней

*Уровень 7, Прикладной (Application Layer), - самый верхний уровень модели OS1.*
Он представляет собой окно для доступа прикладных процессов к сетевым услугам. Прикладной уровень обеспечивает доступ прикладных процессов в среде OSI. Функции прикладного уровня разделяются на две группы: общие и специальные. Первые дают средства взаимодействия, используемые различными приложениями, например, средства организации связи между прикладными процессами. Вторые обеспечивают определенные потребности конкретных приложений, например, обмен файлами, доступ к базам данных и электронную почту.

*Уровень 6, Представительный (Presentation Layer)*   
Представительный уровень предназначен для представления данных, подлежащих передаче между прикладными объектами, представления структур данных, на которые ссылаются прикладные объекты, представлением методов, которые могут использоваться для манипулирования и обработки данных. Представительный уровень имеет дело с синтаксисом, т.е. с формальным их представлением. Семантика, т.е. способ интерпретации данных, их смысл - прерогатива только прикладного уровня. Наличие представительного уровня освобождает приложения от необходимости заботиться о проблеме общего представления данных и обеспечивает независимость от синтаксиса. Это позволяет прикладным объектам использовать любой локальный синтаксис, представительный уровень обеспечивает преобразование локальных синтаксисов в согласованный обоими прикладными объектами. Преобразования синтаксисов выполняются локально и видны для других открытых систем. В связи с этим представительные протоколы не стандартизируются. 

Функции представительного уровня включают:   
1.	запрос на установление сеанса;   
2.	передачу данных;   
.	согласование и пересогласование выбора синтаксиса;   
.	преобразование синтаксиса, включая преобразование данных,    
.	форматирование и специальные преобразования (сжатие, шифрование/дешифрование).   
Представительный уровень отвечает за преобразование протоколов, трансляцию данных, их шифрование, смену или преобразование применяемого набора символов (кодовой таблицы) и расширение графических команд. Представительский уровень, кроме того, управляет сжатием данных для уменьшения передаваемых битов. На этом уровне в Win/DOS работает утилита, называемая редиректором (redirector). Ее назначение - переадресовать операции ввода/вывода к ресурсам сервера Lan Manager.

*Уровень 5, Сеансовый (Session Layer)*    
Сеансовый уровень предназначен для организации и синхронизации диалога и управления обменом данными. С этой целью уровень предоставляет услуги по установлению сеансового соединения между двумя представительными объектами и поддержанию упорядоченного взаимодействия при обмене данными между ними. Для осуществления передачи данных между представительными объектами сеанс отображается на транспортное соединение и использует последнее. Сеанс может быть расторгнут сеансовыми или представительными объектами.
Функции сеансового уровня сводятся к установлению и расторжению сеансового соединения; обмену нормальными и срочными данными; управлению взаимодействием; синхронизации сеанса; восстановлению сеанса. Все эти функции тесно связаны с сеансовым сервисом, поскольку собственные, не инициированные со стороны верхнего уровня действия практически отсутствуют.
Синхронизацию между пользовательскими задачами сеансовый уровень обеспечивает посредством расстановки в потоке данных контрольных точек (chekpoints). Тaким образом, в случае сетевой ошибки, потребуется заново передать только данные, следующие за последней контрольной точкой. На этом уровне выполняется управление диалогом между взаимодействующими процессами, т.е. регулируется, какая из сторон осуществляет передачу, когда, как долго и т.д.

*Уровень 4, Транспортный (Transport Layer)*     
Транспортный уровень обеспечивает прозрачную передачу данных между сеансовыми объектами и освобождает их от функций, связанных с надежной и экономически эффективной передачей данных. Уровень оптимизирует использование имеющихся сетевых ресурсов представляя транспортный сервис при минимальной стоимости. Оптимизация выполняется при ограничениях, накладываемых всеми взаимодействующими в пределах сети сеансовыми объектами, с одной стороны, и возможностями и параметрами сетевого сервиса, который используется транспортным уровнем, с другой. Протоколы транспортного уровня предназначены для межконцевого (point-to-point) взаимодействия, где концы определяются как транспортные объекты-корреспонденты. Транспортный уровень освобождается от маршрутизации и ретрансляции и занимается исключительно обеспечением взаимодействия между оконечными открытыми системами. Транспортные функции зависят от сетевого сервиса и включают:  


•	отображения транспортного адреса на сетевой адрес;       
•	мультиплексирование и расщепление транспортных соединений на сетевые соединения;       
•	установление и расторжение транспортных соединений;       
•	управление потоком на отдельных соединениях;       
•	обнаружение ошибок и управление качеством сервиса;      
•	исправление ошибок;       
•	сегментирование, блокирование и сцепление;       
•	передача срочных блоков данных.      

Транспортный уровень гарантирует доставку пакетов без ошибок, в той же последовательности, без потерь и дублирования. На этом уровне сообщения переупаковываются: длинные разбиваются на несколько пакетов, а короткие объединяются в один. Это увеличивает эффективность передачи пакетов по сети. На транспортном уровне узла-получателя сообщения распаковываются, восстанавливаются в первоначальном виде, и обычно посылается сигнал подтверждения приема. Транспортный уровень управляет потоком, проверяет ошибки и участвует в решении проблем, связанных с отправкой и получением пакетов.


*Уровень 3, Сетевой (Network Layer)*   
Сетевой уровень отвечает за адресацию сообщений и перевод логических адресов и имен в физические адреса. Сетевой уровень обеспечивает установление, поддержание и разъединение сетевых соединений между системами, содержащими взаимодействующие прикладные объекты, а также предоставляет функциональные и процедурные средства для блочного обмена данными между транспортными объектами по сетевым соединениям.
Сетевой уровень определяет маршрут транспортного объекта-отправителя к транспортному объекту-получателю и обеспечивает независимость от особенностей маршрутизации и ретрансляции, связанных с установлением и использованием данного сетевого соединения. 
На этом уровне решаются также такие задачи и проблемы, связанные с сетевым трафиком, как коммутация пакетов, маршрутизация и перегрузки. Если сетевой адаптер маршрутизатора не может передавать большие блоки данных, посланные компьютером-отправителем, на сетевом уровне эти блоки разбиваются на меньшие. Сетевой уровень компьютера-получателя собирает эти данные в исходное состояние.
Функции сетевого уровня:


•	маршрутизация и ретрансляция;   
•	организация сетевых соединений;   
•	мультиплексирование сетевых соединений на канальное соединение;   
•	сегментирование и блокирование;   
•	обнаружение и исправление ошибок;   
•	сериализация;   
•	управление потоком;   
•	передача срочных данных;   
•	возврат к исходному состоянию.   
Сетевые соединения могут иметь различную конфигурацию - от простого двухточечного соединения до сложной комбинации подсетей с различными характеристиками. Обычно сетевые функции разделяются на подуровни. 
*Уровень 2, Канальный (Data Link Layer),*   
Канальный уровень осуществляет передачу кадров (frames) данных от cетевого уровня к физическому. Кадры - это логически организованная структура в которую можно помещать данные. Канальный уровень узла-получателя упаковывает сырой поток битов, поступающих от физического уровня, в кадры данных.   
Канальный уровень обеспечивает функциональные и процедурные средства для установления, поддержания и расторжения канальных соединений между сетевыми объектами и передачи блоков данных. Канальное соединение (канал передачи данных) строится на одном или нескольких физических соединениях.   
Канальный уровень обнаруживает и, в большинстве случаев исправляет ошибки, которые могут возникнуть на физическом уровне. Это позволяет сетевому уровню считать передачу данных по сетевому соединению фактически безошибочной. Помимо этого канальный уровень позволяет сетевому уровню управлять взаимными соединениями физических каналов. транспортный протокол сервис
Обычно, когда канальный уровень посылает кадр, он ожидает со стороны получателя подтверждения приема. Канальный уровень получателя проверяет наличие возможных ошибок передачи. Кадры, поврежденные при передаче, или кадры, получение которых не подтверждено, посылаются вторично.
Функции канального уровня:


•	установление и расторжение канального соединения;   
•	расщепление канального соединения на несколько физических;   
•	сериализация;   
•	обнаружение и исправление ошибок;   
•	управление потоком;   
•	управление соединением физических каналов передачи данных.   


*Уровень 1, Физический (Physical Layer)*      
Это самый нижний в модели OSI. Этот уровень осуществляет передачу неструктурированного потока бит по физической среде (например, по сетевому кабелю).   
Физический уровень обеспечивает механические, электрические, функциональные и процедурные средства активизации, поддержания и деактивизации физических соединений для передачи данных между канальными объектами. Функции уровня сводятся к активизации и деактивизации физического соединения, а также передачи данных.   
Здесь реализуются электрический, оптический, механический и функциональный интерфейсы с кабелем. Физический уровень также формирует сигналы, которые переносят данные, поступившие от всех вышележащих уровней. На этом уровне определяется способ соединения сетевого кабеля с платой сетевого адаптера, в частности, количество контактов в разъемах и их функции. Кроме того, здесь определяется способ передачи данных по сетевому кабелю.   
Физический уровень предназначен для передачи битов (нулей и единиц) от одного компьютера к другому. Уровень отвечает за кодирование данных и синхронизацию битов, гарантируя, что переданная единица будет воспринята именно как единица, а не как ноль. Также физический уровень устанавливает длительность каждого бита и способ перевода бита в соответствующие электрические или оптические импульсы, передаваемые по сетевому кабелю.

###Сеансовый и транспортный уровни OSI


#####2.1	Функции сеансового уровня по управлению диалогом, синхронизации и управления активностью


***Сеансовый уровень*** отвечает за поддержание сеанса связи, позволяя приложениям взаимодействовать между собой длительное время. Уровень управляет созданием/завершением сеанса, обменом информацией, синхронизацией задач, определением права на передачу данных и поддержанием сеанса в периоды неактивности приложений.    
Сеансовый уровень выполняет задачу организации и проведения диалога между прикладными процессами. Он обеспечивает пользователю иллюзию того, что прикладные процессы выполняется не в нескольких, расположенных в различных местах, процессорах, а в одном мощном процессоре. Инициатором сеанса является прикладной объект, который требует проведения сеанса и указывает представительному объекту адрес партнера. После этого представительный объект-отправитель обращается к сеансовому объекту, инициируя сеанс взаимодействия. В системе-получателе все происходит наоборот. Сеансовый объект предлагает представительному объекту принять участие в сеансе. В свою очередь, представительный объект обращается к прикладному объекту с предложением о сеансе.   
Сеансовый уровень обеспечивает выполнение двух основных групп функций: обслуживание сеансов и обеспечение диалоговой формы передачи данных. Задачей первой группы функций является установление и ликвидация сеансового соединения, по которому передаются данные. Вторая группа обеспечивает управление потоками данных.   
***Синхронизация передачи*** обеспечивается помещением в поток данных контрольных точек, начиная с которых возобновляется процесс при нарушении взаимодействия. Он позволяет соответствующим образом совмещать и синхронизировать информацию нескольких потоков, возможно от разных источников. Примером применения является организация видеоконференций в сети когда звуковой и видео потоки должны быть синхронизированы во избежание проблем с синхронизацией движения губ с речью. Управление правами на участие в разговоре гарантирует, что тот, кто показывается на экране, действительно является собеседником, который в данный момент говорит.   
Ещё одним применением являются передачи в прямом эфире, в которых необходимо без резких переходов накладывать звуковой и видео потоки и переходить от одного потока к другому, во избежание перерывов в эфире или излишних наложений.   
Синхронизация сеансовых соединений позволяет устанавливать и находить точки синхронизации процесса взаимодействия объектов во время сеанса. Сущность отображения сеансовых соединений на транспортное соединение заключается в следующем. Во-первых, через одно и то же транспортное соединение могут последовательно передаваться данные, относящиеся к различным сеансам. Во-вторых, один и тот же сеанс может последовательно осуществляться по нескольким транспортным соединениям.   
Завершение сеансового соединения позволяет представительным объектам так закончить сеанс, чтобы не пропали блоки данных, находящиеся в пути.   
***Управление активностью объектов*** позволяет определить, чья в данный момент очередь выполнять определенные операции сеансового взаимодействия. Стандарты задают три формы взаимодействия объектов во время сеанса: дуплексную (диалог), полудуплексную (диалог) и симплексную (монолог).   
Для взаимодействующих прикладных процессов, расположенных в одной и той же системе, сеансовый уровень является самым нижним. Что касается транспортного, сетевого, канального и физического уровней, то они необходимы для взаимодействия тех прикладных процессов, которые находятся в различных системах.

###2.2 Функции и услуги транспортного уровня


***Транспортный уровень*** (англ. Transport layer) - 4-й уровень сетевой модели OSI предназначен для доставки данных без ошибок, потерь и дублирования в той последовательности, как они были переданы. При этом не важно, какие данные передаются, откуда и куда, то есть он предоставляет сам механизм передачи. Блоки данных он разделяет на фрагменты, размер которых зависит от протокола, короткие объединяет в один, а длинные разбивает. Протоколы этого уровня предназначены для взаимодействия типа точка-точка.   
Существует множество классов протоколов транспортного уровня, начиная от протоколов, предоставляющих только основные транспортные функции (например, функции передачи данных без подтверждения приема), и заканчивая протоколами, которые гарантируют доставку в пункт назначения нескольких пакетов данных в надлежащей последовательности, мультиплексируют несколько потоков данных, обеспечивают механизм управления потоками данных и гарантируют достоверность принятых данных.   
Некоторые протоколы сетевого уровня, называемые протоколами без установки соединения, не гарантируют, что данные доставляются по назначению в том порядке, в котором они были посланы устройством-источником. Некоторые транспортные уровни справляются с этим, собирая данные в нужной последовательности до передачи их на сеансовый уровень. Мультиплексирование (multiplexing) данных означает, что транспортный уровень способен одновременно обрабатывать несколько потоков данных (потоки могут поступать и от различных приложений) между двумя системами. Механизм управления потоком данных - это механизм, позволяющий регулировать количество данных, передаваемых от одной системы к другой. Протоколы транспортного уровня часто имеют функцию контроля доставки данных, заставляя принимающую данные систему отправлять подтверждения передающей стороне о приеме данных.   
Транспортный уровень выполняет задачу предоставления сквозных соединений прикладным объектам. Для выполнения указанной задачи транспортный уровень осуществляет передачу данных между системами сквозь все имеющиеся в сети физические средства соединения.
При создании транспортного уровня должна быть обеспечена полная его независимость от типа и характера взаимодействующих процессов. Предоставляемые уровнем соединения являются прозрачными, т.е. по ним могут передаваться любые используемые коды и осуществляться всевозможные методы организации диалога на сеансовом уровне.   
Для осуществления эффективной передачи данных транспортный уровень обеспечивает несколько классов обслуживания, учитывающих все разнообразные требования к транспорту информации, предъявляемые различными прикладными процессами. Классы сервиса характеризуются выбранными множествами параметров (пропускная способность, время передачи, время установления соединения, допустимая частота ошибок и т.д.).   
Сервис, предоставляемый транспортным уровнем, включает: установление и разъединение транспортных соединений; обеспечение взаимодействия сеансового соединения с транспортным соединением; управление последовательностью и обеспечение целостности блоков данных, передаваемых через транспортные соединения; обнаружение ошибок, их частичную ликвидацию, сообщение о неисправленных ошибках; восстановление соединения после появления неисправности; укрупнение либо разукрупнение передаваемых блоков данных; управление потоками транспортных блоков; предоставление приоритета в передаче блоков (нормальная и срочная передача); присылку подтверждений о принятых блоках; сброс блоков с транспортными соединениями при тупиках.   
Благодаря выполнению этих функций транспортный уровень обеспечивает адаптацию системы к любому механизму передачи данных через конкретные физические средства соединения. Более того, транспортный уровень восстанавливает блоки данных, потерянные на уровнях 1-3. Если в физических средствах соединения создается несколько путей доставки блоков данных системе-получателю, то транспортный уровень при отказе одного из сетевых соединений может выбрать другие пути. Причем это он делает так, что прикладной процесс не знает о проводимых переключениях.   
Функционирование уровня происходит в трех сменяющих друг друга фазах: установление транспортного соединения; передача данных; завершение соединения. Транспортный уровень использует две стратегии передачи данных, выполняемых на сетевом уровне: дейтаграммы и виртуальные каналы (соединения). Дейтаграммой является блок данных, который передается транспортным уровнем без организации соединения. Последовательность блоков данных может достичь получателя не в том порядке, в котором она была отправлена. 
Виртуальным каналом называют соединение между транспортным объектом-отправителем и транспортным объектом-получателем, предоставляемое сетевым уровнем. В блоках данных, передаваемых по виртуальным каналам, нет явных адресов отправителя и получателя. Они заключены в номерах каналов.


###2.3	Классы сервиса транспортного уровня


На пути от отправителя к получателю пакеты могут быть искажены или утеряны. Хотя некоторые приложения имеют собственные средства обработки ошибок, существуют и такие, которые предпочитают сразу иметь дело с надежным соединением. Транспортный уровень обеспечивает приложениям или верхним уровням стека - прикладному и сеансовому - передачу данных с той степенью надежности, которая им требуется. 
На транспортном уровне предусмотрено три типа сетевого сервиса.   
***Сервис типа А*** предоставляет сетевые соединения с приемлемым для пользователей количеством необнаруживаемых ошибок и приемлемой частотой сообщений об обнаруженных ошибках.*   
***Сервис типа В*** отличается приемлемым количеством необнаруживаемых ошибок, но неприемлемой частотой сообщений об обнаруженных ошибках.   
Наконец, ***сервис типа С*** предоставляет сетевые соединения с количеством необнаруженных ошибок, неприемлемым для сеансового уровня.
Возникает вопрос: а для чего вообще нужны классы сервиса с неприемлемым количеством ошибок? Ответ состоит в том, что для установки многих сетевых соединений необходимы дополнительные протоколы, обеспечивающие обнаружение и устранение ошибок на достаточном для нормальной работы уровне, и на транспортном уровне такой сервис просто не нужен.     
Выбор класса сервиса транспортного уровня определяется, с одной стороны, тем, в какой степени задача обеспечения надежности решается самими приложениями и протоколами более высоких, чем транспортный, уровней, а с другой стороны, этот выбор зависит от того, насколько надежной является система транспортировки данных в сети, обеспечиваемая уровнями, расположенными ниже транспортного - сетевым, канальным и физическим. Так, например, если качество каналов передачи связи очень высокое и вероятность возникновения ошибок, не обнаруженных протоколами более низких уровней, невелика, то разумно воспользоваться одним из облегченных сервисов транспортного уровня, не обремененных многочисленными проверками, квитированием и другими приемами повышения надежности. Если же транспортные средства нижних уровней изначально очень ненадежны, то целесообразно обратиться к наиболее развитому сервису транспортного уровня, который работает, используя максимум средств для обнаружения и устранения ошибок, - с помощью предварительного установления логического соединения, контроля доставки сообщений по контрольным суммам и циклической нумерации пакетов, установления тайм-аутов доставки и т. п.   
Транспортный уровень, тем не менее, предоставляет программистам возможность писать программы для прикладного уровня в самых различных сетях, не обращая внимания на то, надежна ли передача по этим сетям или нет. Некоторые называют три верхних уровня модели OSI «пользователями транспортного уровня», а четыре нижних - «поставщиками транспортного уровня».


###2.4 Классы и процедуры транспортного протокола


Существует ***пять классов*** сервиса транспортного протокола:   
•	*Класс 0*, известный как телекс, представляет собой сервис с самым низким качеством. В этом классе сервиса предусматривается, что управление потоком данных осуществляет сетевой уровень (под транспортным уровнем). Транспортный уровень разрывает соединение, когда аналогичную операцию выполняет сетевой уровень.    
•	*Сервис класса 1* был разработан CCITT для стандарта Х.25 на сети с коммутацией пакетов. Он обеспечивает передачу срочных данных, однако управление потоком все равно осуществляется на сетевом уровне.   
•	*Класс 2* - это модифицированный класс 0. Уровень сервиса этого класса базируется на предположении о том, что сеть обладает высокой надежностью. Предлагаемое качество сервиса предусматривает возможность мультиплексирования множества транспортных соединений из одного сетевого соединения. Класс 2 обеспечивает необходимую сборку мультиплексированных пакетов данных, прибывающих неупорядоченными.
•	*Класс 3* обеспечивает виды сервиса, предлагаемые уровнями 1 и 2, а в случае обнаружения ошибки предоставляет возможность ресинхронизации для переустановления соединения.   
•	*Класс 4* предполагает, что сетевому уровню присуща надежность, поэтому он предлагает обнаружение и устранение ошибок.
В отношении использования процедур оба взаимодействующих процесса - местный и удаленный - равноправны. Каждый из них может инициировать установление соединения, передачу и прием сообщений, разъединение. Указанные процедуры реализуются транспортными модулями систем - главных и терминальных ЭВМ и инициируются процессами с помощью операторов обращения к процедурам. Выполнение процедуры-оператора можно рассматривать как команду, интерпретируемую транспортной службой и исполняемую транспортной сетью. Когда удаленный процесс в качестве реакции на команду инициирует соответствующую процедуру транспортного интерфейса, действие удаленного процесса, определяемое этой процедурой, можно рассматривать как ответ. Команды и ответы на них связаны с выполнением соответствующих процедур, а реализация последних предполагает формирование сообщений и передачу их между транспортными протоколами через СПД. Таким образом, функционирование транспортных протоколов вычислительной сети сводится к:   
1.	Формированию сообщений;    
2.	Представлению их в пакетной форме для отправки в СПД;   
.	Сборке сообщений из поступающих пакетов;    
.	Интерпретации поступающих команд и сообщений-ответов в соответствии с процедурной характеристикой протокола.

###Заключение


В данной работе рассмотрена модель взаимодействия OSI/ISO, ее уровни, а также функции этих уровней. Подробно описаны сеансовый и транспортный уровни OSI. Представлены функции сеансового уровня по управлению диалогом, синхронизации и управления активностью, функции и услуги транспортного уровня, классы сервиса транспортного уровня,а также классы транспортного протокола.










