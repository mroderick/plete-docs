---
layout: page-layout.njk
title: Plete documentation
---

# plete

A vanilla JavaScript autocomplete component.

## Introduction

## Usage

### npm

### CDN

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/plete@0.2.0/dist/main.css" />
```

## Demos

### Simple values

The `dataSrc` option can be an array of simple values.

<section id="simple">
  <form action=".">
    <fieldset>
      <label>
        Country
        <input type="text" name="country" autocomplete="off" autofocus="autofocus" />
      </label>
    </fieldset>
  </form>
  <p>
    You selected: <span class="selectedValue"></span>
  </p>
  <script type="module">
    const plete = new Plete({
      autoFirst: false,
      input: document.querySelector("#simple input[name='country']"),
      dataSrc: ["Denmark", "Germany", "Spain", "Sweden", "United Kingdom"],
      select: function(value) {
        document.querySelector("#simple .selectedValue").textContent = value;
      }
    });
  </script>
</section>

<!--
<section id="complex">
  <form action=".">
    <fieldset>
      <h2>Complex input</h2>
      <label>
        Country
        <input type="text" name="country" autocomplete="off" autofocus="autofocus" />
      </label>
    </fieldset>
  </form>
  <p>
    You selected: <span class="selectedValue"></span>
  </p>
  <script type="module">
    import Plete from "./dist/main-esm.js";

    const plete = new Plete({
      input: document.querySelector("#complex input[name='country']"),
      dataSrc: [
            { id: "BEL", label: "Belgium" },
            { id: "DNK", label: "Denmark" },
            { id: "GER", label: "Germany" },
            { id: "MCO", label: "Monaco" },
            { id: "SRB", label: "Serbia" },
            { id: "ESP", label: "Spain" },
            { id: "SWE", label: "Sweden" },
            { id: "GBR", label: "United Kingdom" },
            { id: "USA", label: "United States of America" }
      ],
      select: function(value) {
        document.querySelector("#complex .selectedValue").textContent = value;
      }
    });
  </script>
</section>

<section id="custom">
  <form action=".">
    <fieldset>
      <h2>Custom rendering</h2>
      <label>
        Country
        <input type="text" name="country" autocomplete="off" autofocus="autofocus" />
      </label>
    </fieldset>
  </form>
  <p>
    You selected: <span class="selectedValue"></span>
  </p>
  <script type="module">
    import Plete from "./dist/main-esm.js";

    const plete = new Plete({
      input: document.querySelector("#custom input[name='country']"),
      dataSrc: [
            { id: "BEL", label: "Belgium" },
            { id: "DNK", label: "Denmark" },
            { id: "GER", label: "Germany" },
            { id: "MCO", label: "Monaco" },
            { id: "SRB", label: "Serbia" },
            { id: "ESP", label: "Spain" },
            { id: "SWE", label: "Sweden" },
            { id: "GBR", label: "United Kingdom" },
            { id: "USA", label: "United States of America" }
      ],
      render: function(item) {
        return `<b>${item.id}</b> ${item.label}`;
      },
      select: function(id) {
        document.querySelector("#custom .selectedValue").textContent = id;
      }
    });
  </script>
</section>

<section id="remote">
  <form action=".">
    <fieldset>
      <h2>Remote filtering</h2>
      <label>
        Country
        <input type="text" name="country" autocomplete="off" autofocus="autofocus" />
      </label>
    </fieldset>
  </form>
  <p>
    You selected: <span class="selectedValue"></span>
  </p>
  <script type="module">
    import Plete from "./dist/main-esm.js";

    const plete = new Plete({
      input: document.querySelector("#remote input[name='country']"),
      dataSrc: async function filterCountries(query) {
        const response = await fetch(`https://restcountries.eu/rest/v2/name/${query}`);
        const result = await response.json();

        if (!Array.isArray(result)) {
          return [];
        }

        return result.map(function(v) {
          return {
            id: v.alpha3Code,
            label: v.name
          }
        });
      },
      select: function(id) {
        document.querySelector("#remote .selectedValue").textContent = id;
      }
    });
  </script>
</section>
-->

