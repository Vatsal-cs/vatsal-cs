<div align="center">

# Vatsal Jain

**Computing Science @ University of Alberta · graduating 2027**

I build machine-learning systems end to end — data pipeline, model, optimizer, live product — and test them like experiments.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/vatsal-jain-873920228/)
[![Email](https://img.shields.io/badge/vatsalj05@gmail.com-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:vatsalj05@gmail.com)
[![VAR-ified XI](https://img.shields.io/badge/VAR--ified_XI-live_site-000000?style=flat-square&logo=vercel&logoColor=white)](https://var-ified-xi.vercel.app)

</div>

---

## ⚽ [VAR-ified XI](https://var-ified-xi.vercel.app)

**A Fantasy Premier League engine that has to prove every change before it ships.** It predicts every player's points, plans transfers, lineup and captain six weeks ahead under FPL's real rules, and re-plans itself before every deadline.

Live from the model right now — these update on their own every time it re-plans:

[![Model is planning](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fvar-ified-xi.vercel.app%2Foptimized_team.json&query=%24.gameweek&label=model%20is%20planning&prefix=GW%20&style=flat-square&color=E0A64A&labelColor=1B1816)](https://var-ified-xi.vercel.app)
[![Captain this week](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fvar-ified-xi.vercel.app%2Foptimized_team.json&query=%24.captain_odds%5B0%5D.name&label=captain%20this%20week&style=flat-square&color=8FBF7A&labelColor=1B1816)](https://var-ified-xi.vercel.app)

- **Model:** two-stage XGBoost (*will he play?* then *how many points if he does?*) trained on ~87,000 real gameweek results, averaged over five seeds
- **Decisions:** a mixed-integer linear program (PuLP/CBC) over budget, squad quotas, formation, club limits, free transfers and hits — optimal given the predictions, not a top-N sort
- **Rigour:** 24 research studies, 22 pre-registered with a pass/fail rule committed before the run and confirmed on held-back seasons. Found that the random seed alone moves a backtest by up to 175 points, and rebuilt the test harness so every change is judged against that noise
- **Runs itself:** GitHub Actions checks every four hours, re-plans before each deadline and redeploys the site — free tiers only, $0 a month

**What worked, and what didn't.** Every idea is tested against a rule written down before the run:

| Idea | Result | Verdict |
|---|---|---|
| Ownership % as an input (it was silently 0 in training) | +122 points over two seasons, positive on both held-back seasons | ✅ shipped |
| Cup, European and international fixtures as inputs | +87 points; +43 and +11 on the held-back seasons | ✅ shipped |
| Training on this season only, dropping past seasons | −66 points over five gameweeks | ❌ rejected |
| Players' European form as a signal | no measurable signal (+0.04, 95% CI −0.21 to +0.29) | ❌ not built |

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-EB1834?style=flat-square)
![PuLP](https://img.shields.io/badge/PuLP_(MILP)-2E8B57?style=flat-square)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white)

---

## 🌐 Bilingual content website · client project

**A production website built and shipped for a real client.** A bilingual (English and Hindi) site for books, writings, events, media and a photo gallery, with a password-protected admin dashboard so the client's team can update everything without touching code.

- Full content management: create and edit books, events, gallery albums, media and pages, with secure login and password reset
- Books readable right in the browser, and every page served in both languages
- Postgres database and auth on Supabase with versioned schema migrations; input validated with Zod; deployed on Vercel

![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=flat-square&logo=supabase&logoColor=white)
![Tailwind](https://img.shields.io/badge/Tailwind-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white)

---

## 🛡️ [SentinelIQ](https://github.com/Vatsal-cs/sentineliq)

**Fraud detection that knows how sure it is.** Combines a fraud model, breach exposure and the model's own confidence into one of seven graded actions, instead of a blunt freeze-or-clear.

- XGBoost on 590,540 IEEE-CIS transactions with 54 features: **AUC-PR 0.7017**, AUC-ROC 0.9528
- Calibrated with Platt scaling (a raw 0.85 meant ~36% real fraud), plus bootstrap confidence intervals per prediction, so an unsure score gets a softer response than a sure one
- [Live demo](https://sentineliq-godbless.streamlit.app) · [API docs](https://sentineliq.onrender.com/docs)

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-EB1834?style=flat-square)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)

---

## 🎟️ [Elotto](https://github.com/Vatsal-cs/Elotto_app)

**Android event-lottery app, built by a team of six.** Fair sign-ups for high-demand events: waiting lists, random draws with automatic redraws, QR codes, geolocation checks and real-time notifications.

![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![Android](https://img.shields.io/badge/Android-3DDC84?style=flat-square&logo=android&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=flat-square&logo=firebase&logoColor=black)

---

## 🛠️ Toolbox

<p align="center">
  <img src="https://skillicons.dev/icons?i=python,java,ts,js,c,react,nextjs,tailwind,fastapi,flask,django,pytorch,sklearn,postgres,mongodb,sqlite,firebase,androidstudio,githubactions,vercel,git,linux&perline=11" alt="Python, Java, TypeScript, JavaScript, C, React, Next.js, Tailwind, FastAPI, Flask, Django, PyTorch, scikit-learn, PostgreSQL, MongoDB, SQLite, Firebase, Android Studio, GitHub Actions, Vercel, Git, Linux">
</p>
