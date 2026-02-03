---
marp: true
theme: default
_class: lead
paginate: true
backgroundColor: #ffffff
color: #5B2C6F

---

# ⚡ Alpine.js
### Introduction rapide

**Une bibliothèque JavaScript légère**  


Présentée par : *Yasmine Haddad*  
Encadrée par : *M. Essarraj Fouad* 

---

## 🧠 Qu'est-ce que Alpine.js ?

- Alpine.js est une **bibliothèque JavaScript minimaliste**
- Elle permet d'ajouter de l'interactivité **directement dans le HTML**
- Pas besoin de fichiers JS complexes ni de configuration lourde
- Chaque composant gère :
  - ses données
  - ses événements
  - son affichage

---


## Exemple simple :
 **Version JavaScript classique**

```html
<button id="toggleBtn">Afficher le message</button>
<p id="message" style="display: none;">
  Bonjour Alpine.js ! 👋
</p>

<script>
  let isVisible = false;
  const btn = document.getElementById('toggleBtn');
  const msg = document.getElementById('message');
  
  btn.addEventListener('click', () => {
    isVisible = !isVisible;
    if (isVisible) {
      msg.style.display = 'block';
      btn.textContent = 'Masquer le message';
    } else {
      msg.style.display = 'none';
      btn.textContent = 'Afficher le message';
    }
  });
</script>
``` 

---

 **Version Alpine.js**

```html
<div x-data="{ visible: false }">
  <button @click="visible = !visible">
    <span x-text="visible ? 'Masquer le message' : 'Afficher le message'"></span>
  </button>
  
  <p x-show="visible">
    Bonjour Alpine.js ! 👋
  </p>
</div>

<script src="https://unpkg.com/alpinejs" defer></script>
```

- Moins de code
- Plus lisible
- Directement dans le HTML
