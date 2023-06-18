# Broto Mortal
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Olá, olá de novo, este repositório é sobre um teste do nosso primeiro jogo no meu curso. Ele foi feito para testar a movimentação (com script), física, textura e os game objects. A seguir, darei a explicação de como fiz este trabalho. E no final deste Readme, terá o link para o jogo. Vale ressaltar que estamos fazendo esses testes no Unity, então o jogo está dentro do Unity.
## Representação do jogo e seu conceito <br>
![Percurso (B M )](https://github.com/KauanJesusJD/Broto-Mortal/assets/127852225/94f85663-2151-4246-a4f8-8e2c9473ea1d)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A nossa primeira ideia do jogo era fazer uma torre onde o jogador teria que escalá-la. Mas, percebemos que seria muito complicado fazer isso de início. Então resolvemos fazer algo mais tranquilo, então meu parceiro teve a ideia desse jogo. Seria muito mais simples no código e teria início ao fim. Depois de feita a ideia principal, ele foi remasterizado e testado várias vezes, até chegar no jogo atual.<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Broto Mortal é um jogo bem simples, cujo objetivo é chegar ao final do percurso sem bater em nenhuma parede ou obstáculo.<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Como não sabemos fazer uma "morte", considere que quando o personagem bater em algum obstáculo e começar mudar a direção. Voçe deve reiniciar o percurso.
## Personagem e a movimentação
![Brotinho (B M )](https://github.com/KauanJesusJD/Broto-Mortal/assets/127852225/2a76ebe1-a811-4bfd-abbc-3e4d5e7fd961)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;O modelo do personagem foi criado no Blender e salvo como um arquivo .fbx, em seguida, foi importado para o Unity. Para a movimentação, o personagem chamado "Brotinho" foi concebido como um broto voador. A movimentação foi baseada nas teclas de seta do teclado, em que cada seta corresponde a uma direção específica quando pressionada. No Unity, foi criado um novo script dentro do objeto Brotinho, e dentro da função "Void Update", foram adicionados comandos de movimentação para cada tecla de seta, de acordo com seus respectivos eixos. A movimentação para frente é automática, ou seja, o personagem avança no percurso sem a necessidade de pressionar qualquer tecla.
<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Vale ressaltar que adicionamos um novo componente ao personagem, um RigidBody, para torná-lo um objeto físico capaz de interagir com os obstáculos. Além disso, vinculamos a câmera ao personagem para que ela o acompanhasse durante o percurso. Isso proporciona uma experiência mais imersiva ao jogador, permitindo que ele tenha uma visão contínua do personagem à medida que se move pelo ambiente do jogo.

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
 
> 💡 **Dificuldade:** Eu baseei a velocidade automática para frente (o código principal que define a velocidade) de acordo com a minha experiência de jogo. No entanto, dependendo de como você se sentir, se achar difícil ou muito fácil, você pode alterá-lo facilmente. Siga estas etapas:
>
> 1. Navegue até a pasta do jogo.
> 2. Abra as pastas de Assets.
> 3. Localize o arquivo "movimentação.cs".
> 4. Edite o número do meio da movimentação automática para frente. Aumentá-lo tornará mais rápido, enquanto diminuí-lo o deixará  mais lento.
>
> Essa é uma maneira simples de ajustar a velocidade do personagem de acordo com suas preferências e desafios desejados. Experimente diferentes valores até encontrar o equilíbrio que melhor se adapte à sua jogabilidade.
 
 ## Obstáculos
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Obviamente o percurso ate o final e cheio de obstáculos. Entre eles temos:
- ### Paredes <br>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Nesse jogo temos dois tipos de paredes: As do lado de fora que limitam a àrea do percurso e as paredes do lado de dentro que servem como obstáculos normais.
 
![Parede fora (B M)](https://github.com/KauanJesusJD/Broto-Mortal/assets/127852225/8b2a4a7e-554c-447f-bfe0-6bcf6ae707d1)<br>


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Esta parede também conta como obstáculo, ou seja, você não pode encostar nela. Ela foi feita utilizando o GameObject "plane" e um material de grama que baixamos da internet. Optamos por usar especificamente um plano (plane) porque dessa forma podíamos visualizar tanto o lado de dentro do percurso quanto o lado de fora. Essa abordagem foi bastante útil durante o desenvolvimento, pois nos permitiu ter uma visão clara do percurso e ajustar sua construção de maneira adequada.

![Parede Dentro (B M)](https://github.com/KauanJesusJD/Broto-Mortal/assets/127852225/1d0d7e4a-bb5f-415b-8afc-9e628b679ba7)<br>


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Este é um dos obstáculos principais do jogo. Foi criado utilizando um GameObject cubo e aplicando uma textura de tijolo que obtivemos da internet.
- ### Pilar

![Pilar (B M)](https://github.com/KauanJesusJD/Broto-Mortal/assets/127852225/0a175863-156c-46a3-b25c-f5c9c42bb7fe)<br>


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Outro dos obstáculos principais é criado utilizando um GameObject cilindro e aplicando um material de concreto obtido da internet. Esses obstáculos têm várias variações ao longo do percurso, adicionando diversidade e desafios diferentes para o jogador.<br>
- ### Bola 8

![Bola 8 (B M )](https://github.com/KauanJesusJD/Broto-Mortal/assets/127852225/43d29cfc-4645-4ad3-96f1-7e1eee848034)<br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Este obstáculo em particular foi criado utilizando um GameObject esfera e aplicando um material de bola 8 obtido na internet. A escolha desse objeto e textura específica adiciona um elemento temático ao jogo, oferecendo uma variante divertida e visualmente interessante.<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;É importante notar que cada obstáculo tem suas características e exige uma abordagem específica para ser evitado. Portanto, preste atenção a esse obstáculo em particular e tome cuidado para não colidir com ele durante o jogo.
- ### Espetos 

![Espetos (B M )](https://github.com/KauanJesusJD/Broto-Mortal/assets/127852225/adc33b8e-2ceb-4144-8420-6f49827644b6)<br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Esse obstáculo em particular foi criado utilizando um GameObject cápsula e não possui nenhum material específico associado a ele. A cápsula é uma forma geométrica que se assemelha a uma fusão entre o muro e os pilares, tornando-o um obstáculo especialmente desafiador no jogo.

> ⚠️ **Detalhe importante:** É importante destacar que durante o desenvolvimento do jogo, enfrentamos problemas em relação ao personagem (Brotinho) atravessar alguns objetos. Por isso, é crucial prestar atenção aos colliders de cada objeto. O collider define a área de interação e colisão de um objeto, garantindo que o personagem não passe através dele.
>
>Portanto, certifique-se de verificar e ajustar o collider de um objeto, se necessário, para evitar problemas de colisão e assegurar que o jogador tenha uma experiência de jogo adequada e desafiadora.

## Final do Percurso<br>
![Final (B M )](https://github.com/KauanJesusJD/Broto-Mortal/assets/127852225/ee7821fe-ca73-4aad-ad6e-ec440c993604)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Após termos desenvolvido boa parte do percurso, decidimos criar um final satisfatório para o jogo. Para isso, adicionamos uma tela de fundo com a mensagem "Congratulations". Essa tela foi criada utilizando um plano como base e aplicando um material que encontramos na internet. Além disso, adicionamos flores ao redor da tela para dar um toque decorativo. As flores foram obtidas através de assets prontos disponíveis na Unity Store, uma plataforma onde é possível adquirir recursos para uso em jogos.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Essa adição do final com a mensagem de parabéns e as flores proporciona uma sensação de conclusão e recompensa ao jogador que conseguir completar o percurso com sucesso. Digo isso porque esse e um jogo bem difícil de passar.<br>
![Flor estranha (B M )](https://github.com/KauanJesusJD/Broto-Mortal/assets/127852225/b43b2ae1-566f-45b3-b5ec-46c9d40535df)<br>
Link do Asset:https://assetstore.unity.com/packages/3d/vegetation/strange-flower-and-bramble-4441

## Musíca
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Para evitar que o percurso fique em um clima estranho ou silencioso, decidimos adicionar um elemento sonoro. Para isso, inserimos um Game Object de Audio Source e utilizamos a música do filme "Jogos Mortais" como trilha sonora. Essa escolha foi feita para adicionar uma atmosfera de suspense e tensão ao jogo, criando uma experiência mais imersiva para o jogador.

# 🪴 Link do Jogo (Dentro do Drive e compactado)
https://drive.google.com/file/d/1GUtXHefBqaVWO_AAW_kThmrmyfG_ejlQ/view?usp=sharing




