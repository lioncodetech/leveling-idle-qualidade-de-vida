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
- relê os botões das árvores de talentos após cada troca, incluindo abas posteriores como Ambição;
- agenda o chefe diário por rank e a Torre Infinita por margem de poder, usando o avanço e a
  condição de parada do próprio jogo. O horário de cada um é uma **faixa** de duas caixas (por
  exemplo 10:00 e 12:00): todos os dias a extensão sorteia uma hora dentro dela e é nessa hora que
  entra, e o painel mostra a hora que saiu hoje. O sorteio é feito uma vez por dia e fica guardado —
  sortear a cada segundo cairia sempre no início da faixa. Mexer nas caixas sorteia outra vez na
  hora, e duas caixas iguais valem como hora fixa, que é o que acontecia antes de haver faixa;
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
- poções por percentual, mochila/depósito e preparação de venda;
- reviver sozinho ao cair na caçada: escolha o Reviver mais barato que houver, o melhor, ou um
  fixo, com teto de quantos por hora. Reviver **gasta um item da mochila** — por isso a opção
  começa desligada, nunca troca de item por conta própria quando o escolhido acaba e, alcançado o
  teto, deixa a contagem de 10 segundos correr e o jogo levar você para Seul, que é o que já
  acontecia. O XP perdido na queda é da morte e nenhum Reviver desfaz;
- monitor da party, diária, eventos, guerra de time e fadiga;
- pausa geral, registro das ações e bloqueio de botões premium;
- exportação e importação das configurações em arquivo, para levar a outra janela; entre classes diferentes, a build de status e os pesos do equipamento não vêm.

O pacote não troca personagem. A confirmação da venda permanece manual para impedir perda acidental. Automações que alteram o jogo começam desligadas.
