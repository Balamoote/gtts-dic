# gtts-dic
<b>Словарь для связки GoogleTTS (Синтезатор речи Google) + TTSLexx</b>

Прямая ссылка: https://github.com/Balamoote/gtts-dic/archive/refs/heads/main.zip

<b>Внимание:</b> сопутствующие скрипты для обработки книг находятся теперь тут https://github.com/Balamoote/gtts-scripts

<b>Описание:</b></br>
Русский словарь для использования на устройствах Andoid для коррекции произношения движка Speech Services by Google (далее gtts). Используется только совместно с TTSLexx (см. ниже). Словарь составлен по принципу полной замены дефолтных правил произношения на собственные. Описание версий в файле versions.txt

Словарь предоставляется "как есть" и является просто версией, которой автор пользуется сам. Каждый вправе использовать словарь на свой страх и риск, или не использовать его.

Чтобы скачать: нажмите на "Code:" (зеленая кнопка) и далее в меню выберите "Download ZIP"

Чтобы сообщить об ошибке: используйте вкладку Issues

<b>ВНИМАНИЕ: ВАЖНО:</b> перед импортом файла словаря ВСЕГДА закрывайте редактор словаря!!! Если он при импорте останется открытым и в нем будет внесена любая правка, то будет сохранена версия словаря ДО импорта. Просто закройте ВСЁ и только тогда импортируйте lexx.

<b>Особенности:</b>
1. в настройках TTSLexx выключить опцию "замена еЕ на ёЁ". Словарь сделан и тестировался только с выключенной опцией. После полной ё-фикации словаря, возможно, положение этого переключателя будет означать лишь выбор версии ёфикации из двух вариантов: TTSLexx'а или этого словаря.
2. Словарь предназначен для версии движка gtts 24.9.361717975, на более новых версиях из маркета также работает. Однако, офф-лайн голоса в более новых версиях gtts испорчены (хрипы и придыхания в конце фраз, переменная скорость, "распевы" на гласных) и эти более новые версии НЕ используются автором.
По состоянию на сентябрь 2022 года некоторые слова, которые были скорректированы с помощью служебных букв (ь и ъ) могут произноситься неправильно. Поскольку эти новые голоса к использованию непригодны из-за низкого качества, словарь исправляться не будет до того момента, пока не появится исправленная версия движка и голосов.
3. TTSLexx можно установить отсюда: https://play.google.com/store/apps/details?id=sia.netttsengine.ttslexx Поддерживаются 2 набора голосов: офф- и он-лайн. Словарь работает с обоими вариантами, но с он-лайн голосами тестирования не проводилось. Если предполается использовать оба набора голосов, то словарь нужно загружать в TTSLexx дважды, т.е. для каждого набора голосов отдельно - см. настройки TTS.
4. Основой словаря послужил "Полная парадигма. Морфология. Частотный словарь. Совмещенный словарь. Автор М. Хаген. Полная парадигма. Морфология". http://speakrus.ru/dict2/index.htm#morph-paradigm
5. Словарь намеренно сделан таким образом, чтобы охватить максимальное количество словоформ, вне зависимости от того, произносится слово движком правильно или нет. Вызвано это тем, что на практике невозможно отловить все ошибки в обозримое время, а офф-лайновый gtts в части корректности произношения развивается медленно. Достаточно сказать, что корпус словаря "правильно" (т.е. с ударением так же как в словаре) произносится только менее, чем 20% от словарной бызы данного словаря. В результате словарь получился большой, что положительно сказалось на качестве произношения, но несколько пострадала производительность.
6. Почти все шаблоны словаря намеренно включают начало слова. Ни одна словоформа не обрабатывается двумя шаблонами (кроме исключений в виде regex и нескольких шаблонов с кавычками), проверка на двойные срабатывания производится для каждой версии и предполагается, что ошибки этого типа исключены.
7. Шаблоны типа regex используются минимально и почти исключительно для работы с омографами. Они сильно снижают производительность и для других целей их использовать крайне не нежелательно.
8. Наличие "лишних" букв в правой части шаблонов или "неправильное" написание слова призвано исправить произношение движка. Это не ошибка, если слово произносится верно. Второй функцией "лишних" букв является предотвращение срабатывания одного шаблона на результат работы другого.
Словарь наверняка содержит множество неизвестных еще ошибок, о которых желательно сообщать. Пишите, будем исправлять, но помните о наличии в языке омографов.
9. Для обработки омографов используйте скрипты из папки scripts или профильные программы, вроде Demagog. Омографы иногда вносятся в словарь в секцию regex (крайне редко). В сокращенных версиях эта секция отсутствует.
10. Новые версии словаря будут периодически публиковаться по мере внесения изменений.

<b>Слова с буквой ё в тексте (ё-фицированные тексты).</b>
1. Ё-фикация в процессе, по шаблонам:
- e --> ё обработано примерно 165 тыс. из всего 232 тыс. словоформ.
- ё --> ё обработано примерно 230 тыс. из всего 232 тыс. словоформ.

<b>Слова с дефисом.</b>
1. дефис удаляется и части слова с дефисом обрабатываются отдельно. Исключение сделано для некоторых элементов и сочетаний.
2. особые словосочетания можно "исправить" записав через пробел и взяв их в кавычки: папье-маше --> " папье маше "=" па'пье-маше' "
3. регекс, отвечающий за это поведение:

regex"(?i)(?<!\b[гм]|зел[её]но|\bиз|\bкак|\bкое|\bкрасно|\bсветло|\bсеро|\bт[её]мно|\bяйце|[0-9IVXCL])[-'](?!то\b|таки|временн|образн|[ст]воему\b|моему\b)"=" "

4. оставшиеся "нерабочие" шаблоны из словаря удалены.

<b>Особенности работы TTSLexx</b>

Перед внесением изменений в словарь следует знать его особенности. Рекомендуется почитать инструкцию к нему и соответствующую тему на 4pda (название: Speech Services by Google (Синтезатор речи Google, ex. Google text-to-speech https://4pda.to/forum/index.php?showtopic=575965), где можно пообщаться с автором TTSLexx - ssiiaa. Но основное это:
1. Словоформа проходит через весь список шаблонов словаря, т.е. при первом срабатывании шаблона обработка не прекращается. Т.о. особое внимание нужно уделять исключению срабатываний разных шаблонов на одно и то же слово. В числе прочего, такое может происходить, когда один шаблон срабатывает на результат работы другого шаблона, находящегося выше по списку.
2. Порядок сортировки шаблонов в списке в процессе работы: (1) шаблоны regex, (2) шаблоны типа "сло"="сло'", (3) шаблоны типа слово=сло'во.
3. Шаблоны (1) и (2) могут обрабатывать часть слова и, следовательно, могут быть причиной двойной обработки слова, которое может получить 2 ударения, и будет произноситься неправильно даже, если эти 2 ударения будут на одну и ту же "правильную" букву.
4. С практической точки зрения можно считать, что TTSLexx обрабатывает только буквы русского алфавита и знак ударения (U0301). Прочие символы unicode либо игнорируются, либо преобразуются в тот же стандартный русский алфавит.
5. regex-шаблоны работают в зависимости от того, как их понимает система на конкретном устройстве. Тестирование производилось на Android 11. Использовать regex-шаблоны нужно с осторожностью и, если наблюдаются проблемы с производительностью или выдаются ошибки, нужно попробовать удалить эту секцию словаря в первую очередь.

<b>Возможные технические проблемы:</b>

1. После перезагрузки устройства или после обновления движка gtts возможна некорректная работа, например, воспроизведение русского текста английским голосом. В этом случае обычно достаточно зайти в настройки TTSLexx и нажать на один из голосов, чтобы прослушать тестовую фразу. Также проверить язык вопроизведения в читалке.
2. Из-за размера словаря возможны проблемы с производительностью, обычно только при запуске вопроизвения после редактирования словаря (словарь долго читается). Теоретически возможен отказ движка работать с таким большим словарем. Такие факты не наблюдались, но они теоретически возможны. В случае невозможности зайти в настройки TTSLexx, нужно удалить и заново установить TTSLexx - в процессе удалится с устройства также и словарь (альтернативно можно удалить словарь lexx из /data/data/sia.netttsengine.ttslexx/files ).
ВАЖНО: проблемы с производительностью могут быть вызваны не столько самим размером словаря, сколько тем как работает программа-читалка на данном конкретном устройстве. Подтверждена ситуация, когда на полном словаре одни читалки "тормозят", а другие - нет. Рекомендуется попробовать НЕСКОЛЬКО РАЗНЫХ читалок, и проверить работоспособность на них. Некоторые варианты читалок: Alreader, AlreaderX, MoonReader, Libera Pro, eReader и т.д. 
3. Если наблюдается вылет после редактирования словаря пользователем, то скорее всего это ошибка в одном из regex.
4. Если какое-то слово упорно произносится неправильно, игнорируя шаблон, это скорее всего, означает, что срабатывает какой-то другой шаблон ниже по списку (на слово в левой ИЛИ правой части шаблона) и портит произношение. ИЛИ один из шаблонов записан с ошибкой, например, в нем пропущена кавычка.
