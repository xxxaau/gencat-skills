# Literals per a UI — Comunicació Clara Gencat

Patrons de text per als elements d'interfície d'aplicacions de la Generalitat de Catalunya. Segueix sempre la Guia de Comunicació Clara.

---

## Tractament segons context

| Context | Tractament | Exemple |
|---------|-----------|---------|
| Textos administratius, tràmits, resolucions, notificacions | Vós | "Hem rebut la vostra sol·licitud" |
| Missatges d'error i d'estat de la UI | Vós | "Comproveu la connexió i torneu-ho a intentar" |
| Aplicacions adreçades específicament a joves, contextos informals | Tu | "T'hem afegit a la llista d'espera" |

Mai barregis tractaments en un mateix flux. En cas de dubte, usa **vós**.

---

## Botons d'acció

### Principis per a botons
- **Verb en infinitiu** que descrigui l'acció exacta
- Concis: màxim 3 paraules
- No uses puntuació final
- Prou específic perquè no necessiti context: "Enviar la sol·licitud" > "Enviar"

### Botons habituals

| Acció | ✅ Text recomanat | ❌ Evita |
|-------|-----------------|---------|
| Enviar formulari | "Enviar la sol·licitud" / "Enviar" | "Remetre" / "Trametre" |
| Desar esborrany | "Desar" / "Desar l'esborrany" | "Emmagatzemar" / "Guardar" |
| Continuar al pas següent | "Continuar" / "Pas següent" | "Avançar" / "Procedir" |
| Tornar al pas anterior | "Tornar" / "Pas anterior" | "Retrocedir" / "Enrere" |
| Cancel·lar | "Cancel·lar" | "Abandonar" / "Sortir sense desar" |
| Confirmar acció | "Confirmar" / "Sí, confirmo" | "Validar" / "Acceptar" |
| Eliminar element | "Eliminar" | "Suprimir" / "Esborrar" / "Borrar" |
| Descarregar fitxer | "Descarregar" | "Obtenir" / "Download" |
| Adjuntar fitxer | "Adjuntar" / "Afegir fitxer" | "Annexar" / "Pujar" |
| Iniciar sessió | "Iniciar sessió" | "Login" / "Entrar" |
| Tancar sessió | "Tancar sessió" | "Logout" / "Sortir" |
| Cercar | "Cercar" | "Search" / "Buscar" |
| Filtrar resultats | "Aplicar filtres" | "Filtrar" (sol, acceptable) |
| Netejar filtres | "Netejar filtres" / "Treure els filtres" | "Reiniciar" / "Reset" |
| Editar | "Editar" / "Modificar" | "Update" / "Canviar" |
| Veure detall | "Veure detalls" | "Més informació" (massa vague) |
| Tornar a l'inici | "Tornar a l'inici" | "Home" / "Inici" (sol, acceptable) |
| Tancar | "Tancar" | "Close" / "Sortir" |
| Imprimir | "Imprimir" | "Print" |
| Compartir | "Compartir" | "Share" |

---

## Missatges d'error

### Principis per a errors
- **Explica QUÈ ha passat** en termes simples (sense codis críptics)
- **Indica QUÈ ha de fer** el lector per resoldre-ho
- **Veu activa** i tono directe, sense culpabilitzar
- No uses tecnicismes com "error 404", "timeout", "null pointer"
- No comences amb "Error:" — descriu el problema directament

### Errors de validació de formulari

| Camp | ✅ Text recomanat |
|------|-----------------|
| Camp obligatori buit | "Aquest camp és obligatori" |
| Format incorrecte — DNI | "El DNI ha de tenir 8 dígits seguits d'una lletra majúscula (exemple: 12345678A)" |
| Format incorrecte — NIE | "El NIE ha de começar per X, Y o Z, seguit de 7 dígits i una lletra (exemple: X1234567A)" |
| Format incorrecte — email | "Introduïu una adreça de correu electrònic vàlida (exemple: nom@domini.cat)" |
| Format incorrecte — telèfon | "El telèfon ha de tenir 9 dígits sense espais ni guions" |
| Format incorrecte — data | "Introduïu la data en format DD/MM/AAAA (exemple: 15/03/2024)" |
| Format incorrecte — codi postal | "El codi postal ha de tenir 5 dígits" |
| Valor fora de rang | "Introduïu un valor entre [mínim] i [màxim]" |
| Contrasenya feble | "La contrasenya ha de tenir com a mínim 8 caràcters, una majúscula i un número" |
| Contrasenyes no coincideixen | "Les contrasenyes no coincideixen. Comproveu que heu escrit el mateix als dos camps" |
| Fitxer massa gran | "El fitxer supera la mida màxima permesa ([X] MB). Reduïu-lo i torneu-lo a adjuntar" |
| Format de fitxer no acceptat | "Aquest format de fitxer no és acceptat. Podeu adjuntar fitxers [PDF, JPG, PNG]" |
| Selecció obligatòria | "Seleccioneu una de les opcions" |

### Errors de sistema

| Situació | ✅ Text recomanat |
|---------|-----------------|
| Error genèric | "S'ha produït un error inesperat. Torneu-ho a intentar en uns moments" |
| Sense connexió | "No hi ha connexió a Internet. Comproveu la vostra connexió i torneu-ho a intentar" |
| Servei no disponible | "El servei no està disponible en aquest moment. Torneu-ho a intentar més tard" |
| Sessió caducada | "La vostra sessió ha caducat per inactivitat. Torneu a iniciar sessió per continuar" |
| Pàgina no trobada (404) | "No hem trobat la pàgina que cercàveu. Potser ha canviat d'adreça o ja no existeix" |
| Accés denegat (403) | "No teniu permís per accedir a aquesta secció" |
| Temps d'espera superat | "L'operació ha trigat massa. Comproveu la connexió i torneu-ho a intentar" |

### Errors d'autenticació i seguretat

| Situació | ✅ Text recomanat |
|---------|-----------------|
| Credencials incorrectes | "El nom d'usuari o la contrasenya no són correctes" |
| Compte blocat per intents fallits | "Heu superat el nombre màxim d'intents. Per seguretat, el compte queda blocat durant [X] minuts" |
| Certificat digital no detectat | "No hem detectat cap certificat digital. Comproveu que el teniu instal·lat i torneu-ho a intentar" |
| Certificat digital caducat | "El vostre certificat digital ha caducat. Renoveu-lo per continuar amb el tràmit" |
| Codi de verificació (dos passos) | "Us hem enviat un codi de verificació al mòbil acabat en [XXX]. Introduïu-lo per continuar" |

> Per seguretat: no especifiquis quin dels dos camps (usuari o contrasenya) és incorrecte, i no revelis detalls interns del sistema en cap missatge d'error.

---

## Missatges de confirmació i èxit

### Principis
- **Confirma clarament** l'acció completada
- Indica **quan** i **on** veurà el resultat si no és immediat
- Si cal acció addicional, indica-la de forma clara

### Missatges d'èxit

| Acció | ✅ Text recomanat |
|-------|-----------------|
| Formulari enviat | "Hem rebut la vostra sol·licitud" |
| Formulari enviat (amb referència) | "Hem rebut la vostra sol·licitud. El número de referència és [REF-XXXX]" |
| Canvis desats | "S'han desat els canvis" |
| Element eliminat | "S'ha eliminat [l'element]" |
| Contrasenya canviada | "S'ha canviat la contrasenya correctament" |
| Dades actualitzades | "S'han actualitzat les dades del perfil" |
| Fitxer adjuntat | "S'ha adjuntat el fitxer correctament" |
| Notificació enviada | "S'ha enviat la notificació a [nom/adreça]" |

### Missatges de confirmació prèvia (modal/diàleg)

| Acció destructiva | ✅ Títol | ✅ Cos | ✅ Botó confirmar | ✅ Botó cancel·lar |
|-----------------|---------|-------|-----------------|-----------------|
| Eliminar element | "Voleu eliminar [element]?" | "Aquesta acció no es pot desfer." | "Eliminar" | "Cancel·lar" |
| Tancar sessió | "Voleu tancar la sessió?" | "Si teniu canvis sense desar, es perdran." | "Tancar sessió" | "Cancel·lar" |
| Abandonar formulari | "Voleu sortir sense desar?" | "Perdreu les dades que heu introduït." | "Sortir sense desar" | "Continuar editant" |
| Revocar accés | "Voleu revocar l'accés de [persona]?" | "Deixarà de tenir accés immediatament." | "Revocar l'accés" | "Cancel·lar" |

---

## Etiquetes de formulari (labels)

### Principis
- **Nom del camp**, no instrucció ("Nom" > "Escriviu el nom")
- Concís: 1-4 paraules
- Sense dos punts finals a l'etiqueta visible (l'espai en fa la funció)
- El text d'ajuda (placeholder o hint) és opcional, mai substitueix el label

### Etiquetes habituals

| Camp | ✅ Etiqueta | Nota |
|------|-----------|------|
| Nom de pila | "Nom" | |
| Cognoms | "Cognoms" | |
| DNI/NIE | "DNI o NIE" | Especifica els dos |
| Data de naixement | "Data de naixement" | |
| Adreça electrònica | "Adreça electrònica" | (no "Email") |
| Telèfon | "Telèfon" | Si cal especificar: "Telèfon mòbil" / "Telèfon fix" |
| Adreça postal | "Adreça" | |
| Codi postal | "Codi postal" | |
| Municipi | "Municipi" | |
| Contrasenya | "Contrasenya" | |
| Confirmar contrasenya | "Confirmeu la contrasenya" | |
| Comentaris opcionals | "Comentaris (opcional)" | |
| Adjuntar fitxer | "Adjunteu el document" | Especifica el tipus si cal |

### Placeholders (text d'ajuda dins el camp)

| Camp | ✅ Placeholder |
|------|--------------|
| DNI | "Exemple: 12345678A" |
| Data | "DD/MM/AAAA" |
| Email | "nom@domini.cat" |
| Codi postal | "08001" |
| Telèfon | "600 000 000" |
| Cerca | "Cerqueu per nom, referència..." |

---

## Avisos i alertes (banners/toasts)

### Tipus i missatges

| Tipus | Ús | ✅ Exemple de text |
|-------|----|--------------------|
| **Informatiu** (blau) | Informació neutra que l'usuari ha de conèixer | "El termini de presentació acaba el 31 de març" |
| **Avís** (groc/taronja) | Situació que requereix atenció però no és urgent | "Teniu canvis sense desar. Deseu-los abans de sortir" |
| **Error** (vermell) | Problema que impedeix continuar | "No s'ha pogut enviar la sol·licitud. Torneu-ho a intentar" |
| **Èxit** (verd) | Confirmació d'acció completada | "La sol·licitud s'ha enviat correctament" |

---

## Notificacions (correu electrònic i push)

### Correu electrònic transaccional

| Element | Pauta | ✅ Exemple |
|---------|-------|-----------|
| Assumpte | Breu (< 60 caràcters), descriu el fet o l'estat; sense codis al davant | "Hem rebut la vostra sol·licitud" |
| Primera frase | Confirma el fet principal i la data | "Hem rebut la vostra sol·licitud d'ajut el 15/03/2026." |
| Cos | Número de referència, pas següent i termini si n'hi ha | "El número de referència és REF-1234. Rebreu resposta abans del 30 d'abril." |
| Tancament | Enllaç per consultar l'estat o canal de contacte | "Podeu consultar l'estat a la vostra àrea privada." |

### Notificacions push

- Títol: màxim ~50 caràcters, el fet principal ("Nova resposta a la vostra sol·licitud")
- Cos: màxim ~120 caràcters, **sense dades personals ni informació sensible** (es veu amb la pantalla blocada)
- Sempre amb una acció clara en obrir-la

---

## Indicadors d'estat

### Estats d'un expedient / procés

| ✅ Estat (text clar) | Significat |
|--------------------|-----------|
| Pendent de documentació | L'usuari ha d'aportar documents |
| En revisió | L'administració l'està analitzant |
| Pendent de resolució | Espera decisió |
| Aprovat / Acceptat | Resolució favorable |
| Denegat | Resolució desfavorable |
| Arxivat | Tràmit tancat sense resolució |
| Caducat | S'ha superat el termini |
| Anul·lat | S'ha deixat sense efecte |

---

## Textos de pàgines especials

### Pàgina sense resultats
```
Títol: No hem trobat cap resultat
Cos: Proveu de cercar amb altres paraules o traieu alguns filtres.
```

### Estat de càrrega
```
"S'està carregant..."
"Processant la sol·licitud..."
"Comprovant les dades..."
```

### Pantalla de benvinguda / onboarding
```
❌ "Benvingut/da al sistema de gestió d'expedients de la Generalitat de Catalunya"
✅ "Benvingut/da. Des d'aquí podeu gestionar les vostres sol·licituds i consultar-ne l'estat"
```

### Peu de formulari amb camps obligatoris
```
✅ "Els camps marcats amb * són obligatoris"
```

### Missatge de sessió expirant
```
✅ "La vostra sessió caducarà en 5 minuts per inactivitat. Voleu continuar?"
Botó: "Continuar la sessió" | "Tancar la sessió"
```
