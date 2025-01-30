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
   - This is an entirely optional step, rename env to .env
   - Modify the following variables in .envx

  | Variable             | Default                   |
  |----------------------|---------------------------|
  | DUMB_PIN             | (nothing)                 |
  | DUMBBUDGET_PORT      | 3333                      |
  | DUMBBUDGET_DATA_PATH | /opt/dumbsuite/dumbbudget |
  | DUMBDO_PORT          | 3334                      |
  | DUMBDO_DATA_PATH     | /opt/dumbsuite/dumbdo     |
  | DUMBDROP_PORT        | 3335                      |
  | DUMBDROP_DATA_PATH   | /opt/dumbsuite/dumbdrop   |
  | DUMBPAD_PORT         | 3336                      |
  | DUMBPAD_DATA_PATH    | /opt/dumbsuite/dumbpad    |
  | DUMBKAN_PORT         | 3337                      |
  | DUMBKAN_DATA_PATH    | /opt/dumbsuite/dumbkan    |

   - Note that this is a very dumb setup. A less dumber setup would remove ports and configure networks for better isolation.

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

6. **Use the Services:**
  - DumbBudget can be accessed from http://localhost:3333
  - DumbDo can be accessed from http://localhost:3334
  - DumbDrop can be accessed from http://localhost:3335
  - DumbPad can be accessed from http://localhost:3336
  - DumbKan can be accessed from http://localhost:3337

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
