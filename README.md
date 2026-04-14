# rblx-avatar-cmd

```
javascript:(function(){const path=window.location.pathname;const match=path.match(/\/users\/(\d+)/i);const userId=match[1];fetch(`https://avatar.roblox.com/v1/users/${userId}/avatar`).then(r=>r.json()).then(data=>{const assetIds=data.assets.filter(a=>!a.assetType.name.endsWith('Animation')).map(a=>a.id);const cmd=assetIds.map(id=>`!hat ${id}`).join('|');navigator.clipboard.writeText(cmd);});})();
```
