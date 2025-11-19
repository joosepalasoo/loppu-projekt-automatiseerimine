# Multi-Project Flashcards System

Ühiskaust, mis sisaldab veebipõhise matemaatikakaartide rakenduse ning Ansible-põhise serverisse juurutamise lahenduse.

## Kirjeldus
- Webapp kuvab matemaatika flashcard'e ning töötab Docker/Nginx põhjal.
- Ansible projekt võimaldab sama rakenduse automaatset paigaldamist teise Ubuntu VM-i.
- CI/CD pipeline valideerib Dockerfile’i, testib Ansible playbook'i ning võimaldab manuaalset deployment’i.

## Tööriistad

### 1. Git
Miks: kasutusel versioonihalduseks.

### 2. GitHub Actions
Miks: CI/CD pipeline automaatseks testimise jaoks.

### 3. Docker
Miks: rakendus on staatiline ja töötab konteineris.

### 4. Ansible
Miks: võimaldab rakendust serverisse automatiseeritult paigaldada.

## Käivitamine
git clone <repo-url>
cd multi-project
shell
Kopeeri kood

### Webapp container:
cd webapp
docker build -t flashcards .
docker run -d -p 8080:80 flashcards
shell
Kopeeri kood

### Deployment Ansible abil:
cd ansible-deploy
ansible-playbook -i hosts.ini playbook.yml
markdown
Kopeeri kood

## Kuidas Tööriistad Töötavad Koos

1. Webapp hoitakse GitHubis.
2. GitHub Actions kontrollib ja ehitab projekti.
3. Ansible teeb serveri deployment'i.

## Autorid
joosep alasoo IT-23
