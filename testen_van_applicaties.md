# Testen

Tijdens het maken of herschrijven van applicaties is het normaal dat er fouten kunnen gebeuren. Soms worden ze direct gevonden, soms na een PR-request controle of soms pas bij de eindgebruiker. Dit laatste is niet gewenst en kunnen we (grotendeels) voorkomen door het schrijven van testen.

## Waarom testen? (=doel)

Software wordt door softwareontwikkelaars ontworpen voor een bepaalde toepassing. Dit lijkt op zich eenvoudig, maar door de complexiteit van software en de omgeving waarin software werkt, is het praktisch onmogelijk om foutloos software te maken. Dit maakt het testen van software zo belangrijk.

Vanuit de [leverancier](https://nl.wikipedia.org/wiki/Leverancier), [producent](https://nl.wikipedia.org/wiki/Productie), gezien is het doel van het testen, het leveren van het [bewijs](https://nl.wikipedia.org/wiki/Wetenschappelijk_bewijs) dat het ontwikkel- en programmeerwerk goed gedaan is zodat de [factuur](https://nl.wikipedia.org/wiki/Factuur) ingediend en betaald kan worden.

Vanuit de [opdrachtgever](https://nl.wikipedia.org/wiki/Opdrachtgever), [klant](https://nl.wikipedia.org/wiki/Klant), [gebruiker](https://nl.wikipedia.org/wiki/Gebruiker) gezien zijn er meerdere doelen.

- Ten eerste wil men weten of de leverancier heeft gedaan wat is afgesproken.
- Ook wil men de risico's in kunnen schatten bij het gebruik van de software. Men wil weten of de gebruikers met het systeem willen en kunnen gaan werken.
- Ook wil men fouten vinden, en wel zo snel mogelijk, want hoe later fouten gevonden worden hoe duurder het wordt om ze te herstellen.
- Ook wil men fouten voorkomen, dat gebeurt bijvoorbeeld met [statisch testen](https://nl.wikipedia.org/wiki/Statisch_testen).

Testen kost tijd en geld, daarom moet er nagedacht worden over wat er getest wordt en hoe uitgebreid dit gebeurt. Hoe uitgebreid er getest wordt is dan ook afhankelijk van het [budget](https://nl.wikipedia.org/wiki/Budget) en van de risico's die men wil inschatten. In het ideale geval wordt er niet getest, want dat is het goedkoopst, maar vaak durft men dat niet omdat men bepaalde risico's niet wil lopen. Door te testen krijgt men inzicht in die risico's. Daarom moet er een impliciete of expliciete risico-inschatting gemaakt worden. Het testen kost tussen de 10 en 30% van het totale projectbudget. Eventueel kan men met bijvoorbeeld een [testpuntanalyse](https://nl.wikipedia.org/wiki/Testpuntanalyse) een inschatting maken.

Software wordt vóór het operationeel gebruik getest, niet om alle fouten weg te halen, maar om het risico op problemen tijdens het gebruik op een acceptabel niveau te houden. Als het al uitvoerbaar zou zijn, zou het maken van foutloze software een onevenredige hoeveelheid tests en kosten betekenen.

De invoering van het systeem heeft allerlei gevolgen voor de omgeving. Deze gevolgen wil men goed kunnen inschatten. Het gaat om de gevolgen op [Commercieel](https://nl.wikipedia.org/wiki/Commercieel), [Organisatorisch](https://nl.wikipedia.org/wiki/Organisatie), [Personeel](https://nl.wikipedia.org/wiki/Personeel), [Administratief](https://nl.wikipedia.org/wiki/Administratie), [Financieel](https://nl.wikipedia.org/w/index.php?title=Financieel&action=edit&redlink=1) en [Technisch](https://nl.wikipedia.org/wiki/Techniek) gebied.

## Soorten testen

### Unit testen

Met een unit test wordt onderzocht of de ontwikkelde software daadwerkelijk doet waarvoor het gemaakt is. Met deze methode kunnen kleine, losse stukjes logica (units) onafhankelijk van elkaar, snel en grondig getest worden. Bij het opstellen van een unit test stop je bepaalde gegevens in je logica en stel je een aantal verwachte uitkomsten op. De gegevens die je erin stopt, moeten zoveel mogelijk uiteenlopen, dus zowel correcte als incorrecte invoer. De daadwerkelijke uitkomst vergelijk je vervolgens met de verwachte uitkomst, zodat je weet of je logica klopt.

#### FIRST principe

Bij het opstellen van unit tests is het goed om je te houden aan het FIRST principe. FIRST staat voor Fast, Isolated, Repeatable, Self-validating, Thorough:

- Fast: Het is belangrijk dat de unit test snel is. Je wil immers niet elke keer minuten of uren wachten voordat deze is afgerond.
- Isolated: De unit test moet geïsoleerd en onafhankelijk van andere logica uit te voeren zijn.
- Repeatable: Daarnaast moet na het uitvoeren van een test, steeds hetzelfde resultaat volgen.
- Self-validating: De unit test moet zichzelf valideren. Dat wil zeggen: er moet goed of fout uitkomen. Je wilt niet na iedere test handmatig moeten controleren of het resultaat klopt.
- Thorough: De unit test moet grondig zijn. Wij doen dit door alle paden die de logica kan volgen te testen. Je bereikt daarmee een hoge zogeheten test dekking.

### Voorbeeld unit test in .NET

Voor meer informatie over unit testing in .NET: <https://learn.microsoft.com/en-us/dotnet/core/testing/unit-testing-with-dotnet-test>

```cs

    //Unit test class
    [TestClass]
    public class CheckResultIsPositive
    {
        [TestMethod]
        public void CheckResult()
        {
            var num = new Numbers();

            int result = num.Add(10, 15); //will add both numbers

            Assert.IsTrue(result > 0); //check if result is positive or not
        }

        //this test will check if, when adding numbers using Numbers.cs -> Add method, output is as expected or not
        [TestMethod]
        public void CheckIfOutputIsExpected()
        {
            var num = new Numbers();

            int result = num.Add(20, 10); //will add both numbers
           
            Assert.AreEqual<int>(30, result); //check if result is equal to expected value 30
        }
    }
```
