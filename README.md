# mhs.dev

This is a static website built using [Zola](https://www.getzola.org/), a fast static site generator written in Rust.

## Getting Started

1. Install Zola by following the [official installation guide](https://www.getzola.org/documentation/getting-started/installation/).

2. Clone this repository:
   ```
   git clone https://github.com/mhsdef/mhs-website
   cd mhs-website
   ```

3. Run the development server:
   ```
   zola serve
   ```

4. Open your browser and visit `http://127.0.0.1:1111` to see the site.

## Building for Production

To build the site for production, run:

```
zola build
```

The output will be in the `public` directory.
