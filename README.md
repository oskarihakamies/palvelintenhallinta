# h1viisikko


x) 


## Karvinen 2025: Install Salt on Debian 13 Trixie
- Ohjeet saltin asennukselle debianissa. 
-Lyhyt ja ytimekäs selostus saltista, että mitä se tekee ja mihin sitä voi käyttää.
- Hyvin kirjoitettua komentoja, joita itse voi kopioida omalla alustalla ja käyttää seuraavissa tehtävänannoissa. 



## Karvinen 2023: Run Salt Command Locally
- Ohjeet, miten pyörittää salt komentoja paikallisesti.
- Komennot tilafunktioista: pkg, file, service, user, cmd.
- hyvä ja tiivis ohjeistus. 



## Karvinen 2018: Salt Quickstart – Salt Stack Master and Slave on Ubuntu Linux
- Ohjeistus saltissa "masterin" ja "slaven" käyttöön saltissa.
- Slavella tarkoitetaan ohjattua tietokonetta, joka voi olla esimerkiksi palomuurin tai NAT:in takana. Ohjeella mainitaan tämä ja kuinka Master kone on se, jolla voi tehdä muutokset orjakoneisiin.
- Mielestäni mielenkiintoinen aihe ja ohjeet ovat hyvät siihen, että itse pääsen kokeilemaan master/slave kombinaatiota debianilla.



## Karvinen 2006: Raportin kirjoittaminen
- Ohjeet raportin kirjoittamiselle teknisille töille. Esimerkiksi tämän kurssin raportin kirjoittamiselle. 
- Hyvä neuvonta siihen, miten raporttia pitää tehdä samalla, kun työskentelee esimerkiksi eri distroissa. Paljon kätevämpää, sillä sitten ei jää vahingossa jotain välistä.
- Tärkeä tuo kohta 'pahoista mokista', joita raporttia tehdessä ei saisi tehdä. 









a)

<img width="584" height="211" alt="image" src="https://github.com/user-attachments/assets/201d9ee0-aabc-4be7-ba0e-df1438d7604d" />

Debian ladattu. 


b)

Päivitin aluksi paketit ja varmistin, että ne olivat ajantasalla. 

<img width="626" height="79" alt="image" src="https://github.com/user-attachments/assets/90332427-c19a-4539-be19-43a35a7d9aad" />




Tämän jälkeen asensin salt-minionin komennolla sudo apt-get -y install salt-minion.

Jonka jälkeen varmistin sen olevan asennettu. 


<img width="469" height="41" alt="image" src="https://github.com/user-attachments/assets/7ee87aa3-6a7f-4d0e-8b3a-175329979441" />


Salt versiona toimii 3007.8 (Chlorine)

Salt-minion asennettu onnistuneesti. 


c) 

pkg: saltissa pkg.installed tarkemmin. Latasin komennolla sudo salt-call --local -l info state.single pkg.installed tree 'tree' ohjelman ja state.singlella funktio pkg.installed todisti asennuksen onnistuneen. 


<img width="378" height="242" alt="image" src="https://github.com/user-attachments/assets/9496318e-4e31-4e05-9fa3-36ad0666da48" />

State.single komennon avulla sain selville myös tree paketin latauksen keston, mikä kesti 7935ms. Ja samalla muutokset, sekä virheet. Tuloksena muodostui Succeeded: 1 ja Failed: 0



file: hallitsee tiedostoja. Toinen tilafunktio on file tässä tapauksessa file.managed. toi taas esille paikallisessa state.single tilassa tiedot templaten luomiseen. 


<img width="482" height="215" alt="image" src="https://github.com/user-attachments/assets/809b02a3-d2a7-4654-8f98-f2e08935ce6a" />

Kuten huomaamme, niin se näyttää että tiedosto luotiin onnistuneesti ja se kertoo taas aloitusajan, keston (eli kauan kesti luoda tiedosto) ja kommentin, että onnistuiko luominen. 


<img width="588" height="224" alt="image" src="https://github.com/user-attachments/assets/c236bf74-de67-4ae9-afe1-79ee5586a98a" />



Tässä myös näkyy /tmp/hellooskari poistettuna funktiolla file.absent. 

<img width="320" height="201" alt="image" src="https://github.com/user-attachments/assets/df9a624a-a18f-40cc-8a0f-83f07e4a88b9" />




service: hallitsee palveluita esim. apache2. Tässä tapauksessa funktio service.running epäonnistui minulta. 

<img width="469" height="187" alt="image" src="https://github.com/user-attachments/assets/a8afab9f-31ea-422d-99d0-6220356a45d8" />

Kyseessä oleva epäonnistuminen johtuu siitä, että apache2 ei pyöri taustalla tai sitä ei vielä ole asennettu VM:ssäni debian distrolle. Asensin siis apachen komennolla *sudo apt install apache2* ja sain komennon toimintaan. 

<img width="501" height="189" alt="image" src="https://github.com/user-attachments/assets/f121b133-c016-4053-855c-a3d5845c701c" />

Sama state.single, jota käytin Karvinen 2023: Run Salt Command Locally sivulta komennolla antoi minulle onnistuneen state.single summaryn localissa. Apache oli siis toiminnassa ja kesto nopea, sillä se oli jo toiminnassa, eikä latauksia tarvinnut mitata. 




user: käyttäjänhallinta. Tämä näyttää vain oman käyttäjäni olevan ajan tasalla ja paikalla. 


<img width="514" height="174" alt="image" src="https://github.com/user-attachments/assets/83549de8-a636-45ad-a005-6507bc429725" />




cmd: ajaa komentoja ja on olennainen päivityksissä. Esimerkkinä tähän voisi olla komennon sudo salt-call --local -l info state.single cmd.run 'touch /tmp/foo' creates="/tmp/foo" ajaminen, joka luo tyhjän tiedoston /tmp/foo. 



<img width="616" height="239" alt="image" src="https://github.com/user-attachments/assets/083ea56a-c779-4953-9666-3c9b08bfe042" />







d) 

Idempotenssi on matematiikassa ja tietotekniikassa ominaisuus, missä yhtä toimintoa voi ajaa useita kertoja putkeen ja lopputulos on sama, kuin ensimmäisellä kerralla. Esimerkkinä oikeasta elämästä tähän voisi ottaa liikennevalot, sillä olet jo kerran painanut sitä eikä jatkopainallukset aiheuta sivuvaikutuksia. 



Idempotenssi ilmenee tässä salt-call --local komennossa siten, että se ei enää ensimmäisen komennon jälkeen samaa lopputulosta.  

<img width="364" height="119" alt="image" src="https://github.com/user-attachments/assets/d2774f9f-4ad5-4d78-ad38-09c878b978e4" />



<img width="347" height="65" alt="image" src="https://github.com/user-attachments/assets/3a34a258-4484-49db-add4-1051a734d6bf" />




## Lähteet:


Karvinen 2025: Install Salt on Debian 13 Trixie, https://terokarvinen.com/install-salt-on-debian-13-trixie/

Karvinen 2023: Run Salt Command Locally, https://terokarvinen.com/2021/salt-run-command-locally/

Karvinen 2018: Salt Quickstart – Salt Stack Master and Slave on Ubuntu Linux, https://terokarvinen.com/2018/03/28/salt-quickstart-salt-stack-master-and-slave-on-ubuntu-linux/

Karvinen 2006: Raportin kirjoittaminen, https://terokarvinen.com/2006/06/04/raportin-kirjoittaminen-4/

Adetunji 2024: What is Idempotence? Explained with Real-World Examples, https://www.freecodecamp.org/news/idempotence-explained

unRepo (n.d) Understanding Salt States - Salt: https://www.unrepo.com/salt-tool/understanding-salt-states-salt







