````md id="lab17receiver"
# LAB 17 — BroadcastReceiver Android

![Android](https://img.shields.io/badge/Platform-Android-green)
![Java](https://img.shields.io/badge/Language-Java-orange)
![Broadcast](https://img.shields.io/badge/Component-BroadcastReceiver-blue)

## 📌 Description

Ce laboratoire présente l’utilisation des BroadcastReceiver Android pour détecter les événements système et internes.

Fonctionnalités :

- Receiver dynamique ;
- Receiver statique ;
- Broadcast personnalisé ;
- détection du mode avion ;
- BOOT_COMPLETED.

---

# 🎯 Objectifs

- comprendre les BroadcastReceiver ;
- utiliser les broadcasts système ;
- créer un custom broadcast ;
- comprendre exported et permissions Android.

---

# ⚙️ Prérequis

- Android Studio
- Java
- Android SDK

---

# 🚀 Étape 1 — Création du Projet

Créer :

```text
Empty Activity
Language: Java
````
<img width="197" height="435" alt="image" src="https://github.com/user-attachments/assets/2ac116ef-1c64-47da-84c4-00bb3717fc55" />
---

# 📡 Étape 2 — Receiver Dynamique

Créer :

```java id="k8v2rm"
public class AirplaneReceiver
extends BroadcastReceiver {

    @Override
    public void onReceive(
    Context context,
    Intent intent) {

    }
}
```

---

# ✈️ Détection Mode Avion

```java id="m4x7pl"
IntentFilter filter =
new IntentFilter(
Intent.ACTION_AIRPLANE_MODE_CHANGED
);
```

---

# 🔥 Étape 3 — Receiver Statique

Créer :

```java id="u1q5ws"
public class BootReceiver
extends BroadcastReceiver {

}
```

---

# 📱 Étape 4 — Manifest

Ajouter :

```xml id="p6r9xt"
<receiver
    android:name=".BootReceiver"
    android:exported="true">

    <intent-filter>
        <action android:name=
        "android.intent.action.BOOT_COMPLETED"/>
    </intent-filter>

</receiver>
```

---

# 🔐 Permission Boot

```xml id="x3m8vn"
<uses-permission
android:name="android.permission.RECEIVE_BOOT_COMPLETED"/>
```

---

# 📤 Étape 5 — Custom Broadcast

Envoyer :

```java id="f7q2lk"
Intent intent =
new Intent("CUSTOM_ACTION");

sendBroadcast(intent);
```

---

# 📥 Étape 6 — Receiver Custom

```java id="j5v1pr"
IntentFilter filter =
new IntentFilter("CUSTOM_ACTION");
```

---

# 🎨 Étape 7 — Interface

Ajouter :

* bouton envoyer broadcast ;
* TextView état.

---

# ▶️ Étape 8 — Exécution

Résultat attendu :

* détection mode avion ;
* réception broadcast custom ;
* receiver boot actif.

---

# 📚 Concepts Appris

* BroadcastReceiver
* Dynamic Receiver
* Static Receiver
* IntentFilter
* Android Events

---

# ⚠️ Bonnes Pratiques

* unregisterReceiver ;
* éviter traitements lourds ;
* utiliser exported correctement ;
* respecter restrictions Android modernes.

---

# 👨‍💻 Auteur

Ayoub Laafar — EMSI Marrakech

```
```

