# AdGuard Home SafeSearch Enforcer 🛡️

A comprehensive filter list for **AdGuard Home** designed to automatically enforce **SafeSearch** across all major search engines using advanced DNS rewrite rules. Perfect for protecting families and children from explicit content network-wide.

## 🚀 Supported Search Engines
* **Google**
* **YouTube** (Restricted Mode)
* **Bing**
* **Yandex**
* **DuckDuckGo**
* **Brave Search**

---

## 📥 How to Use

You can easily add this list to your AdGuard Home instance as a custom filtering list:

1. Copy the **Raw** link of your `adguard_safesearch.txt` file from GitHub.
2. Open your AdGuard Home administration panel.
3. Navigate to **Filters** > **DNS blocklists**.
4. Click **Add blocklist** -> **Add a custom list**, paste the link, give it a name, and save.

---

## 📋 Rule Syntax & Examples

This list uses AdGuard Home's filter-based DNS rewrite syntax:

```text
# Example SafeSearch / DNS Rewrite Rules
^$dnsrewrite=NOERROR;CNAME;forcesafe.search.brave.com
