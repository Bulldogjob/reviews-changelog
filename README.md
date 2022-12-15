# Reviews changelog

This repository contains meta information on each [review posted on Bulldogjob](https://bulldogjob.pl/companies/profiles).

## Structure

Filenames in the `data` directory correspond to review UUID. Each file contains a record of every event as an RSA-signed JWT.

The repository also contains a public RSA key that can be used for verification.

> Note: This repository was created after reviews were added to bulldogjob.pl. That's why initial records will not correspond to the update times presented in the data and don't have a full historical record.

Provided data includes:
- status - review state; enum: `draft`, `verifed`, `rejected`
- source - way of adding the review to Bulldogjob; enum: `VERFIED_PROCESS`, `PORTAL`
- companyId: ID
- companyName: string
- contentHash: SHA256 of review content, indicates whether content changed at all; string
- updateAt: iso8601 date, string

When events are created:
- Review creation
- Review accepted
- Review rejected
- Review updated by the author
- Review removed by the author

`cert` directory contains public key that can be used for checking each JWT signature.