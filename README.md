# DumbWareIO Docker Compose Setup

This repository provides a `docker-compose.yml` file to run all DumbWare applications in a single environment.

## About DumbWareIO

DumbWareIO is a collection of self-hosted applications designed for simplicity and efficiency. For more details, visit:

- Website: [https://dumbware.io](https://dumbware.io)
- GitHub: [https://github.com/DumbWareio](https://github.com/DumbWareio)

## Included Applications

| Application  | GitHub Repository |
|-------------|------------------|
| DumbBudget  | [DumbBudget Repo](https://github.com/DumbWareio/Dumbbudget) |
| DumbDo      | [DumbDo Repo](https://github.com/DumbWareio/Dumbdo) |
| DumbDrop    | [DumbDrop Repo](https://github.com/DumbWareio/Dumbdrop) |
| DumbPad     | [DumbPad Repo](https://github.com/DumbWareio/Dumbpad) |
| DumbKan     | [DumbKan Repo](https://github.com/DumbWareio/Dumbkan) |

## Prerequisites

- Docker installed on your system
- `docker-compose` installed

## Installation & Usage

1. **Clone the Repository:**
   ```sh
   git clone https://github.com/DumbWareio/dumbcompose.git
   cd dumbcompose
   ```

2. **Modify Configuration:**
   - Replace `YOUR_PORT_HERE` with the desired ports.
   - Replace `/path/to/your/...` with actual host paths.
   - Set any necessary PINs in the `environment` section of `docker-compose.yml`.

3. **Run the Services:**
   ```sh
   docker-compose up -d
   ```

4. **Stopping the Services:**
   ```sh
   docker-compose down
   ```

5. **Updating Containers:**
   ```sh
   docker-compose pull
   docker-compose up -d
   ```

## Troubleshooting

- Check container logs:
  ```sh
  docker-compose logs -f
  ```
- Ensure correct file paths and port mappings.


---
For more details, visit [DumbWareIO](https://dumbware.io).
To support our projects, please consider donating at [Buy Me a Coffee](https://buymeacoffee.com/dumbware).
And as always, join the community at [Discord](https://dumbware.io/discord)!

