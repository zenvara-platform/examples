# Example MS-SQL Connection

A typed connection to a Microsoft SQL Server database, one of Zenvara's
one-connection-per-backend definitions. Credentials live in the secrets store (never
inline in the YAML) — this sample points at a local `localhost` container and pins
`TrustServerCertificate: true` for that self-signed dev cert; a real deployment
should install a valid certificate or leave that at the connector's secure default
(`false`).

See [`example-mssql.connection.yaml`](./example-mssql.connection.yaml).
