# ObsidianMOC

**How to Use Maps of Content (MOCs) and Dataview to Manage Your Vault in Obsidian**

---
#### **Introduction**

Managing a growing knowledge base in Obsidian can be challenging, especially if you’re new to the app. Many users struggle with organizing their notes in a way that remains efficient and scalable as their vault grows. Fortunately, there’s a powerful and flexible method that can transform how you use Obsidian: combining Maps of Content (MOCs) and Dataview queries.

This method allows your vault to organize itself without constant manual upkeep, making it ideal for anyone looking for a long-term, scalable solution. In this guide, we’ll walk through everything from setting up your first MOC to managing complex subjects, all without needing any prior experience.

### **What is a Map of Content (MOC)?**

A **Map of Content**, or **MOC**, is like a navigational hub that organizes your notes around a particular topic. Think of it as a dynamic table of contents that lets you quickly access related notes under a single subject area. But there’s more to an MOC than just being a simple list of links—when combined with the **Dataview** plugin, your MOC becomes a **self-updating, dynamic index** that grows and evolves with your notes.

#### **Breaking Down an MOC Page**

At its most basic level, an MOC is structured with **Sections** (indicated by `# headers`), and each section can have **Subsections** (`## Subtopics`) and even more granular **Sub-subsections** (`### Sub-subtopics`). This hierarchical structure helps you organize your notes in an intuitive way, allowing for both broad overviews and specific details to be linked and categorized.

---

#### **Why MOCs are Different from Folder Systems**

In traditional note-taking systems, like a file and folder setup, you might create folders within folders to group your notes. For example, if you were organizing notes on philosophy, you might have:

- A **Philosophy folder** containing notes on different branches of philosophy like **Stoicism** and **Existentialism**.

While this folder approach works, it can become restrictive. As you accumulate more notes, you may find that a single note belongs to more than one folder, or that certain topics are too broad or narrow to fit neatly into a rigid folder structure.

**MOCs provide a flexible alternative** to this system. Instead of moving notes into multiple folders or creating complex folder hierarchies, you use MOCs to organize notes **by their content and context**. The advantage here is that a note can link to **multiple MOCs**, providing **cross-references** without having to duplicate the note or move it around manually.

#### **A Basic MOC Example**

Let’s say you’re building a **Philosophy MOC**. You could start with an overarching topic like **Philosophy** and then break it down into several subtopics like **Stoicism** and **Existentialism**, which are specific branches within the broader topic.

Here’s how your MOC structure might look at the start:

```
# Philosophy MOC

## Stoicism

## Existentialism

```

But this is just the beginning. You can further break down each subtopic into **sub-subtopics** (i.e., more detailed areas within Stoicism or Existentialism). For example, under Stoicism, you might want to include prominent Stoic figures like **Marcus Aurelius** or core concepts like **Virtue**.

Expanding on the example:

```
# Philosophy MOC

## Stoicism
### Marcus Aurelius
### Virtue

## Existentialism
### Jean-Paul Sartre
### Authenticity

```

Each of these sections can include Dataview queries or links that automatically pull in notes related to that specific subtopic or sub-subtopic.

---

#### **MOCs and Dynamic Content: How They Work with Dataview**

A key feature that makes MOCs so powerful is their ability to remain **dynamic** with the help of the Dataview plugin. Instead of manually updating your MOCs every time you create or modify a note, Dataview queries will automatically pull in notes that reference a specific section of the MOC.

For example, if you create a new note about **Marcus Aurelius**, and in that note you include a link back to the `[[Philosophy MOC#Stoicism]]` section, the note will automatically show up under the Stoicism section of your MOC, without you having to do anything extra. This turns your MOC into a **self-updating, living document**.

In practice, Dataview queries might look something like this:

```
Philosophy MOC (this is the note title)

## Stoicism
```dataview
list from ""
where contains(file.outlinks, [[Philosophy MOC#Stoicism]])
sort file.mtime desc

```

Marcus Aurelius
```
list from ""
where contains(file.outlinks, [[Philosophy MOC#Marcus Aurelius]])
sort file.mtime desc

```

Existentialism

```
list from ""
where contains(file.outlinks, [[Philosophy MOC#Existentialism]])
sort file.mtime desc

```

In this setup:

- **## Stoicism**: Will display all notes linking to the Stoicism section.
- **### Marcus Aurelius**: Will further refine the results to only show notes specifically about Marcus Aurelius.
- The same logic applies for Existentialism, Jean-Paul Sartre, and other sub-subtopics.

---

#### **Flexibility and Scalability with MOCs**

Because MOCs aren’t restricted by a rigid folder structure, they allow your vault to grow as much as needed, while still keeping everything organized. You can create as many subtopics and sub-subtopics as you need, and because each note can link to multiple MOCs, you won’t ever lose track of where a note belongs.

**Example**: If you have a note titled “Marcus Aurelius - Meditations,” this note can easily link to both the **Stoicism** and **Philosophy** MOCs, ensuring it shows up in both places without duplication. Likewise, if your note discusses **Virtue** as a core Stoic concept, you can link it to both `[[Stoicism#Virtue]]` and `[[Philosophy MOC]]`.

---

#### **Summary**

- **MOCs are more flexible** than traditional folders because they allow notes to be organized by content rather than by arbitrary file hierarchies.
- Using **# Sections**, **## Subtopics**, and **### Sub-subtopics**, you can create a detailed and intuitive structure to organize notes by specific topics and their subcategories.
- When combined with Dataview, MOCs automatically update themselves, meaning you never need to manually add or rearrange notes within your MOCs as your vault grows.
- MOCs also allow for **cross-referencing**, meaning the same note can appear in multiple MOCs, without the need to copy or duplicate the note.

In short, MOCs give you the freedom to organize your notes in a way that reflects the **content** and **context** of your information, while remaining scalable and dynamic as your vault expands.


---

### **Setting Up Your Vault: The Folder Structure**

Before diving into MOCs and Dataview, let’s start with your vault's overall structure. A simple, minimalist 3-folder structure is all you need:

1. **MapsOfContent** – This is where all your MOCs will live. Think of this as the central hub of your vault.
2. **Notes** – All your other notes go here, regardless of topic. The beauty of this system is that notes don’t need to be filed into various subfolders.
3. **Templates** – This folder holds templates you may use to ensure consistency across your notes.

With this structure, there’s no need to constantly reorganize notes into new folders as your vault grows. Everything will be automatically managed through MOCs and Dataview, which we’ll explain step-by-step.

---

### **Creating Your First MOC**

Let’s start by creating a basic MOC to see how it works.

1. **Create a New Note** In Obsidian, create a new note and give it a relevant title, such as `Philosophy MOC`. This will be the filename for the note, which is key to making sure everything stays linked and accessible.
    
2. **Structure Your MOC with Sections** Your MOC should include various sections that cover subtopics. For example, if your MOC is about philosophy, you might include sections like “Stoicism,” “Existentialism,” and “Ethics.”
    

Here’s what the structure might look like:

```
Philosophy MOC (this is the note title)

## Stoicism

## Existentialism

## Ethics
```

Each `# Section` or `## Subsection` serves as a container for related notes. As your vault grows, these sections will populate automatically with relevant notes, thanks to the Dataview plugin.

---

### **How Dataview Transforms MOCs into Dynamic Pages**

#### **What is Dataview?**

The Dataview plugin allows you to create dynamic lists that update in real-time as you add, modify, or remove notes. Instead of manually updating your MOCs, Dataview automatically pulls in any note that links to a specific section in your MOC.

#### **Adding Dataview Queries to Your MOC**

Now let’s see how Dataview turns your MOC into a dynamic content hub. Under each section header, you’ll add a Dataview query to pull in related notes. For example, to automatically display notes related to Stoicism, you can use this query:

```
list from ""
where contains(file.outlinks, [[Philosophy MOC#Stoicism]])
sort file.mtime desc

```

This query tells Dataview to:

- **Search**: Look for any notes that link to the `[[Philosophy MOC#Stoicism]]` section.
- **Sort**: Display the notes in order of when they were last modified.

The result will be a list of notes related to Stoicism, which will appear under the `## Stoicism` section of your MOC. Each time you create or update a note that links to Stoicism, this list will update automatically.

Repeat this process for the other sections, such as Existentialism and Ethics, by changing the query to match each section name. For example:

```
list from ""
where contains(file.outlinks, [[Philosophy MOC#Existentialism]])
sort file.mtime desc

```

Now, your MOC will dynamically pull in and display all relevant notes.

---

### **Linking Notes to MOCs**

In order for your notes to appear under the correct section in your MOC, you need to make sure that they link back to that section. This can be done easily by following a consistent note template.

#### **The Basic Note Template**

Each of your notes should include a link back to the relevant section of the MOC at the top. Here’s a template that you can use to ensure every note is connected to the right MOC:

```
#### **MapOfContent:** [[Philosophy MOC#Stoicism]]
---
Your note content goes here.


---
# References
- [[Link to relevant sources]]

```

By including the link `[[Philosophy MOC#Stoicism]]` in the `MapOfContent` field, you ensure that the note is categorized under the Stoicism section in your MOC. The Dataview query will pick up this link and display the note in the MOC automatically.

---

### **Managing Complex Subjects**

As your vault grows, certain MOCs may become too large to manage in a single page. When this happens, you can break out specific sections into their own dedicated MOCs. This ensures that your system remains scalable and organized, even as your vault expands.

#### **Scaling Out a Complex Topic: Promoting Sections into Their Own MOC**

Over time, as your vault grows, certain sections within a broader MOC can accumulate too many notes to be efficiently managed. When this happens, it’s often necessary to “promote” these sections into their own dedicated MOCs to maintain scalability and organization. This process involves not just creating a new MOC, but also **modifying links within the individual notes** so that they point to the new MOC.

Let’s walk through this process step-by-step using the **Technology MOC** example, which includes sections like **Coding**, **Linux**, and **Software Development**.

---

#### **Step-by-Step Guide to Scaling Out a Topic to Its Own MOC**

##### **1. Identifying When a Section Needs Its Own MOC**

As you add more notes to your vault, you might find that certain sections within a broader MOC, such as “Coding” within a **Technology MOC**, begin to feel too crowded. Maybe the number of individual notes about different programming languages or projects is growing, making it harder to navigate and maintain the original MOC.

This is the moment to consider **scaling out** the section into a standalone MOC.

---

##### **2. Creating a New MOC for the Promoted Section**

Once you’ve decided to split the topic into its own MOC, create a new note to serve as the dedicated MOC for that topic. For example, if the “Coding” section is becoming too large, you can create a new note called **Coding MOC**.

Here’s how the structure of your new **Coding MOC** might look:

```
Coding MOC (this is the note title)

## Python

## Bash

## JavaScript

```

This new MOC will contain the same subtopics that were originally in the **Technology MOC**, but now they are organized in a separate, dedicated space.

---

##### **3. Transferring the Sections**

Next, transfer the **subsections** related to coding from the **Technology MOC** to the newly created **Coding MOC**. If you previously had this in the Technology MOC:

```
# Technology MOC

## Coding
### Python
### Bash
### JavaScript

```

You’ll move these sections into the new **Coding MOC**. After this step, your **Technology MOC** will no longer include the coding sections, but the new **Coding MOC** will.

---

##### **4. Updating the Dataview Queries in Both MOCs**

Once you’ve moved the sections to the new MOC, it’s time to update the **Dataview queries** in both the original and the new MOCs to ensure that notes continue to be dynamically linked and displayed in the correct MOCs.

###### **In the Technology MOC**:

Modify the Dataview query that originally pulled in all “Coding” notes, so that it now links to the new **Coding MOC**:

```
list from ""
where contains(file.outlinks, [[Coding MOC]])
sort file.mtime desc

```

This updated query will pull in any note that links to the **Coding MOC**, allowing the **Technology MOC** to maintain access to coding-related content, but without displaying the details directly.

###### **In the Coding MOC**:

Add Dataview queries to the **Coding MOC** that pull in notes for each subsection (e.g., Python, Bash, JavaScript). For example, under “Python,” you’d use:

```
list from ""
where contains(file.outlinks, [[Coding MOC#Python]])
sort file.mtime desc

```

This ensures that all your Python-related notes are displayed under the “Python” subsection of the **Coding MOC**. You’ll repeat this process for the other subtopics like Bash and JavaScript.

---

##### **5. Updating Individual Notes with New MOC Links**

Here’s a critical step that ensures your MOC structure remains effective and functional: **updating the individual notes** themselves. When you promote a section into its own MOC, all the notes that previously linked to the old section in the **Technology MOC** (e.g., `[[Technology MOC#Coding]]`) must now be updated to point to the appropriate section in the **Coding MOC**.

###### **How to Update Your Notes:**

Go into each note that was linked to the original **Technology MOC#Coding** section and modify the **MapOfContent** links to point to the new MOC. For example, if you had a note about **Python** that was previously linked like this:

```
#### **MapOfContent:** [[Technology MOC#Coding]]

```

You will need to update it to:

```
#### **MapOfContent:** [[Coding MOC#Python]]

```

This ensures that the note is now properly categorized under the **Coding MOC** and is pulled into the relevant section of that MOC by the Dataview queries.

---

##### **6. Ensuring Scalability as You Continue to Grow**

This process of promoting sections into their own MOCs can be repeated as needed. For example, if the **Linux** section within your **Technology MOC** eventually becomes too large, you can follow the same steps to create a **Linux MOC**.

Each time you promote a section into its own MOC, it’s important to:

1. **Transfer the relevant sections** from the original MOC to the new MOC.
2. **Update the Dataview queries** in both MOCs to point to the right sections.
3. **Go into each individual note** and update the links in the **MapOfContent** section to reflect the new MOC.

This ensures that your MOCs remain clean, scalable, and interconnected.

---

#### **Why This Process is Essential for Scalability**

The reason it’s so important to update the links in the individual notes is because MOCs work by dynamically pulling in notes based on those links. If a note still points to `[[Technology MOC#Coding]]`, but the coding section has been moved to the **Coding MOC**, that note will no longer appear in the correct place. By taking the time to update each note’s link, you ensure that it remains correctly categorized and displayed.

Additionally, this approach **modularizes your vault**, so no single MOC becomes too large or difficult to manage. By scaling out sections into their own MOCs, you keep everything organized without sacrificing the ability to easily find and cross-reference your notes.

---

#### **Summary of the Scaling-Out Process**

1. **Create a New MOC** for the promoted section (e.g., `Coding MOC`).
2. **Transfer the Sections** from the original MOC (e.g., `Technology MOC`) to the new MOC.
3. **Update the Dataview Queries** in both MOCs to reflect the new structure.
4. **Modify the MOC Links** in each individual note to ensure they point to the correct MOC (e.g., `[[Coding MOC#Python]]` instead of `[[Technology MOC#Coding]]`).
5. **Repeat** this process as needed for other growing sections, ensuring that your vault remains scalable and easy to navigate.

This method allows you to seamlessly grow your vault, while keeping everything organized, interconnected, and accessible.

---

### **Why This System is Scalable and Efficient**

One of the main advantages of this system is its scalability. Unlike traditional folder structures, which require manual reorganization as your notes grow, MOCs and Dataview queries adapt automatically. Here are a few key reasons why this system works so well:

1. **Dynamic Organization**: Dataview ensures that MOCs are always up to date, without the need for manual updates. As long as your notes contain links to the relevant MOC sections, they’ll always be displayed in the right place.
    
2. **Minimal Manual Upkeep**: Since the MOCs organize themselves based on links and queries, you don’t need to spend time moving notes into different folders or adjusting your structure as your vault grows.
    
3. **Scalability**: Whether you have 50 notes or 5,000 notes, this system can handle it. As certain sections of your MOCs become more populated, you can simply split them into their own dedicated MOCs without disrupting the rest of the system.
    

---

### **Final Thoughts: Why MOCs with Dataview Are Superior for Vault Management**

Combining **Maps of Content (MOCs)** with the **Dataview** plugin transforms your Obsidian vault into a **self-organizing knowledge hub**. What makes this approach so powerful is its flexibility and scalability, allowing you to manage your vault efficiently—whether it contains a handful of notes or thousands of them. Let’s delve deeper into why this method is better, less work-intensive, and more efficient compared to other popular approaches for note management.

---

#### **1. Minimal Manual Upkeep: Let the System Work for You**

One of the standout advantages of using MOCs with Dataview is the **minimal manual intervention** required. In traditional folder-based systems, or even systems relying heavily on manual tags and links, you have to continually update the structure. Every time you create or modify a note, there’s an expectation to:

- Move it into the correct folder.
- Update any manually created index pages.
- Ensure that cross-references are accurately placed and updated.

In contrast, the **MOC + Dataview** system automates much of this overhead. With a single link to an MOC section (e.g., `[[Philosophy MOC#Stoicism]]`), your notes are dynamically categorized and displayed. Once the Dataview queries are in place, **they automatically pull in and update notes**, saving you from having to manually organize your notes into folders or manually curate index pages. This eliminates the constant reorganization that comes with other methods, allowing you to **focus on content creation** rather than content management.

---

#### **2. Infinite Scalability: No Need for Folder Creep**

In systems that rely on rigid folder structures, as your vault grows, so does the complexity of your folders. Over time, you find yourself endlessly creating new subfolders, trying to fit notes into categories. This phenomenon is often referred to as **"folder creep,"** where the number of folders becomes unmanageable, and finding the right folder for a note becomes more cumbersome than productive.

With the MOC + Dataview system, there is no need to create endless folders. **MOCs grow and evolve** with your vault, allowing you to dynamically organize content by **context and subject matter**, not by arbitrary file location. When a section within a MOC becomes too large (e.g., **Coding** in a **Technology MOC**), you simply promote it into its own MOC, as we discussed earlier, without changing the underlying structure of your vault.

By eliminating the need for constant folder restructuring, you reduce friction in your workflow, making it easier to find and reference notes regardless of how large your vault becomes.

---

#### **3. Flexibility: Notes Can Belong to Multiple MOCs**

Another key advantage of the MOC system is **flexibility**. In a traditional folder system, each note can only exist in one folder, which often limits how you can organize your information. For example, a note on **Marcus Aurelius** could fit under both **Philosophy** and **Stoicism**, but in a folder system, you’d have to choose just one location or create duplicate notes.

With MOCs, however, notes can easily belong to **multiple MOCs** without duplication. A note about **Marcus Aurelius - Meditations** can be linked to both `[[Philosophy MOC#Stoicism]]` and `[[History MOC#Roman Empire]]`, ensuring it appears under both subjects. This kind of **cross-linking** allows you to organize information according to its content and relevance to multiple subjects, without the limitations imposed by folders.

This flexibility also extends to the way you can **reuse and reorganize information**. If you start with a broad MOC and later find that certain sections grow too large, you can break them out into their own MOCs—promoting them as needed—without disrupting the underlying structure of your notes.

---

#### **4. Less Work, More Efficiency**

When comparing the MOC + Dataview approach to other popular methods, such as heavy reliance on tags, folders, or manually curated indexes, the MOC system is far more efficient for several reasons:

- **Tags Require Maintenance**: Systems based on tags often become cluttered and redundant. You must create and maintain a taxonomy of tags, which requires constant upkeep. Tags are useful for quick categorization, but they don’t provide the structured context that MOCs do, and they require manual intervention to create and curate. Moreover, tags don’t have the same **cross-referencing power** that MOCs provide when you use them in combination with Dataview queries.
    
- **Folders Are Rigid**: Folder-based systems can quickly become overwhelming as the number of notes grows. Once a note is placed in a folder, it’s not easy to make that same note accessible under different contexts, which can lead to a need for duplicated notes or complex, deep folder structures. With MOCs, you eliminate this rigidity. Notes can be linked to multiple MOCs without duplication, and MOCs themselves can evolve as your vault grows.
    
- **Manual Indexes Are Time-Consuming**: Systems that rely on manually curated indexes or manually updating links can become labor-intensive as your vault grows. Each time you create or modify a note, you must remember to update the relevant indexes or links. With Dataview, this process is **completely automated**—your MOCs update themselves every time a note is added, modified, or removed.
    

Ultimately, the MOC + Dataview approach reduces the cognitive load and the time spent managing your vault, making it a much more **hands-off, automated, and efficient system** compared to other methods.

---

#### **5. Adaptability: From Simple to Complex**

One of the most powerful aspects of this system is that it can grow with you. For beginners, starting with a few MOCs and simple Dataview queries is a straightforward way to begin organizing your notes. As your vault grows, you can introduce **more complex structures**, like:

- **Subtopics and Sub-subtopics**: As your MOCs become more detailed, you can easily add `## Subtopics` and `### Sub-subtopics` to further organize your content.
- **Cross-linking between MOCs**: Over time, as certain sections become more complex, you can create MOCs that link to other MOCs, effectively creating **a web of interlinked knowledge hubs**.

This adaptability allows the system to remain useful whether you have 10 notes or 10,000 notes. You’re never locked into a rigid system—you can evolve your MOCs as your knowledge expands, always maintaining an organized and connected vault.

---

### **Why MOCs with Dataview Are Better Than Other Methods**

- **Less manual intervention**: With MOCs and Dataview, your vault essentially organizes itself. You don’t need to constantly reorganize folders, update tags, or manually curate indexes.
    
- **More scalable**: This system can scale with the size of your vault. Whether you have a handful of notes or thousands, your MOCs and Dataview queries will handle the growing complexity without needing to restructure your vault.
    
- **Higher flexibility**: Unlike folders, which force you to choose a single location for each note, MOCs allow your notes to belong to multiple categories at once, reflecting the content and context more accurately.
    
- **Adaptable for all users**: Beginners can start with a simple MOC setup and gradually introduce more complexity as their vault grows. Advanced users can create interlinked MOCs, subtopics, and cross-referenced systems without overwhelming their workflow.
    

---

### **In Conclusion: A Self-Evolving System for Any Vault**

By combining MOCs with Dataview, you create a **living, dynamic structure** that organizes itself around your notes. This method eliminates the need for constant upkeep, allows for flexible organization, and scales effortlessly as your vault grows. Whether you’re managing a few notes for personal research or an extensive knowledge base, this system adapts to your needs, evolving alongside your growing vault.

Invest the time to experiment with this structure, and you’ll quickly see how it can transform the way you manage and interact with your notes—offering a far more streamlined, flexible, and efficient approach than other methods.
