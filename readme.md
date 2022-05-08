# 6 API REST Trello

1. Se abre una cuenta de Trello en https://trello.com/

  ![image](https://github.com/JorgeLMarquez/Explanations/blob/main/API%20REST%20Trello/img0.png) 
  
  ![image](https://github.com/JorgeLMarquez/Explanations/blob/main/API%20REST%20Trello/img1.png)
  
  ![image](https://github.com/JorgeLMarquez/Explanations/blob/main/API%20REST%20Trello/img2.png)
  
  ![image](https://github.com/JorgeLMarquez/Explanations/blob/main/API%20REST%20Trello/img3.png)
  
2. Se necesita una API Rest de Trello la cual contiene un api key y un token que puedes solicitar aquí: https://trello.com/app-key
  - Ve al portal

![image](https://github.com/JorgeLMarquez/Explanations/blob/main/API%20REST%20Trello/img4.png)

  - El primer valor que te mostrará es tu API KEY, guárdalo muy bien.
    
![image](https://github.com/JorgeLMarquez/Explanations/blob/main/API%20REST%20Trello/img5.png)
    
  - Da click en el enlace a TOKEN 
  
  - Te pedirá autorizar tu petición:
  - 
 ![image](https://github.com/JorgeLMarquez/Explanations/blob/main/API%20REST%20Trello/img6.png)
  
  - Enseguida te mostrará el TOKEN:

 ![image](https://github.com/JorgeLMarquez/Explanations/blob/main/API%20REST%20Trello/img7.png)

3. Guarda muy bien tu API KEY y TOKEN (estos valores son como tu usuario y password, ES INFORMACIÓN SENSIBLE).

4. Visita la documentación del Api Rest de Trello https://developer.atlassian.com/cloud/trello/rest/api-group-boards/#api-group-boards
   - Busca cómo crear un nuevo board.
   
 ![image](https://github.com/JorgeLMarquez/Explanations/blob/main/API%20REST%20Trello/img8.png)

   - Busca cómo obtener la información de un board a partir de su ID
![image](https://github.com/JorgeLMarquez/Explanations/blob/main/API%20REST%20Trello/img9.png)
   - Busca cómo obtener la lista de cards de un board
![image](https://github.com/JorgeLMarquez/Explanations/blob/main/API%20REST%20Trello/img10.png)
   - Busca cómo crear una nueva card en un board
![image](https://github.com/JorgeLMarquez/Explanations/blob/main/API%20REST%20Trello/img11.png)

5. Descarga el siguiente archivo de postman e importalo en tu postman: [ ACTUALIZADO Trello API LaunchX.postman_collection.json.zip](https://github.com/LaunchX-InnovaccionVirtual/MissionNodeJS/files/8585319/Trello.API.LaunchX.postman_collection.json.zip)


# Juega con el Api de Trello con las peticiones armadas de postman: Crea un tablero.

6. Ahora sí ve a la siguiente petición para crear un board `POST Create board`:

7. En la sección de `params`, llena los valores (aquí incluye tu api key en el campo `key` y el token en `Token`):

![image](https://github.com/JorgeLMarquez/Explanations/blob/main/API%20REST%20Trello/img12.png)

8. Da click en SEND, mira el response y verifica que tu tablero nuevo se halla creado.

![image](https://github.com/JorgeLMarquez/Explanations/blob/main/API%20REST%20Trello/img13.png)

9. Del response, hay un campo `id` que corresponde al ID del tablero que acabas de crear, guárdalo.


# Obtén la lista de columnas de tu board creado

10. Abre el siguiente request: 

11. Agrega tu API KEY y TOKEN. 
12. Modifica la url, justo después de `/1/boards/` quita el valor que esta ahí y pon el ID de tu board creado anteriormente.

```
https://api.trello.com/1/boards/BOARDID/lists?key=APIKEY&token=TOKEN
```
13. Envía tu request, y verifica la información que recibes. Deberás ver la lista de columnas que tienes en tu tablero:

14. Toma el ID del primer registro que corresponde a la primer columna.

![image](https://github.com/JorgeLMarquez/Explanations/blob/main/API%20REST%20Trello/img15.png)

# Agrega nuevas cards a la primer columna de tu tablero

15. Abre el request POST `Create Card By List Id`:
16. 
17. Agrega los parámetros necesarios: `idList`(el id de la primer columna del paso anterior), `key`, `token`, y `name` (este es el título de tu card nueva).

17. Envía tu request y verifica que la respuesta sea éxitosa. Verifica que efectivamente se haya creado directo en la app de trello.

![image](https://github.com/JorgeLMarquez/Explanations/blob/main/API%20REST%20Trello/img16.png)
