# Mein erstes HTML-Projekt

Diese Repositiry ist im Rahmen unseres Git- & GitHub-Workshops entstanden.

## Inhalt
- `Index.html`: Grundgerüst der Webseite
- `Readme.md`: Projektbeschreibung

## Verwendete Tools
- Visual Studio Code
- Git & GitHub

## Umsetzung mit Git, GitHub und VSCode

Git installieren
winget install --id Git.Git -e --source winget
(-e --source winget ist optional, gibt aber die Sicherheit, das zu 100% die richtigen Pakete installiert werden)

Installation von VSCode über VSCode, Website
Einstellung Sprache in VSCode: Strg + Shift + P Befehlspalette wird geöffnet.
Configure Display Language

Schritt 1 nur, wenn Sie mit ssh ihre Github oder Gitlab Repos absichern wollen. Beschreibung für Windows

1. Github oder Gitlab-Account anlegen, meistens mit SSH Key-Pair. Achtung!! ssh-URL jetzt nutzen

Wenn OpenSSH Authentication in Windows deaktiviert ist, über die PowerShell mit Administratorrechten den Status ändern:

Zuerst den Status auf Manuell oder Automatisch setzen
Set-Service ssh-agent -StartupType Manual (Automatic)

Dienst starten
Start-Service ssh-agent

Den privat Key hinzufügen bzw. registrieren.
ssh-add $HOME/ssh/id_ed25519 

Public vs. Private: Der Agent behält den Private Key im Arbeitsspeicher,
damit nicht bei jeder Verbindung ein Passwort neu eingegeben werden muss. Der Public Key hingegen wird auf GitLab/GitHub hochgeladen.


2. Im Projektordner
Den versteckten git-Ordner erstellen
git init

Einmalige Grundkonfiguration pro Rechner
git config --global user.name "Name"
git config --global user.email "Email"

--global ist optional und für den eigenen Rechner kein Problem
Arbeiten Sie auf einem fremden System, sollte --global weggelassen werden.
Dann gilt die Grundkonfiguration nur für den Projektordner.
Da die Verbindung über ssh hergestellt wird, wird das Passwort nicht mehr abgefragt.
Hier bei ssh wäre das Passwort die Passphrase, wenn im Account eine vergeben wurde.

Ist optional, wird aber empfohlen den Hauptzweig auf main einzustellen.
git branch -M main

Die Dateien für den ersten Commit vorbereiten
Alle Dateien im aktuellen Ordner vormerken
git add .

Den Status prüfen. Die Dateien sollten jetzt grün markiert sein
git status

Der erste Commit. Hier wird der aktuelle Stand festgehalten.
git commit -m "Erster Commit meiner Arbeit"

Verbindung mit dem leeren Repository (Remote) auf GitHub, gitlab.
git remote add origin git@gitlab.com:username/reponame.git

Verbindung prüfen
git remote -v

Alles ins Repository schreiben und für die Zukunft merken (-u)
git push -u origin main
später reicht ein git push

Wenn alles eingerichtet ist werden zur Aktualisierung nur noch drei Befehle im Terminal ausgeführt.
git add .
git commit -m "Name des Commits"
git push

