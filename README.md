# 🚀 Guia passo a passo para instalar o LinuxToys no Fedora Silverblue 42

[![Fedora 42](https://img.shields.io/badge/Fedora-42-blue?logo=fedora)](https://fedoraproject.org/)
[![LinuxToys](https://img.shields.io/badge/LinuxToys-COPR-green)](https://copr.fedorainfracloud.org/coprs/psygreg/linuxtoys/)
[![GitHub](https://img.shields.io/badge/Repo-LinuxToys-lightgrey?logo=github)](https://github.com/psygreg/linuxtoys)

Este é um guia detalhado (clique a clique) para instalar e usar o **LinuxToys** em uma instalação limpa do **Fedora Silverblue 42**.

---

## 📑 Sumário

1. [Após instalar o Fedora Silverblue](#-1-após-instalar-o-fedora-silverblue)
2. [Atualizar o sistema](#-2-atualizar-o-sistema)
3. [Adicionar o repositório LinuxToys](#-3-adicionar-o-repositório-linuxtoys)
4. [Instalar o LinuxToys](#-4-instalar-o-linuxtoys)
5. [Executar o LinuxToys](#-5-executar-o-linuxtoys)
6. [Atualizar o LinuxToys junto com o sistema](#-6-atualizar-o-linuxtoys-junto-com-o-sistema)
7. [Recursos úteis](#-7-recursos-úteis)

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

## 🔹 7. Recursos úteis

* 🔗 [Repositório oficial LinuxToys](https://github.com/psygreg/linuxtoys)
* 🔗 [Página COPR LinuxToys](https://copr.fedorainfracloud.org/coprs/psygreg/linuxtoys/)
* 🔗 [Documentação Fedora Silverblue](https://docs.fedoraproject.org/en-US/fedora-silverblue/)

---

✅ Pronto! Agora você tem o **LinuxToys** funcionando no **Fedora Silverblue 42** 🎉
