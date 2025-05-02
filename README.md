1. Introducción
Este proyecto consiste en un asistente inteligente personalizado para el negocio Katty's Dessert. El agente responde preguntas y ejecuta funciones relacionadas con productos, pedidos, costos, inventario y producción, utilizando LangChain y varias herramientas definidas localmente.
2. Flujo General del Código
-	El asistente se basa en LangChain y sigue estos pasos principales:
-	Se importan las librerías necesarias y se configuran las API Keys (OpenAI y Tavily).
-	Se cargan los datos desde archivos CSV (productos, recetas, pedidos).
-	Se definen herramientas personalizadas (como calcular costos, listar pedidos, etc.).
-	Se crea el agente con un prompt personalizado basado en reglas internas y se enlazan las herramientas.
-	El ejecutor del agente maneja el flujo de conversación y ejecución de herramientas.
3. Herramientas Personalizadas
-	calcular_costos: Calcula el costo de un producto con base en sus ingredientes y sugiere un precio final.
-	 generar_lista_compras: Genera una lista de insumos faltantes para cubrir los pedidos programados.
-	 consultar_productos: Devuelve los productos disponibles, su tiempo de preparación y precio sugerido.
-	 ver_pedidos_programados: Lista los pedidos programados según una fecha opcional proporcionada.
-	 ingredientes_o_descripcion: Obtiene los ingredientes de un producto si está en base de datos, o busca en la web si no.
-	 buscar_web: Herramienta de respaldo para buscar información externa usando Tavily.
-	 youtube_search: Permite buscar videos en YouTube sobre un tema relacionado.
-	 ver_productos_con_stock_bajo: Muestra qué insumos están por debajo del mínimo de inventario.
-	 calcular_produccion_requerida: Calcula la cantidad de cada producto que debe producirse según los pedidos del día.
4. Datos Utilizados
Se utilizan archivos CSV para alimentar el sistema con datos de productos, recetas e historial de pedidos:
-	productos_kattys.csv
-	recetas_katty.csv
-	pedidos_programados.csv
-	reglas_empleados.txt

5. Componentes Técnicos
-	LangChain: Biblioteca base para el desarrollo del agente.
-	LangGraph: Para flujos condicionales con `RunnableBranch`.
-	Herramientas personalizadas: Funciones propias para lógica del negocio.
-	Agente ReAct: Usado para razonar y ejecutar herramientas según necesidad.
-	Memoria: Se usa `ConversationBufferMemory` para mantener contexto.
6.
