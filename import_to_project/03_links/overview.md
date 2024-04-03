# Links

> description: Import your data without duplicating it in Supervisely platform. Data stored in your storage and will be visible in Supervisely.

This method allows you to import data to Supervisely without duplicating it in the platform.

The data will be stored in your storage and will be visible in Supervisely. It can be useful when you have a large dataset (hundreds of gigabytes or more) and you don't want to upload it to Supervisely.

Application will upload data using links to your data.

### Supported providers:

- s3 (AWS S3)
- google (Google Cloud Storage)
- azure (Azure Blob Storage)

### How to use:

It will be necessary to provide the following information:

- **Credentials** - env file with connection settings (provider and API token). Example below ⬇️
- **Links** - CSV, JSON or TXT file with links to items you want to import. Example below ⬇️

1. Prepare .env file with connection settings.

```
# .env file
PROVIDER=s3
API_TOKEN=your_api_token
BUCKET=your_bucket
```

2. Prepare links file.

You can use CSV, JSON or TXT file with links to items you want to import. Choose the format that suits you best:

<details>
<summary>CSV file example</summary>
possible delimiters:`,`, `;``

- CSV file example with two columns: `item_name` and `item_link`:

```csv
image1.jpg,s3://remote-img-test/test_img/berries-01.jpeg
image2.jpg,s3://remote-img-test/test_img/berries-02.jpeg
```

- CSV file example with one column: `item_link`:

```csv
s3://remote-img-test/test_img/berries-01.jpeg
s3://remote-img-test/test_img/berries-02.jpeg
```

</details>

<details>
<summary>JSON file example</summary>

- JSON example list of dictionaries with two keys: `item_name` and `item_link`:

```json
[
  {
    "item_name": "image1.jpg",
    "item_link": "s3://remote-img-test/test_img/berries-01.jpeg"
  },
  {
    "item_name": "image2.jpg",
    "item_link": "s3://remote-img-test/test_img/berries-02.jpeg"
  }
]
```

- JSON example list of dictionaries with `name`: `link` pairs:

```json
[
  { "image1.jpg": "s3://remote-img-test/test_img/berries-01.jpeg" },
  { "image2.jpg": "s3://remote-img-test/test_img/berries-02.jpeg" }
]
```

- JSON example list of links:

```json
[
  "s3://remote-img-test/test_img/berries-01.jpeg",
  "s3://remote-img-test/test_img/berries-02.jpeg"
]
```

</details>

<details>
<summary>TXT file example</summary>

possible delimiters:`,`, `;``

- TXT file example with rows containing two values: `item_name` and `item_link`:

```txt
image1.jpg,s3://remote-img-test/test_img/berries-01.jpeg
image2.jpg,s3://remote-img-test/test_img/berries-02.jpeg
```

- TXT file example with rows containing one value: `item_link`:

```txt
s3://remote-img-test/test_img/berries-01.jpeg
s3://remote-img-test/test_img/berries-02.jpeg
```

</details>

3. Drag and drop prepared files to the corresponding widgets (.env in the first widget and your links file in the second widget.)

4. Press the "RUN" button to start the import process.
