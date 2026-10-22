# The feature walkthrough that floated into empty space

An in-app guide fired on mount, tried to anchor to an element inside a conditional section, found nothing, and drifted. The fix is one check per step: is the target in the DOM right now? If not, skip it.

Read the full hack, with context and what it is good for: https://www.omerbinsaleem.com/hacks/feature-guide-floating-bubble/

## Steps

1. Before each step, check that the target element exists in the DOM right now. If it does not, skip the step and move on. Never anchor to a guess.
2. List every step that assumes a state the user might not be in: a section that renders on data, a tab that is closed, a permission the user lacks.
3. Show each screen's guide once, and record that it was shown, so a skipped step does not come back on the next visit as a surprise.
4. Test the guide with empty data, a new user, and a user with fewer permissions. Your UI does not look the same for everyone at every moment.

## Prompt to copy

```text
Review this in-app guide. For every step, name the element it anchors to and the condition under which that element is not rendered (empty data, closed tab, missing permission, feature flag). Add a guard before each step that checks the element is in the DOM and skips the step otherwise, and list the states I should test the guide in.
```

Tag: Frontend · about 2 minutes · published 2026-10-20
