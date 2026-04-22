# Lab: Investigating Historical Fragments — OSINT Case: Letter

## Room Metadata
- **Platform:** [TryHackMe](https://tryhackme.com/)
- **Category:** Purple Team / OSINT
- **Room:** [Letter](https://tryhackme.com/room/letter)
- **Difficulty:** Easy
- **Status:** `Completed`

## Objective
**Goal:** Analyze water-damaged physical artifacts—an envelope, a newspaper clipping, and a handwritten note—to identify the full name and age of the individual referenced in the correspondence.

## Tools Used
* **Artifact Analysis:** Manual inspection of digital images (Envelope, Clipping, Note).
* **Search Engines:** Google for geographical and historical record correlation.
* **Geographical Mapping:** Postal code verification for location context.

## Methodology

### Phase 1: Artifact Triage & Data Extraction
1.  **Envelope Inspection:** Analyzed the delivery address to isolate geographical markers. Extracted the postal code **29760** (Brittany, France) to establish a localized search area.
2.  **Clipping Analysis:** Evaluated a faded newspaper clipping. Despite the water damage, key phrases and the localized nature of the clipping pointed toward specific regional events or notices.
3.  **Note Correlation:** Analyzed a handwritten note for personal names and context clues that could be cross-referenced with the newspaper's archives.

### Phase 2: OSINT Pivot & Identification
1.  **Geographical Filtering:** Used the postal code and fragments of the address to identify the specific commune or town associated with the delivery.
2.  **Database Interrogation:** Cross-referenced the localized search area with the fragments of the name found in the note and clipping. 
3.  **Flag Construction:** Successfully identified the subject as a 15-year-old individual, leading to the final attribution.

---

## Key Findings
* **Postal Code identified:** `29760`
* **Target Identity:** `Yves-Marie Gourlaouen`
* **Target Age:** `15`
* **Final Flag:** `THM{Yves-Marie_Gourlaouen_15}`

## Reflection
**Real-World Context:** OSINT is rarely about a single "silver bullet" search query; it is about the **logic of connection**. This lab mirrors the process of **Attacker Attribution**—taking "broken" indicators (like a battered envelope) and using them to pivot into verified identities. In a professional security context, this skill is vital for uncovering the real-world actors behind digital footprints. Much like diagnosing a historical failure in an aerospace component, every fragment of evidence is a diagnostic lead waiting to be followed.

