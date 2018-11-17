
## Speech2Text using GCP Speech API
## GCP Speech API on noised audio data

### Goal : 
Send a speech recognition request to Cloud Speech-to-Text in python programming language using speech_recognition API which gathers all benchmark APIs (Google, IBM etc.).
This overview of the solution shows how GCP Speech API is sensible to noised data which makes it lack from distinguishing different signal levels in audio data.

## Dependencies
### Command lines - Linux

To get this straight, please download your api key file from Google Cloud Platform after following their instructions on how to start using Speech API. You will have to download Google Cloud Platform client API to make requests after creating a project on your GCP console.


```python
#!pip install ffmpeg
#!pip3 install -r requirements.txt
```


```python
# set up folders
import os

path = os.path.join(os.getcwd(), "parts")
path_simple = os.path.join(path, "parts_simple")
path_audio = os.path.join(path, "parts_audio")
                           
if not os.path.exists(path):
    os.mkdir(path)
if not os.path.exists(path_simple):
    os.mkdir(path_simple)
if not os.path.exists(path_audio):
    os.mkdir(path_audio)
```


```python
import speech_recognition as sr
from tqdm import tqdm

import IPython
```


```python
!ffmpeg -i sources/simple.wav -f segment -segment_time 30 -c copy parts/parts_simple/out%09d.wav
!ffmpeg -i sources/audio.wav -f segment -segment_time 30 -c copy parts/parts_audio/out%09d.wav
```

## Noiseless audio sample - A children story


```python
IPython.display.Audio('sources/simple.wav')
```

### Speech to text


```python
# MAKE SURE YOU GET YOUR OWN API KEY FILE USING GCLOUD COMMAND LINE
with open("api-key.json") as f:
    GOOGLE_CLOUD_SPEECH_CREDENTIALS = f.read()

r = sr.Recognizer()
files = sorted(os.listdir('parts/parts_simple'))
    
all_text = []
for f in tqdm(files):
    name = 'parts/parts_simple/' + f
    # Load audio file
    with sr.AudioFile(name) as source:
        audio = r.record(source)
    # Transcribe audio file
    text = r.recognize_google_cloud(audio, language='fr-FR', 
                                    credentials_json=GOOGLE_CLOUD_SPEECH_CREDENTIALS)
    all_text.append(text)
print(all_text)
```

    100%|██████████| 9/9 [01:24<00:00,  7.95s/it]

    ["le lion et la souris il était une fois un lion vivait dans la forêt qu'il gouvernait un jour après avoir mangé son repas le lion s'endort mis sous un arbre une petite souris et pensais qu'il serait amusant de jouer sur lui elle commença à monter et descendre au courant ", "sur le lion endormi elle courait pour monter sur la queue et se laisser glisser pour descendre le lionceau d'enrichissement d'un collègue le nom des grosses machines pour la valeur de la cellule ", "fait très peur s'il te plaît ne me mange pas pardonne-moi pour cette fois et laisse-moi partir je ne l'oublierai jamais et peut-être même 15 jours c'est moi qui t'aiderai le lion pas réussi amusé à l'idée que la souris puisse être capable de l'aider qu'il ouvrit ça quand il a laissé repartir mais ta beauté mon ami tu as de la chance que j'ai déjà mangé par matin ", "minozia plus m'embêter car alors je ferai de toi mon prochain repas quelques jours plus tard le lion errer dans la jungle que sa sœur verte installer un piège pour attraper le bio les chasseurs se cacher derrière un arbre en attendant que le lion s'approche du piège dans 5 mois prochain ", "le lion guitariste est mort de ses chasseurs à ta chère ils retournèrent ton village pour importer un chariot afin de transporter le nom était toujours en train de rougir très fort tous les animaux y compris la souris l'entendit rue si je dois lui rendre service à mon tour ", "la souris rejoignit le lion je vais te libérer sur le piège est utilisé par libérer le lion le lion réalisé alors que même une toute petite souris pouvait être d'une grande aide merci ", 'plus jamais je ne te ferai de problème librement dans la forêt qui a sauvé la vie du roi désormais tu es la princesse de cette forêt merci mon va au revoir à bientôt ', "la souris commence à sauter sur son dos et a laissé son sac au bout d'un moment les chasseurs revint avec un gros chariot pour transporter le lion le lion est arrivé et commencer à courir dans leur dire ", 'est-ce que le lion et la souris de bar des amis pour toujours ']


    


## Noisy audio sample from LaManche 


```python
IPython.display.Audio('sources/audio.wav')
```

### Speech to text


```python
with open("api-key.json") as f:
    GOOGLE_CLOUD_SPEECH_CREDENTIALS = f.read()
    
r = sr.Recognizer()
files = sorted(os.listdir('parts/parts_audio'))
    
all_text_fr = []
for f in tqdm(files):
    name = 'parts/parts_audio/' + f
    # Load audio file
    with sr.AudioFile(name) as source:
        audio = r.record(source)
    # Transcribe audio file
    text = r.recognize_google_cloud(audio, language='fr-FR',
                                    credentials_json=GOOGLE_CLOUD_SPEECH_CREDENTIALS)
    all_text_fr.append(text)
print(all_text_fr)
```

    100%|██████████| 20/20 [04:28<00:00, 11.58s/it]

    ['oui oui oui voilà ', "j'ai fait une fois la religion que j'avais pris quelques mots ", 'catalogue de Marie été réceptif ah oui ah oui il a mis des photos et puis ', 'les gamins avec des petites ciboulette ', 'viens me contenter de peu parce que vous étiez un garçon vous aviez des choses différentes et parce que vous étiez autre chose aller chercher des trucs pour les cochons ', 'il a pété de fonctionner ', "alors des feuilles d'ortie tant qu'à mettez toutes les banques à découper Liverdun ", 'alors là tu vas vous savez où tu tiens ma belle oui oui ', "c'est du travail de chercher des belles Oui-Oui ", "qui chante ça fait j'avoue que maintenant il faut bien serrer cordon ", 'à côté de la Roumanie ', 'nourriture des feuilles de poney après ça fonctionne ', 'changer le bruit du cochon et que maintenant et leur donne tout embrasser au boulot ', "c'était agréable ", 'aller travailler ', 'ah bon tu les as rentré insulte ', "aller à mes petits bonheurs fils de l'heure pour venir dîner ", "c'était pour ça ", 'ah non ah non ah non ah non ', 'détruit toutes les alarmes ']


    

