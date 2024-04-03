# Clonar un repositorio privado de GitHub utilizando SSH

En Mac:

1. **Abrir Terminal**:
   - Abre la aplicación Terminal en tu Mac. Puedes encontrarla en la carpeta "Utilidades" dentro de la carpeta "Aplicaciones" o buscarla utilizando Spotlight (cmd + barra espaciadora y luego escribe "Terminal").

2. **Generar una nueva clave SSH (si aún no tienes una)**:
   - Ejecuta el siguiente comando para generar una nueva clave SSH:
     ```
     ssh-keygen -t rsa -b 4096 -C "tu_email@example.com"
     ```
   - Sigue las instrucciones en pantalla para elegir la ubicación del archivo de clave y, opcionalmente, configurar una contraseña para la clave.

3. **Agregar tu clave SSH al agente SSH (si es necesario)**:
   - Si estás utilizando un agente SSH, puedes agregar tu clave SSH ejecutando el siguiente comando:
     ```
     ssh-add -K ~/.ssh/tu_clave_privada
     ```
   - Reemplaza `tu_clave_privada` con el nombre del archivo de tu clave privada SSH si has utilizado un nombre diferente al generarla.

4. **Agregar tu clave SSH a tu cuenta de GitHub**:
   - Copia el contenido de tu clave pública SSH ejecutando el siguiente comando en Terminal:
     ```
     pbcopy < ~/.ssh/tu_clave_publica.pub
     ```
   - Ve a la configuración de claves SSH en tu cuenta de GitHub.
   - Haz clic en "Nueva clave SSH" y pega el contenido de tu clave pública SSH en el campo correspondiente.

5. **Clonar el repositorio privado**:
   - En Terminal, navega al directorio donde deseas clonar el repositorio.
   - Utiliza el comando `git clone` seguido de la URL SSH del repositorio GitHub privado. La URL SSH se puede encontrar en la página principal del repositorio en GitHub y tiene el formato `git@github.com:usuario/repo.git`.
   - Por ejemplo:
     ```
     git clone git@github.com:usuario/repo.git
     ```

6. **Confirmar la autenticación SSH**:
   - Cuando intentes clonar el repositorio, es posible que se te solicite confirmar la autenticación SSH proporcionando tu contraseña de clave SSH. Asegúrate de ingresarla correctamente para continuar con el proceso de clonación.

Siguiendo estos pasos, deberías poder clonar un repositorio privado de GitHub utilizando SSH en tu Mac.
