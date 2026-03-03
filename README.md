# Spring Boot 4 Upgrade with OpenAPI Generator and Jackson 3

A composite OpenRewrite recipe that upgrades a Spring Boot application to version 4, updates the `openapi-generator-maven-plugin` to 7.20.0, and configures it with `useSpringBoot4` and `useJackson3` options.

## What the Recipe Does

The `spring-boot-4-upgrade.yml` recipe performs the following steps:

1. **Upgrades to Spring Boot 4** using the Moderne `UpgradeSpringBoot_4_0` recipe
2. **Upgrades `openapi-generator-maven-plugin`** to version 7.20.0
3. **Adds `<useSpringBoot4>true</useSpringBoot4>`** to the plugin's `<configOptions>` (adds if missing, updates if present)
4. **Adds `<useJackson3>true</useJackson3>`** to the plugin's `<configOptions>` (adds if missing, updates if present)

## Usage with the Moderne CLI

### 1. Build the LST

Build the Lossless Semantic Tree for your repository:

```bash
mod build .
```

### 2. Install the recipe

Install the YAML recipe file into the CLI's local recipe marketplace:

```bash
mod config recipes yaml install spring-boot-4-upgrade.yml
```

See the [mod config recipes yaml install](https://docs.moderne.io/user-documentation/moderne-cli/cli-reference/#mod-config-recipes-yaml-install) reference for more options.

### 3. Run the recipe

Run the recipe against your repository:

```bash
mod run . --recipe com.example.UpgradeToSpringBoot4WithOpenApi
```

See the [mod run](https://docs.moderne.io/user-documentation/moderne-cli/cli-reference/#mod-run) reference for more options.

### 4. Apply the changes

Apply the generated changes to your working tree:

```bash
mod git apply . --last-recipe-run
```
