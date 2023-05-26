Eines HTML i CSS -- PAC 2 -- Documentació - Fet per Oriol Esquena (oesquena@uoc.edu)

**ENLLAÇOS REPOSITORI I PUBLICACIÓ**

El codi s'ha publicat a GitHub, al següent enllaç: [https://github.com/oriolesquena/eines-html-i-css-pac2](https://github.com/oriolesquena/eines-html-i-css-pac2)

La publicació s'ha fet amb Netlify i s'ha publicat en el següent enllaç: [https://dainty-licorice-850b4d.netlify.app/index.html](https://dainty-licorice-850b4d.netlify.app/index.html)

**PROCÉS DE DESENVOLUPAMENT**

El primer pas per iniciar aquesta pràctica ha estat crear un nou repositori utilitzant com a base el que ja s'havia creat per la PAC1.

D'aquesta manera ja es té el repositori local connectat al GitHub i cada vegada que es facin canvis i es vulgui guardar, fent un push, ja quedarà guardat al GitHub.

**Instal·lació de dependències**

Ja de l'anterior PAC es tenia instal·lada la dependència FontAwesome, que s'ha mantingut per aquest projecte, i s'ha instal·lat Sharp, que és una eina per a transformació, processament i optimització d'imatges, amb la comanda: npm install sharp i llavors s'ha creat un fitxer sharp.config.jsonon s'han especificat les característiques de qualitat de les imatges del projecte.

**Compilació per la producció**

Per tal que el projecte web sigui visible per tothom i no només des de l'entorn de desenvolupament local, s'ha penjat en un servidor web.

Per fer-ho, s'ha creat un compte al proveïdor de servidors Netlify i a continuació s'ha vinculat aquest compte amb el repositori de GitHub. A continuació, s'ha determinat la comanda de _build_: npm run build, i la carpeta destí: dist. Fet això, s'ha fet un "_Deploy"_ i s'ha activat el "_Continuous Deployment"_ de forma que cada vegada que es fa un pusha la branca enllaçada del GitHub, Netlify fa un _"Deploy"_ automàticament.

D'aquesta manera ens assegurem que sempre tenim publicada la última versió del codi del projecte web.

**DISSENY I DESENVOLUPAMENT**

Partint ja d'un projecte creat, el primer que s'ha fet ha estat adaptar la capçalera per tal que hi hagués un logotip com es demanava. Així que s'ha dissenyat el logotip (senzill i ràpid) basat en la idea que és un volcà vist des del cel, i per tant s'observa el con i el cràter. El disseny s'ha fet amb Canva i s'ha guardat el fitxer amb SVG i sense fons. Llavors s'ha establert en la capçalera i el peu, però a través del CSS, com a imatge de _background_. Principalment per dos motius: un, ja que en no ser una imatge que aporti informació, sinó que és decorativa, no cal establir-la amb HTML. I el segon motiu és que en ser una imatge en SVG, és a dir vectorial, no depèn de diferents resolucions, ja que sempre ocupa el mateix i per tant no és necessari establir amb l'HTML quina cal que descarregui el navegador en cada situació.

També se li ha aplicat una petita animació en l'estat de _hover_ per tal de donar animació i moviment a la pàgina.

A continuació s'ha editat la imatge que apareix a la pàgina de portada amb _clip-path_ per tal de que simulés la silueta d'un volcà i així ambientés la temàtica. Per fer el _clip-path_ s'ha utilitzat l'eina [Clippy](https://bennettfeely.com/clippy/), que permet ajustar la forma i aconseguir directament el codi en CSS.

Pel que fa a aquesta imatge, i com és amb la majoria d'imatges de la pàgina, s'ha creat un element \<_picture_\> i s'ha ajustat el codi per tal de que a diferents resolucions s'usi una imatge de diferent mida i pes. A més a més, que per defecte s'utilitzi el format WebP i en cas que no sigui possible el JPEG. Això s'ha aconseguit fàcilment gràcies al Sharp. I tant sols implementant una petita _query_ (exemple: /img/croscat-1200px.jpg **?as=webp&width=400** amb negreta la _query_) al final de l'enllaç de la imatge, es pot transformar en la mida i el format desitjat.

Això s'ha aplicat també a les imatges de la resta de pàgines.

Pel que fa a les imatges de la pàgina de detall, hi ha una imatge destacada on s'ha utilitzat la gestió de la direcció d'art, retallant-la per tal de focalitzar l'objectiu i que aquest es visualitzi més bé en pantalles petits com mòbils.

S'ha afegit una altra imatge en la pàgina de detall de format SVG i afegida amb CSS a través del _background_. S'ha ajustat per tal que la mida de la imatge s'adapti a la mida del dispositiu. En el cas de dispositius força petits (mòbils i tablets molt petites) s'ha optat per no mostrar la imatge ja que ocuparia massa espai i és una imatge decorativa.

Pel que fa a la pàgina de categoria, ha estat senzill ja que en la PAC anterior ja s'havia decidit crear una galeria amb imatges en miniatura de les pàgines de detall. Senzillament s'han ajustat les imatges per tal de que siguin amb format WebP per defecte i només s'ha donat la opció d'una mida ja que s'ha fet que el _grid_ no pugui ser més gran que la dimensió màxima de la imatge bàsica i així no cal tenir tres imatges diferents per diferents mides de dispositius.

Una de les que ha portat més feina ha estat l'animació de la pàgina de presentació (Història i formació) on s'ha creat un SVG amb Figma i a continuació s'ha animat en CSS. S'ha decidit crear un volcà que simuli que està en fase d'explosió.

S'ha usat Figma perquè permet agrupar els elements i posar-los un _id_ d'atribut que facilitarà moltíssim l'animació en CSS.

De bones a primeres, s'ha inserit directament el codi SVG al HTML i s'ha animat amb CSS des del fitxer principal de CSS. El problema però ha estat que un cop fet el _build_ el HTML que es generava, obviava els _id_ del fitxer SVG i això feia que no es mostrés l'animació. Així que després d'investigar i observar que altres han tingut un problema semblant, s'ha optat per guardar el CSS dins el mateix fitxer SVG i llavors només haver d'enllaçar el fitxer al HTML com una imatge qualsevol. Un cop fet això, l'animació es visualitza correctament i sense problemes.

El que si que, igual com amb les imatges de decoració de la pàgina de detall, aquesta animació no es mostra en dispositius petits ja que ocupa força espai a la pàgina i no aporta informació.

Fet això la pàgina estava força enllestida. S'ha repassat que complís amb els requisits establerts de WCAG i de validació i també s'ha comprovat que la mida de les imatges que es descarrega el navegador és l'adequada.

S'ha observat que en utilitzar Sharp, les imatges convertides a WebP no redueixen tant el pes, però en canvi si que es carreguen més ràpid. Per exemple s'ha fet una prova on primer s'ha convertit una imatge a WebP amb un conversor en línia i s'ha executat el codi amb aquesta imatge. La imatge original en JPEG ocupava 194 kB, i un cop convertida 97 kB. Però el temps de càrrega a la pàgina era de 12-13 ms. Mentre que amb la imatge convertida per Sharp, el pes final de la imatge descarregada pel navegador era de 156 kB, però el temps de càrrega era inferior, rondant els 6-7 ms. És a dir la meitat!

Vists els resultats s'ha optat per convertir les imatges amb Sharp ja que tot i que pesen un xic més, són pesos molt ínfims i petits (abans de fer la PAC algunes de les imatges de la PAC anterior pesaven 1,1 MB!) i per tant val la pena escurçar el temps de càrrega.

**Llista d'imatges optimitzades i pesos:**

| **Imatge** | **Pes en JPEG** | **WebP (1200px)** | **WebP (800px)** | **WebP (500px)** |
| --- | --- | --- | --- | --- |
| castellfollit2-1200px | 433 kB | 224 kB | 107 kB | 44.5 kB |
| castellfollit-500px-cropped | 207 kB | - | - | 115 kB |
| castellfollit-1200px | 544 kB | 305 kB | 138 kB | 54.7 kB |
| croscat2-1200px | 313 kB | - | - | 33.3 kB |
| croscat-1200px | 308 kB | 194 kB | 91.6 kB | 25.7 kB |
| fageda-1200px | 544 kB | - | - | 71 kB |
| montsacopa-1200px | 217 kB | - | - | 25 kB |
| sta-margarida2-1200px | 370 kB | 176 kB | 76.8 kB | 30.2 kB |
| sta-margarida-500px-cropped | 107 kB | - | - | 44.4 kB |
| sta-margarida-1200px | 263 kB | 101 kB | 51 kB | 23.8 kB |

Com podem veure en aquesta taula la reducció de pesos és important i veiem clarament que un dispositiu mòbil estalviaria una gran quantitat de dades descarregant la imatge de només 500px i en format WebP. Fet que demostra que és útil i important tenir en compte el factor de la resolució i els pesos de les imatges per tenir una web ràpida i eficient de carregar, així com d'estalviar dades als usuaris d'aquesta.

Pel que fa a l'HTML és molt similar al de la PAC anterior i força senzill de comprendre. Pel que fa al CSS, hi ha força més codi ja que per estilitzar els SVG i les imatges i els títols, és necessari. Tot el codi CSS està comentat per tal de facilitar l'entesa d'aquest. Els punts més obvis, com per exemple el color del text o els marges no estan comentats, ja que se suposa que qualsevol que entengui una mica de CSS comprèn què significa.
