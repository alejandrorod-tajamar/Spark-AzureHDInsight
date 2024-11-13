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

Seleccionar **Azure HDInsight** y hacer _click_ en **Crear** >> **Azure HDInsight**.

### 1.2 Configurar el clúster
1. **Datos básicos**:
   - **Nombre del clúster**: Debe ser un nombre único para identificar el clúster.
   - **Suscripción**: Selecciona la suscripción de Azure.
   - **Grupo de recursos**: Crea un grupo de recursos o selecciona uno existente.
   - **Región**: Selecciona la región (por ejemplo, Italy North).

2. **Tipo de clúster**:
   - Selecciona **Spark**, y elige la última versión disponible.

3. **Credenciales del clúster**:
   - Crea unas credenciales de acceso para el clúster. Luego, haz clic en **Siguiente: Almacenamiento**.

4. **Almacenamiento**:
   - **Tipo de almacenamiento principal**: Azure Storage.
   - **Cuenta de almacenamiento principal**: Crea una nueva cuenta de almacenamiento y dale un nombre válido.

5. **Configuración y precios**:
   - En **Nodo Trabajador**, cambia el número de nodos de `4` a `1`.
   - Deja el resto de las configuraciones como están y haz clic en **Revisar y crear**.

6. Espera a que finalice la implementación (esto puede tardar entre 15 y 30 minutos).

---

## 2. Conectar al clúster

1. Entra al recurso del clúster en el portal de Azure.
2. Ve a la sección **Configuración** > **SSH e inicio de sesión del clúster**.
3. Selecciona el nombre del host en el desplegable y copia el comando SSH que aparece debajo:
```bash
ssh <usuario>@<nombre-del-cluster>-ssh.azurehdinsight.net
```
