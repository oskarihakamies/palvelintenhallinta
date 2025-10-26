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

<img width="314" height="46" alt="image" src="https://github.com/user-attachments/assets/162c59e5-c3b1-431b-924d-c92a83cd2153" />


Salt-minion asennettu. 


c) 

pkg: varmistaa paketin olemassaolon esim. apachen. 

file: hallitsee tiedostoja

service: hallitsee palveluita esim. apache2

user: käyttäjänhallinta

cmd: ajaa komentoja ja on olennainen päivityksissä



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







