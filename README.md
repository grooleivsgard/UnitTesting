# UnitTesting
Denne enhetstestingen var en del av et eksamensprosjekt, hvor vi også utførte integrasjons- og systemtesting av en nettbank. 
Gjennom testprosessen ble det avdekket flere avvik, både mindre funksjonalitetsfeil, men også 
alvorlige sikkerhetskritiske mangler ved banksystemet. En rekke avvik gjelder inputvalideringer 
som burde være på plass i et system som håndterer ømfintlig informasjon. Systemet er også 
sårbar for tap, endring og misbruk av kundeinformasjon grunnet manglende 
autoriseringsprosesser. På bakgrunn av testene som er utført, ble produktet evaluert som svært 
høy risiko å lansere da flere sikkerhetskritiske funksjoner ikke fungerer optimalt. Det vil være nødvendig å 
repetere samtlige tester før lansering ved eventuelle forbedringer slik at en ny risikovurdering kan bli utført. 

Følgende ble beskrevet ifb med enhetstestingen av programmet:

Overordnet teststrategi:
Enhetstestene vil bli delt opp slik at det er en testklasse per kontroller, altså fire ulike testklasser. For å 
effektivisere prosessen valgte gruppen å dele opp arbeidet slik at en student hadde ansvar for en 
testklasse. I og med at samtlige metoder i systemet inneholder en sikkerhetssjekk før resten av metoden 
utføres, må hver metode mocke database-kallet. Her vil det være nødvendig å teste både at 
sikkerhetssjekken verifiserer at brukeren er innlogget og at brukeren ikke er innlogget, da dette er et 
kritisk steg i testingen.

Prosedyre:
For enhetstesting kreves rammeverket JUnit, samt Mockito for mocking av databasen. Hver enhetstest 
vil deles opp i tre seksjoner, Arrange, Act og Assert, hvor hver seksjon kun har et ansvarsområde. I 
Arrange-seksjonen vil det være nødvendig å opprette objekter og mocke de relevante databasekallene. 
Under Act vil selve metoden bli kallet på. Til slutt, under Assert, vil forventet returverdi bli sammenlignet 
med faktisk returverdi. Testen kan kjøres når alle disse seksjonene er utfylt og ingen feil i de respektive 
modulene oppdages. Kriterier for at testen er kjørt er at testen bekreftes bestått av IntelliJ og at Code 
Coverage bekrefter at relevante deler av metoden er dekket.

Kriterier for grundighet i testen:
Samtlige metoder i systemet skal enhetstestes hvor målet er å dekke > 95 % av kodelinjene. Hver 
enhetstest vil fungere som en påstand, som skal være små og isolerte med en klar navngivning, slik at 
eventuelle endringer i en annen del av programvaren ikke påvirker selve enhetstesten. Hardkodede 
verdier skal begrenses til kun det nødvendige, som for eksempel ved mocking av database eller 
opprettelse av objekter. If-setninger skal unngås slik at hver test har et tydelig formål. Testene skal 
dermed være frittstående og uavhengige av andre eksterne faktorer som filer og databaser. Til slutt skal 
testene utføres på relativt kort tid, samt være repeterbare ved at de alltid returnerer det samme 
resultatet mellom kjøringene.

Vurdering av testens grundighet:
I testplanen var målsetningen å dekke > 95% av kodelinjene med enhetstester. Med enhetstestene som er utført, har vi oppnådd en 100% dekningsgrad. Dette er dog ikke alene 
representativt for testens grundighet. Alle testene har en klar navngivning, og er basert på én betingelse slik at formålet med testen er tydelig og uavhengig 
av andre faktorer. Alle automatiserte resultater ble det samme som de forventede resultatene.

Gjenstående aktiviteter/oppgaver:
I og med at hver enkelt metode i enhver kontroller er testet og dekningsgraden av kodelinjene 
er 100%, gjenstår det ingen testaktiviteter/oppgaver for enhetstesten. Dersom det forekommer 
endringer i koden vil det likevel være nødvendig å utføre enhetstester på dette. Dette 
inkluderer for eksempel metoden registrerBetaling() dersom denne blir løst. I tillegg kan det 
være nyttig å opprette en verifiseringsklasse da flere av metodene krever inputvalidering. Ved 
slike endringer og tillegg i koden må dette følges opp med enhetstesting. 
