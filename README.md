# AdGuard Home SafeSearch Enforcer 🛡️

A comprehensive and growing filter list for AdGuard Home designed to automatically enforce SafeSearch across major search engines using DNS rewrite rules. Ideal for protecting families, schools, and children from explicit content network-wide.

## 🚀 Supported Search Engines

This list currently enforces SafeSearch on the following search engines:

- **Google** (`forcesafesearch.google.com`)
- **Bing** (`strict.bing.com`)
- **Yandex** (`familysearch.yandex.ru` / `.com`)
- **DuckDuckGo** (`safe.duckduckgo.com`)
- **Brave Search** (`forcesafe.search.brave.com`)
- **Pixabay** (`safesearch.pixabay.com`) *(Opsiyonel - listenizde varsa ekleyebilirsiniz)*

> **Note on Unsupported Engines (e.g., Baidu, Yahoo):** Some search engines do not provide a dedicated SafeSearch CNAME endpoint and rely solely on browser cookies or account settings. Therefore, they cannot be enforced via DNS rewrite rules.

## 📥 How to Use

You can add this list to your AdGuard Home instance as a custom DNS blocklist:

1. Copy the **Raw** link of the `adguard_safesearch.txt` file from this repository.
2. Open your **AdGuard Home** administration panel.
3. Navigate to **Filters** > **DNS blocklists**.
4. Click **Add blocklist** > **Add a custom list**.
5. Paste the Raw URL, give it a recognizable name (e.g., `SafeSearch Enforcer`), and click **Save**.

## 📋 Rule Syntax & Examples

This repository uses AdGuard Home's `$dnsrewrite` modifier syntax instead of standard hosts formatting:

```text
# Example SafeSearch DNS Rewrite Rule
||search.brave.com^$dnsrewrite=NOERROR;CNAME;forcesafe.search.brave.com
