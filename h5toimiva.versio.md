# h5toimiva.versio



Tehtävä aloitettu 23/11 klo 14.49. Luin tiivistelmä tehtävistä läpi annetut tekstit ja aloin tekemään havaintoja. 

## Chacon and Straub 2014: Pro Git, 2ed: 1.3 Getting Started - What is Git?

- Git eroaa keskitetyistä järjestelmistä (kuten CVS tai Subversion) tallentamalla koko historian paikallisesti jokaisella käyttäjällä, mikä mahdollistaa työn teon offlinessa eli ilman nettiä. 
- Git myös käyttää snapshot mallia eli se tallentaa kokonaiset versiot tiedostoina. Tämä myös takaa sen, että jos projektissa työskentelisi monta henkilöä, niin jokaisen muokkaus jää historiaan. 
- Commit komento tehdään paikallisesti, mikä tekee siitä äärimmäisen nopean. 
- Mielestäni git myös todistaa, kuinka fiksu Linus oli hänen keksiessään sen. 

## Gitin käyttö: git add . && git commit; git pull && git push

Käytin tässä tehtävässä lähteenä GitLab Docs: Common Git commands, https://docs.gitlab.com/topics/git/commands/ löysin täältä helpoiten yleisimmät git- komennot, kuten annetut git add ., git commit, git pull ja git push. 

- git add .: Lisää kaikki muutokset eli uudet/muokatut tiedostot valmistelualueelle. Valmistelee tallennusta nykyisestä kansiosta.
- git commit: Tallentaa valmistellut muutokset pysyväksi versioksi paikallisessa varastossa. Lisää yleensä viesti -m "<commit_message>".
- git pull: Hakee ja yhdistää etävaraston (esim. GitHub) uudet muutokset paikalliseen versioon. Päivittää käyttäjän eli minut tai sinut ajan tasalle.
- git push: Lähettää paikalliset tallennuksesi etävarastoon. Jakaa muutoksesi muille.


Nämä tehtävät sain tehtyä 23/11 klo 15.34 eli kesti hieman tarkalleen 45min katsoa ensimmäiset kaksi läpi. 


## Varaston terokarvinen/suolax/ historia, eli loki ja muutokset.
- Klikkaamalla commits auki linkistä https://github.com/terokarvinen/suolax/commits/main/ pääsee näkemään kaikki muutokset, miten gitin avulla ollaan tehty. Niitä voi klikata yksitellen ja nähdä mitä on tehtynä. 
- Suolaxissa on GPL-3.0 license eli tunnettu Free Software Foundation lisenssi vapaalle ohjelmistolle.
- Commitseissa nähdään, miten "Hello World" ollaan luotu salt statella.
- Ihan hyvä valmistus tehtäviä varten sillä tästä voi nähdä, miten muutokset näkyvät githubissa kaikille. 


Nyt alkaa tehtävien teko. 23/11 klo on 16.20

a) Online: Aloitin tehtävän luomalla uuden repon githubiin. 

<img width="539" height="274" alt="image" src="https://github.com/user-attachments/assets/db366027-35e1-488e-9d43-958de7733e36" />


Ja lisäsin siihen README.md sekä GNU GPL-3.0 licensen.



b) Dolly: Seuraavaksi kloonasin "snow" repon debianissa käyttäen viime tunnilla opittua 'git clone (repon SSH linkki)' komentoa. 


<img width="440" height="104" alt="image" src="https://github.com/user-attachments/assets/7297ce9e-4b8e-4118-8a14-d20a77d22496" />

Tämän jälkeen kirjoitin tekstiä micro README.md kansioon ja lähdin puskemaan muutoksia. 


<img width="364" height="114" alt="image" src="https://github.com/user-attachments/assets/021e4f45-3b06-4c5e-b202-acf654300416" />

Tämän jälkeen suoritin peruskomennot gitillä ja pushasin sen weppiin. 

<img width="242" height="117" alt="image" src="https://github.com/user-attachments/assets/51bfa4ca-e9e0-4c18-92e6-c397b646ffcc" />


Loin uuden README.md kansion sekä muokkasin tekstiä alkuperäisessä tiedostossa. 


<img width="389" height="283" alt="image" src="https://github.com/user-attachments/assets/dc9f3d9f-863b-43b0-9119-542c978b9a2e" />


<img width="444" height="166" alt="image" src="https://github.com/user-attachments/assets/ed924212-1ca6-47d1-9862-8bac2ea45fbd" />

23/11 klo 17.16 jatkoin Doh! tehtävän tekoa ja tähän asti kaikki sujuikin mallikkaasti. 

c) Doh! Seuraavaksi aloitin tehtävän tekemällä tyhmän muutoksen gitissä. Loin micro README.md kansioon tekstiä, mutta en commitannut sitä. 



<img width="454" height="158" alt="image" src="https://github.com/user-attachments/assets/33eddf17-d6bd-48e2-92ae-a7b3edaa3270" />

Ja katsoin muutoksen git status komennolla, sekä catilla. 


<img width="455" height="173" alt="image" src="https://github.com/user-attachments/assets/dcc3cce3-5f62-4353-a905-7bc0ee1fb125" />

Tämän jälkeen poistin sen komennolla git reset --hard



<img width="332" height="46" alt="image" src="https://github.com/user-attachments/assets/73f3767c-4efa-4297-b9e3-6d47c3c40d93" />


d) Tukki. Eli seuraavaksi menin katsomaan logejani. Kirjoitin aluksi git log komennon, josta tarkistin perusmuutokset, sekä sähköpostini ja nimeni.


<img width="538" height="152" alt="image" src="https://github.com/user-attachments/assets/bca04604-08d8-4448-a892-551b86351f95" />


Nimi, sähköposti ja git repo näkyivät oikein. Seuraavaksi katsoin git log --patch komenolla kaikki tehdyt muutokset. 


<img width="433" height="216" alt="image" src="https://github.com/user-attachments/assets/694ba12b-082b-4ed3-90be-defe54662286" />

Ja täällä näkyi oikea tekstin lisäys sekä muokkaus. 


Nyt kello on 17-40 ja jatkoin viimeiseen tehtävään. 


e) Suolattu rakki. Seuraavaksi olikin salt tilojen testaamista varastostani. Loin jo nykyiselle hakemistolle snow-tehtava salt hakemiston, jota muokkasin nanolla. 


<img width="353" height="95" alt="image" src="https://github.com/user-attachments/assets/fd80308e-c4ac-40ab-9361-14bfaf586e61" />


Lisäsin simppelin tiedoston siihen, jota pääsisin sitten ajamaan. Seuraavaksi committasin ne ja pushasin eteenpäin. 

<img width="380" height="178" alt="image" src="https://github.com/user-attachments/assets/c57be3c1-8108-4d8e-8584-612a3b94d9e3" />

Käytin commit -m, sillä se on helpompi tapa, jonka opin muuten youtubessa ja  GitLab Docs: Common Git commands, https://docs.gitlab.com/topics/git/commands/

Seuraavaksi ajoin sen läpi. Komentoa käytin Karvinen 2024: Palvelinten hallinta h5 kohdasta, https://terokarvinen.com/palvelinten-hallinta/ eli sudo salt-call --local --file-root srv/salt/ state.apply snow-testi. 

<img width="543" height="256" alt="image" src="https://github.com/user-attachments/assets/ecfa5853-e49c-4fec-9a9d-55423d9bf9e1" />

Ja se ajoi sen läpi onnistuneesti. 

Tässä vielä kuva oikeasta srv/salt kansion lisäyksestä wepin läpi. 


<img width="442" height="182" alt="image" src="https://github.com/user-attachments/assets/6bc5d8ea-1765-4ee6-aa54-fae8c0df6f10" />

Tehtävät tehty 23/11 klo 18.11


## Yhteenveto: 

- Ongelmia ei oikein tullut vastaan ja tehtävät onnistuivat hyvin.
- Tunnilla opitut asiat jäivät hyvin mieleen ja sen takia tehtävät sujuivat.
- Ja kaikki saatiin tehtyä. Mielenkiintoinen aihe kyllä 


## Lähteet:

- Chacon and Straub 2014: Pro Git, 2ed: 1.3 Getting Started - What is Git?, https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F
- Varaston terokarvinen/suolax/ historia, eli loki ja muutokset, https://github.com/terokarvinen/suolax/commits/main/ 
- GitLab Docs: Common Git commands, https://docs.gitlab.com/topics/git/commands/

  Lähteet luettu 23/11
