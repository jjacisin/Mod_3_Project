# Mod_3_Project

--Model Goal:
  --Medicaid reviews the average price of certain drug ingredients in the US to determine if they breach the federal upper limit (FUL)
  --We want to build a model that will predict whether a given ingredient (or combination of ingredients) will breach the FUL based on:
    --Ingredient Name
    --Associated ingredient(s)
    --Strength of an ingredient(s) (or dosage)
    --Form of medication (i.e. tablet, etc.)
    --Route (i.e. Oral, etc.)
    --package size
  --Our target for this data set will be whether or not the Medicaid has determined that an ingredient is in violation of the 175% average manufacturer price

--Stretch Goal:
  --Look at the model's predictions to identify which ingredients are most likely to be above FUL and determine what they are used for


Data Source:
  -- http://www.nber.org/data/federal-upper-limits/2017/
    --Dataset explainer: https://www.medicaid.gov/medicaid-chip-program-information/by-topics/prescription-drugs/true-up/xxxxxdraft-true-up-methodology.pdf
    -- FUL Explainer: https://www.medicaid.gov/medicaid/prescription-drugs/federal-upper-limits/index.html
  -- Explanation of why same ingredients have different forms/strengths:

    -- https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3305679/
      -- Justification for using built in strength dosages
        -- Excerpt:
            -- Partly, this may be due to the difficulty in defining a drug entity in text. In the earlier work that involved automatic drug entity identification [6-9], a drug was simply defined by its generic name/active ingredient. Such approximation may be appropriate for those applications but to formally define a drug, other important specifications should be considered. For instance, a drug's dosage form (DF) indicates the physical form in which a drug is produced and dispensed. It is one of the most important specifications of a drug because it affects the way a drug is administrated in a patient. Drugs with the same ingredients but in different dosage forms can have different uses. For example, if timolol comes as ophthalmic solution (eye drops), it is used to treat glaucoma. If timolol comes as an oral tablet, it is used to treat high blood pressure, to improve survival after a heart attack, and to prevent migraine headaches. Furthermore, dosage forms affect drug absorption and drug distribution in the human body. So in order to confirm drug efficacy and optimize drug therapy, drug pharmacokinetic and pharmacodynamic properties should be modeled and experimented across different dosage forms. For example, tacrolimus, a macrolide with potent immunosuppressive effects, can come as oral capsule and injectable solution. Its pharmacokinetic properties were studied across intravenous, oral, and intramuscular dosage forms [10]. Because of the importance of dosage form in drug development and consumption, it is crucial to provide accurate dosage form information in drug-related information resources.
      --Justification for appropriateness of features:
        --Excerpt
          -- Recent studies have focused on extracting both drug names and related attributes such as strength, route, frequency, form, and duration.
      --Side Bar re NLP:
        -- There was no requirement for normalizing mentions to any standardized nomenclature. More recently, several Natural Language Processing (NLP) systems such as MedEx [13] and MTERMS [14] have been developed to automatically normalize identified drugs to concepts in one or multiple terminologies. These research efforts contribute to the field of automated medication reconciliation across the care continuum [15,16]. They successfully applied NLP techniques to summarize and encode the medication data with high performance (F-Measure > 90%). In these systems, mentions of drug dosage form are captured from clinical narratives but not further normalized to a standard controlled vocabulary.

Future Improvements:
  --Classify drugs
    --add drug types to model
      --http://sideeffects.embl.de/download/
    --Classifications
      --https://en.wikipedia.org/wiki/Anatomical_Therapeutic_Chemical_Classification_System

Current Thoughts:
  --MU: Working to find additional information about the drugs in scope
  --JJ: Write functions that pulls data from Medicare website
    --Provide MU with setlist of ingredients




    **Sourced from WebMD and drugbank.ca
    Most Likely to Be Above FUL:
    BENAZEPRIL HCL
     	Benazepril is used to treat high blood pressure (hypertension). Lowering high blood pressurehelps prevent strokes, heart attacks, and kidney problems. Benazepril is an ACE inhibitor and works by relaxing blood vessels so that blood can flow more easily.
    LOVASTATIN	Lovastatin is used along with a proper diet to help lower "bad" cholesterol and fats (such as LDL, triglycerides) and raise "good" cholesterol (HDL) in the blood. It belongs to a group of drugs known as "statins." It works by reducing the amount of cholesterol made by the liver. Lowering "bad" cholesterol and triglycerides and raising "good" cholesterol decreases the risk of heart disease and helps prevent strokes and heart attacks.
    HCTZ	his medication is used to treat high blood pressure. Lowering high blood pressure helps prevent strokes, heart attacks, and kidney problems. Hydrochlorothiazide belongs to a class of drugs known as diuretics/"water pills." It works by causing you to make more urine. This helps your body get rid of extra salt and water.
    ROSUVASTATIN CALCIUM	Rosuvastatin is used along with a proper diet to help lower "bad" cholesterol and fats (such as LDL, triglycerides) and raise "good" cholesterol (HDL) in the blood. It belongs to a group of drugs known as "statins." It works by reducing the amount of cholesterol made by the liver. Lowering "bad" cholesterol and triglycerides and raising "good" cholesterol decreases the risk of heart disease and helps to prevent strokes and heart attacks.

    DICLOFENAC SODIUM	Diclofenac is used to relieve pain, swelling (inflammation), and joint stiffness caused by arthritis. Reducing these symptoms helps you do more of your normal daily activities. This medication is known as a nonsteroidal anti-inflammatory drug (NSAID).
    **Sourced from WebMD and drugbank.ca
    Least Likely to Be Above FUL:
    PHENYTOIN	An anticonvulsant that is used in a wide variety of seizures. It is also an anti-arrhythmic and a muscle relaxant.
    VALSARTAN	Valsartan is an angiotensin-receptor blocker (ARB) that may be used to treat a variety of cardiac conditions including hypertension, diabetic nephropathy and heart failure. Valsartan lowers blood pressure by antagonizing the renin-angiotensin-aldosterone system (RAAS)
    AMLODIPINE BESYLATE	Amlodipine is used with or without other medications to treat high blood pressure. Lowering high blood pressure helps prevent strokes, heart attacks, and kidney problems. Amlodipine belongs to a class of drugs known as calcium channel blockers. It works by relaxing bloodvessels so blood can flow more easily.
    Amlodipine is also used to prevent certain types of chest pain (angina). It may help to increase your ability to exercise and decrease the frequency of angina attacks. It should not be used to treat attacks of chest pain when they occur. Use other medications (such as sublingual nitroglycerin) to relieve attacks of chest pain as directed by your doctor.]
    LISINOPRIL	Lisinopril is used to treat high blood pressure. Lowering high blood pressure helps prevent strokes, heart attacks, and kidney problems. It is also used to treat heart failure and to improve survival after a heart attack.
    Lisinopril belongs to a class of drugs known as ACE inhibitors. It works by relaxing blood vessels so blood can flow more easily.

     'CYCLOSPORINE']	Cyclosporine is used to prevent organ rejection in people who have received a liver, kidney, or heart transplant. It is usually taken along with other medications to allow your new organ to function normally. Cyclosporine belongs to a class of drugs known as immunosuppressants. It works by weakening the immune system to help your body accept the new organ as if it were your own.
