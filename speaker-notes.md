# ReNest: notas para hablar (~5 min)

Guía para cada una de las 13 diapositivas de [presentation/index.html](presentation/index.html). No es para leer textual: son las ideas a mencionar con tus palabras. Entre corchetes está lo que aparece en pantalla, para que lo señales sin repetirlo.

**Tiempo total objetivo:** ~5:00. Si vas largo, recortá la 7 o la 12 (ver el final).

---

## 1. Portada (0:00, sin tiempo propio)
[Is it really as shown?]

- No te detengas acá: presentate en una línea y pasá directo a la 2.
- Frase de arranque posible: "Esta semana trabajé en una pregunta simple: ¿el producto llega como se ve en la foto?"

## 2. El problema (0:00 – 0:30)
[A trust problem · polaroids listing ≠ pickup day · cita de Sonia · Doubt → No message → Other platform]

- El comprador no puede saber si la condición real del ítem coincide con las fotos y la descripción.
- Remarcar: **no es un problema de fotos bonitas, es de confianza**. Y frena la conversión antes de que empiece la conversación.
- Señalar la cadena: dudo → no le escribo al vendedor → me voy a otra plataforma.
- Dejá que la cita de Sonia hable sola. Leela o parafraseala una vez.

> Transición: "¿Quién es Sonia y cómo sabríamos que lo resolvimos?"

## 3. Quién y qué es el éxito (0:30 – 1:10)
[Sonia, 30 · North Star: Clean purchases per week]

- Sonia en una línea: presupuesto ajustado, amueblando su depto nuevo, busca desde el celular de noche, quiere un sofá a menos de 20 minutos.
- Ya le pasó llegar a buscar algo y encontrarlo más gastado que en las fotos: viaje perdido y menos confianza.
- El JTBD en una frase: saber la condición real **antes** de escribirle al vendedor.
- North Star: **compras semanales completadas sin disputa ni devolución por condición**.
- Por qué esta métrica: mide comportamiento real (✓ real behavior), no depende de un paso opcional como dejar una review (✗ optional reviews). Así no subestima los casos donde la confianza sí se resolvió.

## 4. El MVP y el porqué (1:10 – 2:00)
[3 in. 4 out. · tres etiquetas · Out for now · sello "Same call"]

- Las tres que entran, cada una con su porqué en una frase:
  - **Condition badge:** ataca directo el gap de confianza y es lo más barato de construir (RICE #1).
  - **3+ real photos:** obliga a mostrar evidencia de la condición, con un costo igual de bajo (RICE #2).
  - **Mismatch report:** no previene nada por sí solo. Es **el instrumento de medición**: sin él no hay forma de saber si el North Star se mueve.
- Lo que queda afuera (una línea): tiempo de respuesta, preguntar al vendedor, fotos en alta resolución y vendedor verificado. Dependen de datos o historial que todavía no existen, o resuelven un paso posterior del journey.
- Señalar el sello: no fue una corazonada. RICE, MoSCoW y el chequeo contra el North Star llegaron a la misma decisión.

> Transición: "Así se ve en la app."

## 5. Mockup comprador (2:00 – 2:25)
[What Sonia sees · before / after del listing]

- Antes: una sola foto borrosa, sin señal de condición, texto vago ("Sofa, good").
- Después: 4 fotos reales con ángulos, badge "Visible wear" junto al precio y una línea que explica qué significa.
- Idea clave: **Sonia sabe lo que va a encontrar antes de escribir**.

## 6. Mockup vendedor (2:25 – 2:50)
[What sellers must do · before / after del flujo de publicación]

- Antes: se podía publicar con 1 foto y sin decir nada de la condición.
- Después: mínimo 3 fotos y condición obligatoria, con un ejemplo de qué significa cada estado. Hasta completarlo, no se puede publicar.
- Mencionar que los ejemplos por estado ya son la mitigación del riesgo de la diapositiva 9 (el vendedor optimista).

## 7. Mockup reporte (2:50 – 3:15) *(recortable)*
[How we know it works · 3 pasos → North Star ≤24h]

- Solo desde una orden completada, dentro de una ventana de tiempo.
- Motivo obligatorio y pocos taps, para que la gente lo use de verdad.
- Cada reporte impacta el North Star en menos de 24h, sin que nadie tenga que sacar los datos a mano.
- Frase clave: "Este es el termómetro del MVP".

## 8. Qué significa "done" (3:15 – 3:45)
[What "done" means · Given/When/Then · Testable by QA]

- Mostrar dos criterios del feature #1 (condition badge), no los siete:
  - **Unhappy path:** si el vendedor toca Publish sin elegir estado, se bloquea y el campo queda marcado.
  - **Happy path:** si hay estado elegido, el comprador ve exactamente ese badge en la tarjeta y en el detalle.
- Remarcar: son criterios que QA puede testear, no "se ve bien".
- Si sobra un segundo: también hay un criterio de accesibilidad (contraste WCAG AA, que no dependa solo del color).

## 9. Riesgos y mitigaciones (3:45 – 4:10)
[Every risk, an answer · 3 filas riesgo → mitigación]

- Decir cada riesgo junto con su respuesta, nunca uno suelto:
  - Vendedores eligen un estado optimista → ejemplo junto a cada opción.
  - El badge se pierde entre otras etiquetas → revisión de diseño antes de construir.
  - Los compradores igual no confían → monitorear el North Star las primeras dos semanas. Si no se mueve, lo que estaba mal era la hipótesis de causa raíz, no el badge.

## 10. Recomendación: GO (4:10 – 4:35)
[GO · Ship when · Roll back if · Watch]

- **Decí la decisión primero:** "Mi recomendación es GO." Después, el respaldo.
- Ship when: pasan los criterios de aceptación y al menos un vendedor real revisó las descripciones de estado.
- Roll back if: el North Star cae por debajo del baseline en las dos semanas post-lanzamiento.
- Watch: North Star + % de compradores que le escriben al vendedor (señal temprana).
- Por qué GO: el riesgo de mayor impacto está cubierto por el monitoreo temprano, y los otros dos por trabajo de contenido y diseño ya planeado. Sin matices acá.

## 11. Qué sigue (4:35 – 4:50)
[Now / Next / Later · sello "Strongest next"]

- Now: las tres del MVP. Next: tiempo de respuesta del vendedor y preguntar al vendedor. Later: fotos en alta resolución y vendedor verificado.
- Cerrar con el porqué del próximo paso: el indicador de tiempo de respuesta es el candidato más fuerte porque tres marcos coinciden (Should en MoSCoW, Big bet en valor vs. esfuerzo y apoyo al North Star).

## 12. La pregunta difícil (4:50 – 5:05) *(recortable)*
[Why 2 weeks on a report? · No report = no proof]

- Plantear la pregunta tal cual: ¿por qué gastar 2 semanas-persona en un reporte en vez de un cuarto feature de confianza que el comprador vea?
- Respuesta en una línea: sin el reporte no hay forma de medir si el badge y las fotos funcionan. **Lanzar sin forma de verificar no es un lanzamiento, es una apuesta.**

## 13. Gracias (5:05, sin tiempo propio)
[Thank you. · sellos "As shown" y "Sold"]

- Solo "Gracias". Dejala un par de segundos en pantalla antes de cortar el video.
- Si querés un remate: cierra el círculo con la portada. La pregunta era "¿es como se ve?", y el objetivo es que cada venta termine **as shown**.

---

## Si vas largo
- **Sacar la 7:** mencioná el reporte en una frase en la 4 ("es el termómetro") y ganás ~25 s.
- **Sacar la 12:** meté la respuesta a la pregunta difícil dentro de la 4, cuando justifiques el reporte.
- Las 5 y 6 se pueden decir en 15 s cada una: señalá el antes, señalá el después y seguí.

## Chequeo antes de grabar
- [ ] Cuenta una historia (problema → MVP → readiness → recomendación), no un catálogo.
- [ ] Los criterios mostrados son Given/When/Then y testeables.
- [ ] Cada riesgo se dice con su mitigación.
- [ ] El GO se dice primero, con ship criteria y rollback trigger explícitos.
- [ ] ~5 minutos, no 10.
- [ ] La pregunta difícil queda respondida dentro del video.
