# Este robot es una reimplementacion del robot usando core.async

La implementación original usa un ```agent``` la idea es que el *thread* del agente es el *thread* de la maquina de estados representada por el agente, y cada operacion es una función quees enviada a ser procesada por el agente, el unico parametro que recive la operación es el estado del agente "un mapa", el resultado de la función es metido dentro del mapa y se determina el siguiente estado evaluando el valor *string* de la operacion en forma sequencial en las posibles "salidas" de este estado, la última salida siendo obligada, al determinarse la salida y por lo tanto el siguiente estado se envia al agente la siguiente operacion en la máquina de estados.

La implementacion de esta nueva versión, será usando un atomo que será enviado por una red de ```core.async.chan```, la estructura completa de estos channels será almacenada dentro de un record, la idea inicia asi:

