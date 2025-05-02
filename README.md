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
| DumbWhoIs   | [DumbWhoIs Repo](https://github.com/DumbWareio/DumbWhoIs) |
| DumbTerm    | [DumbTerm Repo](https://github.com/DumbWareio/DumbTerm) |

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
   - This is an entirely optional step: 
     - create a new `.env` file from the .env.example file:
      ```sh 
      cp .env.example .env
      ```
   - Modify the following variables in .env file as needed:

      | Variable                       | Default                   | Description                                    |
      |--------------------------------|---------------------------|------------------------------------------------|
      | DUMB_PIN                       | (nothing)                 | Shared PIN for all services                    |
      | DUMBBUDGET_PORT                | 3333                      | Port for DumbBudget service                    |
      | DUMBBUDGET_DATA_PATH           | ./dumbsuite/dumbbudget    | Data directory for DumbBudget                  |
      | DUMBBUDGET_PIN                 | (nothing)                 | PIN for DumbBudget (overrides DUMB_PIN)        |
      | DUMBBUDGET_BASE_URL            | http://localhost:3333     | Base URL for DumbBudget                        |
      | DUMBBUDGET_CURRENCY            | USD                       | Default currency for DumbBudget                |
      | DUMBBUDGET_SITE_TITLE          | DumbBudget                | Site title for DumbBudget                      |
      | DUMBBUDGET_INSTANCE_NAME       | (nothing)                 | Instance name for DumbBudget                   |
      | DUMBDO_PORT                    | 3334                      | Port for DumbDo service                        |
      | DUMBDO_DATA_PATH               | ./dumbsuite/dumbdo        | Data directory for DumbDo                      |
      | DUMBDO_PIN                     | (nothing)                 | PIN for DumbDo (overrides DUMB_PIN)            |
      | DUMBDO_SITE_TITLE              | DumbDo                    | Site title for DumbDo                          |
      | DUMBDO_ALLOWED_ORIGINS         | *                         | CORS allowed origins for DumbDo                |
      | DUMBDROP_PORT                  | 3335                      | Port for DumbDrop service                      |
      | DUMBDROP_DATA_PATH             | ./dumbsuite/dumbdrop      | Data directory for DumbDrop                    |
      | DUMBDROP_PIN                   | (nothing)                 | PIN for DumbDrop (overrides DUMB_PIN)          |
      | DUMBDROP_TITLE                 | DumbDrop                  | Site title for DumbDrop                        |
      | DUMBDROP_MAX_FILE_SIZE         | 1024                      | Maximum file size in MB                        |
      | DUMBDROP_BASE_URL              | http://localhost:3335     | Base URL for DumbDrop                          |
      | DUMBPAD_PORT                   | 3336                      | Port for DumbPad service                       |
      | DUMBPAD_DATA_PATH              | ./dumbsuite/dumbpad       | Data directory for DumbPad                     |
      | DUMBPAD_SITE_TITLE             | DumbPad                   | Site title for DumbPad                         |
      | DUMBPAD_PIN                    | (nothing)                 | PIN for DumbPad (overrides DUMB_PIN)           |
      | DUMBPAD_BASE_URL               | http://localhost:3336     | Base URL for DumbPad                           |
      | DUMBPAD_ALLOWED_ORIGINS        | *                         | CORS allowed origins for DumbPad               |
      | DUMBPAD_LOCK_TIME              | 15                        | Lock time in minutes                           |
      | DUMBPAD_MAX_ATTEMPTS           | 5                         | Maximum login attempts                         |
      | DUMBPAD_COOKIE_MAX_AGE         | 24                        | Cookie max age in hours                        |
      | DUMBPAD_PAGE_HISTORY_COOKIE_AGE| 365                       | Page history cookie age in days                |
      | DUMBKAN_PORT                   | 3337                      | Port for DumbKan service                       |
      | DUMBKAN_DATA_PATH              | ./dumbsuite/dumbkan       | Data directory for DumbKan                     |
      | DUMBKAN_TITLE                  | DumbKan                   | Site title for DumbKan                         |
      | DUMBKAN_PIN                    | (nothing)                 | PIN for DumbKan (overrides DUMB_PIN)           |
      | DUMBKAN_BASE_URL               | http://localhost:3337     | Base URL for DumbKan                           |
      | DUMBWHOIS_PORT                 | 3338                      | Port for DumbWhois service                     |
      | DUMBWHOIS_SITE_TITLE           | DumbWhois                 | Site title for DumbWhois                       |
      | DUMBWHOIS_ALLOWED_ORIGINS      | *                         | CORS allowed origins for DumbWhois             |
      | DUMBTERM_PORT                  | 3339                      | Port for DumbTerm service                      |
      | DUMBTERM_CONFIG                | ./dumbsuite/dumbterm/config | Configuration directory for DumbTerm         |
      | DUMBTERM_DATA_DIR              | ./dumbsuite/dumbterm/data | Data directory for DumbTerm                    |
      | DUMBTERM_TZ                    | America/Los_Angeles       | Timezone for DumbTerm                          |
      | DUMBTERM_SITE_TITLE            | DumbTerm                  | Site title for DumbTerm                        |
      | DUMBTERM_PIN                   | (nothing)                 | PIN for DumbTerm (overrides DUMB_PIN)          |
      | DUMBTERM_BASE_URL              | http://localhost:3339     | Base URL for DumbTerm                          |
      | ENABLE_STARSHIP                | true                      | Enable Starship prompt in DumbTerm             |
      | DUMBTERM_LOCKOUT_TIME          | 15                        | Lockout time in minutes                        |
      | DUMBTERM_MAX_SESSION_AGE       | 24                        | Maximum session age in hours                   |
      | DUMBTERM_ALLOWED_ORIGINS       | *                         | CORS allowed origins for DumbTerm              |

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
  - DumbWhoIs can be accessed from http://localhost:3338
  - DumbTerm can be accessed from http://localhost:3339
  - Note that the ports are configurable in the .env file.

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
