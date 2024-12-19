Minimo 2 DSA

En la rama main esta el proyecto de android, y en la mara servidor esta el servdiro. 
Yo tenia que realizar el Ejercicio 5, el de la denuncia. 
Tienes el Botoón de "Denuncia" en el menú, para que no tengas que logearte, y no te haga falta la base de datos. 
El cliente escribe la denuncia y en el servidor muestra en consola el resultado, el tema esta en que no lo he hecho como me gustaria. 

Se hace un post envando toda la información por la URL:(
Es la única solución in extremis que he encontrado, tengo la clase Denuncia creada (an ambos lados) para que se envie un @Body desed Android, pero al enviar la denuncia me saltaba el error 415 constantemente. 
He revisado que el cliente mandará en JSON : 
@Headers("Content-Type: application/json")
    @POST("/dsaApp/users/denuncia")
    Call<String> enviarDenuncia(@Body Denuncia denuncia); 

He revisado que el retrodit estuviera bien configurado: 
Retrofit retrofit = new Retrofit.Builder()
                .baseUrl("http://10.0.2.2:8080/dsaApp/")
                .addConverterFactory(GsonConverterFactory.create())
                .build();

 apiService = retrofit.create(ApiService.class);

 En el servidor he rvisado que acepte formato Json: 
  @Consumes(MediaType.APPLICATION_JSON)
    @Produces(MediaType.APPLICATION_JSON)

Pero no he encontrado la solución para ello, asi que de manera horrenada, se envia la información en un Post:(.
En conclusión, en el servidor salen en consola las denucnias, pero el proceso para ello no esta como me gustaria que estuviese. 
Gracias
