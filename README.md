# Math Flashcards App

Veebipõhise matemaatikakaartide rakendus mis töötab asible playbooki kasutades koos dockeriga.

## Kirjeldus
- Matemaatika flashcardid töötavad Docker/Nginx põhjal.
- Ansible abil saame rakenduse automaatset paigaldada.
- CI/CD pipeline valideerib Dockerfile’i, testib Ansible playbook'i ning võimaldab manuaalset deployment’i.

## Tööriistad

### 1. Git
Kasutusel projekti koodi haldamiseks ja version controliks.
### 1.1 Miks kasutasin
Sest see on kohustuslik

### 2. GitHub Actions
Kasutatakse projekti automaatseks ehitamiseks, kontrollimiseks ja testimiseks.
### 2.1 Miks kasutasin
Sest see on kohustuslik

### 3. Docker
Muudab selle ühtlaselt käivitatavaks erinevates keskkondades ja kasutab konteinereid appi jooksutamiseks.
### 3.1 Miks kasutasin
Integreerub CI/CD töövoogu, kus konteiner luuakse ja valideeritakse enne paigaldamist.

### 4. Ansible
Võimaldab rakenduse automatiseeritud paigaldamist serverisse.
### 4.1 Miks kasutasin
Sest kasutab valmis Docker image’i ja seatistab rakenduse tööle.

## Käivitamine
```sh
git clone <repo-url>
cd multi-project
shell
```
### Deployment Ansiblega:
```sh
cd ansible-deploy
ansible-playbook -i hosts.ini playbook.yml
markdown
```

## Rakenduse eemaldamine SERVERIST KUHU PIGALDASITE KOOS ANSIBLEGA

### Docker

```sh
docker stop flashcards
docker rm flashcards
docker rmi flashcards
docker system prune -a
```

### Serverist eemaldamine

```sh
ssh <server>
docker stop flashcards || true
docker rm flashcards || true
docker rmi flashcards || true
rm -rf /opt/flashcards
```

## Kuidas Tööriistad Töötavad Koos

1. Koodi hallatakse Gitiga.
2. GitHub Actions kontrollib ja ehitab projekti automaatselt.
3. Ansible paigaldab rakenduse serverisse, kasutades GitHub Actionsis valideeritud konteinerit.

## Autorid
joosep alasoo IT-23
