# Kafka Failure Radar

A free, lightweight dashboard that shows **where a Kafka incident started**: consumer lag with retry topic and
dead-letter signals on one timeline, broker health, disk capacity and what to look at first.

It runs as **one container** on your own machine (or on a closed network with no internet): the agent that reads
your cluster, the dashboard and its database. No account, no telemetry. It reads offsets and cluster metadata,
never message contents.

> This repository only holds the downloads. Kafka Failure Radar is free to use but **closed-source**; the terms
> are in [LICENSE.txt](LICENSE.txt).

## Download

Get the latest package from the **[Releases](../../releases/latest)** page: `kafka-failure-radar-lite-<version>.tar.gz`
and its `.sha256` checksum file.

```bash
sha256sum -c kafka-failure-radar-lite-<version>.tar.gz.sha256
tar xzf kafka-failure-radar-lite-<version>.tar.gz
cd kafka-failure-radar-lite-<version>
KAFKA_BOOTSTRAP_SERVERS=broker-1:9092 ./install.sh
```

On Windows, run `install.ps1` in PowerShell instead. The package has a full install guide (`INSTALL.md`, and
`KURULUM-LITE.md` in Turkish).

## What you need

- Docker (Docker Desktop on Windows), on an **x86-64** processor
- Network access to your Kafka brokers, at the addresses they advertise
- About 250 MB of memory

## Limits today

- One cluster and one login per installation
- Brokers without TLS or SASL only (PLAINTEXT)
- x86-64 Linux containers only

## Support

By email, best effort, with no promised response time: kurular4@gmail.com. Please include the version
(Settings > About) and the output of `docker compose logs radar`.

## Support the project

It is free. If it saved you an incident, you can [buy me a coffee](https://buymeacoffee.com/kurular4).
Donations are voluntary and give no rights, support or features.

Apache, Apache Kafka and Kafka are trademarks of the Apache Software Foundation. This project is independent
and not affiliated with it.
