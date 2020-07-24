{% set warning_icon = '<span class="glyphicon glyphicon-exclamation-sign" style="color: red;" aria-hidden="true" data-toggle="tooltip" title="An error is expected when you run this command!" ></span>' %}

# Introduktion till Python

> Delar av det här kapitlet är baserat på en handledning av Geek Girls Carrots (https://github.com/ggcarrots/django-carrots).

Låt oss skriva lite kod!

## Python-prompten

> För läsare hemma: denna del omfattas av videon [Python Basics: Integers, Strings, Lists, Variables and Errors](https://www.youtube.com/watch?v=MO63L4s-20U).

För att börja använda Python behöver vi öppna upp *kommandotolken* på datorn. Du bör redan veta hur man gör det – du lärde dig det i kapitlet [Introduktion till kommandotolken](../intro_to_command_line/README.md) .

När du är redo, följ instruktionerna nedan.

Vi vill öppna en Python-konsol, så skriv `python` på Windows eller `python3` på Mac OS/Linux och tryck `enter`.

{% filename %}command-line{% endfilename %}

    $ python3
    Python 3.6.1 (...)
    Type "help", "copyright", "credits" or "license" for more information.
    >>>
    

## Ditt första Python-kommando!

Efter att ha kört Python-kommandot ändrades prompten till `>>>`. För oss innebär detta att vi för tillfället endast får använda kommandon i Python-språket. Du behöver inte skriva in `>>>` – Python kommer att göra det åt dig.

Om du någon gång vill avsluta Python-konsolen, skriv `exit()` eller använd genvägen `Ctrl + Z` för Windows och `Ctrl + D` för Mac/Linux. Då ser du inte `>>>` längre.

För tillfället vill vi inte lämna Python-konsolen. Vi vill lära oss mer om den. Låt oss börja med att skriva lite matematik, skriv `2 + 3` och tryck `enter`.

{% filename %}command-line{% endfilename %}

```python
>>> 2 + 3
5
```

Snyggt! Ser du hur svaret dök upp? Python kan matematik! Du kan prova andra kommandon som:

- `4 * 5`
- `5 - 1`
- `40 / 2`

För att utföra potensräkning, säg 2 upphöjt till 3, skriver vi: {% filename %}command-line{% endfilename %}

```python
>>> 2 ** 3
8
```

Ha kul med detta ett tag och kom sedan tillbaka hit. :)

Som du kan se är Python en utmärkt kalkylator. Om du undrar vad mer du kan göra…

## Strängar

Vad sägs om ditt namn? Skriv ditt förnamn i citattecken så här:

{% filename %}command-line{% endfilename %}

```python
>>> "Ola"
'Ola'
```

Du har nu skapat din första sträng! Det är en sekvens av tecken som kan behandlas av en dator. Strängen måste alltid börja och sluta med samma tecken. Dessa kan vara enkla (`'`) eller dubbla (`"`) citationsecken (det är ingen skillnad!) Citationstecknen talar om för Python att det som är inuti dem är en sträng.

Strängar kan strängas ihop. Prova detta:

{% filename %}command-line{% endfilename %}

```python
>>> "Hi there " + "Ola"
'Hi there Ola'
```

Du kan också multiplicera strängar med ett nummer:

{% filename %}command-line{% endfilename %}

```python
>>> "Ola" * 3
'OlaOlaOla'
```

Om du behöver sätta en apostrof i din sträng, finns det två sätt att göra det.

Använd dubbla citattecken:

{% filename %}command-line{% endfilename %}

```python
>>> "Runnin' down the hill"
"Runnin' down the hill"
```

eller undanta apostrofen med ett omvänt snedstreck (``):

{% filename %}command-line{% endfilename %}

```python
>>> 'Runnin\' down the hill'
"Runnin' down the hill"
```

Snyggt, va? För att se ditt namn i versaler, skriv:

{% filename %}command-line{% endfilename %}

```python
>>> "Ola".upper()
'OLA'
```

Du använde just `upper`-**metoden** på din sträng! En metod (som `upper()`) är en sekvens av instruktioner som Python måste utföra på ett visst objekt (`"Ola"`) när du kallar den.

Om du vill veta antalet bokstäver som finns i ditt namn, finns det en **funktion** för det också!

{% filename %}command-line{% endfilename %}

```python
>>> len("Ola")
3
```

Undrar du varför man ibland anropar funktioner med en `.` i slutet av en sträng (som `"Ola".upper()`) och ibland anropar du först en funktion och placerar strängen inom parenteser? Tja, i vissa fall tillhör funktioner objekt, som `upper()`, som endast kan utföras på strängar. I det fallet kallar vi funktionen för en **metod**. I andra fall tillhör funktioner inte något specifikt och kan användas på olika typer av objekt, precis som `len()`. Därför anger vi `"Ola"` som en parameter till funktionen `len`

### Sammanfattning

OK, nog om strängar. Hittills har du lärt dig om:

- **prompten** – att skriva kommandon (kod) i Python-prompten resulterar i svar i Python
- **tal och strängar** – i Python används nummer för matematik och strängar för textobjekt
- **operatorer** – som `+` och `*`, kombinera värden för att producera ett nytt
- **funktioner** – som `upper()` och `len()`, utför åtgärder på objekt.

Dessa är grunderna i varje programmeringsspråk du lär dig. Redo för något svårare? Vi slår vad om att du är!

## Fel

Låt oss prova något nytt. Kan vi få längden på ett nummer på samma sätt som vi kunde ta reda på längden på vårt namn? Skriv `len(304023)` och tryck `enter`:

{% filename %}{{ warning_icon }} command-line{% endfilename %}

```python
>>> len(304023)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: object of type 'int' has no len()
```

Vi fick vårt första fel! {{ warning_icon }}-ikonen är vårt sätt att förvarna dig om att den kod du är på väg att köra inte fungerar som förväntat. Att göra misstag (även avsiktliga) är en viktig del av inlärningsprocessen!

Det står att objekt av typen "int" (heltal, heltal) inte har någon längd. Så vad kan vi göra nu? Vi kanske kan skriva vårt nummer som en sträng? Strängar har en längd, eller hur?

{% filename %}command-line{% endfilename %}

```python
>>> len(str(304023))
6
```

Det fungerade! Vi använde funktionen `str` inuti funktionen `len`. `str()` konverterar allt till strängar.

- Funktionen `str` omvandlar saker till **strängar**
- Funktionen `int` omvandlar saker till **heltal**

> Viktigt: vi kan konvertera siffror till text, men vi kan inte nödvändigtvis konvertera text till siffror – vad skulle `int('hello')` betyda?

## Variabler

Ett viktigt begrepp inom programmering är variabler. En variabel är inget annat än ett namn för något så att du kan använda det senare. Programmerare använder dessa variabler för att lagra data, göra deras kod mer läsbar och så att de inte behöver komma ihåg vad saker är.

Låt oss säga att vi vill skapa en ny variabel som heter `name`:

{% filename %}command-line{% endfilename %}

```python
>>> name = "Ola"
```

Vi skriver name är lika med Ola.

Som du märkte returnerade ditt program inte något som det gjorde tidigare. Så hur vet vi att variabeln faktiskt existerar? Ange `name` och tryck `enter`:

{% filename %}command-line{% endfilename %}

```python
>>> name
'Ola'
```

Jippi! Din första variabel! :) Du kan alltid ändra vad den refererar till:

{% filename %}command-line{% endfilename %}

```python
>>> name = "Sonja"
>>> name
'Sonja'
```

Du kan använda den i funktioner också:

{% filename %}command-line{% endfilename %}

```python
>>> len(name)
5
```

Grymt, eller hur? Variabler kan vara vad som helst – siffror också! Prova detta:

{% filename %}command-line{% endfilename %}

```python
>>> a = 4
>>> b = 6
>>> a * b
24
```

Men tänk om vi använde fel namn? Kan du gissa vad som skulle hända? Låt oss försöka!

{% filename %}{{ warning_icon }} command-line{% endfilename %}

```python
>>> city = "Tokyo"
>>> ctiy
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'ctiy' is not defined
```

Ett fel! Som du kan se har Python olika typer av fel och detta kallas ett **NameError**. Python kommer att ge dig detta fel om du försöker använda en variabel som ännu inte har definierats. Om du stöter på detta fel senare, kontrollera din kod för att se om du har skrivit fel.

Lek med detta ett tag och se vad du kan göra!

## print-funktionen

Prova det här:

{% filename %}command-line{% endfilename %}

```python
>>> name = 'Maria'
>>> name
'Maria'
>>> print(name)
Maria
```

När du bara skriver `name`, svarar Pythontolken med sträng-*representationen* av variabeln 'name', vilken är bokstäverna M-a-r-i-a, omgivna av enkla citattecken, ''. När du säger `print(name)`, kommer Python att "skriva ut" innehållet i variabeln till skärmen, utan citationstecken, vilket är snyggare.

Som vi kommer att se senare, är `print()` också användbar när vi vill skriva ut saker inifrån funktioner, eller när vi vill skriva ut saker på flera rader.

## Listor

Utöver strängar och heltal, har Python alla möjliga typer av olika objekt. Nu ska vi introducera ett som heter **lista**. Listor är precis vad du tror att de är: objekt som är listor över andra objekt. :)

Kör vidare och skapa en lista:

{% filename %}command-line{% endfilename %}

```python
>>> []
[]
```

Ja, den här listan är tom. Inte särskilt användbar, eller hur? Låt oss skapa en lista över lottnummer. Vi vill inte upprepa oss hela tiden, så vi kommer att lägga listan i en variabel också:

{% filename %}command-line{% endfilename %}

```python
>>> lottery = [3, 42, 12, 19, 30, 59]
```

Okej, vi har en lista! Vad kan vi göra med den? Låt oss se hur många lottnummer det finns i en lista. Har du någon aning om vilken funktion du ska använda för det? Du vet det redan!

{% filename %}command-line{% endfilename %}

```python
>>> len(lottery)
6
```

Ja! `len()` kan ge dig antalet objekt i en lista. Praktisk, eller hur? Nu kommer vi kanske sortera den:

{% filename %}command-line{% endfilename %}

```python
>>> lottery.sort()
```

Detta returnerar ingenting, det ändrade bara ordningen som talen visas i listan. Låt oss skriva ut den igen och se vad som hände:

{% filename %}command-line{% endfilename %}

```python
>>> print(lottery)
[3, 12, 19, 30, 42, 59]
```

Som du ser är talen i din lista nu sorterade från lägsta till högsta värde. Grattis!

Vi kanske vill vända på ordningen? Låt oss göra det!

{% filename %}command-line{% endfilename %}

```python
>>> lottery.reverse()
>>> print(lottery)
[59, 42, 30, 19, 12, 3]
```

Om du vill lägga till något i din lista, kan du göra detta genom att skriva detta kommando:

{% filename %}command-line{% endfilename %}

```python
>>> lottery.append(199)
>>> print(lottery)
[59, 42, 30, 19, 12, 3, 199]
```

Om du bara vill visa det första talet kan du göra detta med **index**. Ett index är det tal som säger var i en lista ett objekt förekommer. Programmerare föredrar att börja räkna på 0, så det första objektet i din lista är vid index 0, nästa är vid 1, och så vidare. Prova det här:

{% filename %}command-line{% endfilename %}

```python
>>> print(lottery[0])
59
>>> print(lottery[1])
42
```

Som du kan se kan du komma åt olika objekt i din lista med hjälp av listans namn och objektets index inuti hakparenteser.

För att ta bort något från din lista måste du använda **index** som vi lärt oss ovan och metoden `pop()`. Låt oss prova ett exempel och förstärka det vi lärt oss tidigare; vi kommer att ta bort det första talet från vår lista.

{% filename %}command-line{% endfilename %}

```python
>>> print(lottery)
[59, 42, 30, 19, 12, 3, 199]
>>> print(lottery[0])
59
>>> lottery.pop(0)
59
>>> print(lottery)
[42, 30, 19, 12, 3, 199]
```

Det gick som smort!

För extra skoj, prova några andra index: 6, 7, 1000, -1, -6 eller -1000. Se om du kan förutse resultatet innan du provar kommandot. Är resultaten vettiga?

Du kan hitta en lista över alla tillgängliga listmetoder i detta kapitel i Pythondokumentationen: https://docs.python.org/3/tutorial/datastructures.html

## Dictionaries

> För läsare hemma: denna del omfattas av videon [Python Basics: Dictionaries](https://www.youtube.com/watch?v=ZX1CVvZLE6c).

En dictionary liknar en lista, men du får tillgång till värden genom att slå upp en nyckel istället för ett numeriskt index. En nyckel kan vara en sträng eller ett tal. Syntaxen för att definiera en tom dictionary är:

{% filename %}command-line{% endfilename %}

```python
>>> {}
{}
```

Detta visar att du just skapat en tom dictionary. Hurra!

Prova att skriva följande kommando (prova också att ersätta informationen med din egen):

{% filename %}command-line{% endfilename %}

```python
>>> participant = {'name': 'Ola', 'country': 'Poland', 'favorite_numbers': [7, 42, 92]}
```

Med det kommandot skapade du just en variabel som heter `participant` med tre nyckelvärdepar:

- Nyckeln `name` pekar på värdet `'Ola'` (ett `sträng`-objekt),
- `country` pekar på `'Poland'` (ytterligare en `sträng`),
- och `favorite_numbers` pekar på `[7, 42, 92]` (en `lista` med tre tal).

Du kan kontrollera innehållet för enskilda nycklar med denna syntax:

{% filename %}command-line{% endfilename %}

```python
>>> print(participant['name'])
Ola
```

Se, det liknar en lista. Men du behöver inte komma ihåg indexet – bara namnet.

Vad händer om vi frågar Python efter värdet av en nyckel som inte finns? Kan du gissa? Låt oss prova och se!

{% filename %}{{ warning_icon }} command-line{% endfilename %}

```python
>>> participant['age']
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'age'
```

Titta, ett till fel! Det här felet är ett **KeyError**. Python är hjälpsamt och berättar att nyckeln `'age'` inte finns i den här dictionaryn.

När ska du använda en dictionary eller en lista? Tja, det är en bra tanke att överväga. Fundera över svaret innan du tittar på det i nästa rad.

- Behöver du bara en ordnad sekvens av objekt? Använd en lista.
- Behöver du associera värden med nycklar, så att du kan slå upp dem effektivt (via nyckeln) senare? Använd en dictionary.

Dictionaries, liksom listor, är *muterbara*, vilket innebär att de kan ändras efter att de har skapats. Du kan lägga till nya nyckel-värde par till en dictionary efter att den skapats, så här:

{% filename %}command-line{% endfilename %}

```python
>>> participant['favorite_language'] = 'Python'
```

Likt listor, kan metoden `len()` på dictionaries returnerar antalet nyckel-värden-par i en dictionary. Gå vidare och skriv in detta kommando:

{% filename %}command-line{% endfilename %}

```python
>>> len(participant)
4
```

Jag hoppas att det känts vettigt fram till nu. :) Redo för mer skoj med dictionaries? Läs vidare för några fantastiska saker.

Du kan använda metoden `pop()` för att ta bort ett objekt i dictionaryn. Om du vill ta bort nyckel-värde-paret som hör till nyckeln `'favorite_numbers'`, skriv in följande kommando:

{% filename %}command-line{% endfilename %}

```python
>>> participant.pop('favorite_numbers')
[7, 42, 92]
>>> participant
{'country': 'Poland', 'favorite_language': 'Python', 'name': 'Ola'}
```

Som du kan se från utskriften har nyckel-värde-paret som hörde till nyckeln 'favorite_numbers' tagits bort.

Utöver detta kan du också ändra ett värde som associeras med en redan skapad nyckel i dictionaryn. Skriv detta:

{% filename %}command-line{% endfilename %}

```python
>>> participant['country'] = 'Germany'
>>> participant
{'country': 'Germany', 'favorite_language': 'Python', 'name': 'Ola'}
```

Som du kan se har värdet på nyckeln `'country'` ändrats från `'Poland'` till `'Germany'`. :) Spännande? Hurrah! Du har precis lärt dig ytterligare något fantastisk.

### Sammanfattning

Grymt! Du vet mycket om programmering nu. I den här sista delen lärde du dig om:

- **fel** – du vet nu hur man läser och förstår fel som dyker upp om Python inte förstår ett kommando du har gett det
- **variabler** – namn för objekt som gör att du kan koda enklare och göra din kod mer läsbar
- **listor** – listor över objekt som lagras i en viss ordning
- **dictionaries** – objekt lagrade som nyckelvärdepar

Taggad inför nästa del? :)

## Jämföra saker

> För läsare hemma: denna del omfattas av videon [Python Basics: Comparisons](https://www.youtube.com/watch?v=7bzxqIKYgf4).

En stor del av programmering handlar om att jämföra saker. Vad är det enklaste att jämföra? Tal! Låt oss se hur det fungerar:

{% filename %}command-line{% endfilename %}

```python
>>> 5 > 2
True
>>> 3 < 1
False
>>> 5 > 2 * 2
True
>>> 1 == 1
True
>>> 5 != 2
True
```

Vi gav Python några tal att jämföra. Som du kan se kan Python inte bara jämföra tal, utan även metodresultat. Trevligt, va?

Undrar du varför vi sätter två likhetstecken `==` bredvid varandra för att jämföra om talen är lika? Vi använder ett enda `=` för att tilldela värden till variabler. Du behöver alltid, **alltid** använda två av dem – `==` – om du vill kontrollera om saker är lika. Vi kan också konstatera att saker och ting är olika varandra. För det använder vi symbolen `!=`, enligt exemplet ovan.

Ge Python ytterligare två uppgifter:

{% filename %}command-line{% endfilename %}

```python
>>> 6 >= 12 / 2
True
>>> 3 <= 2
False
```

Vi har sett `>` och `<`, men vad betyder `>=` och `<=` ? Tolka dem så här:

- x `>` y betyder: x är större än y
- x `<` y betyder: x är mindre än y
- x `<=` y betyder: x är mindre än eller lika med y
- x `>=` y betyder: x är större än eller lika med y

Grymt! Vill du göra ett kommando till? Prova detta:

{% filename %}command-line{% endfilename %}

```python
>>> 6 > 2 and 2 < 3
True
>>> 3 > 2 and 2 < 1
False
>>> 3 > 2 or 2 < 1
True
```

Du kan ge Python så många tal att jämföra som du själv vill, och det kommer att ge dig ett svar! Ganska smart, eller hur?

- **and** – om du använder operatorn `and` måste båda jämförelserna vara sanna för att hela kommandot ska vara sant
- **or** – om du använder operatorn `or` behöver bara en av jämförelserna vara sant för att hela kommandot ska vara sant

Har du hört talas om uttrycket "jämföra äpplen med päron"? Vi provar Python-motsvarigheten:

{% filename %}{{ warning_icon }} command-line{% endfilename %}

```python
>>> 1 > 'django'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: '>' not supported between instances of 'int' and 'str'
```

Här ser du att precis som i talesättet, kan Python inte jämföra ett tal (`int`) och en sträng (`str`). Istället visas ett **TypeError** och säger att de två typerna inte kan jämföras.

## Boolean

Förresten, du lärde dig just om en ny typ av objekt i Python. Det kallas **Boolean**.

Det finns bara två booleska objekt:

- True
- False

Men för att Python ska förstå detta, måste du alltid skriva det som "True" (första bokstaven versal, med resten av bokstäverna gemena). **true, TRUE, och tRUE fungerar inte – endast True är korrekt.** (Samma sak gäller även 'False'.)

Booleaner kan även vara variabler! Se här:

{% filename %}command-line{% endfilename %}

```python
>>> a = True
>>> a
True
```

Du kan också göra på detta sätt:

{% filename %}command-line{% endfilename %}

```python
>>> a = 2 > 5
>>> a
False
```

Träna och ha kul med booleaner genom att försöka köra följande kommandon:

- `True and True`
- `False and True`
- `True or 1 == 1`
- `1 != 2`

Grattis! Booleaner är en av de coolaste finesserna inom programmering, och du har precis lärt dig att använda dem!

# Spara!

> För läsare hemma: denna del omfattas av videon [Python Basics: Saving files and "If" statement](https://www.youtube.com/watch?v=dOAg6QVAxyk).

Hittills har vi skrivit all vår python-kod i tolken, vilket begränsar oss till att ange en rad kod åt gången. Normala program sparas i filer och körs av vårt programmeringsspråks **interpretator** eller **kompilator**. Hittills har vi kört våra program en rad åt gången i Python-**interpretatorn**. Vi kommer att behöva mer än en rad kod för de kommande uppgifterna, så vi kommer snabbt behöva:

- Avsluta Python-tolken
- Öppna valfri kodeditor
- Spara lite kod i en ny python-fil
- Kör den!

För att avsluta Pythontolken som vi har använt, skriv in funktionen `exit()`

{% filename %}command-line{% endfilename %}

```python
>>> exit()
$
```

Detta kommer att ta dig tillbaka till kommandotolken.

Tidigare valde vi ut en kodeditor från avsnittet [Kod-editor](../code_editor/README.md). Vi kommer nu att behöva öppna redigeraren och skriva lite kod till en ny fil (eller om du använder en Chromebook, skapa en ny fil i molnet IDE och öppna filen, som kommer öppnas i den medföljande kodeditorn):

{% filename %}editor{% endfilename %}

```python
print('Hello, Django girls!')
```

Du är såklart en ganska erfaren Python-utvecklare nu, så skriv gärna lite kod som du har lärt dig idag.

Nu behöver vi spara filen och ge den ett beskrivande namn. Låt oss kalla filen **python_intro.py** och spara den på skrivbordet. Vi kan namnge filen vadsomhelst, men det viktigaste är att se till att filnamnet slutar med **.py**. Filändelsen **.py** berättar för vårt operativsystem att detta är en **körbar Python-fil** och att Python kan köra den.

> **Observera** Du bör lägga märke till en av de häftigaste sakerna med kodredigerare: färger! I Python-konsolen hade allt samma färg; nu bör du se att funktionen `print` är en annan färg än strängen. Detta kallas "syntax highlighting", och det är en riktigt användbar finess vid kodning. Färgen på saker kommer att ge dig ledtrådar, såsom oavslutade strängar eller en stavfel i ett nyckelordsnamn (som `def` i en funktion, som vi kommer se nedan). Detta är en av anledningarna till att vi använder en kodeditor. :)

Med filen sparad är det dags att köra den! Använda de färdigheter du har lärt dig i kommandoradsavsnittet, använd terminalen till **byta katalog** till skrivbordet.

<!--sec data-title="Change directory: OS X" data-id="python_OSX"
data-collapse=true ces-->

På en Mac kommer kommandot att se ut ungefär så här:

{% filename %}command-line{% endfilename %}

    $ cd ~/Desktop
    

<!--endsec-->

<!--sec data-title="Change directory: Linux" data-id="python_linux"
data-collapse=true ces-->

På Linux kommer det att bli så här:

{% filename %}command-line{% endfilename %}

    $ cd ~/Desktop
    

(Kom ihåg att ordet "Desktop" kan vara översatt till ditt lokala språk.)

<!--endsec-->

<!--sec data-title="Change directory: Windows Command Prompt" data-id="python_windows" data-collapse=true ces-->

I Windows Command Prompt, kommer det att vara så här:

{% filename %}command-line{% endfilename %}

    > cd %HomePath%\Desktop
    

<!--endsec-->

<!--sec data-title="Change directory: Windows Powershell" data-id="python_windowsPSH" data-collapse=true ces-->

Och i Windows Powershell, kommer det att vara så här:

{% filename %}command-line{% endfilename %}

    > cd $Home\Desktop
    

<!--endsec-->

Om du fastnar, be om hjälp. Det är precis vad coacherna är här för!

Använd nu Python för att köra koden i filen så här:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Hello, Django girls!
    

Obs: på Windows känns "python3" inte igen som ett kommando. Använd istället "python" för att köra filen:

{% filename %}command-line{% endfilename %}

```python
> python python_intro.py
```

Okej! Du körde just ditt första Python-program som var sparat till en fil. Känns det fantastiskt?

Du kan nu gå vidare till ett viktigt verktyg inom programmering:

## If … elif … else

Lots of things in code should be executed only when given conditions are met. That's why Python has something called **if statements**.

Replace the code in your **python_intro.py** file with this:

{% filename %}python_intro.py{% endfilename %}

```python
if 3 > 2:
```

If we were to save and run this, we'd see an error like this:

{% filename %}{{ warning_icon }} command-line{% endfilename %}

    $ python3 python_intro.py
    File "python_intro.py", line 2
             ^
    SyntaxError: unexpected EOF while parsing
    

Python expects us to give further instructions to it which are executed if the condition `3 > 2` turns out to be true (or `True` for that matter). Let’s try to make Python print “It works!”. Change your code in your **python_intro.py** file to this:

{% filename %}python_intro.py{% endfilename %}

```python
if 3 > 2:
    print('It works!')
```

Notice how we've indented the next line of code by 4 spaces? We need to do this so Python knows what code to run if the result is true. You can do one space, but nearly all Python programmers do 4 to make things look neat. A single Tab will also count as 4 spaces as long as your text editor is set to do so. When you made your choice, don't change it! If you already indented with 4 spaces, make any future indentation with 4 spaces, too - otherwise you may run into problems.

Save it and give it another run:

{% filename %}command-line{% endfilename %}

```python
$ python3 python_intro.py
It works!
```

Note: Remember that on Windows, 'python3' is not recognized as a command. From now on, replace 'python3' with 'python' to execute the file.

### What if a condition isn't True?

In previous examples, code was executed only when the conditions were True. But Python also has `elif` and `else` statements:

{% filename %}python_intro.py{% endfilename %}

```python
if 5 > 2:
    print('5 is indeed greater than 2')
else:
    print('5 is not greater than 2')
```

When this is run it will print out:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    5 is indeed greater than 2
    

If 2 were a greater number than 5, then the second command would be executed. Let's see how `elif` works:

{% filename %}python_intro.py{% endfilename %}

```python
name = 'Sonja'
if name == 'Ola':
    print('Hey Ola!')
elif name == 'Sonja':
    print('Hey Sonja!')
else:
    print('Hey anonymous!')
```

and executed:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Hey Sonja!
    

See what happened there? `elif` lets you add extra conditions that run if the previous conditions fail.

You can add as many `elif` statements as you like after your initial `if` statement. For example:

{% filename %}python_intro.py{% endfilename %}

```python
volume = 57
if volume < 20:
    print("It's kinda quiet.")
elif 20 <= volume < 40:
    print("It's nice for background music")
elif 40 <= volume < 60:
    print("Perfect, I can hear all the details")
elif 60 <= volume < 80:
    print("Nice for parties")
elif 80 <= volume < 100:
    print("A bit loud!")
else:
    print("My ears are hurting! :(")
```

Python runs through each test in sequence and prints:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Perfect, I can hear all the details
    

## Comments

Comments are lines beginning with `#`. You can write whatever you want after the `#` and Python will ignore it. Comments can make your code easier for other people to understand.

Let's see how that looks:

{% filename %}python_intro.py{% endfilename %}

```python
# Change the volume if it's too loud or too quiet
if volume < 20 or volume > 80:
    volume = 50
    print("That's better!")
```

You don't need to write a comment for every line of code, but they are useful for explaining why your code is doing something, or providing a summary when it's doing something complex.

### Sammanfattning

In the last few exercises you learned about:

- **comparing things** – in Python you can compare things by using `>`, `>=`, `==`, `<=`, `<` and the `and`, `or` operators
- **Boolean** – a type of object that can only have one of two values: `True` or `False`
- **Saving files** – storing code in files so you can execute larger programs.
- **if … elif … else** – statements that allow you to execute code only when certain conditions are met.
- **comments** - lines that Python won't run which let you document your code

Time for the last part of this chapter!

## Your own functions!

> For readers at home: this part is covered in the [Python Basics: Functions](https://www.youtube.com/watch?v=5owr-6suOl0) video.

Remember functions like `len()` that you can execute in Python? Well, good news – you will learn how to write your own functions now!

A function is a sequence of instructions that Python should execute. Each function in Python starts with the keyword `def`, is given a name, and can have some parameters. Let's give it a go. Replace the code in **python_intro.py** with the following:

{% filename %}python_intro.py{% endfilename %}

```python
def hi():
    print('Hi there!')
    print('How are you?')

hi()
```

Okay, our first function is ready!

You may wonder why we've written the name of the function at the bottom of the file. When we write `def hi():` and the indented lines following, this is us writing instructions for what the `hi()` function should do. Python will read and remember these instructions, but won't run the function yet. To tell Python we want to run the function, we have to call the function with `hi()`. Python reads the file and executes it from top to bottom, so we have to define the function in the file before we call it.

Let's run this now and see what happens:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Hi there!
    How are you?
    

Note: if it didn't work, don't panic! The output will help you to figure why:

- If you get a `NameError`, that probably means you typed something wrong, so you should check that you used the same name when creating the function with `def hi():` and when calling it with `hi()`.
- If you get an `IndentationError`, check that both of the `print` lines have the same whitespace at the start of a line: python wants all the code inside the function to be neatly aligned.
- If there's no output at all, check that the last `hi()` *isn't* indented - if it is, that line will become part of the function too, and it will never get run.

Let's build our first function with parameters. We will change the previous example – a function that says 'hi' to the person running it – with a name:

{% filename %}python_intro.py{% endfilename %}

```python
def hi(name):
```

As you can see, we now gave our function a parameter that we called `name`:

{% filename %}python_intro.py{% endfilename %}

```python
def hi(name):
    if name == 'Ola':
        print('Hi Ola!')
    elif name == 'Sonja':
        print('Hi Sonja!')
    else:
        print('Hi anonymous!')

hi()
```

Remember: The `print` function is indented four spaces within the `if` statement. This is because the function runs when the condition is met. Let's see how it works now:

{% filename %}{{ warning_icon }} command-line{% endfilename %}

    $ python3 python_intro.py
    Traceback (most recent call last):
    File "python_intro.py", line 10, in <module>
      hi()
    TypeError: hi() missing 1 required positional argument: 'name'
    

Oops, an error. Luckily, Python gives us a pretty useful error message. It tells us that the function `hi()` (the one we defined) has one required argument (called `name`) and that we forgot to pass it when calling the function. Let's fix it at the bottom of the file:

{% filename %}python_intro.py{% endfilename %}

```python
hi("Ola")
```

And run it again:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Hi Ola!
    

And if we change the name?

{% filename %}python_intro.py{% endfilename %}

```python
hi("Sonja")
```

And run it:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Hi Sonja!
    

Now, what do you think will happen if you write another name in there? (Not Ola or Sonja.) Give it a try and see if you're right. It should print out this:

{% filename %}command-line{% endfilename %}

    Hi anonymous!
    

This is awesome, right? This way you don't have to repeat yourself every time you want to change the name of the person the function is supposed to greet. And that's exactly why we need functions – you never want to repeat your code!

Let's do something smarter – there are more names than two, and writing a condition for each would be hard, right? Replace the content of your file with the following:

{% filename %}python_intro.py{% endfilename %}

```python
def hi(name):
    print('Hi ' + name + '!')

hi("Rachel")
```

Let's call the code now:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Hi Rachel!
    

Congratulations! You just learned how to write functions! :)

## Loopar

> For readers at home: this part is covered in the [Python Basics: For Loop](https://www.youtube.com/watch?v=aEA6Rc86HF0) video.

This is the last part already. That was quick, right? :)

Programmers don't like to repeat themselves. Programming is all about automating things, so we don't want to greet every person by their name manually, right? That's where loops come in handy.

Still remember lists? Let's do a list of girls:

{% filename %}python_intro.py{% endfilename %}

```python
girls = ['Rachel', 'Monica', 'Phoebe', 'Ola', 'You']
```

We want to greet all of them by their name. We have the `hi` function to do that, so let's use it in a loop:

{% filename %}python_intro.py{% endfilename %}

```python
for name in girls:
```

The `for` statement behaves similarly to the `if` statement; code below both of these need to be indented four spaces.

Here is the full code that will be in the file:

{% filename %}python_intro.py{% endfilename %}

```python
def hi(name):
    print('Hi ' + name + '!')

girls = ['Rachel', 'Monica', 'Phoebe', 'Ola', 'You']
for name in girls:
    hi(name)
    print('Next girl')
```

And when we run it:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Hi Rachel!
    Next girl
    Hi Monica!
    Next girl
    Hi Phoebe!
    Next girl
    Hi Ola!
    Next girl
    Hi You!
    Next girl
    

As you can see, everything you put inside a `for` statement with an indent will be repeated for every element of the list `girls`.

You can also use `for` on numbers using the `range` function:

{% filename %}python_intro.py{% endfilename %}

```python
for i in range(1, 6):
    print(i)
```

Which would print:

{% filename %}command-line{% endfilename %}

    1
    2
    3
    4
    5
    

`range` is a function that creates a list of numbers following one after the other (these numbers are provided by you as parameters).

Note that the second of these two numbers is not included in the list that is output by Python (meaning `range(1, 6)` counts from 1 to 5, but does not include the number 6). That is because "range" is half-open, and by that we mean it includes the first value, but not the last.

## Sammanfattning

That's it. **You totally rock!** This was a tricky chapter, so you should feel proud of yourself. We're definitely proud of you for making it this far!

For official and full python tutorial visit https://docs.python.org/3/tutorial/. This will give you a more thorough and complete study of the language. Cheers :)

You might want to briefly do something else – stretch, walk around for a bit, rest your eyes – before going on to the next chapter. :)

![Cupcake](images/cupcake.png)