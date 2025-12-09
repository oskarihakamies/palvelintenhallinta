# h2soittokotiin


## Karvinen 2014: Hello Salt Infra-as-Code

- Artikkelissa kerrotaan, miten luodaan Saltin "Hello world" eli toisin sanoen yksinkertainen esimerkki Saltin konfiguraatiohallintajärjestelmästä
- "Hello world" - esimerkki kirjoitetaan init.sls tiedostoon.
- Lopussa selitys, miten idempotenssi toimii ajamalla komentoja uudestaan terminaalissa. 


## Salt Contributors: Salt overview – Rules of YAML, YAML simple structure, Lists and dictionaries - YAML block structures.

- Simppeli ohjerakenne YAML:in pelisäännöistä esimerkiksi data on muotoiltu key: value pareihin YAML:issa 
- YAML koostuu kolmesta perus elementistä. Scalars eli avain-arvo-pareista, joissa arvo on numero, merkkijono tai boolearinen arvo. Lists, eli avain (key:) seurattuna arvojen listalla jokainen arvo omalla rivillään, edeltää kaksi välilyöntiä ja viivan. Ja viimeisenä sanakirjat eli vain-arvo-parien ja listojen kokoelma.
- YAML on myös järjestetty lohkorakenteisiin




## Salt contributors: The top file - Introduction and A Basic example

- Johdannossa lyhyt tiivisitelmä siitä, miten useimmat infrastruktuurit toimivat.
- Tehokkaaseen hallintaan tarvitaan ryhmien roolien määrittelyä, kuten Apache-palvelimen asennus ja käynnistys front-end-koneille
- Saltin top.sls-tiedosto yhdistää koneiden ryhmät konfiguraatio rooleihin ja on state tree-hierarkian huipulla.
- Top tiedoistoissa on kolme eri komponenttia. Ympäristö, kohde ja tilatiedostot. 




a)

Aloitin tehtävän tarkastamalla oliko minulla salt-minion ladattuna. 

<img width="355" height="89" alt="image" src="https://github.com/user-attachments/assets/bad87590-f1be-4d41-b233-3940fb2a374f" />

Tämän jälkeen latasin micro editorin. 

<img width="304" height="79" alt="image" src="https://github.com/user-attachments/assets/3e359bfa-654c-48ff-ac2e-8034932055f7" />

Tehtävän tarkoituksena oli paikallisesti kokeilla infraa koodina. Loin siis alkuun kansion "Hello" moduuliin 

<img width="253" height="56" alt="image" src="https://github.com/user-attachments/assets/85957c2b-1441-4a23-bcc4-9f1d12c8180f" />

Olin tällä hetkellä oikeassa kansiossa myös ja avasin sitten microeditorin. Microeditoriin ajoin idempotentin koodin saltin omalla kielellä. Tämän jälkeen ajoin koodin salt-call --localilla ja varmistin, että se oli onnistunut. 


<img width="362" height="212" alt="image" src="https://github.com/user-attachments/assets/dbc4d804-a8b6-4fc7-9030-60f3addb48fb" />


Kuten huomaamme, niin esimerkkitiedoston luominen onnistui. Varmistetaan vielä, että Salt teki mitä se sanoi tekevänsä. 

<img width="259" height="31" alt="image" src="https://github.com/user-attachments/assets/63c5ec5b-fd94-4144-ada7-8d2320ddcaeb" />

Tehtävä siis onnistui. 








b)


Tehtävä topping. Aloitin tehtävän siirtymällä salttiin ja varmistin myös aluksi, että hakemisto oli olemassa. 

<img width="163" height="20" alt="image" src="https://github.com/user-attachments/assets/3e42cd9d-1e23-47e7-9ecb-b7e6f2010a3d" />


Loin tämän jälkeen tiedoston nanolla ja lisäsin Top files sivulla annetun koodin. tiedoston sisälle. 


<img width="271" height="62" alt="image" src="https://github.com/user-attachments/assets/0f3f515f-dc9c-46a3-8a61-939a97a106ca" />

Seuraavaksi lähdin luomaan tiedostoja core.sls ja edit.sls, jotta jokainen tila päästäisiin ajamaan kerralla läpi. * merkki alkuperäisessä top- tiedostossa ajaa kaikki tiedostot hakemistosta /srv/salt/



<img width="275" height="71" alt="image" src="https://github.com/user-attachments/assets/7ae65b0d-5831-4b83-ba16-b72763d04c9c" />


Käytin edit.sls kohdalla pkg.installed nanoa, mutta sillä ei ollut tehtävänannon kannalta väliä, mitä editoria käytin vaan se, että top filen ajaminen toimii. 



Seuraavaksi kokeilin, että toimiiko se peruskomennolla salt-call --localilla ja vastaukseksi sain: 



<img width="500" height="322" alt="image" src="https://github.com/user-attachments/assets/f2fffafd-dff9-497d-b37e-3b8c269aaf4c" />



<img width="452" height="155" alt="image" src="https://github.com/user-attachments/assets/e82c01e4-7835-428a-b5fe-2d0affe8c5ae" />


Eli sain ajettua molemmat samalla kertaa. Siinä kesti vain hieman päälle 9s, mutta tehtävä onnistui.






c)

Seuraavaksi viisikko tiedostossa tehtävä edessä. Eli tässä teen erilliset esimerkit jokaisesta tilafunktiosta. Eli aloitetaan luomalla jokaiselle hakemisto. 


Loin alkuun hakemistot jokaiselle viidelle eri polulle komennolla sudo touch /srv/salt/hellopkg/init.sls


Aloitin sitten pkg:lla ja nanossa kirjoitin, että se asentaisi 'treen' eli hakemistopuun. 




<img width="313" height="56" alt="image" src="https://github.com/user-attachments/assets/5c0216f7-1623-494b-b8ac-6d8369257078" />

Tein samalla muille, eli user, cmd, service ja filelle omat /srv/salt/hello""/init.sls.


Kun olin muodostanut tiedostot, niin seuraavan tehtävänä oli ajaa ne samanaikaisesti. 


<img width="311" height="31" alt="image" src="https://github.com/user-attachments/assets/bf144d87-624e-416d-997a-da14562a2142" />



top.sls tiedoston sisään samalla tähtimerkillä ja merkaten aiemmat tiedostot.



<img width="341" height="112" alt="image" src="https://github.com/user-attachments/assets/d4c071c4-87a6-4245-b765-bc8eb7e325c0" />



Seuraavaksi kokeilin, että onnistuiko se kun ajoin sen läpi paikallisesti. 




<img width="366" height="131" alt="image" src="https://github.com/user-attachments/assets/144dec49-dfee-4a40-9851-5600fd0c8332" />


Ja se onnistui. Seuraavana tehtävänä idempotentin sls- tiedoston tekeminen.





d)


Eli tehtävänä olisi luoda sls.tiedosto ja käyttää kahta saltin tilafunktiota. 


Käytän tehtävässä pkg lataamaan ohjelman esimerkiksi nginx ja serviceä varmistamaan, että se on toiminnassa.


Aloitin luomalla hakemiston ja kirjoittamalla tilatiedot tiedostoon. 



<img width="297" height="136" alt="image" src="https://github.com/user-attachments/assets/3b739430-93bc-4688-96f9-abbdcee7bb04" />





Tämän jälkeen lisäsin top.sls ja muokkasin serverin nimen siihen ajoa varten. 



<img width="290" height="66" alt="image" src="https://github.com/user-attachments/assets/b8f5b335-3be0-4d08-8a07-b9fdd75622a8" />


Ja viimeisenä lähdin ajamaan tiedostoa alas. 



<img width="608" height="357" alt="image" src="https://github.com/user-attachments/assets/31b235b3-e19c-4a9d-9509-fc378325078c" />


nginx ei ilmeisesti ole päällä, joten sain virheilmoituksen. Yritin korjata sitä asentamalla nginxia suoraan, mutta se vieläkin näytti virhettä. 


Idempotenssin pystyy silti todistamaan ajamalla komennon sudo salt-call --local state.apply


<img width="245" height="111" alt="image" src="https://github.com/user-attachments/assets/22db1513-443e-4310-8ad2-fb0d9830729f" />



Sillä muutoksia ei tapahdu. 





## Lähteet

Karvinen 2014: Hello Salt Infra-as-Code. https://terokarvinen.com/2024/hello-salt-infra-as-code/

Salt Contributors: Salt overview – Rules of YAML, YAML simple structure, Lists and dictionaries - YAML block structures. https://docs.saltproject.io/salt/user-guide/en/latest/topics/overview.html#rules-of-yaml

Salt contributors: The top file - Introduction and A Basic example, https://docs.saltproject.io/en/latest/ref/states/top.html

