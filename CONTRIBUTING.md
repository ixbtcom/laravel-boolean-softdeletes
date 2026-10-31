# Contributing

The test harness uses Laravel 13 / Testbench 11, Pest 4 / PHPUnit 12, PHPStan 2 and Larastan 3. CI runs the tests and static analysis on PHP 8.4 and 8.5; PHP formatting uses PHP 8.4. Run PHP checks in Linux with the matching `chialab/php` image.

- Install Composer 2.11.1 and run `composer install --prefer-dist --no-progress --no-interaction`.
- Run the full existing tests: `composer test`.
- Run static analysis: `composer phpstan`.
- Check PHP formatting: `composer cs-fix -- --dry-run --diff --using-cache=no`.
- Check other formatting with Node 22 and pnpm 11.1.2: `pnpm dlx prettier@3.6.2 --check .`.
- Run the dependency audit: `composer audit --locked --format=json`.

Security advisory blocking remains enabled, with no advisory exceptions. CI publishes JSON audit results and resolved direct dependency versions as artifacts, plus JUnit reports for the test jobs. Transport exit 100 may be retried once in GitLab; assertion and solver failures are not retried.
