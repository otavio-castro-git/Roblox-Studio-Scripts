# Advanced Movement System — Roblox

Um sistema de movimentação avançada para **Roblox Studio**, feito para dar ao jogador uma experiência de movimento fluida e dinâmica, com corrida, parkour, wall run, escalada, dash e slide — tudo em um único script.

---

## Funcionalidades

- **Corrida progressiva** — velocidade e FOV aumentam gradualmente com double tap em W
- **Auto-Step / Parkour** — sobe obstáculos automaticamente ao correr
- **Wall Run** — corre em paredes laterais pressionando A ou D
- **Climbing** — escala paredes frontais com animações de subida e descida
- **Double Jump** — pulos extras no ar configuráveis
- **Dash** — impulso rápido em qualquer direção com Q
- **Slide** — desliza em rampas com E, com física de inclinação real

---

## Instalação

1. Abra o **Roblox Studio**
2. No painel **Explorer**, vá até `StarterPlayer → StarterCharacterScripts`
3. Insira um **LocalScript**
4. Cole o conteúdo do arquivo `AdvancedMovement.lua` dentro do LocalScript
5. Adicione as animações necessárias como filhos do LocalScript (veja a seção de Animações)

---

## Animações necessárias

O script busca as animações pelos nomes abaixo. Todas devem ser objetos do tipo `Animation` e filhos diretos do LocalScript:

| Nome | Descrição |
|---|---|
| `RunAnim` | Animação de corrida |
| `JumpAnim` | Animação de pulo ao correr |
| `FallAnim` | Animação de queda |
| `WallRunL` | Wall run para a esquerda |
| `WallRunR` | Wall run para a direita |
| `Flip` | Pulo saindo do wall run |
| `Parkour1` `Parkour2` `Parkour3` | Animações de auto-step (escolhidas aleatoriamente) |
| `ClimbAnim` | Animação de escalada em movimento |
| `ClimbAnimIdle` | Animação de escalada parado |
| `DashFront` | Dash para frente |
| `DashBack` | Dash para trás |
| `DashLeft` | Dash para esquerda |
| `DashRight` | Dash para direita |
| `SlideAnim` | Animação de slide |

---

## Controles

| Ação | Tecla |
|---|---|
| Correr | Double tap `W` |
| Wall Run | Correr + `A` ou `D` próximo a uma parede |
| Pular do Wall Run | `Space` ou `Q` durante o wall run |
| Escalar | `W` de frente para uma parede |
| Double Jump | `Space` no ar |
| Dash | `Q` |
| Slide | `E` em uma rampa |
| Cancelar Slide | `Space` durante o slide |

---

## Configurações

Todas as variáveis de configuração ficam no topo do script e podem ser ajustadas livremente:

### Corrida
```lua
local DOUBLE_TAP_TIME = 0.30   -- tempo máximo entre toques para ativar a corrida
local TRANSITION_TIME = 4.5    -- tempo para chegar à velocidade máxima
local DEFAULT_SPEED = 16       -- velocidade normal
local MIN_RUN_SPEED = 24       -- velocidade mínima para ativar efeitos de corrida
local MAX_SPEED = 42           -- velocidade máxima
local DEFAULT_FOV = 70         -- FOV padrão
local MAX_FOV = 110            -- FOV máximo durante a corrida
```

### Pulo
```lua
local DEFAULT_JUMP_HEIGHT = 7  -- altura de pulo normal
local MIN_RUN_JUMP = 8         -- altura de pulo ao iniciar a corrida
local MAX_RUN_JUMP = 12        -- altura de pulo na velocidade máxima
```

### Double Jump
```lua
local MAX_AIR_JUMPS = 7        -- quantidade de pulos extras no ar
local JUMP_COOLDOWN = 0.2      -- tempo mínimo entre pulos
```

### Dash
```lua
local DASH_SPEED = 75          -- velocidade do dash
local DASH_DURATION = 0.35     -- duração do dash
local DASH_COOLDOWN = 0.2      -- cooldown entre dashes
```

### Slide
```lua
SlideSettings.BaseSpeed = 65         -- velocidade base do slide
SlideSettings.MaxMultiplier = 2      -- multiplicador máximo de velocidade
SlideSettings.Cooldown = 0.15        -- cooldown entre slides
```

### Escalada
```lua
local CLIMB_SPEED = 20         -- velocidade de escalada
local CLIMB_RAY_DISTANCE = 2.5 -- distância dos raycasts frontais
```

---

## Requisitos

- Roblox Studio
- Script deve estar em `StarterCharacterScripts` como **LocalScript**
- Todas as animações listadas acima devem estar presentes como filhos do script

---

## 🚧 Work in Progress

Este sistema ainda está em desenvolvimento ativo. Novos sistemas de movimentação e melhorias podem chegar em atualizações futuras. Sugestões e contribuições são bem-vindas — fique à vontade para abrir uma issue ou pull request.
