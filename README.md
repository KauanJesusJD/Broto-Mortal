# Broto Mortal
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ola ola denovo, este repositorio e sobre um teste do nosso primeiro jogo no meu curso. Ele foi feito pra testar a movimentacao (com script), fisica, textura e os game objects. A seguir darei a explicacao  de como fiz este trabalho. E no final deste Readme, terá o link para o jogo. Vale ressaltar que estamos fazendo esses testes no Unity, entao o jogo esta dentro do Unity.<br>
## Representação do jogo <br>
![image](https://github.com/KauanJesusJD/Broto-Mortal/assets/127852225/b90e578e-1a9b-41eb-a944-0445d2e3e3e0)<br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A nossa primeira ideia do jogo era fazer uma torre onde o jogador teria que escala-lá. Mas, percebemos que seria muito complicado fazer isso de inicio. Entao resolvemos fazer algo mais tranquilo, entao meu parceiro teve a ideia desse jogo. Seria muito mais simples no codigo e teria inicio ao fim. Depois de feito a ideia principal, ele foi remasterizado e testado varias vezes, ate chegar no jogo atual.<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Broto Mortal e um jogo bem simples, seu objetivo e chegar no final do percurso é nao bater em nenhuma parede e obstaculo.
## Personagem e a movimentacao.
![image](https://github.com/KauanJesusJD/Broto-Mortal/assets/127852225/51b1b4b9-13e9-45c7-a164-281446e4fc68)
 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;O modelo do personagem foi feito no Blender, salvo como um arquivo .fbx e depois mandamos ele pro Unity. Para a movimentacao, o "Brotinho" (Nome do personagem) seria um broto que voa. Entao a movimentacao foi baseada nas setas do teclado (Cada uma seguindo sua respectiva direcao quando apertada). Dentro do Unity, nos criamos um "new script" dentro do Brotinho e fomos no "Void Update" e inserimos os comandos de movimentacao para cada seta (Nos seus respectivos eixos). A movimentacao para a frente seria automatica, entao tu avanca no percurso sem precisar apertar nada.

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
### 1. Paredes
 
