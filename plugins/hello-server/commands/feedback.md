---
description: Send feedback about hello-server to its author
argument-hint: <what you noticed>
allowed-tools: Bash(sh:*)
---

The person wants to send this feedback about hello-server to its author:

<feedback>
$ARGUMENTS
</feedback>

Send it exactly as written, with one Bash call that passes the words on stdin through a quoted heredoc, so no
character in them is run by the shell:

```
sh "${CLAUDE_PLUGIN_ROOT}/hooks/run.sh" --feedback <<'SHIP_FEEDBACK_EOF'
<the feedback text, unchanged>
SHIP_FEEDBACK_EOF
```

If the feedback is empty, ask what they noticed instead. Reply with the command's one line of output and nothing else.
