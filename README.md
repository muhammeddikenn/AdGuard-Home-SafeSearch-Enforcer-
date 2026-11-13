# AdGuard Home SafeSearch Enforcer 🛡️

A comprehensive, strict, and actively maintained filter list for AdGuard Home designed to enforce SafeSearch across major search engines using DNS rewrite rules—**and completely block unsupported search engines** that lack DNS-level SafeSearch capabilities to prevent filter bypassing. Ideal for protecting families, schools, and networks from explicit content.

## 🔒 How It Works (Zero-Bypass Policy)

1. **Supported Engines (Enforced):** Queries are automatically rewritten via CNAME to the engine's official SafeSearch endpoint.
2. **Unsupported Engines (Blocked):** Search engines that rely solely on browser cookies or account settings (such as Baidu or Yahoo) are blocked at the DNS level so users cannot bypass network-wide filtering.

## 🚀 Search Engine Coverage

This repository is continuously expanding. Below is the current status of supported and blocked search engines:

| Search Engine | Policy / Status | Action / CNAME Endpoint |
| :--- | :---: | :--- |
| **Google** | ✅ SafeSearch Enforced | `forcesafesearch.google.com` |
| **Bing** | ✅ SafeSearch Enforced | `strict.bing.com` |
| **Yandex** | ✅ SafeSearch Enforced | `familysearch.yandex.ru` / `.com` |
| **DuckDuckGo** | ✅ SafeSearch Enforced | `safe.duckduckgo.com` |
| **Brave Search** | ✅ SafeSearch Enforced | `forcesafe.search.brave.com` |
| **Pixabay** | 🚧 Planned (Enforce) | `safesearch.pixabay.com` |
| **YouTube (Restricted)** | 🚧 Planned (Enforce) | `restrict.youtube.com` |
| **Baidu** | 🚫 Blocked (No DNS SafeSearch) | Domain blocked (`\|\|baidu.com^`) |
| **Yahoo Search** | 🚫 Blocked (No DNS SafeSearch) | Domain blocked (`\|\|search.yahoo.com^`) |
| **Others (Startpage, Qwant, etc.)** | 🔄 Investigating | *Enforce if supported, otherwise block* |

## 📥 How to Use

You can easily add this list to your AdGuard Home instance as a custom filtering list:

1. Copy the **Raw** link of the `adguard_safesearch.txt` file from this repository.
2. Open your **AdGuard Home** administration panel.
3. Navigate to **Filters** > **DNS blocklists**.
4. Click **Add blocklist** > **Add a custom list**.
5. Paste the Raw URL, give it a recognizable name (e.g., `SafeSearch Enforcer`), and click **Save**.

## 📋 Rule Syntax & Examples

This list uses AdGuard Home's native `$dnsrewrite` and domain blocking filter syntax:

```text
# Enforce SafeSearch via DNS Rewrite
||search.brave.com^$dnsrewrite=NOERROR;CNAME;forcesafe.search.brave.com

# Block Search Engines Without DNS SafeSearch Support
||baidu.com^
||search.yahoo.com^
