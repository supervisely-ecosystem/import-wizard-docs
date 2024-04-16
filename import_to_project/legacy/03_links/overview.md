# Links

> title: Import data without duplicating it in Supervisely platform. Data stored in your storage and will be visible in Supervisely.

> description:
> This way you can import data from your storages (i.e. AWS S3, Google Cloud Storage, Azure Blob Storage) to Supervisely without duplicating it in the platform. Application will upload data using links to your data. The data will be stored in your storage and will be visible in Supervisely. It can be useful when you have a large dataset (hundreds of gigabytes or more) and you don't want to upload it to Supervisely.

> ℹ️ How to use: Drag and drop the `.env` file with connection settings (provider and API token) and the links file (`CSV`, `JSON` or `TXT`) with links to items you want to import. Example of the `.env` file and links file are provided in the docs.
