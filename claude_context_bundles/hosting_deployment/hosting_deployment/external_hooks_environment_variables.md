# External hooks environment variables

**Source:** https://docs.n8n.io/hosting/configuration/environment-variables/external-hooks/

---

# External hooks environment variables

File-based configuration

You can add `_FILE` to individual variables to provide their configuration in a separate file. Refer to [Keeping sensitive data in separate files](../../configuration-methods/#keeping-sensitive-data-in-separate-files) for more details.

You can define external hooks that n8n executes whenever a specific operation runs. Refer to [Backend hooks](../../../../embed/configuration/#backend-hooks) for examples of available hooks and [Hook files](../../../../embed/configuration/#backend-hook-files) for information on file formatting.

| Variable | Type | Description |
| `EXTERNAL_HOOK_FILES` | String | Files containing backend external hooks. Provide multiple files as a colon-separated list ("`:`"). |
| `EXTERNAL_FRONTEND_HOOKS_URLS` | String | URLs to files containing frontend external hooks. Provide multiple URLs as a colon-separated list ("`:`"). |
