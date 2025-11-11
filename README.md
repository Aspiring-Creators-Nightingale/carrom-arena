# Carrom Arena — Main Repository

This repository serves as the **main hub** for the Carrom Online project, combining the **Godot client** and **Express server** as Git submodules.

It allows you to manage, develop, and deploy the project in a unified workspace while keeping the client and server codebases modular and independent.

---

## 📂 Repository Structure

```
carrom-online/
├── client/   # Godot client (submodule)
├── server/   # Express WebSocket server (submodule)
├── LICENSE
└── README.md
```

- `client/` — Contains the Godot project for the multiplayer Carrom game.
- `server/` — Contains the Node.js + Express + WebSocket server managing rooms, moves, and game state.
- `LICENSE` — License for the overall project.
- `README.md` — Documentation for the main repository.

---

## 🔹 Submodule Notes

This repository **uses submodules**, meaning the client and server are independent repositories.

### Cloning the repository

```bash
git clone --recurse-submodules git@github.com:YourName/carrom-online.git
```

If you already cloned without `--recurse-submodules`:

```bash
git submodule update --init --recursive
```

---

### Updating submodules

To pull the latest changes in a submodule:

```bash
# Inside the submodule folder
cd client
git pull origin main

cd ../server
git pull origin main
```

Then, update the main repo to point to the new submodule commits:

```bash
cd ..
git add client server
git commit -m "Update submodules to latest commits"
git push
```

---

### Adding new submodules

```bash
git submodule add <repo-url> <path>
git commit -m "Add new submodule"
git push
```

---

## ⚙️ Development Workflow

1. **Work in a submodule**

   - Make changes, commit, and push directly in the `client` or `server` repository.

2. **Update submodule reference in main repo**

   - After pushing changes in a submodule, return to the main repo:

```bash
git add client server
git commit -m "Update submodule reference"
git push
```

3. **Testing**

   - Start the server from `/server`:

```bash
cd server
pnpm install
pnpm start
```

- Open Godot client from `/client` and connect to the server for multiplayer testing.

---

## 🔹 Collaboration Tips

- **Private submodules:** All contributors must have access to the client and server repos.
- **Pulling changes:** Always use `--recurse-submodules` to keep submodules in sync.
- **Avoid editing submodules in the main repo directly** — commit inside the respective repo first.

---

## 📜 License

Apache-2.0 © 2025 Aspiring Creators
