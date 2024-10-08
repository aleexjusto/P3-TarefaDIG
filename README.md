# P3-TarefaDIG

**1.Realiza unha consulta "dig danielcastelao.org" e identific cada parte da resposta (IN, CNAME, A, QUERY SECTION, ANSWER SECTION, AUTHORITY SECTION, etc)**
Al realizar esa consulta, podemos observar lo siguiente:

IN: observamos o tipo A

Answer section: observamos o nome do dominio e a súa IP, neste caso danielcastelao. org coa dirección IP 178.211.133.37 

Query section: observamos que aparece o nome do dominia, neste caso danielcastelao. org e o tipo A

Authority section: observamos que indica os servidores DNS autoritativos, neste caso ns.danielcastelao.org


**2.Realiza consutas dos seguintes nomes e identifica as diferencias: moodle.danielcastelao.org, www.danielcastelao.org**  

Neste caso diferencianse en que moodle.danielcastelo.org é un subdominio, e www.danielcastelao.org apunta a unha dirección IP.

**3.Averigua o nome e IP dos servidores de DNS autoritativos de www.danielcastelao.org, por qué soen ser 2 servidores autoritativos?**

Cando realizo o comando `dig ns danielcastelao.org` apareceme o seguinte:
```
danielcastelao.org.	900	IN	NS	ns2.hover.com.
danielcastelao.org.	900	IN	NS	ns1.hover.com.
```
Hai dous servidores autoritativos para garatir que si un servidor falla, o outro seguiría en uso.

**4.Realiza as consultas de nomes inversas: 130.206.164.68 e de outras dúas IPs que se che ocorran.**

130.206.164.68 : 

**5.A qué servidor DNS estás consultando? Cómo o podes cambiar sen tocar os ficheiros de configuración do sistema?**

Co comando `cat /etc/resolv.conf`podemos obsevar o servidor DNS, no meu caso  127.0.0.53

Se quero cambiar para o servidor de google, co comando `dig "8.8.8.8 www.danielcastelao.org`.

**6.Obtén o rexistro SOA (Start of Authority) do dominio  moodle.danielcastelao.org preguntándolle ó servidor DNS de google e logo preoguntándollo directamente ó servidor primario do dominio danielcastelao.org.**

Para obter o rexistro SOA preguntandolle ó servidro DNS de google, usaremos o comando `dig @8.8.8.8 SOA moodle.danielcastelao.org`

E se queremos consultalo directamente ao servidor primario `dig @ns.danielcastelao.org SOA moodle.danielcastelao.org`.

**7.Consulta a IP de www.elpais.com. Cánto tempo queda almaceado o rexistro de recurso no DNS local?, se preguntas ó DNS local por este recurso, qué observas no TTL do rexistro?**



**8.Busca o TTL de distintos nomes de dominio de servicios que escollas, a qué se poden deber as diferencias?**

**9.Determina o TTL máximo (original) dun nome de dominio.**
**10.Averigua cántas máquinas con distintas IPs están detrás do dominio web www.google.es, sempre son as mesmas e na mesma orde? por qué?**

**11.Pregunta o mesmo a un server raiz (J.ROOTSERVERS.NET por exemplo) e comproba na resposta se o server acepta o modo recursivo**

**12.Se queremos ver tóda-las queries que fai o servidor de DNS, qué opción temos que usar? averigua a IP de www.timesonline.co.uk, especifica os pasos dados**

**13.Usando a información dispoñible a traveso do DNS especifica a máquina (nome e IP) ou máquinas que actúan como servers de correo do dominio danielcastelao.org**

**14.Podes obter os rexistros AAAA de www.facebook.com? a qué corresponden?**
