# Decisiones tomadas durante el proyecto

Este documento recoge las decisiones técnicas y de alcance consolidadas durante el desarrollo del proyecto.

## 1. Alcance funcional
- El proyecto se plantea como una plataforma web de gestión de citas y servicios para profesionales autónomos y pequeñas empresas.
- Aunque nació a partir de un caso real del ámbito terapéutico, no se limita a ese sector.
- El MVP se centra en cubrir el flujo principal de exploración, reserva, pago y gestión básica profesional.

## 2. Estructura de repositorios
- Se mantiene un repositorio público para documentación, entregas y material de apoyo.
- El código fuente y la documentación técnica detallada permanecen en un repositorio privado para proteger la propiedad intelectual del proyecto.

## 3. Stack tecnológico final
- Frontend: HTML5, CSS3 y JavaScript en formato SPA sin framework.
- Backend: Python con FastAPI, SQLAlchemy y Pydantic.
- Base de datos: PostgreSQL.
- Testing: pytest.
- Herramientas de apoyo: Git/GitHub, Postman, Figma y Docker como apoyo opcional.

## 4. Modelo general de arquitectura
- Se adopta una arquitectura separada por capas: frontend SPA, API backend y base de datos PostgreSQL.
- La autenticación se separa de la identidad base de usuario.
- El sistema usa roles para diferenciar perfiles de cliente, profesional y administración.
- El perfil público profesional se separa de los datos privados de facturación.

## 5. Decisiones de modelado relevantes
- La disponibilidad se modela como agenda recurrente y las reservas como tramos ocupados.
- La disponibilidad visible se calcula a partir de agenda menos reservas, en lugar de almacenar huecos libres precalculados.
- Los datos de facturación se mantienen separados del perfil público.
- Las facturas se tratan como registros con trazabilidad, no como documentos libremente editables.
- Los identificadores técnicos se mantienen en inglés en la implementación para conservar coherencia técnica.

## 6. Pagos y facturación
- Stripe se utiliza en modo test en el estado actual del MVP.
- PayPal queda contemplado como integración posterior dentro del alcance ampliado.
- Todo pago confirmado debe desembocar en la generación de su factura correspondiente dentro de la lógica del sistema.
- El justificante visible para el usuario y la factura fiscal no se consideran la misma cosa.

## 7. Alcance del MVP
- Se prioriza el núcleo funcional completo antes que mejoras accesorias.
- Se incluyen autenticación, perfil profesional, servicios, disponibilidad, reservas, pagos, facturas, mensajería y soporte en alcance MVP.
- Se dejan fuera del MVP funcionalidades como reseñas, asistente conversacional, automatizaciones avanzadas, excepciones complejas de agenda, OAuth y panel admin ampliado.

## 8. Decisiones pospuestas para futuras versiones
- Login con Google OAuth.
- Recordatorios automáticos reales por email.
- Inteligencia de agenda y sugerencia automática de huecos.
- Reseñas vinculadas a reservas reales.
- Galería de imágenes por servicio.
- Integraciones de pago adicionales según región.
- Evolución del sistema de facturación hacia capas de cumplimiento más avanzadas.
