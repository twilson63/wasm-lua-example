# Compile Lua to Wasm

This example compiles a simple lua script to a wasm file which can be called in the browser with js bindings.

## Create our lua script

hello.lua

```lua
function hello()
  return ('Hello World')
end
```

## Create a definition.yml file

```yaml
entry_file: hello.lua
output_file: hello.js

functions:
  hello:
    return: string

```

## Compile to wasm

```sh
docker run --rm -v $PWD:/src ysugimoto/webassembly-lua emcc-lua
```

## Open in browser

```sh
npx w3
```