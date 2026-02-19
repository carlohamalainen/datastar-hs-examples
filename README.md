# datastar-hs-examples

Examples for the [datastar-hs](https://github.com/carlohamalainen/datastar-hs) package.

All examples serve on http://localhost:3000.

### hello-world-warp

Types out "Hello, world!" character by character with a configurable delay. Uses plain WAI/Warp with pattern matching on `(requestMethod, pathInfo)`.

```bash
cabal run hello-world-warp
```

### hello-world-servant

Same as hello-world-warp but uses Servant for routing. The SSE endpoint is a `Raw` servant endpoint that delegates to `sseResponse`.

```bash
cabal run hello-world-servant
```

### hello-world-channel

Same as hello-world but uses STM to allow restarting the animation mid-stream by changing the delay.

```bash
cabal run hello-world-channel
```

### activity-feed

Demonstrates patching elements and signals together: an activity feed with auto-generation and manual event buttons.

```bash
cabal run activity-feed
```

### heap-view

A GHC heap visualizer that walks the heap from a root expression and renders it as an interactive table. Supports forcing individual thunks and live-updating as lazy evaluation proceeds.

```bash
cabal run heap-view -- simple-list
cabal run heap-view -- live-map
cabal run heap-view -- live-fibs
```

### Deploying with Ansible

```bash
ansible-playbook -i inventory.ini deploy.yml
```
