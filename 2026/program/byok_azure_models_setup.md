# 🔑 Adding the BSMP Azure AI Models to Your Codespace (BYOK) <!-- {docsify-ignore-all} -->

In this class, you'll use **GitHub Copilot in agent mode** with **BSMP's own Azure AI models** instead of relying on limited free credits. This is called **BYOK** — *Bring Your Own Key*.

This page walks you through **two things you'll set up at the start of every class**:

1. **Add the BSMP model to GitHub Copilot** (so you can use it in agent mode), and
2. **Create your `.env` file** (so your app code can call the model).

?> ⏱️ **Do this at the beginning of every class.** Codespaces may reset between sessions, so you'll re-add the model and re-create your `.env` file each time. It only takes a minute once you've done it once.

<br>

---

## 📍 Step 0: Find Your Chapter's Keys

All of the model info you need — the **endpoint**, **API key**, **deployment/model name**, and **API version** — lives in a **Loop page on the BSMP Team site in your tenant**.

> Open the Loop page titled **"BSMP AI Models and Keys"** and find the section for **your chapter / location**.
> * [Houston - BSMP AI Models Keys.loop](https://m365cpi70459279.sharepoint.com/:fl:/g/contentstorage/CSP_00c67cf6-0806-4c5c-a926-bc5c9ae9cc1c/IQBxO-9SQtnsR7y5R1fZ18_1Ab-JFup7kb_wpC3RBm2p49Y?e=phO6Ru&nav=cz0lMkZjb250ZW50c3RvcmFnZSUyRkNTUF8wMGM2N2NmNi0wODA2LTRjNWMtYTkyNi1iYzVjOWFlOWNjMWMmZD1iJTIxOW56R0FBWUlYRXlwSnJ4Y211bk1IT0RUX1FadlgyVkhyNDIzSUpHUjhzQnhlR1g0SmRYdFRieHUtMUdpLXNNOCZmPTAxVURWTDRMVFJIUFhWRVFXWjVSRDNaT0tISzdNNVBUN1YmYz0lMkYmYT1Mb29wQXBwJnA9JTQwZmx1aWR4JTJGbG9vcC1wYWdlLWNvbnRhaW5lciZ4PSU3QiUyMnclMjIlM0ElMjJUMFJUVUh4dE16WTFZM0JwTnpBME5Ua3lOemt1YzJoaGNtVndiMmx1ZEM1amIyMThZaUU1Ym5wSFFVRlpTVmhGZVhCS2NuaGpiWFZ1VFVoUFJGUmZVVnAyV0RKV1NISTBNak5KU2tkU09ITkNlR1ZIV0RSS1pGaDBWR0o0ZFMweFIya3RjMDA0ZkRBeFZVUldURFJNVjFGV1NVbElNbEZOUnpZMVJFazBVVnBUTmxkU05qSlhUMDAlM0QlMjIlMkMlMjJpJTIyJTNBJTIyNjY0OWFiZDMtZjNjMy00OTVlLThkODktYzI2NmIwOWE3Yzk5JTIyJTdE)
> * [NYC - BSMP AI Models Keys.loop](https://m365cpi70459279.sharepoint.com/:fl:/g/contentstorage/CSP_00c67cf6-0806-4c5c-a926-bc5c9ae9cc1c/IQAuga7cZNqHRbdkVM32pMgpAUloxraJo1WLRaBb0VJl1Fg?e=vdcdUf&nav=cz0lMkZjb250ZW50c3RvcmFnZSUyRkNTUF8wMGM2N2NmNi0wODA2LTRjNWMtYTkyNi1iYzVjOWFlOWNjMWMmZD1iJTIxOW56R0FBWUlYRXlwSnJ4Y211bk1IT0RUX1FadlgyVkhyNDIzSUpHUjhzQnhlR1g0SmRYdFRieHUtMUdpLXNNOCZmPTAxVURWTDRMUk9RR1hOWVpHMlE1QzNPWkNVWlgzS0pTQkomYz0lMkYmYT1Mb29wQXBwJnA9JTQwZmx1aWR4JTJGbG9vcC1wYWdlLWNvbnRhaW5lciZ4PSU3QiUyMnclMjIlM0ElMjJUMFJUVUh4dE16WTFZM0JwTnpBME5Ua3lOemt1YzJoaGNtVndiMmx1ZEM1amIyMThZaUU1Ym5wSFFVRlpTVmhGZVhCS2NuaGpiWFZ1VFVoUFJGUmZVVnAyV0RKV1NISTBNak5KU2tkU09ITkNlR1ZIV0RSS1pGaDBWR0o0ZFMweFIya3RjMDA0ZkRBeFZVUldURFJNVjFGV1NVbElNbEZOUnpZMVJFazBVVnBUTmxkU05qSlhUMDAlM0QlMjIlMkMlMjJpJTIyJTNBJTIyNjBkMzMxZDAtZjE4Mi00MDlkLTk0Y2ItMDAyYmRiN2I4ZWI0JTIyJTdE)
> * [Tampa  Florida - BSMP AI Models Keys.loop](https://m365cpi70459279.sharepoint.com/:fl:/g/contentstorage/CSP_00c67cf6-0806-4c5c-a926-bc5c9ae9cc1c/IQDDGojtFNzpTquvqXcp3er8AaEcsHp_m01ouMdFNCAx2kE?e=OvQDw5&nav=cz0lMkZjb250ZW50c3RvcmFnZSUyRkNTUF8wMGM2N2NmNi0wODA2LTRjNWMtYTkyNi1iYzVjOWFlOWNjMWMmZD1iJTIxOW56R0FBWUlYRXlwSnJ4Y211bk1IT0RUX1FadlgyVkhyNDIzSUpHUjhzQnhlR1g0SmRYdFRieHUtMUdpLXNNOCZmPTAxVURWTDRMV0RES0VPMkZHNDVGSEtYTDVKTzRVNTMyWDQmYz0lMkYmYT1Mb29wQXBwJng9JTdCJTIydyUyMiUzQSUyMlQwUlRVSHh0TXpZMVkzQnBOekEwTlRreU56a3VjMmhoY21Wd2IybHVkQzVqYjIxOFlpRTVibnBIUVVGWlNWaEZlWEJLY25oamJYVnVUVWhQUkZSZlVWcDJXREpXU0hJME1qTkpTa2RTT0hOQ2VHVkhXRFJLWkZoMFZHSjRkUzB4UjJrdGMwMDRmREF4VlVSV1REUk1WMUZXU1VsSU1sRk5SelkxUkVrMFVWcFRObGRTTmpKWFQwMCUzRCUyMiUyQyUyMmklMjIlM0ElMjI5NWJjYzhkOC00ZjNiLTRjYmUtOWY4Yy0zZGJlYmJjYjAyNDYlMjIlN0Q%3D)
> * [Raleigh, NCA/DMV - BSMP AI Models Keys.loop](https://m365cpi70459279.sharepoint.com/:fl:/g/contentstorage/CSP_00c67cf6-0806-4c5c-a926-bc5c9ae9cc1c/IQC1s7BJ9VSxSbhH0qQY4ipsAZQc4eRiiopjDmZsu_mKpzk?e=0OWbfS&nav=cz0lMkZjb250ZW50c3RvcmFnZSUyRkNTUF8wMGM2N2NmNi0wODA2LTRjNWMtYTkyNi1iYzVjOWFlOWNjMWMmZD1iJTIxOW56R0FBWUlYRXlwSnJ4Y211bk1IT0RUX1FadlgyVkhyNDIzSUpHUjhzQnhlR1g0SmRYdFRieHUtMUdpLXNNOCZmPTAxVURWTDRMVlZXT1lFVDVLVVdGRTNRUjZTVVFNT0VLVE0mYz0lMkYmYT1Mb29wQXBwJng9JTdCJTIydyUyMiUzQSUyMlQwUlRVSHh0TXpZMVkzQnBOekEwTlRreU56a3VjMmhoY21Wd2IybHVkQzVqYjIxOFlpRTVibnBIUVVGWlNWaEZlWEJLY25oamJYVnVUVWhQUkZSZlVWcDJXREpXU0hJME1qTkpTa2RTT0hOQ2VHVkhXRFJLWkZoMFZHSjRkUzB4UjJrdGMwMDRmREF4VlVSV1REUk1WMUZXU1VsSU1sRk5SelkxUkVrMFVWcFRObGRTTmpKWFQwMCUzRCUyMiUyQyUyMmklMjIlM0ElMjI5NWJjYzhkOC00ZjNiLTRjYmUtOWY4Yy0zZGJlYmJjYjAyNTQlMjIlN0Q%3D)

Your chapter section will list something like:

| Field | Example value |
|-------|----------------|
| Copilot Chat model — used in **Part 1** | `gpt-5.4-nano` |
| App deployment — `AZURE_OPENAI_DEPLOYMENT`, used in **Part 2** | `gpt-5-nano` |
| Endpoint | `https://<your-chapter-resource>.openai.azure.com/` |
| API Key | `••••••••••••••••` |
| API Version | `2026-xx-xx` |

!> 🔒 **Keep your keys private.** These keys are shared just for class. Don't post them in public repos, chats, or your final project video.


<br>

---

## 🧩 Part 1: Add the Model to GitHub Copilot

This lets you select the BSMP model when using **Copilot agent mode**.

### Step 1 — Open the model picker

In your Codespace, open the **Copilot Chat** panel and click the **model selector** dropdown (where the current model name is shown). It might currently say **`Auto`** (the default) — that's fine; click it anyway.

![alt text](../../_media/github_byok/1_model_picker.png)

### Step 2 — Choose "Manage Models" / "Add Model"

At the bottom of the model list, click the **⚙️ Manage Models** (or **Add a model**) option.

![Placeholder: screenshot of the Copilot Chat model selector dropdown and Manage Models option](../../_media/github_byok/1_model_selector_dropdown.png ":size=720")

### Step 3 — Click Add Model and Select "Azure" as the provider

At the top right in green should be a button to "Add Models". Select that. When prompted for a provider, choose **Azure**.

![Placeholder: screenshot of selecting Azure as the model provider](../../_media/github_byok/2_copilot_select_azure.png)

Hit enter as well to use `Azure` as the Group Name. 

![alt text](../../_media/github_byok/2_select_azure.png)


### Step 4 - Enter in the API key

Copy the API Key from the **AI Models and Keys** Loop page and paste it when prompted like so and then hit `Enter`:

![alt text](../../_media/github_byok/4_copilot_api_key.png)

### Step 5 — Enter your chapter's model details

Copy the values from your chapter's **AI Models and Keys** Loop page and update lines 9 and 10 in the `chatLanguageModels.json`. 

- line 9 `name` update model name to: `gpt-5.4-nano`
- line 10 `url` update to the model url: `https://....openai.azure.com/`

![Placeholder: screenshot of entering the Azure model endpoint, key, and deployment name](../../_media/github_byok/5_copilot_enter_model_details.png ":size=720")

### Step 6 — Select your model

Back in the model dropdown, you may need to expand **Other Models…** at the bottom of the list to find your newly added **BSMP Azure model**. Select it — you're now ready to use it in **agent mode**! ✅

![Placeholder: screenshot of the BSMP model selected in the dropdown](../../_media/github_byok/6_copilot_model_selected.png ":size=720")

<br>

---

## 📄 Part 2: Create Your `.env` File

Your app code (the chatbots and agents you build) reads the model info from a **`.env` file** in your project. You'll create this from the provided **`.env-sample`** in the repo root.

### Step 1 — Copy the sample

In the terminal inside your Codespace, run:

```bash
cp .env-sample .env
```

### Step 2 — Fill in your chapter's values

Open `.env` and paste in the values from your chapter's **AI Models and Keys** Loop page [Houston](https://m365cpi70459279.sharepoint.com/:fl:/g/contentstorage/CSP_00c67cf6-0806-4c5c-a926-bc5c9ae9cc1c/IQBxO-9QtnsR7y5R1fZ18_1Ab-JFup7kb_wpC3RBm2p49Y?e=phO6Runav=cz0lMkZjb250ZW50c3RvcmFnZSUyRkNTUF8wMGM2N2NmNi0wODA2LTRjNWMtYTkyNi1iYzVjOWFlOWNjMWMmZD1iJTIxOW56R0FBWUlYRXlwSnJ4Y211bk1IT0RUX1FadlgyVkhyNDIzSUpHUjhzQnhlR1g0SmRYdFRieHUtMUdpLXNNOCZmPTAxVURWTDRMVFJIUFhWRVFXWjVSRDNaT0tISzdNNVBUN1YmYz0lMkYmYT1Mb29wQXBwJnA9JTQwZmx1aWR4JTJGbG9vcC1wYWdlLWNvbnRhaW5lciZ4PSU3QiUyMnclMjIlM0ElMjJUMFJUVUh4dE16WTFZM0JwTnpBME5Ua3lOemt1YzJoaGNtVndiMmx1ZEM1amIyMThZaUU1Ym5wSFFVRlpTVmhGZVhCS2NuaGpiWFZ1VFVoUFJGUmZVVnAyV0RKV1NISTBNak5KU2tkU09ITkNlR1ZIV0RSS1pGaDBWR0o0ZFMweFIya3RjMDA0ZkRBeFZVUldURFJNVjFGV1NVbElNbEZOUnpZMVJFazBVVnBUTmxkU05qSlhUMDAlM0QlMjIlMkMlMjJpJTIyJTNBJTIyNjY0OWFiZDMtZjNjMy00OTVlLThkODktYzI2NmIwOWE3Yzk5JTIyJTdE) | [NYC](https://m365cpi70459279.sharepoint.com/:fl:/g/contentstorage/CSP_00c67cf6-0806-4c5c-a926-bc5c9ae9cc1c/IQAuga7cZNqHRbdkVM32pMgpAUloxraJo1WLRaBb0VJl1Fg?e=vdcdUf&nav=cz0lMkZjb250ZW50c3RvcmFnZSUyRkNTUF8wMGM2N2NmNi0wODA2LTRjNWMtYTkyNi1iYzVjOWFlOWNjMWMmZD1iJTIxOW56R0FBWUlYRXlwSnJ4Y211bk1IT0RUX1FadlgyVkhyNDIzSUpHUjhzQnhlR1g0SmRYdFRieHUtMUdpLXNNOCZmPTAxVURWTDRMUk9RR1hOWVpHMlE1QzNPWkNVWlgzS0pTQkomYz0lMkYmYT1Mb29wQXBwJnA9JTQwZmx1aWR4JTJGbG9vcC1wYWdlLWNvbnRhaW5lciZ4PSU3QiUyMnclMjIlM0ElMjJUMFJUVUh4dE16WTFZM0JwTnpBME5Ua3lOemt1YzJoaGNtVndiMmx1ZEM1amIyMThZaUU1Ym5wSFFVRlpTVmhGZVhCS2NuaGpiWFZ1VFVoUFJGUmZVVnAyV0RKV1NISTBNak5KU2tkU09ITkNlR1ZIV0RSS1pGaDBWR0o0ZFMweFIya3RjMDA0ZkRBeFZVUldURFJNVjFGV1NVbElNbEZOUnpZMVJFazBVVnBUTmxkU05qSlhUMDAlM0QlMjIlMkMlMjJpJTIyJTNBJTIyNjBkMzMxZDAtZjE4Mi00MDlkLTk0Y2ItMDAyYmRiN2I4ZWI0JTIyJTdE) | [Tampa  Florida](https://m365cpi70459279.sharepoint.com/:fl:/g/contentstorage/CSP_00c67cf6-0806-4c5c-a926-bc5c9ae9cc1c/IQDDGojtFNzpTquvqXcp3er8AaEcsHp_m01ouMdFNCAx2kE?e=OvQDw5&nav=cz0lMkZjb250ZW50c3RvcmFnZSUyRkNTUF8wMGM2N2NmNi0wODA2LTRjNWMtYTkyNi1iYzVjOWFlOWNjMWMmZD1iJTIxOW56R0FBWUlYRXlwSnJ4Y211bk1IT0RUX1FadlgyVkhyNDIzSUpHUjhzQnhlR1g0SmRYdFRieHUtMUdpLXNNOCZmPTAxVURWTDRMV0RES0VPMkZHNDVGSEtYTDVKTzRVNTMyWDQmYz0lMkYmYT1Mb29wQXBwJng9JTdCJTIydyUyMiUzQSUyMlQwUlRVSHh0TXpZMVkzQnBOekEwTlRreU56a3VjMmhoY21Wd2IybHVkQzVqYjIxOFlpRTVibnBIUVVGWlNWaEZlWEJLY25oamJYVnVUVWhQUkZSZlVWcDJXREpXU0hJME1qTkpTa2RTT0hOQ2VHVkhXRFJLWkZoMFZHSjRkUzB4UjJrdGMwMDRmREF4VlVSV1REUk1WMUZXU1VsSU1sRk5SelkxUkVrMFVWcFRObGRTTmpKWFQwMCUzRCUyMiUyQyUyMmklMjIlM0ElMjI5NWJjYzhkOC00ZjNiLTRjYmUtOWY4Yy0zZGJlYmJjYjAyNDYlMjIlN0Q%3D) | [Raleigh, NCA/DMV](https://m365cpi70459279.sharepoint.com/:fl:/g/contentstorage/CSP_00c67cf6-0806-4c5c-a926-bc5c9ae9cc1c/IQC1s7BJ9VSxSbhH0qQY4ipsAZQc4eRiiopjDmZsu_mKpzk?e=0OWbfS&nav=cz0lMkZjb250ZW50c3RvcmFnZSUyRkNTUF8wMGM2N2NmNi0wODA2LTRjNWMtYTkyNi1iYzVjOWFlOWNjMWMmZD1iJTIxOW56R0FBWUlYRXlwSnJ4Y211bk1IT0RUX1FadlgyVkhyNDIzSUpHUjhzQnhlR1g0SmRYdFRieHUtMUdpLXNNOCZmPTAxVURWTDRMVlZXT1lFVDVLVVdGRTNRUjZTVVFNT0VLVE0mYz0lMkYmYT1Mb29wQXBwJng9JTdCJTIydyUyMiUzQSUyMlQwUlRVSHh0TXpZMVkzQnBOekEwTlRreU56a3VjMmhoY21Wd2IybHVkQzVqYjIxOFlpRTVibnBIUVVGWlNWaEZlWEJLY25oamJYVnVUVWhQUkZSZlVWcDJXREpXU0hJME1qTkpTa2RTT0hOQ2VHVkhXRFJLWkZoMFZHSjRkUzB4UjJrdGMwMDRmREF4VlVSV1REUk1WMUZXU1VsSU1sRk5SelkxUkVrMFVWcFRObGRTTmpKWFQwMCUzRCUyMiUyQyUyMmklMjIlM0ElMjI5NWJjYzhkOC00ZjNiLTRjYmUtOWY4Yy0zZGJlYmJjYjAyNTQlMjIlN0Q%3D) :

```bash
AZURE_OPENAI_ENDPOINT="https://<your-chapter-resource>.openai.azure.com/"
AZURE_OPENAI_API_KEY="<your-chapter-api-key>"
AZURE_OPENAI_DEPLOYMENT="gpt-5-nano"
AZURE_OPENAI_API_VERSION="2026-xx-xx"
```

![Placeholder: screenshot of a completed .env file in VS Code](../../_media/github_byok/env_file_filled.png ":size=720")


!> ⚠️ **Never commit your `.env` file.** It's already in `.gitignore` so your keys stay out of GitHub — keep it that way.

### Step 3 — Confirm it's working

Run the lesson's starter app (for most lessons this is):

```bash
python app.py
```

If the app starts and your AI chat responds, you're all set! 🎉

<br>

---

## ✅ Quick Start Checklist (Every Class)

- [ ] Open the lesson repo in **Codespaces**
- [ ] Open the [AI Models and Keys Loop](https://m365cpi70459279.sharepoint.com/:fl:/g/contentstorage/CSP_00c67cf6-0806-4c5c-a926-bc5c9ae9cc1c/IQAWC-BuQNgHSpmIUWXOJsslAXicIrKKvjPfgXfLJyUqIVk?e=nrxiAW&nav=cz0lMkZjb250ZW50c3RvcmFnZSUyRkNTUF8wMGM2N2NmNi0wODA2LTRjNWMtYTkyNi1iYzVjOWFlOWNjMWMmZD1iJTIxOW56R0FBWUlYRXlwSnJ4Y211bk1IT0RUX1FadlgyVkhyNDIzSUpHUjhzQnhlR1g0SmRYdFRieHUtMUdpLXNNOCZmPTAxVURWTDRMUVdCUFFHNFFHWUE1RkpUQ0NSTVhIQ05TWkYmYz0lMkYmYT1Mb29wQXBwJnA9JTQwZmx1aWR4JTJGbG9vcC1wYWdlLWNvbnRhaW5lciZ4PSU3QiUyMnclMjIlM0ElMjJUMFJUVUh4dE16WTFZM0JwTnpBME5Ua3lOemt1YzJoaGNtVndiMmx1ZEM1amIyMThZaUU1Ym5wSFFVRlpTVmhGZVhCS2NuaGpiWFZ1VFVoUFJGUmZVVnAyV0RKV1NISTBNak5KU2tkU09ITkNlR1ZIV0RSS1pGaDBWR0o0ZFMweFIya3RjMDA0ZkRBeFZVUldURFJNVjFGV1NVbElNbEZOUnpZMVJFazBVVnBUTmxkU05qSlhUMDAlM0QlMjIlMkMlMjJpJTIyJTNBJTIyOTViY2M4ZDgtNGYzYi00Y2JlLTlmOGMtM2RiZWJiY2IwMjJlJTIyJTdE) page → find **your chapter**
- [ ] **Part 1:** Add the BSMP Azure model to Copilot and select it in the model dropdown
- [ ] **Part 2:** `cp .env-sample .env` and paste in your chapter's endpoint, key, deployment, and API version
- [ ] Run the app (`python app.py`) and confirm the AI responds

<br>

---

## 🆘 Troubleshooting

- **"Too many requests" / rate limited?** The class model can get busy. Let your instructor know — there's a **backup model** you can switch to using the same steps in Part 1.
- **App can't find the key?** Make sure your file is named exactly `.env` (not `.env.txt`) and is in the project root.
- **Model not showing in Copilot?** Re-open the model dropdown and confirm you selected the BSMP Azure model, not the default.
- **Still stuck?** Bring it to **office hours (Mondays, 2 PM EST)** or ask a mentor in class.
