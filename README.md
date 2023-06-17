# Broto Mortal
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ola ola denovo, este repositorio e sobre um teste do nosso primeiro jogo no meu curso. Ele foi feito pra testar a movimentacao (com script), fisica, textura e os game objects. A seguir darei a explicacao  de como fiz este trabalho. E no final deste Readme, terá o link para o jogo. Vale ressaltar que estamos fazendo esses testes no Unity, entao o jogo esta dentro do Unity.<br>
## Representação do jogo <br>
![image](https://github.com/KauanJesusJD/Broto-Mortal/assets/127852225/b90e578e-1a9b-41eb-a944-0445d2e3e3e0)<br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A nossa primeira ideia do jogo era fazer uma torre onde o jogador teria que escala-lá. Mas, percebemos que seria muito complicado fazer isso de inicio. Entao resolvemos fazer algo mais tranquilo, entao meu parceiro teve a ideia desse jogo. Seria muito mais simples no codigo e teria inicio ao fim. Depois de feito a ideia principal, ele foi remasterizado e testado varias vezes, ate chegar no jogo atual.<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Broto Mortal e um jogo bem simples, seu objetivo e chegar no final do percurso é nao bater em nenhuma parede e obstaculo.<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Como não sabemos fazer uma "morte", considere que quando o personagem bater em algum obstaculo e começar mudar a direção. Voçe deve reiniciar o percurso.
## Personagem e a movimentação
![image](https://github.com/KauanJesusJD/Broto-Mortal/assets/127852225/51b1b4b9-13e9-45c7-a164-281446e4fc68)
 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;O modelo do personagem foi feito no Blender, salvo como um arquivo .fbx e depois mandamos ele pro Unity. Para a movimentacao, o "Brotinho" (Nome do personagem) seria um broto que voa. Entao a movimentacao foi baseada nas setas do teclado (Cada uma seguindo sua respectiva direcao quando apertada). Dentro do Unity, nos criamos um "new script" dentro do Brotinho e fomos no "Void Update" e inserimos os comandos de movimentacao para cada seta (Nos seus respectivos eixos). A movimentacao para a frente seria automatica, entao tu avanca no percurso sem precisar apertar nada.<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Vale notar que colocamos um "New componente" no personagem, um RigidBody. Para que o objeto fosse algo fisico e pudesse atingir os obstaculos. Tambem linkamos a camera com o personagem para que ela acompanhasse ele durante o percurso.

    void Update()
    {
	{ transform.Translate(0f, 0.1f, 0f); } //Movimentação automatica pra frente
        if (Input.GetKey(KeyCode.UpArrow)){ transform.Translate(0f, 0f, 0.3f); }//Movimentação para cima (Seta pra cima)
        if (Input.GetKey(KeyCode.DownArrow)) { transform.Translate(0f, 0f, -0.3f); }//Movimentação para baixo (Seta pra baixo)
        if (Input.GetKey(KeyCode.LeftArrow)) { transform.Translate(0.3f, 0f, 0f); }//Movimentação para esquerda (Seta pra esquerda)
        if (Input.GetKey(KeyCode.RightArrow)) { transform.Translate(-0.3f, 0f, 0f); }//Movimentação para direita (Seta pra direita)
        if (Input.GetKey(KeyCode.Space)) { transform.Translate(0f, 0f, 0.3f); }//traslação

        // O Input.GetKey diz que quando a tecla for apertada, algo vai acontecer.
		// KeyCode."nome_da_tecla" serve pra botar qual teclar o GetKey vai pegar.
        
    }
 
> 💡 **Dificuldade:** Eu basei a velocidade automatica pra frente (O codígo principal que define a velocidade) de acordo com a minha experiencia de jogo. Mas, dependendo de como tu for, se achar difícil ou muito facil. Tu pode alterar isso, so e necessarío:
> 1. Ir na pasta do Jogo
> 2. Abrir as pastas do Assets
> 3. Abrir o arquivo "movimentação.cs"
> 4. Editar o numéro do meio da movimentação automatica pra frente (Aumenta-lo vai deixar mais rapido e diminui-lo mais lento)
 
 ## Obstaculos
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Obviamente o percurso ate o final e cheio de obstaculos. Entre eles temos:
- ### Paredes <br>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Nesse jogo temos dois tipos de paredes: As do lado de fora que limitam a àrea do percurso e as paredes do lado de dentro que servem como obstaculos normais.
 
![Parede fora (B M)](https://github.com/KauanJesusJD/Broto-Mortal/assets/127852225/b09a4137-501c-4802-b8c4-0c4a58b5a0a3)<br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Esta parede tambem conta como obstaculo. Ou seja, voce nao pode enconstar nelas. Ela foi feita com o GameObject "plane" e um material de grama que baixamos pela internet. Utilizamos especificamente um plane porque podiamos ver o lado de dentro do percurso do lado de fora è do lado de dentro do percurso nao fosse possivel ver o lado de fora, isso ajudava bastante no desenvolvimento do percurso.

![Parede Dentro (B M)](https://github.com/KauanJesusJD/Broto-Mortal/assets/127852225/ecdad4de-6300-47e3-94d5-097e4b7a5fba)<br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Este e um dos obstaculos principais. Foi feito com um GameObject Cubo, usando uma textura de tijolo que baixamos da internet.
- ### Pilar

![Pilar (B M)](https://github.com/KauanJesusJD/Broto-Mortal/assets/127852225/61e320b7-a48c-4e47-8f18-17bd0b3dd78a)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Outro dos obstaculos principais. Foi feito com o GameObject Cilindro e um material de concreto pego da internet. Estes obstaculos tem varias variaçoes comforme o percurso passa.<br>
- ### Bola 8

![Bola 8 (B M )](https://github.com/KauanJesusJD/Broto-Mortal/assets/127852225/0ba33c84-73e6-49e1-b20f-55fe678de45c)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Este foi feito com um GameObject Esfera e um material de Bola 8 pego na internet.<br>
- ### Espetos 

![Espetos (B M )](https://github.com/KauanJesusJD/Broto-Mortal/assets/127852225/cbc6a9f3-3eeb-46c7-b7c3-d4505aca829e)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Um dos obstaculos mais difícies. Foi feito com o GameObject Capsula é este nao tem material. Ele e como uma fusao do muro com os pilares, so que mais dificil no geral.<br>
> ⚠️ **Detalhe importante:** Voçe precisa prestar atencao no Collider de cada objeto. Pois, no meio do nosso desenvolvimento do jogo. Tivemos alguns problemas com o Brotinho os atravessando, entao, sempre verifique e modifique o collider de um objeto se precisar.


