# Using wasm-pack

This tool was created by the Rust / Wasm Working Group and is the most actively developed tool for building WebAssembly applications. It supports packaging code into `npm` modules and has an accompanying [Webpack plugin](https://github.com/wasm-tool/wasm-pack-plugin) for easy integration with an existing JavaScript application. Find more information [here](https://rustwasm.github.io/docs/wasm-pack/introduction.html).

{% hint style="info" %}
Note that the crate-type in your `Cargo.toml` will need to be `cdylib` when using `wasm-pack`
{% endhint %}

### Install

```bash
cargo install wasm-pack
```

### Build

This command will produce a bundle in the `./pkg` directory with your app's compiled WebAssembly along with a JavaScript wrapper which can be used to start your application.

```bash
wasm-pack build --target web
```

### Bundle

For more information on Rollup visit this [guide](https://rollupjs.org/guide/en/#quick-start)

```bash
rollup ./main.js --format iife --file ./pkg/bundle.js
```

### Serve

Feel free to use your preferred server. Here we use a simple python server to serve to [http://\[::1\]:8000](http://[::1]:8000).

```bash
python -m http.server 8000
```

### Supported Targets

* `wasm32-unknown-unknown`

