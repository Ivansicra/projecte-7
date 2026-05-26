# Exercicis

## Anàlisi en viu

### ICMP

Kali ja té instal·lat Wireshark. Si esteu utilitzant un Ubuntu Desktop, instal·la i configura Wireshark.

Posa en marxa la captura de paquets de Wireshark sobre la targeta de xarxa del teu Kali amb adaptador pont:

- **Adreça IP:** `192.168.c.x/24` on `c` és `2` per 2n A i `4` per 2n B, i `x` el teu número de llista.
- **Porta d'enllaç:** `192.168.c.254`
- **DNS:** `8.8.8.8`

Obre una consola i executa un `ping` a algun servei o al router de l’escola. Deixa que faci quatre o cinc peticions i atura la comanda (el `ping` per defecte a Linux no para d’enviar paquets).

> **Nota:** No facis un ping a la teva pròpia màquina perquè els paquets realment no surten de la teva màquina i el Wireshark no els pot capturar.

Atura la captura de paquets. Veuràs que s’ha capturat un munt de paquets, sense discriminar, però només volem veure els que fan referència al ping que hem fet.

Per fer-ho, apliquem un filtre de visualització, que permet triar el que volem veure de tot el que s’ha capturat.

Dintre aquest protocol trobem els tipus `echo request/reply`, que són els que fa servir la comanda `ping`.

Escriu la paraula `icmp` a **Filter:**.

#### Preguntes

- Quin número de tipus de ICMP té la petició d’eco i quin la resposta d’eco?
- Com ho veus?
- Incorpora una captura de pantalla on es vegi el tipus de ICMP.

A les opcions avançades de la targeta activa el mode promiscu amb l’opció **Permetre-ho tot**.

```text
promiscous_mode
