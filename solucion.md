## Servidores DHCP Windows

Dado o seguinte escenario:

  ![Imagen Imagen0.png](/imagenes/Imagen0.png)

Os equipos ned, rob serán os servidores dns para o dominio stark.lan (Debian) e tywin para lanister.lan (Windows)

Instala no equipo tyrion (Windows) o rol de servidor DHCP coa seguinte configuración: (deberás ter apagados os servidores DHCP do punto anterior)

**1**. Un ámbito para os equipos da rede privada lanister, con un intervalo de exclusión.

**2**. Deberás crear unha reserva estática que estará no rango de enderezos do seu ámbito correspondente.

**3**. Establece os nomes de dominio e servidores DNS primario de cada zona.

**4**. Deberás actualizar a zona primaria no servidor DNS tywin.

**5**. Engade outro ámbito para a rede primaria stark (necesitas outra interface de rede) que actualice a zona prinaria DNS definida no equipo arya.

**6**. Instala no equipo jaime un servizo DHCP failover para a subrede lanister.

**7**. Necesitarás polo menos tres clientes (Cercei,Joffrey, Myrcella) para a rede lannister e un para a  rede stark (jon).
Inclúe capturas de:

  - Configuración dos ambitos e rangos de enderezos

    Configuración do ambito stark.lan:

    ![Imagen Imagen1_1.png](/imagenes/Apartado1_1.png)

    Configuración do ambito lannister.lan:

    ![Imagen Imagen1_2.png](/imagenes/Apartado1_2.png)

  - Configuración de opcións

    Configuración do ambito stark.lan:

    ![Imagen Imagen2_1.png](/imagenes/Apartado2_1.png)

    Configuración do ambito lannister.lan:    

    ![Imagen Imagen2_2.png](/imagenes/Apartado2_2.png)

  - Configuración da actualización

    Configuracion no equipo TRYION sobre o ambito lannister.lan:

    ![Imagen Imagen3_1.png](/imagenes/Apartado3_1.png)

    Configuracion no equipo TYWIN sobre a zona de busqueda directa lannister.lan:

    ![Imagen Imagen3_2.png](/imagenes/Apartado3_2.png)

  - Vídeo no que o cliente renova a concesión, e se ve  a zona DNS unha vez que o DHCP actualiza o DNS. Tamén o cliente debe ser capaz de resolver o seu propio nome (non FQDN).

    **VIDEO:**  [Clica aqui para ver el vídeo](https://www.youtube.com/watch?v=TbuC1eQ6rSY)

    Cliente CERCEI resolvendo a sua propia zona:

    ![Imagen Imagen4_2.png](/imagenes/Apartado4_2.png)

    Cliente MYRCELLA resolvendo a sua propia zona:

    ![Imagen Imagen4_3.png](/imagenes/Apartado4_3.png)

    Cliente JOFFREY resolvendo a sua propia zona:

    ![Imagen Imagen4_4.png](/imagenes/Apartado4_4.png)

  - Clientes das dúas subredes, amosando DNS, router e enderezo IP.

    Cliente CERCEI: 

    ![Imagen Imagen5_1.png](/imagenes/Apartado5_1.png)

    Cliente MYRCELLA:

    ![Imagen Imagen5_2.png](/imagenes/Apartado5_2.png)

    Cliente JOFFREY:

    ![Imagen Imagen5_3.png](/imagenes/Apartado5_3.png)

  - Configuración dos servidores 
  
    Configuración no ambito stark.lan da conmutacion por error:

    ![Imagen Imagen6_1.png](/imagenes/Apartado6_1.png)

    Configuración no ambito lannister.lan da conmutacion por error:

    ![Imagen Imagen6_2.png](/imagenes/Apartado6_2.png)

  - Capturas dos clientes obtendo enderezos cos dous servidores failover encendidos, e con un acendido e outro apagado (de forma alterna)

    Resultado de que os dous servidores estan funcionando:

    ![Imagen Imagen7_1.png](/imagenes/Apartado7_1.png)

    Cliente CERCEI con ip asignada por TRYON:

    ![Imagen Imagen7_2.png](/imagenes/Apartado7_2.png)

    Cliente MYRCELLA con ip asignada por JAIME:

    ![Imagen Imagen7_3.png](/imagenes/Apartado7_3.png)

    Cliente JOFFREY con ip asignada por TRYON:

    ![Imagen Imagen7_4.png](/imagenes/Apartado7_4.png) 
   

**8**. Elimina a interface de rede 192.168.11.8 de tyrion, e configura o servizo DHCP Relay no router. 
Comproba que os equipos da rede stark.lan reciben a configuración de rede de xeito correcto. 
Inclúe as capturas necesarias.

  Configuracion do router instalando un DHCP RELAY:

  ![Imagen Imagen8_1.png](/imagenes/Apartado8_1.png)

  Cliente JON:

  ![Imagen Imagen8_2.png](/imagenes/Apartado8_2.png)




