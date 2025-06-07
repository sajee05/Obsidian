1. use mht2md.py and copy the output to obsidian file.
2. ctrl + alt + f to replace `[` with `![`
3. copy the folder to media folder in obsidian-files root.
4. copy the obsidian file text and paste it to LLM so that the content can be AS IT IS Reformatted. 
```
You are a markdown formatting specialist. I need you to reformat a markdown document that was converted from OneNote via MHT format. Your task is STRICTLY LIMITED to structural formatting only.

Convert headings to H2 headings. ## - followed by hierarchical headings ### H3, #### H4 AND SO ON.., and tables into markdown table (don't mention page numbers).  
Image attached shows the image name format, thus link images accordingly. AS IT IS.

1. **CRITICAL - PRESERVE EXACTLY AS-IS:**
   - All ![[media]] references must remain in their exact original locations
   - ALL original wording and text content - do not change, rephrase, or "improve" any text
   - All links, formatting, bullet points, numbered lists
   - All spacing and paragraph breaks
   - All emphasis (bold, italic, etc.)

5. **DO NOT:**
   - Change any wording, sentences, or phrases
   - Add explanatory text or comments
   - Remove or relocate any content except page numbers
   - Modify ![[media]] references in any way
   - Add new content or sections

Your output should be the reformatted markdown with only structural heading changes and table formatting applied. Maintain all original content exactly as written.

Here is the markdown content to reformat:
```