[![Build Status](https://travis-ci.org/bihealth/ansible-role-davrods.svg?branch=master)](https://travis-ci.org/bihealth/ansible-role-davrods)

# Davrods

Setup of a Davrods server.

## Requirements

The iRODS server must be setup separately.

## Role Variables

See `defaults/main.yml` for all role variables and their documentation.

## Dependencies

- `bihealth.ssl_certs`
- `bihealth.apache`

## Example Playbook

```yaml
- name: install and configure davrods
  vars:
    # bihealth.ssl_certs --------------------------------------------------------------------------
    ssl_certs_certs:
      - name: instance  # self-signed
    # bihealth.davrods ----------------------------------------------------------------------------
    davrods_irods_ip: "127.0.0.1"
    davrods_irods_cert: |
      -----BEGIN CERTIFICATE-----
      MIIDkTCCAnmgAwIBAgIJAKgu1r7NjBhoMA0GCSqGSIb3DQEBCwUAMF8xCzAJBgNV
      BAYTAkRFMQ8wDQYDVQQIDAZCZXJsaW4xDzANBgNVBAcMBkJlcmxpbjEMMAoGA1UE
      CgwDQklIMQ0wCwYDVQQLDARDVUJJMREwDwYDVQQDDAhpbnN0YW5jZTAeFw0xOTA4
      MTMwNzM2MjVaFw0yOTA4MTAwNzM2MjVaMF8xCzAJBgNVBAYTAkRFMQ8wDQYDVQQI
      DAZCZXJsaW4xDzANBgNVBAcMBkJlcmxpbjEMMAoGA1UECgwDQklIMQ0wCwYDVQQL
      DARDVUJJMREwDwYDVQQDDAhpbnN0YW5jZTCCASIwDQYJKoZIhvcNAQEBBQADggEP
      ADCCAQoCggEBANqRqa3m6HUSnuR3KA3eRHmTMxckul3ABlkCnRwm2I1+WQsA9aR+
      Wk+Dz4THOVmABL0Tb+hoWbS93hqwbT1p1tmYtpizenKU/+He3KlRiAEpzp9K7m/W
      NJP0cooCl7k1YF3W3b9fA3D/HEKgLfZ7+VIj1X4Srh59XeB9SIzhCocPyJKxFpm6
      T5LQ2mFzax6BiEard0jtkA20ZOmPSwglQYBV0YYukE4N6+QhCCtttnk7GER+vThU
      1Ual4F2cMAbh0e3Dn3x1Ehaj1/05NPuI/GckQgrynHSqidPUyFwmbsxQtIp1ezZq
      w9pjfkQW5G7w/kQQu3bJD7kzr96fBVwRJdUCAwEAAaNQME4wHQYDVR0OBBYEFMuo
      eSBixQgSfDJEdBgRh1v+QX9AMB8GA1UdIwQYMBaAFMuoeSBixQgSfDJEdBgRh1v+
      QX9AMAwGA1UdEwQFMAMBAf8wDQYJKoZIhvcNAQELBQADggEBAJ2/NDE+Hf8FwezK
      S/Q1+kTMDtHQlbYWpkVQZGVOg+9yz75FQtVlkjNEGDIsHUcBv9a4WMOVVrd9vJ3a
      ytAS5QmIJxcbS4SgAePyvbg0vsl6BTE2lXDq3XvG0u+pBoZkIvIiJYRZF84B5LD5
      BJroFKggh+XeHQClaVBTj5gknF65ueUmcxtugIyN+k4Yp53pPnWYjs7gTr8W3mxb
      JCdorXt0sCEf7K6FeJvJF5oTilOj67CNn2vgSwIq9lVKvUMOJomKf8PIthqmuxZj
      V3O8NmFlXMTgddnzQHLoPiaMkcwqyqipYaAe+Tv4WAzxzmfVC7uxdUeyoKrnsmGb
      13fycGA=
      -----END CERTIFICATE-----
    davrods_irods_zone_name: "exampleZone"
    davrods_irods_sodar_enable_proxy: true
    davrods_irods_sodar_url: "https://sodar.example.com"
  roles:
    - role: bihealth.davrods
```

## Open Issues

- Support Fedora and Debian through source builds.

## License

MIT

## Author Information

- Manuel Holtgrewe

Created with love at [Core Unit Bioinformatics (CUBI), Berlin Institute of Health (BIH)](https://www.cubi.bihealth.org).
