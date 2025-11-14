# Automating Tasks in Photoshop with the Actions Panel

This guide shows you how to **record an Action** (a saved sequence of Photoshop commands) and then apply it to multiple files using **Batch processing**.

---

## 1. Access the Actions Panel

1. Open Photoshop.  
2. From the top menu, choose **Window › Actions**.  
3. The **Actions panel** opens. By default, it may appear docked with the **History** panel.  

<!-- Screenshot: Actions panel visible in Photoshop interface -->

---

## 2. Create a New Action Set (Optional)

- Actions are stored inside **Sets** (folders).  
- In the Actions panel, click the **folder icon** (bottom of panel).  
- Name the set something descriptive (e.g., *Resizing Workflows*).  

<!-- Screenshot: Creating a new Action Set -->

---

## 3. Create a New Action

1. In the Actions panel, click the **plus (+) icon** (New Action).  
2. Enter:  
   - **Name:** e.g., *Resize to 1200px Wide*  
   - **Set:** select the folder from step 2  
   - **Function Key:** optional keyboard shortcut  
   - **Color:** optional for easy identification  
3. Click **Record**. Photoshop begins recording all steps you take.  

<!-- Screenshot: New Action dialog box -->

---

## 4. Record Your Steps

While recording:

- **Every command** you apply is stored.  
- Example:  
  1. Go to **Image › Image Size**.  
  2. Change width to **1200 px**, keep “Constrain Proportions” checked.  
  3. Go to **File › Save As** → choose JPEG.  
  4. Adjust quality settings, click Save.  

- When finished, click the **Stop button** (square icon at bottom of Actions panel).  

<!-- Screenshot: Recording in progress, red dot active -->

---

## 5. Test the Action

- Open any image.  
- In the Actions panel, select your action.  
- Click the **Play button** (triangle).  
- Confirm that the steps work as intended.  

<!-- Screenshot: Playing an Action -->

---

## 6. Batch Process Multiple Files

1. Go to **File › Automate › Batch…**  
2. Configure:  
   - **Set:** choose the set containing your action  
   - **Action:** select the action you recorded  
   - **Source:** choose where the input files are (Folder, Opened Files, etc.)  
   - **Destination:** choose how and where to save output files (None, Save and Close, or Folder)  
   - **File Naming:** customize how output files are named (e.g., DocumentName + `_resized`).  
3. Click **OK** to run.  

<!-- Screenshot: Batch Processing dialog box -->

---

## 7. Saving and Exporting Actions

- To reuse or share actions:  
  - Open the Actions panel menu (three-line hamburger icon).  
  - Choose **Save Actions…**  
  - Photoshop saves a `.atn` file that can be imported later.  

<!-- Screenshot: Actions panel menu with Save option -->

---

## 8. Tips for Better Automation

- Add **Stops**: Insert a pause with instructions by using **Insert Stop** (panel menu).  
- Use **Droplets**: Automate drag-and-drop workflows by creating **Droplets** (File › Automate › Create Droplet).  
- Protect Originals: Always run tests on **copies** of files before batch processing an entire folder.  
- Group Related Actions: Organize similar tasks (resize, watermark, color correction) into a single set.  

---

✅ With this process, you can standardize repetitive Photoshop tasks and apply them efficiently to hundreds of files.