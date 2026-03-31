# 🧠 Նախագիծ: Neural Network Visualizer — Ուղղորդված ուղի

**Ժամանակացույց:** 2 շաբաթ  
**Բարդություն:** ⭐⭐ Ուղղորդված  
**Կարող եք օգտագործել:** Պաշտոնական փաստաթղթեր (Official documentation), Stack Overflow, AI գործիքներ հասկացությունները հասկանալու համար — բայց ամբողջ կոդը պետք է գրվի և հասկացվի ձեր կողմից: Հարցման դեպքում դուք պետք է կարողանաք բացատրել ձեր կոդի ցանկացած տող:

---

## 📖 Նախքան սկսելը — Հիմնական հասկացություններ
Կարդացեք սրանցից յուրաքանչյուրը ուշադիր: Դրանք բացատրում են, թե **ինչու** ենք մենք անում որոշակի բաներ, այլ ոչ թե միայն **ինչպես**:

### Ի՞նչ է Virtual Environment-ը:
Պատկերացրեք ձեր համակարգիչը որպես խոհանոց, որը կիսում են շատ շեֆ-խոհարարներ (նախագծեր): Եթե մի խոհարարին պետք է աղի 1.0 տարբերակը, իսկ մյուսին՝ աղի 2.0 տարբերակը, նրանք կբախվեն: **Virtual environment**-ը յուրաքանչյուր նախագծին տալիս է իր սեփական մասնավոր խոհանոցը:  
**Կանոն:** Միշտ ակտիվացրեք ձեր virtual environment-ը նախագծի վրա աշխատելուց առաջ:

### Ի՞նչ է requirements.txt-ն:
Պատկերացրեք, թե դուք տորթ եք թխել, և ձեր ընկերը ցանկանում է պատրաստել նույնը: Դուք նրան կտաք բաղադրատոմս՝ ճշգրիտ բաղադրիչներով: **requirements.txt**-ն հենց այդ բաղադրատոմսն է Python փաթեթների (packages) համար.
```text
plotly>=5.18
numpy>=1.24
```
Այժմ ցանկացած ոք կարող է մուտքագրել `pip install -r requirements.txt` և ստանալ ճիշտ նույն փաթեթները, որոնք դուք եք օգտագործել:

### Ի՞նչ է .gitignore-ը:
Որոշ ֆայլեր **շատ մեծ են** կամ **շատ անձնական** GitHub-ում տեղադրելու համար: **.gitignore** ֆայլը այն ֆայլերի ցանկն է, որոնք Git-ը պետք է ձևացնի, թե գոյություն չունեն: Դուք երբեք չպետք է վերբեռնեք (upload).
* `venv/` — ձեր virtual environment-ը (կարող է լինել 200+ MB)
* `__pycache__/` — ավտոմատ գեներացվող «աղբ» ֆայլեր
* `outputs/` — ֆայլեր, որոնք ցանկացած ոք կարող է վերագեներացնել՝ աշխատեցնելով ձեր կոդը

### Ի՞նչ է Neural Network-ը: (Պարզեցված)
Պատկերացրեք, դուք ունեք կետեր էջի վրա՝ որոշները կարմիր, որոշները կապույտ, խառնված իրար: Դուք ցանկանում եք գծել մի ալիքաձև գիծ, որը բաժանում է դրանց: **Neural network**-ը սովորում է, թե որտեղ գծել այդ գիծը հետևյալ կերպ.
1. Կռահել պատահականորեն
2. Ստուգել, թե որքան սխալ էր կռահումը (**loss**)
3. Մի փոքր ուղղել կռահումը
4. Կրկնել հարյուրավոր անգամներ (**epochs**)
Կռահել-ստուգել-ուղղել յուրաքանչյուր փուլը մեկ մարզման քայլ է: Բավարար քայլերից հետո գիծը գեղեցիկ տեղավորվում է դասերի միջև:

### Ի՞նչ է Plotly-ն:
Plotly-ն ստեղծում է **ինտերակտիվ գրաֆիկներ** — դուք կարող եք պահել մկնիկը արժեքները տեսնելու համար, մեծացնել (zoom), պտտել 3D գրաֆիկները և արտահանել ամեն ինչ որպես HTML ֆայլ, որը բացվում է ցանկացած բրաուզերում: Սա այն է, ինչ մենք կօգտագործենք մեր նեյրոնային ցանցը վիզուալիզացնելու համար:

### Ի՞նչ է go-ն ընդդեմ px-ի:
Plotly-ն ունի երկու հիմնական ինտերֆեյս.
* **plotly.express (px)** — արագ և հեշտ, հիանալի է պարզ գրաֆիկների համար: Ինչպես Instagram-ի ֆիլտրերը՝ ընտրեք մեկը և վերջ:
* **plotly.graph_objects (go)** — լիակատար վերահսկողություն, ավելի շատ կոդ, բայց դուք կարող եք հարմարեցնել ամեն ինչ: Ինչպես Photoshop-ը: Մենք կօգտագործենք **երկուսն էլ** այս նախագծում:

---

## 🖥️ ՕՀ-ին հատուկ հրամանների տեղեկատու
Այս նախագծի ընթացքում տերմինալի որոշ հրամաններ տարբերվում են ըստ օպերացիոն համակարգի (OS): Այս բաժինը ձեր «հուշաթերթիկն» է (cheat sheet):

### 🍎 macOS
```bash
# Python — macOS-ը հաճախ պահանջում է "python3"՝ "python"-ի փոխարեն
python3 --version                    # Ստուգել Python-ի տարբերակը
python3 -m venv venv                 # Ստեղծել virtual environment
source venv/bin/activate             # Ակտիվացնել virtual environment
deactivate                           # Ապաակտիվացնել virtual environment
pip3 install -r requirements.txt     # Տեղադրել փաթեթները
python3 data/generate.py             # Աշխատեցնել սկրիպտը
python3 main.py                      # Աշխատեցնել հիմնական pipeline-ը

# Թղթապանակի ստեղծում
mkdir nn-visualizer-guided           # Ստեղծել թղթապանակ
cd nn-visualizer-guided              # Մտնել թղթապանակ
mkdir -p data model viz outputs      # Ստեղծել մի քանի թղթապանակներ

# Git
git init                             # Նախաձեռնել (initialize) ռեպոզիտորիան
git add requirements.txt .gitignore  # Ավելացնել ֆայլերը staging area
git commit -m "your message"         # Կատարել քոմիթ (commit) հաղորդագրությամբ
git log --oneline                    # Դիտել քոմիթների պատմությունը
git remote add origin <URL>          # Միանալ GitHub-ին
git push -u origin main              # Վերբեռնել GitHub (առաջին անգամ)
git push                             # Վերբեռնել GitHub (հետագայում)
```

### 🪟 Windows (Command Prompt)
```cmd
# Python — Windows-ը սովորաբար օգտագործում է "python" (ոչ թե python3)
python --version                     # Ստուգել Python-ի տարբերակը
python -m venv venv                  # Ստեղծել virtual environment
venv\Scripts\activate                # Ակտիվացնել virtual environment
deactivate                           # Ապաակտիվացնել virtual environment
pip install -r requirements.txt      # Տեղադրել փաթեթները
python data\generate.py              # Աշխատեցնել սկրիպտը
python main.py                       # Աշխատեցնել հիմնական pipeline-ը

# Թղթապանակի ստեղծում
mkdir nn-visualizer-guided           # Ստեղծել թղթապանակ
cd nn-visualizer-guided              # Մտնել թղթապանակ
mkdir data model viz outputs         # Ստեղծել թղթապանակներ

# Git (նույնն է բոլոր ՕՀ-ների համար)
git init
git add requirements.txt .gitignore
git commit -m "your message"
git log --oneline
git remote add origin <URL>
git push -u origin main
git push
```

### 🐧 Linux (Bash)
```bash
# Python — Linux դիստրիբյուտիվների մեծ մասն օգտագործում է "python3"
python3 --version                    # Ստուգել Python-ի տարբերակը
python3 -m venv venv                 # Ստեղծել virtual environment
source venv/bin/activate             # Ակտիվացնել virtual environment
deactivate                           # Ապաակտիվացնել virtual environment
pip install -r requirements.txt      # Տեղադրել փաթեթները
python3 data/generate.py             # Աշխատեցնել սկրիպտը
python3 main.py                      # Աշխատեցնել հիմնական pipeline-ը

# Թղթապանակի ստեղծում
mkdir nn-visualizer-guided           # Ստեղծել թղթապանակ
cd nn-visualizer-guided              # Մտնել թղթապանակ
mkdir -p data model viz outputs      # Ստեղծել թղթապանակներ

# Git (նույնն է բոլոր ՕՀ-ների համար)
git init
git add requirements.txt .gitignore
git commit -m "your message"
git log --oneline
git remote add origin <URL>
git push -u origin main
git push
```

💡 **Նշում python-ի և python3-ի վերաբերյալ:** macOS-ում և Linux-ում `python`-ը երբեմն մատնանշում է Python 2-ը (որը հնացած է): Միշտ օգտագործեք `python3` ապահով լինելու համար: Windows-ում տեղադրող ծրագիրը սովորաբար կարգավորում է `python`-ը որպես Python 3: Ստուգելու համար աշխատեցրեք `python --version` — եթե այն ասում է 2.x, անցեք `python3`-ի:  
💡 **Նշում path separators-ի վերաբերյալ:** macOS-ը և Linux-ը օգտագործում են forward slashes (`data/generate.py`): Windows-ը օգտագործում է backslashes (`data\generate.py`): Python կոդի մեջ միշտ օգտագործեք forward slashes կամ `os.path.join()` — Python-ը կկատարի փոխակերպումը ձեր փոխարեն:

---

## 🗂 Պահանջվող ռեպոզիտորիայի կառուցվածքը
Ձեր GitHub ռեպոզիտորիան պետք է ունենա հետևյալ տեսքը.

```text
nn-visualizer-guided/
│
├── README.md                  # ԴՈՒՔ եք գրում սա — նկարագրեք ձեր նախագիծը
├── requirements.txt           # Փաթեթների ցանկ (տրված է ստորև)
├── .gitignore                 # Բացառվող ֆայլեր (տրված է ստորև)
│
├── data/
│   └── generate.py            # Առաջադրանք 1
│
├── model/
│   └── train.py               # Առաջադրանք 2
│
├── viz/
│   ├── scatter2d.py           # Առաջադրանք 3
│   ├── training_curves.py     # Առաջադրանք 4
│   ├── decision_boundary.py   # Առաջադրանք 5
│   └── scatter3d.py           # Առաջադրանք 6
│
├── outputs/                   # Ձեր արտահանված .html գրաֆիկները այստեղ են
│
└── main.py                    # Աշխատեցնում է ամեն ինչ
```

**Ինչո՞ւ առանձին ֆայլեր:** Յուրաքանչյուր ֆայլ անում է ՄԵԿ բան: Սա հեշտացնում է կոդը գտնելը, սխալները (bugs) ուղղելը և մի մասի վրա աշխատելը՝ առանց մյուսները փչացնելու: Իրական ծրագրային թիմերը միշտ այսպես են կազմակերպում կոդը:

---

## ⚙️ Կարգավորում (Setup) — Հետևեք այս քայլերին ճշգրիտ
Ընտրեք ձեր օպերացիոն համակարգը և հետևեք քայլերին.

**🍎 macOS / 🐧 Linux**
```bash
mkdir nn-visualizer-guided && cd nn-visualizer-guided
git init
mkdir -p data model viz outputs
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

**🪟 Windows**
```cmd
mkdir nn-visualizer-guided
cd nn-visualizer-guided
git init
mkdir data model viz outputs
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

Պատճենեք սա **requirements.txt**-ի մեջ.
```text
numpy>=1.24
pandas>=2.0
plotly>=5.18
scikit-learn>=1.3
torch>=2.0
```

Պատճենեք սա **.gitignore**-ի մեջ.
```text
venv/
__pycache__/
*.pyc
outputs/*.html
.DS_Store
```

Կատարեք ձեր առաջին քոմիթը.
```bash
git add requirements.txt .gitignore
git commit -m "Initial setup: add requirements and gitignore"
```

✅ **Checkpoint:** Դուք այժմ պետք է ունենաք Git ռեպո մեկ քոմիթով: Ստուգելու համար աշխատեցրեք `git log --oneline`:

---

## 📝 Առաջադրանքներ

### Առաջադրանք 1 — Գեներացնել տվյալների բազան (10 միավոր)
Ֆայլ՝ `data/generate.py`: Մենք կօգտագործենք ներկառուցված տվյալների բազա, որը կոչվում է **"moons"** — երկու կիսալուսնաձև պատկերներ, որոնք համընկնում են:  
**Աշխատեցրեք ավարտելիս.**
* macOS/Linux: `python3 data/generate.py`
* Windows: `python data\generate.py`

Մեկնարկային կոդ — լրացրեք **TODO** մասերը.
```python
"""
Dataset Generation
==================
Այս սկրիպտը ստեղծում է 2D "moons" տվյալների բազա binary classification-ի համար
և պահպանում այն որպես CSV ֆայլ:
"""
import numpy as np
import pandas as pd
from sklearn.datasets import make_moons
from sklearn.preprocessing import StandardScaler

def generate_dataset(n_samples=1000, noise=0.2, random_state=42):
    """
    Գեներացնել 2D moons տվյալների բազա:
    """
    # Քայլ 1: Գեներացնել լուսինները
    X, y = make_moons(n_samples=n_samples, noise=noise, random_state=random_state)

    # Քայլ 2: Ստանդարտացնել հատկանիշները (Standardize features)
    # StandardScaler-ը տվյալները կենտրոնացնում է 0-ի շուրջ՝ 1 ստանդարտ շեղմամբ
    scaler = StandardScaler()
    X = scaler.fit_transform(X)

    # Քայլ 3: Ստեղծել DataFrame
    # TODO: Ստեղծել pandas DataFrame 'x1', 'x2', 'label' սյուներով
    # Հուշում: X-ն ունի (1000, 2) ձև — սյուն 0-ն x1-ն է, սյուն 1-ը՝ x2-ը
    df = ...  # ՁԵՐ ԿՈԴԸ ԱՅՍՏԵՂ

    return df

if __name__ == "__main__":
    df = generate_dataset()
    print(f"Dataset shape: {df.shape}")
    print(f"Class distribution:\n{df['label'].value_counts()}")

    # TODO: Պահպանել DataFrame-ը data/dataset.csv հասցեով
    # Հուշում: df.to_csv("path/to/file.csv", index=False)
    ...  # ՁԵՐ ԿՈԴԸ ԱՅՍՏԵՂ
    print("Dataset saved to data/dataset.csv")
```

**Ի՞նչ է `if __name__ == "__main__":`-ը:**
Երբ Python-ը աշխատեցնում է ֆայլը ուղղակիորեն, այն սահմանում է հատուկ փոփոխական `__name__`-ը որպես `"__main__"`: Եթե մեկ այլ ֆայլ ներմուծում (import) է այն, `__name__`-ը դառնում է մոդուլի անունը: Այս բլոկը նշանակում է՝ «աշխատեցրու այս կոդը միայն այն ժամանակ, երբ ֆայլը կատարվում է ուղղակիորեն»:

Ավարտելուց հետո կատարեք քոմիթ.
```bash
git add data/generate.py
git commit -m "feat: add dataset generation script"
```

---

### Առաջադրանք 2 — Մարզել նեյրոնային ցանցը (15 միավոր)
Ֆայլ՝ `model/train.py`: Մենք կկառուցենք պարզ նեյրոնային ցանց PyTorch-ով:

**Աշխատեցրեք ավարտելիս.**
* macOS/Linux: `python3 model/train.py`
* Windows: `python model\train.py`

Մեկնարկային կոդ — լրացրեք **TODO** մասերը.
```python
"""
Neural Network Training
========================
Այս սկրիպտը սահմանում է նեյրոնային ցանց, մարզում է այն և պահպանում կշիռները:
"""
import json
import numpy as np
import pandas as pd
import torch
import torch.nn as nn
from sklearn.model_selection import train_test_split

# ─── Քայլ 1: Սահմանել նեյրոնային ցանցը ───────────────────────
class MoonClassifier(nn.Module):
    """
    Պարզ feedforward նեյրոնային ցանց:
    Ճարտարապետություն:
        Input (2 features) -> Hidden 1 (32 neurons, ReLU) -> Hidden 2 (16 neurons, ReLU) -> Output (1 neuron, Sigmoid)
    """
    def __init__(self):
        super().__init__()
        self.net = nn.Sequential(
            nn.Linear(2, 32),
            nn.ReLU(),
            nn.Linear(32, 16),
            nn.ReLU(),
            nn.Linear(16, 1),
            nn.Sigmoid()
        )

    def forward(self, x):
        """Ուղիղ տարածում (Forward pass)"""
        return self.net(x)

# ─── Քայլ 2: Բեռնել տվյալները ────────────────────────────────────
def load_data(path="data/dataset.csv"):
    df = pd.read_csv(path)
    X = df[["x1", "x2"]].values
    y = df["label"].values
    
    # Բաժանել: 80% մարզման, 20% վալիդացիայի համար
    X_train, X_val, y_train, y_val = train_test_split(X, y, test_size=0.2, random_state=42)

    # Փոխակերպել PyTorch tensor-ների
    X_train_t = torch.FloatTensor(X_train)
    y_train_t = torch.FloatTensor(y_train).unsqueeze(1)
    X_val_t = torch.FloatTensor(X_val)
    y_val_t = torch.FloatTensor(y_val).unsqueeze(1)
    return X_train_t, y_train_t, X_val_t, y_val_t

# ─── Քայլ 3: Մարզման ցիկլ (Training Loop) ────────────────────────────────────
def train_model(epochs=200, lr=0.01):
    X_train, y_train, X_val, y_val = load_data()
    model = MoonClassifier()
    loss_fn = nn.BCELoss() # Binary Cross-Entropy
    optimizer = torch.optim.Adam(model.parameters(), lr=lr)

    history = {"train_loss": [], "val_loss": [], "train_acc": [], "val_acc": []}

    for epoch in range(epochs):
        model.train()
        optimizer.zero_grad()
        train_preds = model(X_train)
        train_loss = loss_fn(train_preds, y_train)
        train_loss.backward()
        optimizer.step()

        # Հաշվարկել ճշտությունը (accuracy)
        train_acc = ((train_preds > 0.5).float() == y_train).float().mean().item()

        model.eval()
        with torch.no_grad():
            val_preds = model(X_val)
            val_loss = loss_fn(val_preds, y_val)
            val_acc = ((val_preds > 0.5).float() == y_val).float().mean().item()

        # TODO: Ավելացնել բոլոր 4 մետրիկաները history բառարանի մեջ
        # Հուշում: Use .item() on loss tensors
        ... # ՁԵՐ ԿՈԴԸ ԱՅՍՏԵՂ (4 տող)

        if (epoch + 1) % 50 == 0:
            print(f"Epoch {epoch+1}/{epochs} — Loss: {train_loss.item():.4f} | Val Acc: {val_acc:.2%}")

    return model, history

if __name__ == "__main__":
    model, history = train_model()
    with open("model/history.json", "w") as f:
        json.dump(history, f)
    
    # TODO: Պահպանել մոդելի կշիռները torch.save-ի միջոցով
    # Հուշում: torch.save(model.state_dict(), "path/to/model.pth")
    ... # ՁԵՐ ԿՈԴԸ ԱՅՍՏԵՂ
    print("Model saved to model/model.pth")
```

Ավարտելուց հետո կատարեք քոմիթ.
```bash
git add model/train.py
git commit -m "feat: add neural network training with validation tracking"
```

---

### Առաջադրանք 3 — 2D Scatter Plot (10 միավոր)
Ֆայլ՝ `viz/scatter2d.py`: Ստեղծեք պարզ 2D գրաֆիկ՝ ձեր տվյալները տեսնելու համար:

**Աշխատեցրեք ավարտելիս.**
* macOS/Linux: `python3 viz/scatter2d.py`
* Windows: `python viz\scatter2d.py`

Մեկնարկային կոդ.
```python
import pandas as pd
import plotly.express as px

def create_scatter(csv_path="data/dataset.csv"):
    df = pd.read_csv(csv_path)
    # TODO: Ստեղծել scatter plot օգտագործելով px.scatter
    # Պարտադիր արգումենտներ: data_frame, x, y, color="label"
    # Լրացուցիչ (լիարժեք միավորների համար): title, template="plotly_dark", labels
    fig = ... # ՁԵՐ ԿՈԴԸ ԱՅՍՏԵՂ
    
    fig.write_html("outputs/scatter2d.html")
    return fig

if __name__ == "__main__":
    fig = create_scatter()
    fig.show()
```

---

### Առաջադրանք 4 — Մարզման կորեր (Training Curves) (15 միավոր)
Ֆայլ՝ `viz/training_curves.py`: Գծագրեք, թե ինչպես է մոդելը լավացել մարզման ընթացքում:

**Աշխատեցրեք ավարտելիս.**
* macOS/Linux: `python3 viz/training_curves.py`
* Windows: `python viz\training_curves.py`

Մեկնարկային կոդի TODO-ներ.
* Ավելացնել `go.Scatter` թրեյսեր (traces) Loss-ի և Accuracy-ի համար:
* Գտնել ամենացածր `val_loss` ունեցող էպոխան և ավելացնել ուղղահայաց գիծ (`fig.add_vline`):

---

### Առաջադրանք 5 — 2D Decision Boundary (20 միավոր)
Ֆայլ՝ `viz/decision_boundary.py`: Սա ցույց է տալիս, թե **որտեղ է նեյրոնային ցանցը գծում սահմանը** երկու դասերի միջև:

**Աշխատեցրեք ավարտելիս.**
* macOS/Linux: `python3 viz/decision_boundary.py`
* Windows: `python viz\decision_boundary.py`

TODO-ներ.
* Ավելացնել `go.Contour` շերտը decision boundary-ի համար:
* Ավելացնել `go.Scatter` շերտը իրական կետերի համար:

---

### Առաջադրանք 6 — 3D Scatter Plot (15 միավոր)
Ֆայլ՝ `viz/scatter3d.py`: Ուսումնասիրեք Plotly-ի 3D հնարավորությունները:

**Աշխատեցրեք ավարտելիս.**
* macOS/Linux: `python3 viz/scatter3d.py`
* Windows: `python viz\scatter3d.py`

TODO-ներ.
* Ավելացնել մեկական `go.Scatter3d` թրեյս յուրաքանչյուր դասի (class) համար:

---

### Առաջադրանք 7 — Գրել main.py (5 միավոր)
Ֆայլ՝ `main.py`: Այս սկրիպտը պետք է աշխատեցնի ամեն ինչ հերթականությամբ:

TODO-ներ.
* Import անել բոլոր ֆունկցիաները և կանչել դրանք:

---

### Առաջադրանք 8 — Գրել ձեր README.md-ն (10 միավոր)
Ձեր **README.md**-ն առաջին բանն է, որ մարդիկ տեսնում են GitHub-ում: Այն պետք է ներառի.
* Նախագծի վերնագիր և նկարագրություն
* Կարգավորման հրամաններ (Setup instructions) բոլոր 3 ՕՀ-ների համար
* Ֆայլերի նկարագրություն
* Սքրինշոթներ (Screenshots) ձեր վիզուալիզացիաներից

---

## 📊 Գնահատման սանդղակ (Grading Rubric) — Ընդհանուր 100 միավոր

### Վիզուալիզացիաներ (50 միավոր)
| Առաջադրանք | Միավոր | Ինչին եմ ուշադրություն դարձնելու |
| :--- | :--- | :--- |
| Task 1 — Dataset generation | 5 | Աշխատում է, ստեղծում է CSV, reproducible է |
| Task 2 — Neural network | 10 | Մարզվում է, պահպանում է history-ն, տպում է պրոգրեսը |
| Task 3 — 2D scatter | 5 | Ինտերակտիվ է, գունավոր, dark theme |
| Task 4 — Training curves | 10 | Երկու պանել, range slider, լավագույն էպոխան նշված է |
| Task 5 — Decision boundary | 15 | Contour + scatter overlay, ընթեռնելի |
| Task 6 — 3D scatter | 10 | 3 դասեր, պտտվող, առանցքների անուններ |
| Task 7 — main.py | 5 | Աշխատեցնում է ամբողջ pipeline-ը մեկ հրամանով |

### GitHub Պրակտիկա (50 միավոր)
| Չափանիշ | Միավոր | Ինչին եմ ուշադրություն դարձնելու |
| :--- | :--- | :--- |
| Repository structure | 10 | Համապատասխանում է պահանջվող կառուցվածքին |
| requirements.txt | 5 | Ամբողջական և ճիշտ է |
| .gitignore | 5 | venv, pycache, outputs բացառված են |
| README.md | 10 | Վերնագիր, setup հրամաններ, սքրինշոթ |
| Commit history | 15 | Առնվազն 6 քոմիթ հստակ հաղորդագրություններով |
| Code quality | 5 | Մաքուր կոդ, TODO-ները փոխարինված են իրական կոդով |

---
**Ինչպիսի՞ն է լավ Commit հաղորդագրությունը.**
`feat: add dataset generation script` — նոր ֆունկցիոնալի ավելացում



# 🧠 Project: Neural Network Visualizer — Guided Track

> **Timeline:** 2 week  
> **Difficulty:** ⭐⭐ Guided  
> **You may use:** Official documentation, Stack Overflow, AI tools for understanding concepts — but all code must be written and understood by you. If asked, you should be able to explain any line of your code.

---

## 📖 Before You Start — Key Concepts

Read each of these carefully. They explain *why* we do things, not just *how*.

### What is a Virtual Environment?

Think of your computer as a kitchen shared by many chefs (projects). If one chef needs salt version 1.0 and another needs salt version 2.0, they'll clash. A **virtual environment** gives each project its own private kitchen.

**Rule:** Always activate your virtual environment before working on the project.

### What is `requirements.txt`?

Imagine you baked a cake and your friend wants to make the same one. You'd give them a recipe with exact ingredients. `requirements.txt` is that recipe for Python packages:

```
plotly>=5.18
numpy>=1.24
```

Anyone can now type `pip install -r requirements.txt` and get the exact same packages you used.

### What is `.gitignore`?

Some files are **too big** or **too personal** to put on GitHub. The `.gitignore` file is a list of files that Git should pretend don't exist. You never want to upload:
- `venv/` — your virtual environment (can be 200+ MB)
- `__pycache__/` — auto-generated junk files
- `outputs/` — files anyone can regenerate by running your code

### What is a Neural Network? (Simplified)

Imagine you have dots on a page — some red, some blue, mixed together. You want to draw a wiggly line that separates them. A neural network **learns** where to draw that line by:

1. Guessing randomly
2. Checking how wrong the guess was (**loss**)
3. Adjusting the guess slightly
4. Repeating hundreds of times (**epochs**)

Each round of guess-check-adjust is one training step. After enough steps, the line fits nicely between the classes.

### What is Plotly?

Plotly makes **interactive charts** — you can hover to see values, zoom in, rotate 3D plots, and export everything as an HTML file that opens in any browser. This is what we'll use to visualize our neural network.

### What is `go` vs `px`?

Plotly has two main interfaces:
- **`plotly.express` (px)** — quick and easy, great for simple plots. Like Instagram filters — pick one and go.
- **`plotly.graph_objects` (go)** — full control, more code, but you can customize everything. Like Photoshop.

We'll use **both** in this project.

---

## 🖥️ OS-Specific Commands Reference

Throughout this project, some terminal commands differ by operating system. This section is your **cheat sheet** — refer back to it whenever you need a command.

### 🍎 macOS

```bash
# Python — macOS often requires "python3" instead of "python"
python3 --version                    # Check Python version
python3 -m venv venv                 # Create virtual environment
source venv/bin/activate             # Activate virtual environment
deactivate                           # Deactivate virtual environment
pip3 install -r requirements.txt     # Install packages
python3 data/generate.py             # Run a script
python3 main.py                      # Run the main pipeline

# Folder creation
mkdir nn-visualizer-guided           # Create a folder
cd nn-visualizer-guided              # Enter the folder
mkdir -p data model viz outputs      # Create multiple folders (-p = no error if exists)

# Git
git init                             # Initialize a repo
git add requirements.txt .gitignore  # Stage files
git commit -m "your message"         # Commit with a message
git log --oneline                    # View commit history (compact)
git remote add origin <URL>          # Connect to GitHub
git push -u origin main              # Push to GitHub (first time)
git push                             # Push to GitHub (subsequent times)
```

### 🪟 Windows (Command Prompt)

```cmd
# Python — Windows usually uses "python" (not python3)
python --version                     # Check Python version
python -m venv venv                  # Create virtual environment
venv\Scripts\activate                # Activate virtual environment
deactivate                           # Deactivate virtual environment
pip install -r requirements.txt      # Install packages
python data\generate.py              # Run a script (note: backslashes)
python main.py                       # Run the main pipeline

# Folder creation
mkdir nn-visualizer-guided           # Create a folder
cd nn-visualizer-guided              # Enter the folder
mkdir data model viz outputs         # Create multiple folders

# Git (same on all OS)
git init
git add requirements.txt .gitignore
git commit -m "your message"
git log --oneline
git remote add origin <URL>
git push -u origin main
git push
```

### 🐧 Linux (Bash)

```bash
# Python — most Linux distros use "python3"
python3 --version                    # Check Python version
python3 -m venv venv                 # Create virtual environment
source venv/bin/activate             # Activate virtual environment
deactivate                           # Deactivate virtual environment
pip install -r requirements.txt      # Install packages
python3 data/generate.py             # Run a script
python3 main.py                      # Run the main pipeline

# Folder creation
mkdir nn-visualizer-guided           # Create a folder
cd nn-visualizer-guided              # Enter the folder
mkdir -p data model viz outputs      # Create multiple folders

# Git (same on all OS)
git init
git add requirements.txt .gitignore
git commit -m "your message"
git log --oneline
git remote add origin <URL>
git push -u origin main
git push
```

> **💡 Note on `python` vs `python3`:** On macOS and Linux, `python` sometimes points to Python 2 (which is outdated). Always use `python3` to be safe. On Windows, the installer usually sets `python` to Python 3. To check, run `python --version` — if it says 2.x, switch to `python3`.

> **💡 Note on path separators:** macOS and Linux use forward slashes (`data/generate.py`). Windows uses backslashes (`data\generate.py`). In Python code itself, always use forward slashes or `os.path.join()` — Python handles the conversion for you.

---

## 🗂 Required Repository Structure

Your GitHub repo must look like this:

```
nn-visualizer-guided/
│
├── README.md                  # YOU write this — describe your project
├── requirements.txt           # Package list (provided below)
├── .gitignore                 # Files to exclude (provided below)
│
├── data/
│   └── generate.py            # Task 1
│
├── model/
│   └── train.py               # Task 2
│
├── viz/
│   ├── scatter2d.py           # Task 3
│   ├── training_curves.py     # Task 4
│   ├── decision_boundary.py   # Task 5
│   └── scatter3d.py           # Task 6
│
├── outputs/                   # Your exported .html plots go here
│
└── main.py                    # Runs everything
```

> **Why separate files?** Each file does ONE thing. This makes it easy to find code, fix bugs, and work on one piece without breaking others. Real software teams always organize code this way.

---

## ⚙️ Setup — Follow These Steps Exactly

Pick your operating system and follow the steps:

### 🍎 macOS

```bash
mkdir nn-visualizer-guided && cd nn-visualizer-guided
git init
mkdir -p data model viz outputs
python3 -m venv venv
source venv/bin/activate
pip3 install -r requirements.txt
```

### 🪟 Windows

```cmd
mkdir nn-visualizer-guided
cd nn-visualizer-guided
git init
mkdir data model viz outputs
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

### 🐧 Linux

```bash
mkdir nn-visualizer-guided && cd nn-visualizer-guided
git init
mkdir -p data model viz outputs
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

### Copy this into `requirements.txt`:

```
numpy>=1.24
pandas>=2.0
plotly>=5.18
scikit-learn>=1.3
torch>=2.0
```

### Copy this into `.gitignore`:

```
venv/
__pycache__/
*.pyc
outputs/*.html
.DS_Store
```

### Make your first commit:

```bash
git add requirements.txt .gitignore
git commit -m "Initial setup: add requirements and gitignore"
```

✅ **Checkpoint:** You should now have a Git repo with one commit. Run `git log --oneline` to verify.

---

## 📝 Tasks

---

### Task 1 — Generate the Dataset (10 pts)

**File:** `data/generate.py`

We'll use a built-in dataset called **"moons"** — two crescent shapes that overlap. It's simple but not trivially separable, which makes it interesting for a neural network.

**Run when complete:**
- macOS/Linux: `python3 data/generate.py`
- Windows: `python data\generate.py`

**Starter code — fill in the `TODO` parts:**

```python
"""
Dataset Generation
==================
This script creates a 2D "moons" dataset for binary classification
and saves it as a CSV file.

What are "moons"? Two interleaving crescent (half-moon) shapes.
The neural network needs to learn a curved boundary to separate them.
"""

import numpy as np
import pandas as pd
from sklearn.datasets import make_moons
from sklearn.preprocessing import StandardScaler

def generate_dataset(n_samples=1000, noise=0.2, random_state=42):
    """
    Generate a 2D moons dataset.

    Parameters
    ----------
    n_samples : int
        How many data points to create (total, split between two classes)
    noise : float
        How much random scatter to add (0 = perfect crescents, 1 = very messy)
    random_state : int
        Seed for reproducibility — same number = same dataset every time

    Returns
    -------
    pd.DataFrame
        DataFrame with columns: 'x1', 'x2', 'label'
    """
    # Step 1: Generate the moons
    # make_moons returns two arrays: X (coordinates) and y (labels)
    X, y = make_moons(n_samples=n_samples, noise=noise, random_state=random_state)

    # Step 2: Standardize the features
    # StandardScaler makes the data centered around 0 with standard deviation 1
    # This helps the neural network learn faster
    scaler = StandardScaler()
    X = scaler.fit_transform(X)

    # Step 3: Create a DataFrame
    # TODO: Create a pandas DataFrame with columns 'x1', 'x2', 'label'
    # Hint: X has shape (1000, 2) — column 0 is x1, column 1 is x2
    # Hint: pd.DataFrame({"column_name": array, ...})
    df = ...  # YOUR CODE HERE

    return df

if __name__ == "__main__":
    # This block runs only when you execute the file directly.
    # It does NOT run when another file imports this module.

    df = generate_dataset()
    print(f"Dataset shape: {df.shape}")
    print(f"Class distribution:\n{df['label'].value_counts()}")

    # TODO: Save the DataFrame to data/dataset.csv
    # Hint: df.to_csv("path/to/file.csv", index=False)
    # The index=False part means "don't save the row numbers"
    ...  # YOUR CODE HERE

    print("Dataset saved to data/dataset.csv")
```

> **What is `if __name__ == "__main__":`?**  
> When Python runs a file directly (like `python3 data/generate.py`), it sets a special variable `__name__` to `"__main__"`. When another file *imports* it (like `from data.generate import generate_dataset`), `__name__` is set to the module name instead. This `if` block means "only run this code when the file is executed directly, not when imported."

**After completing this, commit:**
```bash
git add data/generate.py
git commit -m "feat: add dataset generation script"
```

---

### Task 2 — Train the Neural Network (15 pts)

**File:** `model/train.py`

We'll build a simple neural network in PyTorch. Don't worry if PyTorch is new to you — the starter code has detailed comments explaining every line.

**Run when complete:**
- macOS/Linux: `python3 model/train.py`
- Windows: `python model\train.py`

**Starter code — fill in the `TODO` parts:**

```python
"""
Neural Network Training
========================
This script defines a simple neural network, trains it on the moons dataset,
and saves the training history and model weights.
"""

import json
import numpy as np
import pandas as pd
import torch
import torch.nn as nn
from sklearn.model_selection import train_test_split

# ─── Step 1: Define the Neural Network ───────────────────────

class MoonClassifier(nn.Module):
    """
    A simple feedforward neural network for binary classification.

    Architecture:
        Input (2 features)
          → Hidden layer 1 (32 neurons) + ReLU activation
          → Hidden layer 2 (16 neurons) + ReLU activation
          → Output (1 neuron) + Sigmoid activation

    What is ReLU?
        ReLU(x) = max(0, x). It keeps positive values and turns negatives to 0.
        Without activation functions, the network could only learn straight lines.
        ReLU lets it learn curves.

    What is Sigmoid?
        Sigmoid(x) = 1 / (1 + e^(-x)). It squashes any number into the range (0, 1).
        This is perfect for binary classification: output close to 0 = Class 0,
        output close to 1 = Class 1.
    """
    def __init__(self):
        super().__init__()  # Initialize the parent class (required by PyTorch)
        self.net = nn.Sequential(
            # nn.Sequential chains layers together — data flows through in order
            nn.Linear(2, 32),    # 2 inputs → 32 neurons (2 because we have x1, x2)
            nn.ReLU(),           # Activation function
            nn.Linear(32, 16),   # 32 → 16 neurons
            nn.ReLU(),           # Activation function
            nn.Linear(16, 1),    # 16 → 1 output neuron
            nn.Sigmoid()         # Squash output to probability (0 to 1)
        )

    def forward(self, x):
        """Forward pass — this is called when you do model(input_data)."""
        return self.net(x)


# ─── Step 2: Load the Data ────────────────────────────────────

def load_data(path="data/dataset.csv"):
    """Load dataset and split into train/validation sets."""
    df = pd.read_csv(path)

    # Separate features (x1, x2) from labels
    X = df[["x1", "x2"]].values   # shape: (1000, 2)
    y = df["label"].values          # shape: (1000,)

    # Split: 80% for training, 20% for validation
    # random_state ensures the same split every time
    X_train, X_val, y_train, y_val = train_test_split(
        X, y, test_size=0.2, random_state=42
    )

    # Convert NumPy arrays to PyTorch tensors
    # PyTorch needs FloatTensor for features and unsqueeze(1) to make labels 2D
    X_train_t = torch.FloatTensor(X_train)
    y_train_t = torch.FloatTensor(y_train).unsqueeze(1)  # (800,) → (800, 1)
    X_val_t = torch.FloatTensor(X_val)
    y_val_t = torch.FloatTensor(y_val).unsqueeze(1)

    return X_train_t, y_train_t, X_val_t, y_val_t


# ─── Step 3: Training Loop ────────────────────────────────────

def train_model(epochs=200, lr=0.01):
    """
    Train the model and return the training history.

    Parameters
    ----------
    epochs : int
        How many times to loop through the entire training data
    lr : float
        Learning rate — how big each adjustment step is.
        Too big = overshoots, too small = takes forever.
    """
    # Load data
    X_train, y_train, X_val, y_val = load_data()

    # Create model, loss function, and optimizer
    model = MoonClassifier()
    loss_fn = nn.BCELoss()  # Binary Cross-Entropy — standard for binary classification
    optimizer = torch.optim.Adam(model.parameters(), lr=lr)
    # Adam is a smart optimizer — it adjusts the learning rate per-parameter automatically

    # This dictionary will store our metrics for plotting later
    history = {
        "train_loss": [],
        "val_loss": [],
        "train_acc": [],
        "val_acc": []
    }

    for epoch in range(epochs):
        # ── Training phase ──
        model.train()  # Set model to training mode
        optimizer.zero_grad()  # Clear leftover gradients from last step

        train_preds = model(X_train)          # Forward pass
        train_loss = loss_fn(train_preds, y_train)  # Calculate loss
        train_loss.backward()                  # Backward pass (compute gradients)
        optimizer.step()                       # Update weights

        # Calculate training accuracy
        # (preds > 0.5) converts probabilities to 0/1 predictions
        train_acc = ((train_preds > 0.5).float() == y_train).float().mean().item()

        # ── Validation phase ──
        model.eval()  # Set model to evaluation mode (disables dropout, etc.)
        with torch.no_grad():  # Don't compute gradients — we're just evaluating
            val_preds = model(X_val)
            val_loss = loss_fn(val_preds, y_val)
            val_acc = ((val_preds > 0.5).float() == y_val).float().mean().item()

        # TODO: Append all four metrics to the history dictionary
        # Hint: history["train_loss"].append(...)
        # Hint: Use .item() on loss tensors to get a plain Python number
        ...  # YOUR CODE HERE (4 lines)

        # Print progress every 50 epochs
        if (epoch + 1) % 50 == 0:
            print(f"Epoch {epoch+1}/{epochs} — "
                  f"Loss: {train_loss.item():.4f} | "
                  f"Val Acc: {val_acc:.2%}")

    return model, history


# ─── Step 4: Save Everything ──────────────────────────────────

if __name__ == "__main__":
    model, history = train_model()

    # Save training history as JSON
    with open("model/history.json", "w") as f:
        json.dump(history, f)
    print("Training history saved to model/history.json")

    # TODO: Save the model weights using torch.save
    # Hint: torch.save(model.state_dict(), "path/to/model.pth")
    # state_dict() contains all the learned weights and biases
    ...  # YOUR CODE HERE

    print("Model saved to model/model.pth")
```

**After completing this, commit:**
```bash
git add model/train.py
git commit -m "feat: add neural network training with validation tracking"
```

---

### Task 3 — 2D Scatter Plot (10 pts)

**File:** `viz/scatter2d.py`

Start with a simple 2D scatter plot to see your dataset.

**Run when complete:**
- macOS/Linux: `python3 viz/scatter2d.py`
- Windows: `python viz\scatter2d.py`

**Starter code:**

```python
"""
2D Scatter Plot
===============
Visualize the moons dataset as an interactive scatter plot.
"""

import pandas as pd
import plotly.express as px

def create_scatter(csv_path="data/dataset.csv"):
    """Create an interactive scatter plot of the dataset."""
    df = pd.read_csv(csv_path)

    # TODO: Create a scatter plot using px.scatter
    # Required arguments:
    #   - data_frame=df
    #   - x="x1"
    #   - y="x2"
    #   - color="label"             ← colors by class
    #
    # Optional but REQUIRED for full marks:
    #   - color_continuous_scale=    ← try "RdBu", "Viridis", or "Plasma"
    #   - title=                     ← give it a descriptive title
    #   - labels={"x1": "...", "x2": "..."}   ← human-readable axis names
    #   - hover_data=                ← list of columns to show on hover
    #   - template="plotly_dark"     ← dark theme (looks nicer)
    #
    # Hint: fig = px.scatter(data_frame=df, x=..., y=..., color=..., ...)

    fig = ...  # YOUR CODE HERE

    # Export to HTML
    fig.write_html("outputs/scatter2d.html")
    print("Saved to outputs/scatter2d.html")

    return fig

if __name__ == "__main__":
    fig = create_scatter()
    fig.show()  # Opens in your browser
```

> **What does `fig.show()` do?** It opens the plot in your default web browser. During development, use this to see your plot immediately. `fig.write_html()` saves it as a file for submission.

**After completing, commit:**
```bash
git add viz/scatter2d.py
git commit -m "feat: add 2D scatter plot visualization"
```

---

### Task 4 — Training Curves (15 pts)

**File:** `viz/training_curves.py`

Plot how the model improved during training.

**Run when complete:**
- macOS/Linux: `python3 viz/training_curves.py`
- Windows: `python viz\training_curves.py`

**Starter code:**

```python
"""
Training Curves
===============
Visualize loss and accuracy over training epochs.

What is make_subplots?
    It creates a figure with multiple charts side by side (or stacked).
    Think of it as a grid where each cell holds one chart.
"""

import json
import plotly.graph_objects as go
from plotly.subplots import make_subplots

def create_training_curves(history_path="model/history.json"):
    """Create a 2-panel training curves plot."""

    # Load the training history
    with open(history_path) as f:
        history = json.load(f)

    epochs = list(range(1, len(history["train_loss"]) + 1))

    # Create a figure with 1 row, 2 columns
    # shared_xaxes=True means both panels share the same x-axis (epochs)
    fig = make_subplots(
        rows=1, cols=2,
        subplot_titles=("Loss Over Time", "Accuracy Over Time"),
        shared_xaxes=True
    )

    # ── Left panel: Loss ──
    # TODO: Add two line traces for train_loss and val_loss
    # Use fig.add_trace(go.Scatter(...), row=1, col=1)
    #
    # go.Scatter arguments you'll need:
    #   x=epochs             ← the x values
    #   y=history[...]       ← the y values
    #   name="Train Loss"    ← legend label
    #   mode="lines"         ← draw lines (not just dots)
    #   line=dict(color="...", width=2)   ← customize appearance
    #
    # Add BOTH train_loss and val_loss as separate traces

    ...  # YOUR CODE HERE (2 traces)

    # ── Right panel: Accuracy ──
    # TODO: Add two line traces for train_acc and val_acc
    # Same pattern as above, but row=1, col=2

    ...  # YOUR CODE HERE (2 traces)

    # ── Styling ──
    # TODO: Find the epoch with the LOWEST validation loss
    # Hint: Use the min() function with a key, or np.argmin
    # Then add a vertical line at that epoch using fig.add_vline
    #
    # fig.add_vline(
    #     x=best_epoch,
    #     line_dash="dash",
    #     line_color="yellow",
    #     annotation_text="Best epoch"
    # )

    best_epoch = ...  # YOUR CODE HERE

    # Add range slider — this lets users zoom into specific epoch ranges
    fig.update_xaxes(rangeslider_visible=True, row=1, col=1)

    # Update layout
    fig.update_layout(
        template="plotly_dark",
        title_text="Training Progress",
        height=400
    )

    fig.write_html("outputs/training_curves.html")
    print("Saved to outputs/training_curves.html")
    return fig

if __name__ == "__main__":
    fig = create_training_curves()
    fig.show()
```

**After completing, commit:**
```bash
git add viz/training_curves.py
git commit -m "feat: add training curves with range slider"
```

---

### Task 5 — 2D Decision Boundary (20 pts)

**File:** `viz/decision_boundary.py`

This is the most exciting 2D plot — it shows **where the neural network draws the line** between the two classes.

**How it works:**
1. Create a dense grid of points covering the entire plot area
2. Run every grid point through the trained model
3. Color each point by its predicted probability
4. This creates a smooth color map showing the decision regions

**Run when complete:**
- macOS/Linux: `python3 viz/decision_boundary.py`
- Windows: `python viz\decision_boundary.py`

**Starter code:**

```python
"""
Decision Boundary
=================
Visualize how the neural network separates the two classes.

What is a meshgrid?
    Imagine drawing a grid on graph paper. np.meshgrid creates the x,y
    coordinates of every intersection point. If you have 200 x-values and
    200 y-values, you get 40,000 intersection points covering the full area.
"""

import numpy as np
import pandas as pd
import torch
import plotly.graph_objects as go

# We need to import the model class to load it
# This import will work if you run from the project root folder
import sys; sys.path.insert(0, ".")
from model.train import MoonClassifier

def create_decision_boundary(csv_path="data/dataset.csv", model_path="model/model.pth"):
    """Visualize the decision boundary of the trained model."""

    # Load dataset
    df = pd.read_csv(csv_path)

    # Load trained model
    model = MoonClassifier()
    model.load_state_dict(torch.load(model_path, weights_only=True))
    model.eval()  # Set to evaluation mode

    # ── Create meshgrid ──
    # We create a grid of points covering the data range, with some padding
    padding = 0.5
    x_min, x_max = df["x1"].min() - padding, df["x1"].max() + padding
    y_min, y_max = df["x2"].min() - padding, df["x2"].max() + padding

    # 200 evenly spaced points in each direction = 40,000 grid points
    xx, yy = np.meshgrid(
        np.linspace(x_min, x_max, 200),
        np.linspace(y_min, y_max, 200)
    )

    # Flatten the grid into a list of (x1, x2) pairs
    # np.c_ concatenates columns: shape becomes (40000, 2)
    grid_points = np.c_[xx.ravel(), yy.ravel()]

    # Run the grid through the model
    with torch.no_grad():
        grid_tensor = torch.FloatTensor(grid_points)
        predictions = model(grid_tensor).numpy().reshape(xx.shape)
        # predictions now has shape (200, 200) — a probability for each grid point

    # ── Build the plot ──
    fig = go.Figure()

    # TODO: Add a Contour trace for the decision boundary
    # Use go.Contour with:
    #   x=np.linspace(x_min, x_max, 200)   ← x-axis values
    #   y=np.linspace(y_min, y_max, 200)   ← y-axis values
    #   z=predictions                        ← the probability grid
    #   colorscale="RdBu"                    ← red/blue color scheme
    #   opacity=0.7                          ← semi-transparent
    #   colorbar=dict(title="P(class=1)")    ← label for the color bar
    #   contours=dict(showlines=False)       ← hide contour lines for cleaner look

    fig.add_trace(...)  # YOUR CODE HERE

    # TODO: Add the real data points on top as a Scatter trace
    # Use go.Scatter with:
    #   x=df["x1"], y=df["x2"]
    #   mode="markers"
    #   marker=dict(
    #       color=df["label"],
    #       colorscale="RdBu",
    #       size=5,
    #       line=dict(width=0.5, color="white")   ← white border on each dot
    #   )

    fig.add_trace(...)  # YOUR CODE HERE

    # ── Layout ──
    fig.update_layout(
        template="plotly_dark",
        title="Neural Network Decision Boundary",
        xaxis_title="Feature x1",
        yaxis_title="Feature x2",
        width=700,
        height=600
    )

    fig.write_html("outputs/decision_boundary.html")
    print("Saved to outputs/decision_boundary.html")
    return fig

if __name__ == "__main__":
    fig = create_decision_boundary()
    fig.show()
```

**After completing, commit:**
```bash
git add viz/decision_boundary.py
git commit -m "feat: add decision boundary contour plot"
```

---

### Task 6 — 3D Scatter Plot (15 pts)

**File:** `viz/scatter3d.py`

Now let's explore Plotly's 3D capabilities! We'll generate a **new 3D dataset** just for this visualization.

**Run when complete:**
- macOS/Linux: `python3 viz/scatter3d.py`
- Windows: `python viz\scatter3d.py`

**Starter code:**

```python
"""
3D Scatter Plot
===============
Generate a 3D dataset and visualize it as an interactive 3D scatter plot.

What is Scatter3d?
    It's like a normal scatter plot but with a z-axis. You can click and drag
    to rotate the view, scroll to zoom, and hover to see values. This is
    one of Plotly's most impressive features.
"""

import numpy as np
import plotly.graph_objects as go
from sklearn.datasets import make_blobs

def create_3d_scatter():
    """Create an interactive 3D scatter plot of a 3-class blob dataset."""

    # Generate 3D data with 3 clusters
    # make_blobs creates groups (blobs) of points in n-dimensional space
    X, y = make_blobs(
        n_samples=600,       # 600 total points
        centers=3,           # 3 separate groups
        n_features=3,        # 3D (x, y, z)
        random_state=42,
        cluster_std=1.5      # How spread out each blob is
    )

    # Define one color per class
    colors = ["#FF6B6B", "#4ECDC4", "#45B7D1"]   # red, teal, blue
    symbols = ["circle", "diamond", "square"]

    fig = go.Figure()

    # TODO: Add one Scatter3d trace PER CLASS
    # Loop through classes 0, 1, 2 and add a trace for each
    #
    # for cls in [0, 1, 2]:
    #     mask = (y == cls)   ← boolean array: True where label equals cls
    #     fig.add_trace(go.Scatter3d(
    #         x=X[mask, 0],
    #         y=X[mask, 1],
    #         z=X[mask, 2],
    #         mode="markers",
    #         name=f"Class {cls}",       ← legend label
    #         marker=dict(
    #             size=4,
    #             color=colors[cls],
    #             symbol=symbols[cls],
    #             opacity=0.8
    #         )
    #     ))

    ...  # YOUR CODE HERE

    # TODO: Update the layout
    # fig.update_layout(
    #     template="plotly_dark",
    #     title="3D Blob Dataset",
    #     scene=dict(
    #         xaxis_title="X",
    #         yaxis_title="Y",
    #         zaxis_title="Z"
    #     ),
    #     scene_camera=dict(eye=dict(x=1.5, y=1.5, z=0.8))   ← starting angle
    # )

    ...  # YOUR CODE HERE

    fig.write_html("outputs/scatter3d.html")
    print("Saved to outputs/scatter3d.html")
    return fig

if __name__ == "__main__":
    fig = create_3d_scatter()
    fig.show()
```

> **Try this:** After opening the plot in your browser, click and drag to rotate it. Scroll to zoom. Double-click to reset the view. This is what makes Plotly 3D special — you're exploring data, not just looking at a picture.

**After completing, commit:**
```bash
git add viz/scatter3d.py
git commit -m "feat: add 3D scatter plot visualization"
```

---

### Task 7 — Write `main.py` (5 pts)

**File:** `main.py`

This script should run everything in order.

**Run when complete:**
- macOS/Linux: `python3 main.py`
- Windows: `python main.py`

**Starter code:**

```python
"""
Main Pipeline
=============
Runs the entire project: generate data → train model → create all plots.

Why have a main.py?
    Imagine someone downloads your project from GitHub. They shouldn't have to
    figure out which files to run in which order. main.py does it all with
    one command.
"""

import os

# Create outputs folder if it doesn't exist
os.makedirs("outputs", exist_ok=True)

print("=" * 50)
print("STEP 1: Generating dataset...")
print("=" * 50)
# TODO: Import and call your dataset generation function
# from data.generate import generate_dataset
# ...

print("\n" + "=" * 50)
print("STEP 2: Training neural network...")
print("=" * 50)
# TODO: Import and call your training function
# from model.train import train_model
# ...

print("\n" + "=" * 50)
print("STEP 3: Creating visualizations...")
print("=" * 50)
# TODO: Import and call each visualization function
# from viz.scatter2d import create_scatter
# from viz.training_curves import create_training_curves
# from viz.decision_boundary import create_decision_boundary
# from viz.scatter3d import create_3d_scatter
# ...

print("\n" + "=" * 50)
print("ALL DONE! Check the outputs/ folder for your HTML plots.")
print("=" * 50)
```

---

### Task 8 — Write Your README.md (10 pts)

Your `README.md` is the **first thing people see** on your GitHub page. It should include:

1. **Project title** and a one-sentence description
2. **Setup instructions** — how to install and run your project. Include commands for **all three operating systems** (macOS, Windows, Linux) — copy/adapt from the OS Reference section above.
3. **What each file does** — brief description of each script
4. **Screenshots** — at least one screenshot or GIF of your visualizations. To add images:
   - Take a screenshot of your plot in the browser
   - Save it in your repo (e.g., `screenshots/decision_boundary.png`)
   - Reference it in README: `![Decision Boundary](screenshots/decision_boundary.png)`

> **Why does README matter?** On GitHub, the README is your project's first impression. Recruiters, teachers, and collaborators read it to decide if your project is worth exploring. A good README makes you look professional.

---

## 📊 Grading Rubric — 100 points total

### Visualizations (50 pts)

| Task | Points | What I'm Looking For |
|------|--------|---------------------|
| Task 1 — Dataset generation | 5 | Runs, creates CSV, reproducible |
| Task 2 — Neural network | 10 | Trains, saves history + model, prints progress |
| Task 3 — 2D scatter | 5 | Interactive, colored, dark theme, custom labels |
| Task 4 — Training curves | 10 | Two panels, range slider, best epoch marked |
| Task 5 — Decision boundary | 15 | Contour + scatter overlay, readable, color bar |
| Task 6 — 3D scatter | 10 | 3 classes, rotatable, axis labels, camera set |
| Task 7 — main.py | 5 | Runs the whole pipeline with one command |
| **Subtotal** | **50** | |

### GitHub Practices (50 pts)

| Criteria | Points | What I'm Looking For |
|----------|--------|---------------------|
| Repository structure | 10 | Matches the required layout |
| `requirements.txt` | 5 | Complete and correct |
| `.gitignore` | 5 | venv, pycache, outputs excluded |
| `README.md` | 10 | Title, setup instructions (all 3 OS), screenshot, file descriptions |
| Commit history | 15 | **At least 6 commits** with clear messages (not one giant commit!) |
| Code quality | 5 | Clean code, TODOs are replaced with actual code |
| **Subtotal** | **50** | |

### What Good Commit Messages Look Like

```
feat: add dataset generation script        ← adding a new feature
feat: add neural network training
feat: add 2D scatter plot
fix: correct color scale on scatter plot    ← fixing a bug
feat: add training curves with slider
feat: add decision boundary visualization
feat: add 3D scatter plot
docs: write README with screenshots         ← documentation
```

**Bad commit messages:** `update`, `stuff`, `asdfg`, `final`, `done`

---

## ⚠️ Common Mistakes to Avoid

1. **Forgetting `model.eval()`** before making predictions — this can give wrong results
2. **Running scripts from the wrong folder** — always `cd` to the project root first
3. **Not activating the virtual environment** — you'll get "module not found" errors
4. **Committing the venv folder** — this makes your repo enormous. Check `.gitignore`!
5. **Leaving `...` or `TODO` in your final code** — replace ALL starter code placeholders
6. **Using the wrong Python command** — remember: `python3` on macOS/Linux, `python` on Windows

---

## 💡 Tips for Success

- **Run each file as you finish it.** Don't wait until the end. Use `fig.show()` to check your plots.
- **Commit after each task.** This builds your commit history naturally.
- **Read the error messages.** They usually tell you exactly what line has a problem and what went wrong.
- **Google the error message** if you're stuck — someone has probably had the same issue.
- **Ask for help early.** Don't spend an hour stuck on one line.

---

*You've got this. Take it one task at a time, commit as you go, and build something you're proud of!* 🚀
