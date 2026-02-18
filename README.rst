# SearXJP

![SearXNG](https://raw.githubusercontent.com/searxng/searxng/master/client/simple/src/brand/searxng.svg)

**SearXJP** is a customized fork of [SearXNG](https://github.com/searxng/searxng), optimized for the Asian region (Japan/China/Korea) and branded for the SearXJP privacy instance.

## ⚠️ Fork Scope & Transparency

This repository is a **Strict Static Asset Customization**.

We believe in the security and stability of the core SearXNG project. Therefore, to maintain trust and ensure upstream security updates can be applied immediately, **we do not modify the core Python application logic.**

### What has been changed in this fork?

1.  **Static Assets:**
    *   Logos, Favicons, and touch icons have been replaced with SearXJP branding.
    *   CSS styles (Theme colors) customized for the instance identity.
2.  **Documentation & Localization:**
    *   `about.md` and `search_syntax.md` have been rewritten to reflect our "Split-Knowledge Architecture" and include translations for Japanese, Korean, Chinese, Vietnamese, Thai, and Indonesian.
3.  **Default Configuration:**
    *   `settings.yml` defaults have been tuned for Asian search engines and privacy settings suitable for our infrastructure.

### What has NOT been changed?

*   **NO Logic Changes:** The core metasearch logic, result aggregation, and scrubbing mechanisms are 100% identical to upstream SearXNG.
*   **NO JavaScript Tracking:** We have **not** added any external JavaScript, analytics, pixels, or tracking scripts. The client-side code remains pure.
*   **NO Backdoors:** Authentication and proxy handling remain untouched.

## Credits & Upstream

This project is powered by **SearXNG**. We are grateful to the contributors of the original project for building the most privacy-respecting metasearch engine in the world.

*   **Original Project:** [SearXNG on GitHub](https://github.com/searxng/searxng)
*   **Documentation:** [docs.searxng.org](https://docs.searxng.org)

## License

This project is licensed under the **GNU Affero General Public License (AGPL-3.0)**.
See [LICENSE](LICENSE) for more details.
