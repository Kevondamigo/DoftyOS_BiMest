# DoftyOS_BiMest
El proyecto se llama BiMest Manager en este podremos encontrar la documentación que cada integrante desarrollo

Kevin Sandoval Nieves
Juan Pablo Sebastian Flores Varela
Said Santiago Díaz Loya
Daniel Alejandro Pérez Esquivel
Daniel Meza Sánchez
Carlos Daniel Pérez Arzate
Eduardo Lopéz Pérez

# BiMest Manager: Ecosistema SaaS de Gobernanza de Recursos
Resumen Ejecutivo
BiMest Manager es una solución de software de nivel empresarial desarrollada por el equipo de ingeniería Dofty OS de la Universidad La Salle Nezahualcóyotl. Definido no solo como un software de inventario, sino como un Ecosistema SaaS de Gobernanza de Recursos, el sistema está diseñado para digitalizar el control de activos materiales y espacios físicos en organizaciones diversas como universidades, laboratorios y centros de trabajo.
El propósito central del proyecto es eliminar la fricción operativa del "papel y lápiz" y la incertidumbre en la disponibilidad de recursos mediante un sistema inteligente de préstamos y trazabilidad total. Los tres valores fundamentales que BiMest Manager aporta al usuario son:

    Gobernanza y Trazabilidad Total: Control absoluto sobre quién posee un recurso, en qué estado se encuentra y cuándo debe ser devuelto, eliminando pérdidas por desarticulación administrativa.
    Modularidad Dinámica: Inspirado en sistemas de colaboración modernos, permite la formación de equipos en tiempo real y la gestión de inventarios mediante "Kits" lógicos.
    Mitigación de Riesgos Institucionales: Vinculación de adeudos materiales con el estatus académico o administrativo del usuario, incentivando la responsabilidad y el retorno oportuno de los activos.

--------------------------------------------------------------------------------
Análisis Detallado de Temas Principales
Arquitectura y Conceptos Clave
BiMest Manager se fundamenta en una estructura técnica robusta y una lógica de negocio diseñada para entornos de alto volumen (hasta 250 usuarios diarios por laboratorio).

    Patrón de Arquitectura: El sistema utiliza el patrón Modelo-Vista-Controlador (MVC) para garantizar una separación clara de responsabilidades y facilitar el mantenimiento del código.
    Gestión de Kits como "Recetas": A diferencia de los sistemas tradicionales, un "Kit" en BiMest no es un objeto físico con ID único, sino una agrupación lógica o plantilla de artículos individuales. Esto permite una gestión de stock dinámica y precisa.
    Grupos Just-In-Time (JIT): Los grupos de trabajo se forman en el momento de la práctica mediante el escaneo de códigos QR, digitalizando instantáneamente la responsabilidad colectiva.
    Modelo de Control de Acceso (RBAC): La seguridad y visibilidad de los datos se rigen por un sistema de roles estrictos:
        Owner: Control total de la organización y facturación.
        Administrador (Staff): Gestión de inventario (CRUD), aprobación de préstamos y control de adeudos.
        Supervisor (Maestro): Autorización de préstamos específicos para sus clases y visualización de reportes.
        Usuario Final (Alumno): Consulta de catálogo y solicitudes de préstamo.
        Responsable de Equipo (Rol Temporal): El sistema asigna responsabilidad legal y académica a un integrante específico durante una sesión.

Funcionalidades Core
El sistema integra capacidades técnicas avanzadas para cubrir todo el ciclo de vida del recurso:

    Gestión de Inventario Multi-almacén: Capacidad de gestionar múltiples estantes y tipos de materiales (cristalería, equipos médicos, pesas, etc.) con estados visuales (rojo/verde) para identificar entregas y deudas.
    Ciclo de Préstamos Inteligente: Proceso automatizado que incluye la solicitud, aprobación por parte del administrador en menos de un segundo (persistencia en tiempo real) y validación de adeudos previos.
    Sistema de Notificaciones y Recordatorios: Bombardeo de notificaciones al alumno y, opcionalmente, al tutor académico en caso de retraso o rotura de material.
    Gestión de Adeudos y Excepciones: Herramientas para que el staff reporte material dañado y bloquee al usuario en el sistema institucional (evitando, por ejemplo, que realice exámenes si tiene adeudos).
    Analítica y Estadísticas: Generación de datos mensuales sobre rotura de materiales para justificar compras de stock y reposición basada en frecuencias de uso.

Evidencias y Flujos de Trabajo
El diseño del sistema se basa en flujos validados por personal operativo (coordinadores y laboratoristas):

    Validación de Dominio: El registro está restringido a correos institucionales (ej. @ulsaneza.edu.mx) para asegurar que solo miembros de la organización accedan.
    Flujo del "Camino Feliz" (Happy Path):
        El supervisor prepara la práctica.
        El alumno forma un equipo vía QR (incluso sin app nativa, vía Flutter/HTML).
        El administrador despacha el kit validando que no existan adeudos.
        El sistema actualiza el estado del stock en tiempo real.
    Procesamiento de Excepciones: El sistema permite el "Override" de staff para casos donde un alumno sin equipo necesita integrarse a un grupo ya lleno o cuando se requiere ajustar la lista de materiales de una práctica sobre la marcha (ajustes dinámicos).
    Validación de Devolución: Implementación de un periodo de gracia (típicamente 8 días) antes de escalar el reporte a niveles jerárquicos superiores (tutores o padres en el caso de preparatoria).

--------------------------------------------------------------------------------
Estructura y Conclusiones
Stack Tecnológico y Desarrollo
El proyecto se encuentra en una fase de desarrollo activo con una fecha de entrega crítica para el 7 de junio. Se han priorizado herramientas con curvas de aprendizaje amigables para cumplir con los plazos académicos sin comprometer la calidad:

    Backend: Node.js para la lógica de servidores.
    Frontend: Desarrollo multiplataforma nativo.
    Ingeniería: Uso de Swagger UI para documentación de APIs y Flyway para migraciones de bases de datos.

Conclusiones sobre Escalabilidad y Estado Actual
El análisis de las fuentes revela que BiMest Manager está diseñado para la escalabilidad masiva a través de un modelo SaaS de cuatro niveles:

    Freemium: Para organizaciones pequeñas (hasta 50 ítems).
    Básico y Pro: Incrementan el volumen de transacciones y usuarios, añadiendo herramientas de importación/exportación de Excel.
    Enterprise: Ofrece integración SSO/Active Directory, branding completo y desarrollo de funcionalidades personalizadas.

Estado del Proyecto: El sistema está transitando de un modelo basado en papel y macros de Excel hacia una automatización total. La arquitectura flexible permite alternar proveedores de infraestructura, asegurando que el software pueda evolucionar de un entorno de laboratorio universitario a cualquier escenario de gestión de recursos materiales a gran escala.
Métrica de Escalabilidad
	
Plan Freemium
	
Plan Enterprise
Usuarios
	
Hasta 20
	
Personalizado
Préstamos Mensuales
	
100
	
Ilimitados
Inventario
	
50 ítems
	
Ilimitado
Seguridad
	
Registro Manual
	
SSO / AD
El sistema se perfila como una herramienta indispensable para la modernización administrativa, reduciendo el desperdicio de papel y optimizando el tiempo del personal operativo en un 90% mediante la automatización de bitácoras y registros de asistencia.
