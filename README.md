# dev-upgrade
# Przeładowanie kognitywne 
Istnieją 4 uchwyty (sloty) w pamięci, gdzie człowiek może skupić się dobrze na jednej rzeczy, ale na 3 już gorzej.
Przy większej ilości pamięć się zaciera.
Dlatego zagnieżdżenia w kodzie są złe.

# DRY - do not repeat yourself
Nie duplikuj logiki biznesowej, ale kod może się powtarzać. Czasami wydzielony wcześniej wspólny kod może się zmienić, 
gdy wymagania się zmienią.
Powielony kod boli, gdy trzeba przeprowadzić zmianę w kilku miejscach, nie z powodu tego, że kodu jest więcej!

# Liskov principle
Dziediczenie ma wspierać polimorfizm, nie służyć do wydzielania wspólnej logiki/pól. Patrz wyżej ⬆

# Mock vs stub = test double (testowy kaskader :))
Stub - uczymy go różnych zachowań - when, then
Mock - do weryfikowania czy akcje się wykonały

Mock
 spy: (oryginalny komponent z podmianą jakiejś części, możemy też podsłuchiwać parametry przekazane do komponentu)
 mock: do weryfikowania czy akcje się wykonały
 
Stub:
 stub - uczymy go różnych zachowań - when, then
 dummy - głupia prosta odpowiedź, czasami wymagana przez kompilator
 fake - zaślepka do testów, gdy produkcyjnie nie istnieje i nie znamy jeszcze jego zachowania
 
Przy poleceniach typu command używamy najczęściej mocka, a przy query - stuba

# Modelowanie systemu wg widoku
To zły pomysł. Patrz google - logika pod spodem jest zdecydowanie bardziej skomplikowana niż interfejs użytkownika.

# Zasada skauta
Weź sobie do serca ;)

# Whitebox testing
Rozbierania komponentu na drobne części, aby móc go skonfigurować - duża ilość stubów.
Jest uważany za antywzorzec - fragile test - test kruchy. Zmiana kodu testowanego powoduje popsucie testów - testy są bez sensu ;)
Można to rozwiązac poprzez wydzielenie przygotowania komponentu do osobnego miejsca lub lepiej: wydzielić nowy komponent zawierający testowaną logikę.

# Jak rozwiązac problem?
Najlepsze rozwiazanie problemu, to nie robić sobie problemu na początku :)

# CQRS 
Command może zwracać rezultat operacji, nie musi to być typ void. Nie powinien jednak zwracać stanu.

# Silna kohezja (wiązanie)
Wysoka kohezja - wszystkie pola używane we wszystkich metodach.
Przy niskiej kohezji warto przemyśleć rozdzielenie klasy, aby stworzyć mniejsze klasy mniej powiąane ze sobą.
Przy niskiej kohezji można zadać pytanie, czy w przyszłości kohezja może się zmienić. 
Zrobić to można poprzez antywymagania, tzn. zadać pytanie czy 2 niepowiązane pola mogą być kiedyś ze sobą powiązane w jakieś wymaganie?
Czy granica obiektów może zostać złamana?

# Mniejsze powiązanie między obiektami