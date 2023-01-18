# axeman
An updated and edited version of https://github.com/CaliDog/Axeman to download RSA public keys modulus from CT logs

## Usage

Options are the same as on the original tool.

List CT logs from https://www.gstatic.com/ct/log_list/v3/log_list.json :
```sh
./axeman.py -v -l
```

Download RSA public keys modulus from the https://ct.googleapis.com/logs/argon2023 CT log, running on 5 threads :
```sh
./axeman.py -v -u https://ct.googleapis.com/logs/argon2023 -o output_dir -f axeman_argon2023_log -c 5
```

## Notes

- A lot of duplicate modulus will be downloaded, especially from the "extra_data" part of CT log entries. These can be de-duped later.
- The output is not storage-efficient, as its size could be reduced by a lot.
