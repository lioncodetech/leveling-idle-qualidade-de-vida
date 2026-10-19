# Leveling Idle - qualidade de vida

Extensão de qualidade de vida para `https://levelingidle2d.com.br/`.

Na 0.14.0, a extensão ganhou fila do Codex, missões, chefe diário, Torre Infinita, Forja com
reservas e organização segura do time e dos equipamentos das sombras. A diária continua lembrando
o resgate pelo dia de Brasília para não reabrir a janela até a próxima virada.

## Recursos

- painel resumido com personagem, HP, mana, XP, alvo, mochila, dano da party e ping;
- o painel muda de tamanho pela alça do canto, e a largura e a altura ficam guardadas junto com a
  posição; minimizado ele volta a encolher até o cabeçalho;
- modo minimizado com personagem, HP e alvo;
- modo leve que remove animações e transições;
- opção separada para ocultar o cenário mantendo o HUD e o combate;
- intervalo configurável para a atualização do painel;
- posição, visibilidade e configurações guardadas por conta;
- `Alt+Q` mostra ou esconde o painel.
- `Alt+G` desliga os gráficos (liga o modo leve sem animações e sem cenário) e `Alt+H` liga de novo; o HUD e o combate continuam.
- distribuição automática dos pontos de status: escolha uma das 3 builds da classe que o jogo oferece ou monte a sua com um peso para cada atributo; sempre que houver pontos livres, a extensão abre a janela de Status, distribui, confirma e fecha a janela;
- aba Equipamento: equipar os melhores pelo poder (botão "Equipar melhores" do jogo) ou pelos seus atributos preferidos, com peso e "exigir" para cada atributo das peças, a cada N minutos, uma vez por dia num horário ou uma vez por semana num dia e horário, e opcionalmente ao subir de nível;
- build de talentos: uma lista em ordem de talentos e o nível de cada um; sempre que houver pontos de talento, a extensão abre a árvore, aprende na ordem e fecha a janela, pulando o que ainda estiver bloqueado;
- escada de caçadas por marco de nível, lendo todas as páginas e dificuldades da lista, mantendo a caça atual sem opção segura;
- modo Codex separado por Monstros, Loots, Equipamentos e Aprimoramento, priorizando o próximo marco incompleto;
- aceita missões disponíveis e resgata automaticamente as recompensas concluídas, sem abandonar ou trocar missões;
- as missões aceitam **faixas de horário, quantas você quiser**: em cada faixa a extensão sorteia
  uma hora, uma vez por dia, e é nessa hora que confere. Duas faixas — uma de manhã e outra à
  noite — apanham o que só fica pronto mais tarde, coisa que uma visita única nunca apanharia. O
  painel mostra a hora que saiu hoje em cada faixa. Sem faixa nenhuma, nada muda: continua a
  conferir de 5 em 5 minutos. A faixa é marcada como feita antes de a verificação começar, para
  que uma janela que não abre não vire uma tentativa a cada volta do laço até o fim do dia;
- relê os botões das árvores de talentos após cada troca, incluindo abas posteriores como Ambição;
- agenda o chefe diário por rank e a Torre Infinita por margem de poder, usando o avanço e a
  condição de parada do próprio jogo. O horário de cada um é uma **faixa** de duas caixas (por
  exemplo 10:00 e 12:00): todos os dias a extensão sorteia uma hora dentro dela e é nessa hora que
  entra, e o painel mostra a hora que saiu hoje. O sorteio é feito uma vez por dia e fica guardado —
  sortear a cada segundo cairia sempre no início da faixa. Mexer nas caixas sorteia outra vez na
  hora, e duas caixas iguais valem como hora fixa, que é o que acontecia antes de haver faixa.
  Ao abrir a janela do chefe ela
  pergunta ao **jogo** se o rank de hoje já foi feito — pelo rótulo da aba, e sobretudo por não haver
  mais o botão Enfrentar — e, se já foi, marca o dia e só fecha a janela. A marca local não bastava:
  ela não sabe do chefe que você enfrentou à mão nem do que outra janela já fez, e sem isso a
  extensão reabria a janela a cada minuto até à meia-noite sem nunca conseguir entrar. A janela
  passou a fechar em todos os caminhos, incluindo o do erro. E porque um desafio obriga a sair da
  caçada, a extensão guarda qual era — lê o cartão **live** na lista antes de sair, que é a única
  fonte do nome — e volta a ela no fim, fechando a janela do desafio e a lista. Antes o
  personagem ficava parado na cidade a ganhar nada até a escada reparar nisso, e com a escada
  desligada ficava ali para sempre. Quem **entrou** no desafio não é arrancado de volta: a volta
  só acontece quando não se entrou, e acontece dentro da vez da fila;
- explica no painel que o descanso é offline e mantém reservas pagas do Hotel sob controle manual;
- roda várias abas do Codex em fila, encanta somente peças vestidas até o limite e as reservas escolhidas, e organiza time/equipamentos das sombras sem liberar ou fundir nenhuma;
- compra de poções no NPC da cidade: grava o caminho até ele uma vez e, quando a poção acaba ou a cada N minutos, volta à cidade, refaz o caminho, completa cada item até a quantidade escolhida só com ouro, nas abas Consumíveis e Essências (nunca na de diamantes), e fecha a loja;
- venda de equipamento ao Brok na ida ao NPC ou com a mochila cheia, até a raridade escolhida, nunca materiais nem peças travadas;
- ao chegar ao NPC a extensão fala com ele pela **tecla E**, como o jogador faz, em vez de clicar:
  o jogo manda `interact` sem coordenada e quem atende é a proximidade, então não há ponto para
  errar — e um clique perdido no cenário mexeria o personagem para longe. O clique em volta do NPC
  continua lá, mas só como último recurso;
- o caminho até o NPC é repetido com o **compasso variado**: as pausas entre as pernas mudam muito
  de uma ida para a outra, e o tempo de tecla premida quase nada (±3%), porque tecla premida é
  distância. O caminho guardado continua sendo o que você andou;
- e se mesmo assim a loja não abrir, ela **chega mais perto sozinha**: anda mais um bocadinho nos
  dois sentidos que o caminho mais andou e aperta E de novo, até três vezes. O erro de chegada tem
  sinal — um caminho chega sempre curto, nunca longo, porque cada perna recomeça a aceleração —
  então o conserto é continuar, e não procurar em volta;
- e se nada disso abrir a loja, ela **recarrega a página e tenta mais uma vez** — no máximo duas
  vezes por hora. O teto existe porque o defeito que isto conserta e o defeito que isto pode causar
  são o mesmo: com o NPC movido ou o jogo em manutenção, recarregar sem limite vira um laço que
  recarrega para sempre e nunca diz o que está errado. O pedido fica guardado no navegador, porque
  nada em memória sobrevive a um recarregamento, e é apagado antes da segunda tentativa começar; um
  pedido com mais de cinco minutos é ignorado, para que um F5 seu no dia seguinte não mande a
  extensão sair a comprar sozinha. A segunda tentativa espera o jogo ficar de pé e respeita a pausa
  geral. Dá para desligar na aba Suprimentos;
- poções por percentual, mochila/depósito e preparação de venda;
- reviver sozinho ao cair na caçada: escolha o Reviver mais barato que houver, o melhor, ou um
  fixo, com teto de quantos por hora. Reviver **gasta um item da mochila** — por isso a opção
  começa desligada, nunca troca de item por conta própria quando o escolhido acaba e, alcançado o
  teto, deixa a contagem de 10 segundos correr e o jogo levar você para Seul, que é o que já
  acontecia. O XP perdido na queda é da morte e nenhum Reviver desfaz;
- **resgata a recompensa diária de login sozinha**: quando o jogo acende o aviso, ela abre a
  janela, carrega em Resgatar e confere que resgatou mesmo antes de dar por feito. Quem manda é o
  sinal do jogo, não a marca guardada aqui — se a marca se enganar (relógio mexido, conta aberta
  noutra máquina, dia que virou com o jogo fechado), ela resgata na mesma. Não depende do
  interruptor das Rotinas: receber o que o jogo oferece de graça não é uma ação de risco;
- **fila: uma automação de cada vez.** Antes, cada automação só olhava a própria bandeira, e por
  isso o chefe diário podia começar no meio da ida ao NPC — duas a clicar na mesma tela, cada uma a
  fechar a janela da outra. Agora quem chega e encontra alguém a trabalhar **espera a vez**, por
  ordem de chegada, e o painel diz quem a tem e quem está na fila. Quem espera demais (cinco
  minutos) desiste por agora em vez de ficar preso, e uma vez que passe dos dez minutos é dada por
  abandonada, para que um erro fora do alcance do `finally` não tranque tudo para sempre. A
  **caçada não tem prioridade**: ela não toma a vez de ninguém e não se mexe enquanto houver alguém
  a trabalhar ou à espera — trocar de caçada um minuto depois dá no mesmo, mas abrir a lista de
  caçadas por cima da loja fecha a janela de quem está a comprar. No manual, quem manda é você;
- monitor da party, diária, eventos, guerra de time e fadiga;
- pausa geral, registro das ações e bloqueio de botões premium;
- exportação e importação das configurações em arquivo, para levar a outra janela; entre classes diferentes, a build de status e os pesos do equipamento não vêm.

O pacote não troca personagem. A confirmação da venda permanece manual para impedir perda acidental. Automações que alteram o jogo começam desligadas.
