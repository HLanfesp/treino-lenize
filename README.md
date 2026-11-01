# 💜 Treino Lenize

App de treino de musculação da Lenize — mesmo padrão do seu app de agosto (vanilla JS, `localStorage`, sem dependências), com melhorias.

## O que tem
- **5 dias + sábado opcional** (Glúteos & Posterior · Costas & Bíceps A · Quadríceps & Glúteos B · Ombros & Tríceps · Costas B/Bíceps B/Peito · Sáb opcional: Glúteos & Ombros Pump). Domingo = descanso.
- **Organizado por andar da SmartFit 305N** e com **bisets só onde rendem mais** (polia + polia, costas + peito, core). O timer tem descanso próprio por exercício e no biset avisa "direto para o B".
- **Periodização mensal:** Novembro (4 semanas): S1 adaptação (manual) → S2 volume +2,5% → S3 choque +5% → S4 deload (−20% carga, −40% séries automático).
- **Sugestão automática de carga** arredondada para pesos que existem (halter 1/2 kg, barra e máquina 2,5, polia 1,25) + "📒 Última vez" em cada exercício (dupla progressão).
- **Registro série a série** (carga + reps), barra de progresso e timer de descanso.
- **Painel de acompanhamento:**
  - Evolução por exercício com 3 métricas: **Carga máxima**, **1RM estimado** (Epley) e **Tonelagem** (kg × reps).
  - **Volume semanal por músculo vs. meta**, destacando as prioridades ⭐ (glúteos, costas, ombros, bíceps).
  - **Recordes (PRs)** automáticos.
- **Histórico** e **backup** (exportar/importar JSON).

## ⚠️ Importante: histórico entre meses
No app de agosto, cada mês era um repositório/URL diferente — e o `localStorage` é isolado por URL, então **o histórico se perdia ao trocar de mês**.

Aqui a ideia é **manter sempre o mesmo endereço**. Para virar setembro→outubro→…→dezembro, você só edita os dados do mês dentro do `index.html` (a constante `MONTH` e, se mudar exercícios, o `PLAN`) e faz commit **no mesmo repositório**. Assim o `localStorage` continua o mesmo e a **progressão até dezembro aparece num gráfico só**.

## Publicar (GitHub Pages)
1. Crie **um** repositório (ex.: `treino-lenize`) — reutilize todo mês, não crie um por mês.
2. Suba o `index.html`.
3. Settings → Pages → Branch `main` / `root` → Save.
4. Acesse a URL do Pages no celular e **Adicionar à Tela de Início** (vira app em tela cheia).

## Atualizar para o próximo mês
Edite no `index.html`:
- `MONTH` → `key`, `label`, `year`, `month` e as `weeks` (datas + modo de cada semana).
- `BASE_WEEK` → a semana em que a carga é manual (normalmente a 1ª do mês).
- `START_KG` → carga inicial sugerida da semana base (tirada do mês anterior).
- `PAST_DELOADS` → acrescente o deload do mês que terminou (só colore o gráfico).
- `PLAN` → só se quiser trocar exercícios. Exercícios que saírem do plano vão para `LEGACY_EX` (continuam no gráfico e nos PRs).

O histórico registrado (`localStorage`) **não é tocado** por essas edições.

---
*Plano completo em `Plano_Treino_Lenize.md`. v3 · Novembro 2026.*
