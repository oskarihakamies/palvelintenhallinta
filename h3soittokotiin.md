# h3.soittokotiin


## Karvinen 2021: Two Machine Virtual Network With Debian 11 Bullseye and Vagrant 

- Näytetään taas " Hello world " tyylisesti, miten vagrant toimii
- Lopussa pieni vinkki myös vikatilanteeseen.
- Ohjeet kahden verkon yhdistämiseen Debianissa vagrantin avulla
- Kerrotaan hyvin, miten tuhota/nollata virtuaalimasiinat, jotta voidaan aloittaa uusilla virtuaalimasiinoilla.



## Karvinen 2018: Salt Quickstart – Salt Stack Master and Slave on Ubuntu Linux

- Ohjeistus saltissa "masterin" ja "slaven" käyttöön saltissa.
- Slavella tarkoitetaan ohjattua tietokonetta, joka voi olla esimerkiksi palomuurin tai NAT:in takana. Ohjeella mainitaan tämä ja kuinka Master kone on se, jolla voi tehdä muutokset orjakoneisiin.
- Mielestäni mielenkiintoinen aihe ja ohjeet ovat hyvät siihen, että itse pääsen kokeilemaan master/slave kombinaatiota debianilla.


## Karvinen 2023: Salt Vagrant - automatically provision one master and two slaves

- Ohjeet ja komennot ovat aika tiiviitä, joten tätä ennen pitäisi tietää linuxin perusteet, jotta ohjelman teko onnistuisi paljon helpommin. 
- Näytetään, miten kolmea erilaista konetta voidaan pyörittää ja annettu valmis vagrantfile
- Lopullisena tavoitteena on saada idempotenssi




a)

Aloitin tehtävän katsomalla oliko minulla vagrant asennettuna. 

<img width="362" height="112" alt="image" src="https://github.com/user-attachments/assets/4779889f-7b16-4d40-be95-54c99ca19c3b" />

Minulta siis puuttui se, joten menin vagrantin sivuille ja katsoin komennon asennusta varten debianissa. 


<img width="418" height="188" alt="image" src="https://github.com/user-attachments/assets/78180cf6-992a-4527-bc3c-65bb54e97f87" />


Tämän jälkeen varmistin vielä sen, että oliko se asennettuna. 


<img width="274" height="56" alt="image" src="https://github.com/user-attachments/assets/113dddd4-5394-429b-a562-e5efea8b2d22" />




Ja 2.4.9 versio vagrantista näkyi tarkistettuani. 


Virtualboxin versio oli tämä.


<img width="253" height="25" alt="image" src="https://github.com/user-attachments/assets/d67bfdce-7443-440c-af0a-67f661269c7b" />


b)

Tässä tehtävässä minulla tuli myös sama ongelma, kuin C- kohdassa. En saanut käynnistettyä vagrantia vagrant up komennolla






c)


Aloitin tehtävän luomalla uuden hakemiston ja vaihdoin siihen. 

<img width="132" height="25" alt="image" src="https://github.com/user-attachments/assets/a5206188-d7a1-4eed-96db-49334c4ffac6" />

Tämän jälkeen tallensin tiedostoon Vagrantfile skriptin, jonka sain Karvinen 2021: Two Machine Virtual Network With Debian 11 Bullseye and Vagrant, https://terokarvinen.com/2021/two-machine-virtual-network-with-debian-11-bullseye-and-vagrant/ sivulta 


<img width="329" height="153" alt="image" src="https://github.com/user-attachments/assets/2743d266-f3c2-46bb-8a61-2066da0f50de" />

Kun olin käynnistämässä vagrantia, niin se alkoi herjaamaan tätä: 


<img width="373" height="206" alt="image" src="https://github.com/user-attachments/assets/5c9cf86c-f14d-42ca-bf0a-5d0f785ace88" />



Yritin katsoa netistä vinkkejä, mutta en päässyt ongelmanratkaisussa eteenpäin pidemmän ajan jälkeenkään. 



d)

Tehtävän aloitus. Päivitin ensiksi package listin, jonka jälkeen varmistin, että onko virtualbox ladattuna. 


<img width="370" height="184" alt="image" src="https://github.com/user-attachments/assets/066bdb3c-b059-42cb-89ac-279c07dcb325" />


Loin samalla uuden hakemiston nimeltä saltdemo ja vaihdoin siihen. 


Tallensin Karvinen 2023: Salt Vagrant - automatically provision one master and two slaves, https://terokarvinen.com/2023/salt-vagrant/#infra-as-code---your-wishes-as-a-text-file sivulta tekstitiedoston tämän jälkeen. 

<img width="353" height="224" alt="image" src="https://github.com/user-attachments/assets/e31aabbc-0c46-400a-9498-dd491b671ef8" />

Tämän jälkeen kokeilin toimivuutta vagrant up komennolla.



<img width="369" height="191" alt="image" src="https://github.com/user-attachments/assets/5620c66a-ae66-4cd1-84ba-7524423bc508" />


Se herjasi samaa, kuten jokaisessa edellisessä tehtävässä. Muilla on oletettavasti tullut sama ongelma vastaan ja en pääse ratkaisemaan sitä. Tietoa en myöskään löytäynyt virheeseen

En tiedä jos kyseessä on Windowsin sisäinen esto, minkä takia en pääse eteenpäin. 



e)

Viimeisenä tehtävänä oli kokeilla vähintään kahta eri tilaa verkon yli. Valitsin tässä pkg ja file. 


Käynnistin Masterin ja minionin ja tarkistin sitten Masterissa yhteyden pinggaamalla: 


<img width="283" height="86" alt="image" src="https://github.com/user-attachments/assets/ff2313f9-779b-40c1-9364-4006078d6418" />

Tämän jälkeen loin SLS-tiedoston aiempien tehtävien pohjalta, missä käytin pkg ja file

<img width="376" height="110" alt="image" src="https://github.com/user-attachments/assets/ed30f475-f69c-4126-8f5e-a2ce08a9c671" />

Tämän jälkeen ajoin sen verkon yli:

<img width="348" height="177" alt="image" src="https://github.com/user-attachments/assets/25d9fd31-b0a6-4a35-a2de-44a633df36f8" />

<img width="320" height="84" alt="image" src="https://github.com/user-attachments/assets/fde76947-66b8-4ead-83e5-37f0194a39ce" />


Ja näin sain molemmat tilat kokeiltua verkon yli. 


Loppujen lopuksi epäonnistunut tehtävä minulta tuon vagrantin takia ja korjailen sen varmaan ensi tunnilla yhdessä eri henkilöiden kanssa. 



## Lähteet: 

Karvinen 2021: Two Machine Virtual Network With Debian 11 Bullseye and Vagrant, https://terokarvinen.com/2021/two-machine-virtual-network-with-debian-11-bullseye-and-vagrant/

Karvinen 2018: Salt Quickstart – Salt Stack Master and Slave on Ubuntu Linux, https://terokarvinen.com/2018/salt-quickstart-salt-stack-master-and-slave-on-ubuntu-linux/?fromSearch=salt%20quickstart%20salt%20stack%20master%20and%20slave%20on%20ubuntu%20linux

Karvinen 2023: Salt Vagrant - automatically provision one master and two slaves, https://terokarvinen.com/2023/salt-vagrant/#infra-as-code---your-wishes-as-a-text-file
