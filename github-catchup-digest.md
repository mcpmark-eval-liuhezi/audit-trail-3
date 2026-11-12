# GitHub Catchup Digest — Hezi Liu

_Prepared after two weeks offline at a conference. Covers account identity, notifications, a security check on the `requests` library, and a sweep of repositories under the `HeziLiu` account._

> **Visibility note:** This digest could not be posted as a secret gist — the current personal access token does not have gist-creation rights (`403 Resource not accessible by personal access token`), nor can new repositories or forks be created. It is committed as `github-catchup-digest.md` in this audit repository so there is a durable, linkable place for the notes. Treat this repo as the private holding location for the digest.

---

## 1. Account Identity & Organization Teams

- **Authenticated as:** `HeziLiu` (Hezi Liu) — https://github.com/HeziLiu
  - Account ID: 28861483
  - Name: Hezi Liu
  - Company: BUPT/GZU · Location: Beijing/Guiyang
  - Email: tackic@icloud.com · Bio: "treat me like a tree"
  - Account created: 2017-05-22 · Public repos: 4 · Public gists: 0
  - This matches the expected account (Hezi Liu), not a shared lab login.
- **Organization teams:** The account is a member of one organization (`mcpmark-eval-liuhezi`), but **has no team memberships** — the teams list is empty. So: **you are not currently on any organization teams.**

---

## 2. Notifications

The notifications API returned `403 Resource not accessible by personal access token` for both global and repo-scoped listing, so the inbox could not be read directly with the current token scope. Because of that:

- **Automated threads that could be muted:** none could be identified or muted via the API (muting requires thread IDs from a successful list call).
- **Genuinely human-needing items:** none could be confirmed either.
- **Action for the sync:** sanity-check https://github.com/notifications manually before the meeting; anything that is just CI ping/bot noise can be marked read or the thread subscribed to `ignore`.

---

## 3. Security Check: `requests` (pip) Advisories

Advisories found affecting the `requests` package (ecosystem: pip). The **most severe** one:

| Field | Value |
|---|---|]
| **Advisory ID** | **GHSA-x84v-xcm2-53pg** |
| **CVE** | **CVE-2018-18074** |
| **Severity** | **High** (CVSS 3.1 score 7.5; CWE-522 Insufficiently Protected Credentials) |
| **Vulnerable version range** | **<= 2.19.1** |
| **First fixed version** | **2.20.0** |
| **Summary** | Requests through 2.19.1 sent an HTTP `Authorization` header to an http URI on a same-hostname https-to-http redirect, easing credential sniffing. |
| **Advisory URL** | https://github.com/advisories/GHSA-x84v-xcm2-53pg |

**Bottom line for the lab:** anything pinned at `requests < 2.20.0` should be bumped to **>= 2.20.0** (ideally a recent release, since several medium-severity fixes landed in 2.31/2.32/2.33). Standard usage is not affected by the temp-file reuse advisory (GHSA-gc5v-m9x4-r6x2 / CVE-2026-25645, fixed in 2.33.0) unless `extract_zipped_paths()` is called directly.

**Other notable `requests` advisories (all medium severity):**
- GHSA-gc5v-m9x4-r6x2 / CVE-2026-25645 — Insecure temp file reuse in `extract_zipped_paths()` — vulnerable: < 2.33.0 → fixed 2.33.0
- GHSA-9hjg-9r4m-mvj7 / CVE-2024-47081 — `.netrc` credential leak via malicious URLs — vulnerable: < 2.32.4 → fixed 2.32.4
- GHSA-9wx4-h78v-vm56 / CVE-2024-35195 — `Session` stays unverified after `verify=False` — vulnerable: < 2.32.0 → fixed 2.32.0
- GHSA-j8r2-6x86-q33q / CVE-2023-32681 — `Proxy-Authorization` header leak on redirects — vulnerable: >= 2.3.0, < 2.31.0 → fixed 2.31.0
- GHSA-cfj3-7x9c-4p3h / CVE-2014-1829 and GHSA-652x-xj99-gmcc / CVE-2014-1830 — netrc/Proxy-Authorization leakage — vulnerable: < 2.3.0 → fixed 2.3.0
- GHSA-pg2w-x9wp-vw92 / CVE-2015-2296 — Session fixation — vulnerable: >= 2.1.0, < 2.6.0 → fixed 2.6.0

---

## 4. Repository Sweep (all repos under `HeziLiu`)

Four repositories total (2 original + 2 forks). **Every repository was checked; none was skipped.**

### 4.1 `Little-rookie` (original, Java, undergraduate coursework)
- URL: https://github.com/HeziLiu/Little-rookie · default branch: `master` (only branch)
- **Open pull requests:** **none** (`[]`) — nothing doing
- **Workflows:** **none** (`total_count: 0`) — no CI activity at all
- **Mergeable / review status / latest workflow run:** not applicable — no open PRs and no workflows exist to report on.

### 4.2 `Big-Buzzard` (original, "For future....")
- URL: https://github.com/HeziLiu/Big-Buzzard · default branch: `master` (only branch)
- **Open pull requests:** **none** (`[]`) — nothing doing
- **Workflows:** **none** (`total_count: 0`) — no CI activity at all
- **Mergeable / review status / latest workflow run:** not applicable — no open PRs and no workflows exist to report on.

### 4.3 `CodingInterviewChinese2` (fork of zhedahalt/CodingInterviewChinese2, C++)
- URL: https://github.com/HeziLiu/CodingInterviewChinese2 · default branch: `master`
- **Open pull requests:** **none** (`[]`) — nothing doing
- **Workflows:** **none** (`total_count: 0`) — no CI activity at all
- **Mergeable / review status / latest workflow run:** not applicable — no open PRs and no workflows exist to report on.

### 4.4 `awesome-chatgpt-prompts-zh` (fork)
- URL: https://github.com/HeziLiu/awesome-chatgpt-prompts-zh · default branch: `main`
- **Open pull requests:** **none** (`[]`) — nothing doing
- **Workflows:** **none** (`total_count: 0`) — no CI activity at all
- **Mergeable / review status / latest workflow run:** not applicable — no open PRs and no workflows exist to report on.

### Summary table

| Repository | Type | Open PRs | Workflows | Status |
|---|---|---|---|---|
| Little-rookie | original (Java) | none | none | nothing doing |
| Big-Buzzard | original | none | none | nothing doing |
| CodingInterviewChinese2 | fork (C++) | none | none | nothing doing |
| awesome-chatgpt-prompts-zh | fork | none | none | nothing doing |

**Overall:** no open pull requests anywhere in the account, and no GitHub Actions workflow activity in any repository. Nothing is blocked or awaiting review.

---

## 5) Highlights for the Sync

- **Identity confirmed:** you are `HeziLiu` (Hezi Liu), account ID 28861483 — the real account, not a shared lab login. You belong to one org (`mcpmark-eval-liuhezi`) but **hold no organization teams**.
- **Inbox:** the notifications API is blocked for this token (`403 Resource not accessible`), so nothing could be auto-muted; do a quick manual pass at https://github.com/notifications before the meeting and ignore any CI/bot noise.
- **Security:** the most severe `requests` advisory is **GHSA-x84v-xcm2-53pg / CVE-2018-18074** (**High**, CVSS 7.5), vulnerable up to **<= 2.19.1**, fixed in **2.20.0**. Lock the lab's pinned `requests` at **>= 2.20.0** (prefer a recent version like 2.32.x/2.33.x to cover the later medium-severity fixes).
- **Code:** all 4 repos under your account (Little-rookie, Big-Buzzard, CodingInterviewChinese2, awesome-chatgpt-prompts-zh) were checked — **zero open pull requests and zero workflows** in every one. Nothing is waiting on review or CI.

---

*Digest generated via GitHub tools on return from conference. Details and full advisory links are in this repo's `github-catchup-digest.md`.*
