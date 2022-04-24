# GitHub Actions Templates for Zephir and Phalcon

Unified templates of Zephir.

## Inspection with PHP Code Sniffer

```yaml
jobs:
  # PHP CodeSniffer inspection
  phpcs:
    uses: zephir-lang/templates/.github/workflows/phpcs.yml@main
    with:
      standard: ./phpcs.xml
```

## Generate Stubs for Phalcon and validates with PSALM

```yaml
jobs:
  # Generate stubs and validates with PSALM
  stubs:
    uses: zephir-lang/templates/.github/workflows/phalcon-stubs.yml@main
    with:
      extensions: psr, zephir_parser
```

## Creates Phalcon PECL package

```yaml
jobs:
  generate:
    uses: zephir-lang/templates/.github/workflows/phalcon-pecl.yml@main
    with:
      extensions: psr, zephir_parser
    secrets:
      composer-token: ${{ secrets.GITHUB_TOKEN }}
```

## Install Phalcon extension after build and makes simple health checks

```yaml
jobs:
  install:
    uses: zephir-lang/templates/.github/workflows/phalcon-install-from-build.yml@main
    with:
      extensions: psr, zephir_parser
```
