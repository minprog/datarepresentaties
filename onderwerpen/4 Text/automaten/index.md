# Automaten

Bestudeer het korte college hieronder.

Beantwoord daarna de vragen. Je antwoorden worden beoordeeld op inzet en correctheid (3 punten voor de hele opdracht).

![embed](https://www.youtube.com/embed/iixnLh55wp0)

- [Open lecture notes](https://v4.software-carpentry.org/regexp/mechanics.html)

## Vending machine

Reguliere expressies zijn speciaal bedacht voor het herkennen van patronen in teksten. Maar finite state machines zijn veel algemener. Die kunnen we gebruiken om allerlei soorten processen in kaart te brengen. Een aankoop doen bij een drankenautomaat kunnen we uittekenen als een finite state machine. Het idee is om de **regels die gelden in de automaat** te vatten in zo'n tekening.

Laten we aannemen dat de automaat knoppen heeft om cijfers in te voeren. Elk product heeft een code van twee cijfers. Er is ook een module om contactloos te betalen. Ten minste de volgende regels gelden:

- Als iemand een cijfer intikt moet daarna nog een cijfer worden ingetikt
- Als iemand een tweede cijfer intikt en de keuze is ongeldig, dan kan opnieuw worden begonnen
- Als iemand een geldige keuze maakt wordt de betaalmodule geactiveerd
- Als de betaalmodule een fout geeft dan wordt deze gedeactiveerd en kan opnieuw worden begonnen
- Als de betaalmodule succesvol geld heeft geïnd dan wordt deze gedeactiveerd en kan het drankje worden uitgegeven

Probeer nu alle mogelijke "states" van de automaat zo goed mogelijk in kaart te brengen, zodat op een eenduidige manier alle regels kunnen worden toegepast. Zoals je ziet in de regels wordt er geen verschil gemaakt tussen soorten drankjes en prijzen. Dit is een abstractie (weglating). De crux van het in kaart brengen is dat systeemfouten worden voorkomen: het kan niet zo zijn dat een drankje wordt uitgegeven als er nog geen keuze is gemaakt, of als er nog niet betaald is.

1.  Breng het hele proces in kaart door een finite state machine te tekenen. Upload een versie van je tekening onderaan deze pagina (bij de submit).

2.  In welke **toestanden** kan de automaat verkeren? De starttoestand is bijvoorbeeld als nog niemand op een knop heeft gedrukt.

    <textarea name="form[q1]" rows="8" required></textarea>

3.  Welke dingen kunnen **gebeuren** in het proces om een stap verder te komen?

    <textarea name="form[q2]" rows="8" required></textarea>

4.  Welke **eindtoestanden** zijn er?

    <textarea name="form[q3]" rows="8" required></textarea>
