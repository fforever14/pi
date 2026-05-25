# @earendil-works/pi-ai-providers

Provider presets, generated model metadata, environment API key helpers, and OAuth helpers for `@earendil-works/pi-ai`.

Runtime API compatibility lives in `@earendil-works/pi-ai`; this package only owns provider catalog and auth convenience behavior.

```typescript
import { getEnvApiKey, getModel } from "@earendil-works/pi-ai-providers";
import { complete } from "@earendil-works/pi-ai";

const model = getModel("openai", "gpt-4o-mini");
const message = await complete(
	model,
	{ messages: [{ role: "user", content: "Hello" }] },
	{ apiKey: getEnvApiKey("openai") },
);
```

OAuth helpers are available from `@earendil-works/pi-ai-providers/oauth`:

```typescript
import { loginGitHubCopilot } from "@earendil-works/pi-ai-providers/oauth";

const credentials = await loginGitHubCopilot(callbacks);
```
