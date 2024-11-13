# Tutorial Completo: Iniciar Apache Spark en Azure HDInsight

Azure HDInsight es un servicio gestionado que permite trabajar con herramientas del ecosistema Hadoop, como Apache Spark. Este tutorial te guiará paso a paso para configurar y usar Spark en HDInsight, desde la creación del clúster hasta la ejecución de trabajos Spark.

---

## 1 - Crear un clúster HDInsight con Spark

### 1.1 - Crear un recurso HDInsight en el portal de Azure

Acceder al portal de [Azure](https://portal.azure.com).

Hacer _click_ en **Crear un recurso**:

![image](https://github.com/user-attachments/assets/ccb1ae51-fd57-434a-b73a-7a59d89bd6fb)

Buscar **HDInsight** en la barra de búsqueda:

![image](https://github.com/user-attachments/assets/afdc8abf-6e62-46cf-9f85-e592b6994389)

Seleccionar **Azure HDInsight** y hacer _click_ en **Crear** >> **Azure HDInsight**:

![image](https://github.com/user-attachments/assets/31f1b753-31ba-4713-a738-965cb3b8d284)

### 1.2 - Configurar el clúster

**Datos básicos**:

- **Nombre del clúster**: Debe ser un nombre único para identificar el clúster.
- **Suscripción**: Seleccionar la suscripción de Azure.
- **Grupo de recursos**: Crear un grupo de recursos o seleccionar uno existente.
- **Región**: Seleccionar la región, en este caso, Italy North.

![image](https://github.com/user-attachments/assets/72738e01-687d-45b6-a2cc-b68b97ca2ea5)

![image](https://github.com/user-attachments/assets/3aa0fb33-4bcb-4771-9a60-9132d8030ce0)

- **Tipo de clúster**: Seleccionar **Spark**, y elegir la última versión disponible:

![image](https://github.com/user-attachments/assets/0ffd8c87-4540-47e2-a168-ec6feac77f7e)

![image](https://github.com/user-attachments/assets/f81088a7-d773-47bb-89dc-cd8c85dc9787)

![image](https://github.com/user-attachments/assets/fe6082a1-60e9-4948-a4a2-a01f1f3d06ca)

- **Credenciales del clúster**: Crear unas credenciales de acceso para el clúster. Después, hacer _click_ en **Siguiente: Almacenamiento>>**:

![image](https://github.com/user-attachments/assets/10a9b76a-5c3a-4da8-bf7b-e8e478e13b17)

**Almacenamiento**:

   - **Tipo de almacenamiento principal**: **Azure Storage**.
   - **Cuenta de almacenamiento principal**: _Crear nuevo_ >> Introducir un nombre válido para la nueva cuenta de almacenamiento, y hacer _click_ en **De acuerdo**.

   ![image](https://github.com/user-attachments/assets/683c468c-ae1a-4fe9-ba76-87981b6c40e1)

   ![image](https://github.com/user-attachments/assets/c0960219-3a3b-43bf-8db5-b1898f625c48)

**Configuración y precios**:

   - En **Nodo Trabajador**, cambiar el número de nodos de `4` a `1`, para evitar el siguiente error:

   ![image](https://github.com/user-attachments/assets/142556a7-6eb8-437e-940e-1a71b078cbef)
     
Dejar el resto de las configuraciones como están y hacer _click_ en **Revisar y crear**.

Esperar a que finalice la implementación (esto puede tardar entre 15 y 30 minutos).

![image](https://github.com/user-attachments/assets/cc9e36bf-f46a-4f51-9614-2fd6aab9712b)

---

## 2. Conectar al clúster

Entrar al recurso del clúster, y buscar la sección de _Configuración_ >> _SSH e inicio de sesión del clúster_. Seleccionar el **nombre del host** en el desplegable, y copiar el comando que aparece debajo:

```bash
ssh <usuario>@<nombre_del_cluster>-ssh.azurehdinsight.net
```

![image](https://github.com/user-attachments/assets/8b642776-9421-4a93-970f-57fe716dc92d)
