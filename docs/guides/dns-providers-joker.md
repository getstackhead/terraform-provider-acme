---
page_title: "joker"
subcategory: "DNS Providers"
---

-> The following documentation is auto-generated from the ACME
provider's API library [lego](https://go-acme.github.io/lego/).  Some
sections may refer to lego directly - in most cases, these sections
apply to the Terraform provider as well.

# Joker DNS Challenge Provider

The `joker` DNS challenge provider can be used to perform DNS challenges for
the [`acme_certificate`][resource-acme-certificate] resource with
[Joker](https://joker.com).

[resource-acme-certificate]: ../resources/certificate.md

For complete information on how to use this provider with the `acme_certifiate`
resource, see [here][resource-acme-certificate-dns-challenges].

[resource-acme-certificate-dns-challenges]: ./certificate.md#using-dns-challenges

## Example

```hcl
resource "acme_certificate" "certificate" {
  ...

  dns_challenge {
    provider = "joker"
  }
}
```
## Argument Reference

The following arguments can be either passed as environment variables, or
directly through the `config` block in the
[`dns_challenge`][resource-acme-certificate-dns-challenge-arg] argument in the
[`acme_certificate`][resource-acme-certificate] resource. For more details, see
[here][resource-acme-certificate-dns-challenges].

[resource-acme-certificate-dns-challenge-arg]: ./certificate.md#dns_challenge

In addition, arguments can also be stored in a local file, with the path
supplied by supplying the argument with the `_FILE` suffix. See
[here][acme-certificate-file-arg-example] for more information.

[acme-certificate-file-arg-example]: ./certificate.md#using-variable-files-for-provider-arguments

* `JOKER_API_KEY` - API key (only with DMAPI mode).
* `JOKER_API_MODE` - 'DMAPI' or 'SVC'. DMAPI is for resellers accounts. (Default: DMAPI).
* `JOKER_PASSWORD` - Joker.com password.
* `JOKER_USERNAME` - Joker.com username (email address).

* `JOKER_HTTP_TIMEOUT` - API request timeout.
* `JOKER_POLLING_INTERVAL` - Time between DNS propagation check.
* `JOKER_PROPAGATION_TIMEOUT` - Maximum waiting time for DNS propagation.
* `JOKER_TTL` - The TTL of the TXT record used for the DNS challenge.


