## 📌 Nivy AIOS Work Status — Quick Resume

- **Last updated:** 2026-09-16
- **Purpose here:** Supporting email-verification capability/repository; this is not the main AIOS implementation repo.
- **Nivy AIOS work status:** See `AIOS-WORK-STATUS.md` for last work, progress, next task, blockers and evidence.
- **Where to start:** `AIOS-WORK-STATUS.md` → then `nivyindia/Nivy-Next-AIOS` canonical implementation plan/tracker.
- **Exact completion %:** Do not infer from this repository's code/template count.

---

[![Crate](https://img.shields.io/crates/v/check-if-email-exists.svg)](https://crates.io/crates/check-if-email-exists)
[![Docs](https://docs.rs/check-if-email-exists/badge.svg)](https://docs.rs/check-if-email-exists)
[![Docker](https://img.shields.io/docker/v/reacherhq/backend?color=0db7ed&label=docker&sort=date)](https://hub.docker.com/r/reacherhq/backend)
[![Actions Status](https://github.com/reacherhq/check-if-email-exists/workflows/pr/badge.svg)](https://github.com/reacherhq/check-if-email-exists/actions)

<br /><br />

<p align="center"><img align="center" src="https://storage.googleapis.com/saasify-uploads-prod/696e287ad79f0e0352bc201b36d701849f7d55e7.svg" height="96" alt="reacher" /></p>
<h1 align="center">check-if-email-exists</h1>
<h4 align="center">Check if an email address exists without sending any email.<br/>Comes with a <a href="./backend">⚙️ HTTP backend</a>.</h4>

<br /><br /><br />

## 👉 Live Demo: https://reacher.email

<img src="https://storage.googleapis.com/saasify-uploads-prod/696e287ad79f0e0352bc201b36d701849f7d55e7.svg" height="68" align="left" />

This is open-source, but I also offer a **SaaS** solution that has `check-if-email-exists` packaged in a nice friendly web interface. If you are interested, find out more at [No2Bounce.com](https://no2bounce.com/?ref=github). If you have any questions, you can contact me at amaury@reacher.email.

<br />

## Get Started

3 non-SaaS ways to get started with `check-if-email-exists`.

### 1. ⚙️ HTTP backend using Docker (popular method 🥇) [[Full docs](./backend/README.md)]

This option allows you to run a HTTP backend using Docker 🐳, on a cloud instance or your own server. Please note that outbound port 25 must be open.

```bash
docker run -p 8080:8080 reacherhq/backend:latest
```

Then send a `POST http://localhost:8080/v0/check_email` request with the following body:

```js
{
    "to_email": "someone@gmail.com",
    "proxy": {
        "host": "my-proxy.io",
        "port": 1080,
        "username": "me",
        "password": "pass"
    }
}
```

**Note regarding proxy servers**
It is possible to operate Reacher with your own IP addresses. But if you wish to process more than very small volumes you will need SMTP proxy servers. For SMTP proxy servers please use [proxy25.com](https://proxy25.com/?ref=github)

### 2. Download the CLI [[Full docs](./cli/README.md)]

> Note: The CLI binary doesn't connect to any backend, it checks the email directly from your computer.

Head to the [releases page](https://github.com/reacherhq/check-if-email-exists/releases) and download the binary for your platform.

```bash
> $ check_if_email_exists --help
check_if_email_exists 0.9.1
Check if an email address exists without sending an email.

USAGE:
    check_if_email_exists [FLAGS] [OPTIONS] [TO_EMAIL]
```

Check out the [dedicated README.md](./cli/README.md) for all options and flags.

### 3. Programmatic Usage [[Full docs](https://docs.rs/check-if-email-exists)]

In your own Rust project, you can add `check-if-email-exists` in your `Cargo.toml`:

```toml
[dependencies]
check-if-email-exists = "0.9"
```

And use it in your Rust project as documented by the upstream project.

## License

`check-if-email-exists`'s source code is provided under a **dual license model**.

### Commercial license

If you want to use `check-if-email-exists` to develop commercial sites, tools, and applications, the Commercial License is the appropriate license. Purchase a commercial license from the upstream project.

### Open source license

If you are creating an open-source application under a license compatible with the GNU Affero GPL License v3, you may use `check-if-email-exists` under the terms of the [AGPL-3.0](./LICENSE.AGPL).
