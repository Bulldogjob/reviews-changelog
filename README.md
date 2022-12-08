# Reviews changelog

This repository contains meta information on each [review posted on Bulldogjob](https://bulldogjob.pl/companies/profiles).

## Structure

Filenames in the `data` directory correspond to review UUID.
Each file contains a record of every event as a RSA-signed JWT.

Repository also contains public RSA key that can by used for verification.

> Note: This repository was created after reviews were added to bulldogjob.pl. That's why initial records will not correspond to the update times presented in the data and don't have a full historical record.

Provided data includes:
- status - review state; enum: `draft`, `verifed`, `rejected`
- source - way of adding the review to Bulldogjob; enum: `VERFIED_PROCESS`, `PORTAL`
- companyId: ID
- companyName: string
- contentHash: SHA256 of review content, indicates whether content changed a all; string
- updateAt: iso8601 date, string