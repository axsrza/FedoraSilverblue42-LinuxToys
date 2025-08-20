# Guia passo a passo para instalar o LinuxToys no Fedora Silverblue 42

Este é um guia detalhado (clique a clique) para instalar e usar o **LinuxToys** em uma instalação limpa do **Fedora Silverblue 42**.

---

## 🔹 1. Após instalar o Fedora Silverblue

* Ligue o computador e faça login na sua conta de usuário normalmente.
* Abra o **Terminal** (pressione `Super` → digite **Terminal** → `Enter`).

---

## 🔹 2. Atualizar o sistema

No terminal, execute:

```bash
rpm-ostree update
```

Se aparecerem atualizações, reinicie o sistema:

```bash
systemctl reboot
```

---

## 🔹 3. Adicionar o repositório LinuxToys

No terminal, rode os comandos abaixo **um por vez**:

```bash
wget https://copr.fedorainfracloud.org/coprs/psygreg/linuxtoys/repo/fedora-$(rpm -E %fedora)/psygreg-linuxtoys-fedora-$(rpm -E %fedora).repo
```

```bash
sudo install -o 0 -g 0 psygreg-linuxtoys-fedora-$(rpm -E %fedora).repo /etc/yum.repos.d/psygreg-linuxtoys-fedora-$(rpm -E %fedora).repo
```

```bash
rpm-ostree refresh-md
```

---

## 🔹 4. Instalar o LinuxToys

Agora instale o pacote:

```bash
rpm-ostree install linuxtoys
```

Depois, reinicie para aplicar a instalação:

```bash
systemctl reboot
```

---

## 🔹 5. Executar o LinuxToys

Após o reboot, você pode abrir o LinuxToys de duas formas:

* Pelo menu de aplicativos (procure por **LinuxToys**).
* Pelo terminal:

```bash
linuxtoys
```

---

## 🔹 6. Atualizar o LinuxToys junto com o sistema

Sempre que quiser atualizar tudo (incluindo o LinuxToys):

```bash
rpm-ostree upgrade
```

E depois reinicie o sistema.

---

## 🔹 7. (Opcional) Usar via Git (para modo CLI)

Caso queira rodar o LinuxToys direto do código (útil para automação):

Instale dependências:

```bash
rpm-ostree install git python3 python3-gobject gtk3 zenity curl wget jq
systemctl reboot
```

Clone o repositório e rode:

```bash
git clone https://github.com/psygreg/linuxtoys.git
cd linuxtoys
chmod +x p3/run.py
./p3/run.py
```

Para rodar no **modo CLI** (automatizado):

```bash
LT_MANIFEST=1 ./p3/run.py
```

> Aqui você define os scripts desejados no arquivo `manifest.txt`.

---

✅ Pronto! Agora você tem o **LinuxToys** funcionando no Fedora Silverblue 42.
