En esta demostración, configuraremos el servicio Bastion, las actualizaciones de máquinas virtuales, las extensiones de máquina virtual y el cifrado de disco. Opcionalmente, usaremos RDP para conectarnos a una máquina virtual de Windows y SSH para conectarnos a una máquina Linux.

## Tarea 1: Uso del servicio Bastion

Nota: Esta tarea requiere una máquina virtual. Si va a realizar la siguiente tarea, las actualizaciones de la máquina virtual, use una máquina virtual de Windows y mantenga la sesión en ejecución.

En esta tarea, configuraremos el servicio Bastion y nos conectaremos a una máquina virtual con servicio.

### Configuración del servicio Bastion

1. En el Portal, vaya a su máquina virtual de Windows.

2. Asegúrese de que la máquina virtual está En ejecución.

![image](https://user-images.githubusercontent.com/110675810/193914545-08bdffb7-ca90-4fb4-be48-21897e763569.png)

3. Haga clic en Conectar y seleccione Bastion.

![image](https://user-images.githubusercontent.com/110675810/193921178-1bffb086-a872-4377-84d7-43bdbf2056c7.png)

4. Haga clic en Usar Bastion. Tenga en cuenta que la instalación del servicio solo es necesaria una vez.

![image](https://user-images.githubusercontent.com/110675810/193914656-3cf33510-03ff-4efc-adbc-ac0769d85161.png)

5. Dado que va a crear el servicio Bastion desde la máquina virtual de destino, observe que la mayor parte de la información de red se ha rellenado automáticamente. 
   Tenga en cuenta que al servicio Bastion se le asignará una dirección IP pública.

![image](https://user-images.githubusercontent.com/110675810/193923268-3bba3828-fe2a-4644-9a50-0c4b6c158bfd.png)

6. Para crear la subred Bastion en la red virtual, haga clic Administrar configuración de subred.

![image](https://user-images.githubusercontent.com/110675810/193923815-27842bbf-d691-4187-9c31-f5ef75b2be17.png)

7. En la hoja de subred de red virtual, haga clic en + Subred.

![image](https://user-images.githubusercontent.com/110675810/193924014-27602114-e8d0-4721-89db-b93f64f96361.png)

8. En la página Agregar subred, escriba AzureBastionSubnet como nombre de subred. Tenga en cuenta que este nombre no se puede cambiar.

9. Especifique el intervalo de direcciones en la notación CIDR. Por ejemplo, 10.1.1.0/27.

10. Haga clic en Aceptar y luego en Crear. El servicio tardará unos minutos en implementarse.

![image](https://user-images.githubusercontent.com/110675810/193924367-56ae5242-9bc9-401e-882d-2c5c6c0185f6.png)

### Conexión a la máquina virtual mediante Bastion

1. En la hoja Información general de la máquina virtual de destino, seleccione Conectar y luego Bastion.

![image](https://user-images.githubusercontent.com/110675810/193921494-b1bf651d-23ec-47d5-8765-cfb0e3cbf2f9.png)

2. En la página Connect to Bastion (Conectar a Bastion) escriba las credenciales de inicio de sesión de la máquina virtual.

![image](https://user-images.githubusercontent.com/110675810/193916528-09d07599-bb3f-4755-8f0d-c76372204b91.png)

3. Observe la casilla para abrir la sesión en una nueva ventana.

![image](https://user-images.githubusercontent.com/110675810/193916694-87165fe8-855c-439b-90f3-9d136bb524a7.png)

4. Haga clic en Conectar. Si recibe un mensaje que indica que las ventanas emergentes están bloqueadas, permita la sesión.

5. Una vez conectada la sesión, inicie la paleta de herramientas de acceso al Portapapeles de Bastion seleccionando las dos flechas. Las flechas se encuentran en la parte central izquierda de la sesión. Explique esta característica de copiar y pegar.

![image](https://user-images.githubusercontent.com/110675810/193918230-72036f3f-152e-4b95-a9e2-155a47d89c62.png)

6. En el Portal, vaya al host Bastion y, en Configuración, seleccione Sesiones.

![image](https://user-images.githubusercontent.com/110675810/193922183-5a5ed82b-dab8-4000-86b9-e65d71e2ee0c.png)

7. Revise la experiencia de administración de sesiones y la capacidad de eliminar una sesión.

![image](https://user-images.githubusercontent.com/110675810/193922485-32ad886e-f1fb-4fbb-b2d5-a349abcc60e4.png)

8. Si tiene tiempo, revise los componentes de Bastion y cómo esto proporciona una forma segura de acceder a sus máquinas virtuales.

![image](https://user-images.githubusercontent.com/110675810/193922739-76b2765f-7f81-48fa-83fc-7e97f0c5fea4.png)


## Tarea 2: Actualizaciones de máquina virtual

Nota: Esta tarea requiere una máquina virtual en ejecución. Es posible que quiera habilitar Update Management antes de esta lección.

En esta tarea, revisaremos la administración de actualizaciones de máquinas virtuales.

1. En el Portal, vaya a su máquina virtual.

![image](https://user-images.githubusercontent.com/110675810/193926757-ee4c015f-99d6-4816-b3c7-54d936f523fe.png)

2. En Operaciones, seleccione Update Management.

![image](https://user-images.githubusercontent.com/110675810/193926978-3f80ba6c-0c0c-4fb1-b881-4d72ea7daab5.png)

3. Seleccione el área de trabajo de Azure Log Analytics y la cuenta de Automation y, a continuación, haga clic en Habilitar.

4. Espere a que Update Management se implemente. La implementación puede tardar hasta 15 minutos y los resultados pueden tardar más.

![image](https://user-images.githubusercontent.com/110675810/194125097-ab37fa27-a2d6-47a2-8fd1-48f19e7ea8aa.png)

5. Seleccione Actualizaciones que faltan y use el vínculo Información para abrir el artículo de soporte técnico de la actualización.

![image](https://user-images.githubusercontent.com/110675810/194125505-2a48a91e-6056-4e88-a616-7f8e4950d8ac.png)

6. Seleccione Programar implementación de actualizaciones.

![image](https://user-images.githubusercontent.com/110675810/194127669-75a4ef31-3637-4552-a595-ee87ed55b3bc.png)

![image](https://user-images.githubusercontent.com/110675810/194128005-bb8f0212-9557-4769-92ab-71e39950e595.png)

7. Revise las distintas opciones, como las ventanas de mantenimiento, las opciones de reinicio, la programación, las clasificaciones y las bases de conocimiento para incluir y excluir.

![image](https://user-images.githubusercontent.com/110675810/194128711-2ebb245d-db79-4355-bf7f-32b0863fff99.png)

8. Puede ver el estado de la implementación en la pestaña Implementaciones de actualización. Los valores disponibles señalan si no se ha intentado, se ha completado correctamente y ha dado error.



## Tarea 3: Extensiones de máquina virtual

En esta tarea, instalaremos la extensión IaaSAntimalware.

1. En el Portal, seleccione la máquina virtual.

2. En Configuración, haga clic en Extensiones. Revise cómo se usan las extensiones.

3. En la página Extensiones, haga clic en + Agregar.

4. Desplácese por las extensiones disponibles y revise qué extensiones están disponibles.

5. Seleccione Microsoft Antimalware. Analice las características de esta extensión.

6. Haga clic en Crear.

7. En la página Instalar extensión, utilice los iconos informativos para explicar Archivos y ubicaciones excluidos, Extensiones de archivo excluidos y Procesos excluidos.

8. Revise Protección en tiempo real y Ejecutar un análisis programado.

9. Revise otras opciones que le resulten interesantes.

10. Una vez implementada la extensión, la página de extensiones mostrará la extensión IaaSAntimalware.

