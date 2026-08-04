# Rules for Antigravity Coding Assistant

## Network Constraints
- **Do not test or check `https://twblg.dict.edu.tw/holodict_new/audio/3400.mp3` (or other audio files in that directory) from backend scripts / command line**: The backend sandboxed environment blocks outgoing connection requests to this audio path, which causes commands (such as `curl`) to hang and time out.
- **Client-Side Browsers Have Full Access**: The user's browser client-side Javascript can load and play audio from `https://twblg.dict.edu.tw/holodict_new/audio/[id].mp3` directly without any issue.
