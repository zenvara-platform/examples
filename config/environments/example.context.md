# Example Environment

An environment is a named composition of connections — the profile a flow runs
against. A flow never binds a connection by name directly; it names logical aliases
(here `db` and `mail`), and the chosen environment maps each alias to a real
connection at run time (selected via the single `on=<env>` parameter on every
invocation surface). This example environment maps `db` to `example-mssql` and
`mail` to `example-email`.

See [`example.environment.yaml`](./example.environment.yaml) and the connections it
references under [`../connections/`](../connections/).
