# Gruut-cat-v.2
![PDF as Image](poster-final.png)
# ca-gruutv2

# Phonetic Transcriber improvement in Catalan

This project is an enhanced phonetic transcription system that combines a grapheme-to-phoneme (G2P), offering sophisticated phonetic conversion with improvements in preprocessing and database comparisons. 

## Key Improvements

1. **Database Comparison Codes**: Includes tools to compare and construct databases effectively, facilitating analysis and updates.
2. Final databases can be found at gruut-demo/gruut-demo/final_bases, and the models and lexicons can be found at gruut-demo/gruut-demo/data/ca-{dialect}
   where {dialect}={ca-ce,ca-no,ca-va,ca-ba}
   gruut-demo/gruut-demo also contains the ocdes used to do this data refinement "diferencies_entrenament.py", "lev_dis.py"
   
3. **Tonic Vowel Distribution**: Enhanced preprocessing steps address the distribution of tonic vowels, improving the accuracy of stress placement.
    Changes in the preprocessing, in the function giving each word a tonic accent, making dictionaries of common distributions of phonemes.
      
4. **Accent Correction**: Corrected handling of words with multiple accents, and introduced vowel reduction to resolve inaccuracies in such cases.
   with the reduction implied in each dialect:

    vowel_reduction_eastern = {
    ' ɛ ': ' ə ',
    ' e ': ' ə ',
    ' a ': ' ə ',
    ' ɔ ': ' u ',
    ' o ': ' u ',}

    vowel_reduction_western = {
    ' ɛ ': ' e ',
    ' ɔ ': ' o '}

    vowel_reduction_balearic = {
    ' ɛ ': ' ə ',
    ' e ': ' ə ',
    ' a ': ' ə ',
    ' ɔ ': ' o ',}


  
7. **Vocalic Contact Between Words**: Added support for handling vowel-to-vowel interactions between consecutive words, ensuring phonetic continuity.

gruut --language "ca-ce" "quinze anys"
"{ k 'i n z } { 'a ɲ s }"

gruut --language "ca-ce" "cara oberta"
"{ k 'a ɾ ə } { w β 'ɛ r t ə }"



8. **Consonantic Contact Between Words**: Improved handling of consonant-to-consonant transitions between words, supporting smoother phonetic transitions in connected speech.

gruut --language "ca-ce" "peix alat"
"{ p 'ɛ ʒ } { ə l 'a t }"

gruut --language "ca-ce" "has arribat"
"{ 'a z } { ə r i β 'a t }"

gruut --language "ca-va" "ara dono"
"{ 'a ɾ a } { ð 'o n o }"


## Prerequisites

- Python 3.7+
- Required libraries installed (e.g., `sqlite3`, `typing`, and `pathlib`)

## Files
# Assuming all necessary models and lexicons are properly set up
g2p_model_path = "gruut-demo/data/ca-{dialect}/g2p/model.crf"
lexicon_db_path = "gruut-demo/data/ca-{dialect}//lexicon.db"

