# MySQL StatefulSet Deployment

This Kubernetes manifest deploys a MySQL database as a StatefulSet. It includes:
- A **Secret** for storing the MySQL root password.
- A **Service** to expose the MySQL database.
- A **StatefulSet** to manage MySQL Pods and PersistentVolumeClaims.

## Components

1. **Secret**:
   - Stores the MySQL root password in Base64-encoded format.

2. **Service**:
   - A headless Service (`clusterIP: None`) exposing MySQL on port `3306`.


3. **StatefulSet**:
   - Manages MySQL Pods with a PersistentVolume for data storage.
   - Uses the `mysql:8.0` image and sets environment variables for the root password and database name.


## How to Deploy

1. Apply the manifest:
   ```bash
   kubectl apply -f mysql-sts.yaml
