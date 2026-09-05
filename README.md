# 💜 Treino Lenize

App de treino de musculação da Lenize — mesmo padrão do seu app de agosto (vanilla JS, `localStorage`, sem dependências), com melhorias.

## O que tem
- **Split de 6 dias** (Glúteos+Posterior · Ombro+Bíceps · Quadríceps+Internos · Peito+Tríceps · Costas · Glúteos+Ombros) + core nos dias de inferior. Domingo = descanso.
- **Periodização mensal:** S2 base (carga manual) → S3 progressão +5% → S4 deload −25%.
- **Sugestão automática de carga:** a semana base é preenchida manualmente; nas semanas seguintes o app sugere a carga (aumento ou deload) e é só aceitar ou editar.
- **Registro série a série** (carga + reps), barra de progresso e timer de descanso.
- **Painel de acompanhamento:**
  - Evolução por exercício com 3 métricas: **Carga máxima**, **1RM estimado** (Epley) e **Tonelagem** (kg × reps).
  - **Volume semanal por músculo vs. meta**, destacando as prioridades ⭐ (glúteos, quadríceps, ombros).
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
- `PLAN` → só se quiser trocar exercícios.

O histórico registrado (`localStorage`) **não é tocado** por essas edições.

---
*Plano completo em `Plano_Treino_Lenize.md`. v1 · Setembro 2026.*
