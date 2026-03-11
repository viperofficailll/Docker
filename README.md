# 🐳 Docker
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)

---

## 📦 What is Containerization?

- Packs your **code, libraries, and settings** in one box
- Solves the *"it works on my machine"* problem
- Lighter than a VM — shares the host OS
- `Docker` is the most popular tool to build & run containers

> 💡 Pack your app in a box → ship it anywhere → it just works!

---
## 🤔 Why Does Containerization Matter?

- 🔁 **Consistency** — Works the same on *every* machine, no surprises
- ⚡ **Speed** — Starts in seconds, saves time
- 🔒 **Isolation** — One app crashes? Others keep running safely
- 📈 **Scale** — Getting more users? Spin up more containers instantly
- ☁️ **Portable** — Works on any computer, server, or cloud without changes

> 💡 Just like shipping containers made cargo easy to transport worldwide — Docker does the same for your app.
---
## 🛠️ Problems Docker Solves

### For Developers 👨‍💻
- ❌ *"Works on my machine"* → ✅ Works on **every** machine
- ❌ Spending hours setting up environment → ✅ One command `docker run` and you're done
- ❌ App breaks when teammate runs it → ✅ Everyone runs the **exact same box**

### For Operations Teams ⚙️
- ❌ Deploying is slow and risky → ✅ Ship containers **instantly and safely**
- ❌ One app crash takes everything down → ✅ Each app is **isolated** in its own container
- ❌ Hard to handle more users → ✅ Just spin up **more containers** in seconds

> 💡 Docker gives developers and ops teams a **common language** —
> build it once, run it anywhere, manage it easily.



---
## 🏗️ Docker Architecture

![Docker Architecture](https://miro.medium.com/v2/1*GoZ56yZNpG_VnGGvqhYlCQ.png)
> 📖 Source: [Docker Architecture — MrDevSecOps](https://medium.com/@mrdevsecops/docker-architecture-7cffa1d8f1df)

---

> 💡 Docker works like a **restaurant** — you order, the kitchen cooks, food comes from a store.

---

### 3 Main Parts

| Part | Analogy | Role |
|---|---|---|
| 🖥️ **Client** | You (customer) | Where you type commands |
| ⚙️ **Docker Host** | The kitchen | Where everything runs |
| 🏪 **Registry** | Grocery store | Stores ready-made images |

---

### 🖥️ Client — *You giving orders*
- You type commands like `docker build`, `docker pull`, `docker run`
- These commands are sent to the **Docker Daemon** to execute

---

### ⚙️ Docker Host — *The kitchen*
- **Docker Daemon** — the brain, listens to your commands and does the work
- **Images** — ready-made recipes pulled from the Registry
- **Containers** — the actual running apps, created from images

---

### 🏪 Registry — *The store*
- Stores all **pre-built images** (Ubuntu, Nginx, Redis, etc.)
- **Docker Hub** is the default public store — free to use
- You can also create your **own private registry**

---

### 🔄 How it all flows
```
You type command   →   Client
Client talks to    →   Docker Daemon
Daemon fetches     →   Image from Registry
Daemon runs        →   Container 🎉
```

> 💡 **Image** = Recipe &nbsp;|&nbsp; **Container** = Cooked meal &nbsp;|&nbsp; **Registry** = Cookbook store


---

## ⚙️ How Does Docker Work?

> 💡 Think of Docker like an **online food order** — you pick a meal, it gets prepared, and served to you.


### 🔄 Step by Step (Simply)

**Step 1 — You write a `Dockerfile`**
- A simple text file with instructions like:
  *"Use Python, copy my code, run this command"*
- Think of it as writing a **recipe** 📝

**Step 2 — Docker `build` creates an Image**
- Docker reads your Dockerfile and **bakes it into an Image**
- Image = a ready-to-use **frozen meal** 🧊

**Step 3 — Docker `run` starts a Container**
- Docker takes your image and **brings it to life**
- Container = your frozen meal, now **heated and ready** 🍽️

**Step 4 — Container runs your app**
- Your app is now running in its own **isolated box**
- Stop it, restart it, copy it — anytime ✅

---

### 🗺️ The Full Flow
```
Dockerfile   →   docker build   →   Image
   📝                               🧊
                                     ↓
                              docker run
                                     ↓
                               Container 🎉
                            (your app is live!)
```

---

### 3 Things to Remember

| Term | Simply |
|---|---|
| 📝 `Dockerfile` | Your recipe / instructions |
| 🧊 `Image` | The frozen, ready-to-use package |
| 📦 `Container` | The live, running app |

> 💡 Write once → Build once → Run anywhere!


---
## 🖼️ What is a Docker Image?

> 💡 A Docker Image is like a **मomo recipe (मम: को recipe)** —
> the recipe itself is not a momo, but every momo you make from it tastes identical.


### Simply Put
- An image is a **read-only template** used to create containers
- It contains your **code + libraries + settings** — everything your app needs
- You **can't run** an image directly — you run a **container made from it**


### 🥟 Analogy

| Docker Term | Analogy |
|---|---|
| 🖼️ **Image** | Momo recipe (template) |
| 📦 **Container** | The actual momo being steamed (running app) |
| 🏪 **Docker Hub** | Cookbook store where you find recipes |

---

### Where do Images come from?

- 📝 **You build one** — write a `Dockerfile` → `docker build`
- 🏪 **You pull one** — download from Docker Hub → `docker pull ubuntu`

---

### 🔑 Key Facts

- ✅ One image → **many containers**
- ✅ Images are **read-only** (never change)
- ✅ Containers are **temporary**, images are **permanent**
- ✅ Images are made of **layers** (each step in Dockerfile = one layer)

---

### Layers? Simply...
```
Layer 3 → Add your momo filling          ← your changes
Layer 2 → Prepare the dough              ← your changes
Layer 1 → Base ingredients (flour, water) ← from Docker Hub
```
> 💡 Each layer is **cached** — so rebuilding is super fast! 🚀
> Just like you don't remake the dough every time — you reuse it! 🥟

---

## 📦 What is a Docker Container?

> 💡 If a Docker Image is the **momo recipe**,
> then a Container is the **actual momo being steamed right now!** 🥟


### Simply Put
- A container is a **live, running instance** of an image
- It has everything needed to run your app — all in one isolated box
- You can **start, stop, delete** a container anytime without affecting the image

---

### 🥟 Analogy

| Docker Term | Analogy |
|---|---|
| 🖼️ **Image** | Momo recipe |
| 📦 **Container** | Momo being steamed right now |
| 🍽️ **Running Container** | Momo ready to eat |
| 🗑️ **Stopped Container** | Momo eaten, plate is empty |

---

### Image vs Container

| | 🖼️ Image | 📦 Container |
|---|---|---|
| State | Frozen, static | Live, running |
| Changes | ❌ Never changes | ✅ Can change while running |
| Reuse | ✅ Make many containers | ❌ One running instance |

---

### 🔑 Key Facts
- ✅ One image can create **many containers** at once
- ✅ Each container is **isolated** — they don't interfere
- ✅ Containers are **lightweight** — starts in seconds
- ✅ When deleted, container is gone — **image stays safe**

---

### Simple Commands
```bash
docker run ubuntu      # create & start a container from image
docker ps              # see all running containers
docker stop <name>     # stop a container
docker rm <name>       # delete a container
```

> 💡 Container = **momo in the steamer** — make as many as you want,
> the recipe (image) never changes! 🥟

---

## 📝 What is a Dockerfile?




### Simply Put
- A Dockerfile is a **simple text file** with step-by-step instructions
- Docker **reads this file** and builds an Image from it
- No Dockerfile = No Image = No Container

---

### 🥟 How it connects
```
Dockerfile   →   docker build   →   Image   →   docker run   →   Container
(recipe card)     (cooking)        (frozen momo)   (steaming)     (ready momo!)
```

---

### 📄 A Simple Dockerfile (with plain explanation)
```dockerfile
# Step 1 — Start with a base (like buying flour from a store)
FROM ubuntu

# Step 2 — Install what you need (like preparing your tools)
RUN apt-get install python3

# Step 3 — Copy your code into the container
COPY . /app

# Step 4 — Tell Docker how to start your app
CMD ["python3", "app.py"]
```

---

### 🔑 Most Used Instructions

| Instruction | Simply means |
|---|---|
| `FROM` | Start from this base image |
| `RUN` | Run this command while building |
| `COPY` | Copy files into the container |
| `CMD` | Run this when container starts |
| `EXPOSE` | Open this port for traffic |

---

### Why is it used? ✅

- ✅ **Automates** setup — no manual installation ever
- ✅ **Consistent** — same result every time, every machine
- ✅ **Shareable** — share one file, anyone can build your app
- ✅ **Version controlled** — save it in Git like normal code

> 💡 Without Dockerfile, you'd have to manually set up every machine —
> like making momo without a recipe, **every cook makes it differently!** 🥟


---

## 🎼 What is Docker Compose?

> 💡 Docker Compose is like ordering a **full Nepali thali** —
> instead of ordering dal, bhat, tarkari, momo one by one,
> you order the **whole set in one go!** 🍱


### Simply Put
- Docker Compose lets you run **multiple containers together**
- Instead of starting each container manually, **one command starts all**
- Everything is defined in a single file called `docker-compose.yml`

---

### 🍱 Analogy

| Docker Term | Analogy |
|---|---|
| 🍚 **Container 1** (App) | Bhat (rice) |
| 🫘 **Container 2** (Database) | Dal |
| 🥗 **Container 3** (Cache) | Tarkari |
| 🍱 **Docker Compose** | The full thali — served together! |

---

### Without vs With Compose
```bash
# ❌ Without Compose — start everything manually
docker run app
docker run database
docker run cache

# ✅ With Compose — one command does it all!
docker compose up
```

---

### 📄 A Simple docker-compose.yml
```yaml
version: "3"
services:

  app:                        # your main application
    build: .
    ports:
      - "3000:3000"

  database:                   # your database
    image: postgres
    environment:
      POSTGRES_PASSWORD: 1234

  cache:                      # your cache
    image: redis
```

---

### 🔑 Key Facts

- ✅ **One file** controls all your containers
- ✅ **One command** to start everything → `docker compose up`
- ✅ **One command** to stop everything → `docker compose down`
- ✅ Containers can **talk to each other** automatically

---

### Simple Commands
```bash
docker compose up      # start all containers
docker compose down    # stop all containers
docker compose logs    # see what's happening
docker compose ps      # see running containers
```

> 💡 Docker Compose = **full thali order** —
> one order, everything comes together, nothing missing! 🍱

---

## 🤔 Why is Docker Compose Useful?

> 💡 Imagine running a **Nepali restaurant** —
> you need a cook, a waiter, and a cashier working **together**.
> Docker Compose makes sure everyone shows up and works in sync! 🍱


### The Real Problem Without Compose

Most real apps need **multiple services** running together —

| Service | Example |
|---|---|
| 🖥️ **Frontend** | Your website |
| ⚙️ **Backend** | Your API server |
| 🗄️ **Database** | PostgreSQL / MongoDB |
| ⚡ **Cache** | Redis |

Without Compose — you'd have to **manually start, connect, and manage** each one.
That's slow, painful, and error-prone! 😤

---

### ✅ What Compose Solves

- 🚀 **One command** — `docker compose up` starts everything together
- 🔗 **Auto connects** — services can talk to each other automatically
- 📄 **One file** — entire app setup lives in `docker-compose.yml`
- 👥 **Team friendly** — share one file, whole team runs same setup
- 🔁 **Consistent** — works same on every machine, every time

---

### 🍱 Real World Flow

---

## 🛠️ Common Use Cases of Docker

> 💡 Docker is like a **Nepali khaja set** —
> useful for breakfast, lunch, dinner
> and every stage in between! 🍱


### 👨‍💻 In Development (Writing Code)

| Use Case | Nepali Analogy |
|---|---|
| 🖥️ **Local Setup** | New cook joins → give them the **recipe book** → cooking in minutes, no confusion |
| 🧪 **Testing** | Test momo in a **clean steamer** every time, no yesterday's smell |
| 🔄 **Multiple Versions** | Make **sukuti and momo** in same kitchen without mixing them up |
| 👥 **Team Consistency** | Every dhaba in Nepal makes dal bhat the **same way** from same recipe |

---

### 🚀 In Production (Serving Real Users)

| Use Case | Nepali Analogy |
|---|---|
| 📦 **Deploying Apps** | Pack your **khaja set in a tiffin box** → deliver anywhere → tastes the same |
| 📈 **Scaling** | Dashain rush? Open **more counters** at the momo pasal instantly |
| 🔒 **Isolation** | One **tawa** breaks? Other tawas keep cooking safely |
| 🔁 **Updates** | New menu item ready? Serve it **while old items are still being cooked** |

---

### 🌍 Real World Examples
```
🏦 Banks        → Each service runs in its own safe tiffin box
🛒 E-commerce   → Spin up more counters during Dashain sales 🎉
🎮 Gaming       → Open new game tables instantly for new players
📱 Startups     → Cook fast, deliver anywhere, add more cooks when busy
```

---

### 🔑 Simply Remember

- 👨‍💻 **Dev** — same recipe, same taste, every cook, every kitchen
- 🚀 **Production** — fast delivery, easy scaling, nothing interferes

> 💡 Docker is like **MoMo Pasal during Dashain** —
> same recipe, more steamers, more counters,
> more customers served — **zero chaos!** 🥟


---

## ⚠️ Docker Security & Risks to Know

> 💡 Docker is like running a **busy Nepali restaurant** —
> if you don't manage it properly,
> anyone can walk into the kitchen and mess things up! 🍱


### 🔒 Security Risks

| Risk | Simply |
|---|---|
| 🚪 **Running as Root** | Like giving **every customer the keys** to your kitchen — dangerous! Always run as limited user |
| 📦 **Untrusted Images** | Downloading random images = **buying momo from unknown source** — could be poisoned! Use official images only |
| 🔓 **Exposed Ports** | Opening wrong ports = **leaving restaurant back door open** at night — close what you don't need |
| 🔑 **Secrets in Dockerfile** | Putting passwords in Dockerfile = **writing safe combination on the wall** — never do this! |

---

### ⚙️ Operational Risks

| Risk | Simply |
|---|---|
| 💾 **Disk Filling Up** | Old containers and images pile up = **leftover food blocking the kitchen** — clean regularly |
| 📈 **No Resource Limits** | One container uses all memory = **one greedy customer eating everyone's dal bhat** — set limits! |
| 📋 **No Logging** | Not monitoring containers = **running restaurant with eyes closed** — always check logs |
| 🔄 **No Restart Policy** | Container crashes and stays down = **cook leaves, no one replaces them** — set auto restart |

---

### ✅ Simple Best Practices
```bash
# ✅ Always use specific image versions
FROM ubuntu:22.04          # not just FROM ubuntu (too risky!)

# ✅ Never store secrets in Dockerfile
ENV PASSWORD=1234          # ❌ wrong — visible to everyone!
# Use environment files instead ✅

# ✅ Set resource limits
docker run --memory=512m --cpus=1 myapp

# ✅ Clean up regularly
docker system prune        # removes unused containers & images
```

---

### 🔑 Simply Remember

| Do ✅ | Don't ❌ |
|---|---|
| Use official images | Use random unknown images |
| Set resource limits | Let containers use unlimited memory |
| Keep secrets in env files | Put passwords in Dockerfile |
| Clean old containers | Let unused containers pile up |
| Monitor logs | Run containers blindly |

> 💡 Docker security is like running a **safe Nepali restaurant** —
> lock the back door, trust your suppliers,
> don't give everyone the kitchen keys,
> and clean up after closing! 🔒🍱

---

## 🔄 Docker for Consistent Environments

> 💡 Imagine every **dal bhat** ordered in Nepal
> tastes exactly the same — whether you're in
> Kathmandu, Pokhara, or Mustang.
> That's what Docker does for your app! 🍱


### The Real Problem Without Docker
```
👨‍💻 Developer's laptop    → App works fine ✅
🧪 Tester's machine       → App crashes ❌
🚀 Production server      → Something else breaks ❌

Reason → Everyone has different setup, versions, settings!
```

> 😤 Like giving the **same momo recipe** to 3 cooks —
> but each has different flour, different steamer, different fire.
> Result? **3 different momos!**

---

### ✅ How Docker Fixes This

| Stage | Without Docker | With Docker |
|---|---|---|
| 👨‍💻 **Development** | *"Works on my machine"* | Same container = same result |
| 🧪 **Testing** | Different setup = unreliable tests | Clean identical box every test |
| 🚀 **Deployment** | Server setup takes hours | Ship container = runs instantly |

---

### 🥟 The Momo Analogy
```
Without Docker                    With Docker
──────────────                    ───────────
Dev makes momo with    →          Everyone uses the
different flour                   SAME tiffin box 🥟

Tester uses different  →          Open tiffin anywhere —
steamer                           same momo inside!

Production has         →          Kathmandu, Pokhara, Mustang
different fire                    — tastes IDENTICAL 🎉
```

---

### 🔑 3 Stages Simply

**👨‍💻 Development**
- Every developer runs the **exact same container**
- New teammate joins → `docker run` → ready in minutes
- No more *"install this, configure that"* confusion

**🧪 Testing**
- Tests run in a **fresh clean container** every time
- No leftover data, no surprise failures
- Same test environment = **reliable results**

**🚀 Deployment**
- Same container tested locally = **same container deployed**
- No surprises on the production server
- Deploy in seconds, not hours

---

> 💡 Docker is like a **sealed tiffin box from your aamaa** —
> same love, same taste, same ingredients,
> whether you open it in Kathmandu office
> or Pokhara hiking trail! 🍱❤️