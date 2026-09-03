# Buzón de sugerencias

Una página pública donde cualquiera del área deja una propuesta y vota las que
ya están. Se abre desde el celular, sin cuenta ni contraseña.

## De dónde salen los datos

Nada está escrito a mano: todo sale de dos tablas del proyecto `curso-claude`
en Supabase.

- `propuestas` — `id`, `creado_en`, `nombre`, `persona`, `justificacion`
- `votos` — `id`, `creado_en`, `propuesta_id`, `votante`

`votante` es un número al azar guardado en el navegador: evita votar dos veces
la misma propuesta, no identifica a nadie. La llave `sb_publishable_` de
`index.html` es pública a propósito; la `sb_secret_` nunca va aquí.

## Qué es `CLAUDE.md`

Las instrucciones que Claude lee solo al abrir esta carpeta: qué es el proyecto,
de dónde sale cada cifra, cómo trabajar aquí (en rama, nunca sobre `main`) y qué
nunca hacer. Si cambia la forma de trabajar, se cambia ahí.

## Cómo se continúa

GitHub guarda el proyecto, Netlify lo publica, Supabase guarda los datos. Abre
una sesión de Claude sobre este repositorio y pide el cambio en una rama:
Netlify hace una vista previa para revisar, y solo fusionar publica. Si la
página deja de mostrar datos, casi siempre Supabase se pausó: **Resume project**.
