# ⚠️  Working on this is very tempting and Addictive. Take precaution.

**Ensure you have completed your DAILY TARGETS, and Remember your menifestations and priorities in life**

## Roadmap

#productivity-and-tech🗑️ 

- [ ] 1. API Key rotator : Round robin => prompt ✅ #ticktick 
- [x] 2. Rag PDF Citations => prompt ✅ ✅ 2025-05-04 #ticktick 
- [x] 3. Fact check clickable. next to cited sources. => prompt ✅  [link](https://ticktick.com/webapp/#p/681aaaf2c71c710000000041/tasks/681ab6c174148e55307d3c48) #ticktick  %%[ticktick_id:: 681ab6c174148e55307d3c48]%% ✅ 2025-05-04
- [!] ~~4. implement this logic replacing gemini normal output : "C:\Users\FO\Desktop\nanoPerplexityAI-main" => prompt ❌~~ ✅ 2025-05-04 #ticktick 

---

## instructions for future-self

-COPY working hai,
preprepo-GUI not working. - NOT REALLY IMP TO FIX EITHER. FOCUS ON ROI. FOCUS ON GOAL.
![[image.png]]

- this already contains <> and </> you will see when you copy.
- this is not a necessity right now, do it in your absolute free time. Priority rn is `Daily Targets and [[Strategy]]`
- do [[#Roadmap]] one by one.

---

## Prompt - inclusive of [[#Roadmap|1. 2. 3.]]

<critical> 
    Don't change anything else except for what's needed. Do NOT MAKE ANY    OTHER CHANGE except for what's explicitly being instructed. Do not make assumptions, be factual by verifying, never ever make any typo, the changes described will be made for both front-end and backend and dependencies, if any, i.e., full-stack. Instead of adding more lines to the same file, create new files for the new separate functions being described to you. Always understand the implied tasks in case of instruction deficiency based on "GOAL", never hallucinate ask for it in case you have ANY confusion. DONT BREAK THE CODE.
</critical>

<task>
1. add 2 Mark down CLICKABLE Links to the end of each and every generated point in "Summary AI" / "AI Summary" Card's output which summarises the RGA output. Goal is to increase reliability and user trust. Buttons are as follows:
    A. Citation (like perplexity and notebook LM as it's an RAG solution `[citation number](website link)` ): "1", "2", "3"...and so on for however many sentences/sources/points there are. Clicking on the button will open the pdf and page number exactly where that line is cited from-in Sumtra PDF: (this pdf opening logic will be exactly similar to the logic that when i open any default view result - any item from the list, it opens sumatra pdf, exact page and highlights the exact word. 
    Also, Hovering on these "1", "2", "3", "4",... etc buttons next to each and every sentence will display the pdf's name and page number.
    (in case you will ask the LLM Itself to do this, add this in "summary ai" settings with save button as another system prompt called "Appended Citation Prompt" -Editable by user if needed, add the default one to the app by yourself for maximum accuracy, perfect results i.e. very explicit as if what's needed, this prompt will ONLY be appended to the AI summary prompt output, in both agent/normal search)
    B. "🔍"  next to every citation button in the same formatting as citation clicking on which, will send that particular sentence/point it is added next to to the user specified search engine/LLM and for that, in the "Summary AI" settings add two more feilds with save button, where user can enter the link in the form of: "https://google.com/search?q={}", "https://www.perplexity.ai/search?q={}" (perlxity link is default) etc. + Another feild with the fact checking prompt/query which will be appended to User's query like a fact check system prompt sent via link such as https://www.perplexity.ai/search?q={}. also editable, although add a default fact check system prompt meticulously crafted which will fact check each and every word, in a table with : [sentence, word, correct/incorrect/semi-correct, why, source]

</task>

<task>
2. Add API Key rotator with round robin algorithm for each and every API call being made, smartly. 
    User can add as many API Keys as they want, for that, replace the current API key field, and in it's exact place add a "API Keys" button --> clicking on which will open a Medium-large size modal/pop-up with a cross button to close it and save button with confirmation and an Add button to add more API keys. where user can add AS MANY API Keys as they want.
    it'll be in this format: 
    A Table View: | Name | Key | Requests made 
    (When adding a key user can add a Name to it, the key in the second column of course, requests made from each key will be tracked and written here)
    Rows can be as many keys the user adds, as such ensure it has a scroll bar to scroll down and explore all the rows.
    GOAL= Quick responses, more Api key limits, less load on a single LLM. Better error handling and API Key Management.
</task>

<Critical>
Ensure you don't make any assumptions, even whatever user has said, verify it, understand its functioning, backend/frontend/connections/etc.
And each and every file you make, read, edit, effect, read and analyse and verify with 100% accuracy and factuality about all of its connected files/functions as well. Never ever make any assumptions. Always verify everything and before starting, without being a lazy bot, analyse the whole repo and all the functions/connections to understand the context with 100% accuracy.
Important! Never make any mistake, recheck everything yourself twice before making changes, no hallucinations, for each request and actions, verify that you haven't made any typo/forgotten anything/forgot to add functions. Don't make silly/unnecessary mistakes by mistake. DONT CHANGE ANY OTHER FUNTIONS. DONT BREAK THE CODE OR ANY FEATURE.
</Critical>

---
