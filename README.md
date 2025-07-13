# examen-2025


| Código | Error | Remediación |
|--|--|--|
| `regmatch_t regmatch[10]; rc = ap_regexec(..., p->regexp->re_nsub + 1, regmatch, 0);` |Parámetro nmatch puede exceder tamaño del array → desbordamiento de búfer.  | Usar constante común (ej. MAX_MATCHES) para declarar el tamaño del array y el valor de nmatch. |
|  if (args[i].startsWith("--delimiter=")) { delimiter = args[i].substring(12); }| Valor de 'delimiter' controlado por el usuario sin validación → riesgo de inyección SQL. | Validar contra lista blanca de delimitadores válidos (;, |, etc.). |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |


```cpp
regmatch_t regmatch[10];
rc = ap_regexec(..., p->regexp->re_nsub + 1, regmatch, 0);
