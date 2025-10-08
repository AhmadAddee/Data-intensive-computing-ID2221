# Setting up the environment

- First, make sure you have Docker Desktop installed.
- Open the command prompt, navigate to this folder, and run `docker compose -f .\spark-docker.yml up -d`
  > If you run into port-occupation issues, figre what service is occupying that port (e.g., `netstat -ano | findstr ":3306"`), get the name of the service (`Get-Process -Id <PID>`), and stop it (`Stop-Service "<name>"`).
- Check that the containers are running by typing `docker ps`.
- Install [MariaDB Connector/C](https://mariadb.com/downloads/connectors/connectors-data-access/c-connector/) for Windows.
- Make sure you have Java 17 JDK (`java --version`), and an environment variable pointed to it (`$ENV:JAVA_HOME`)
- Add a new Environment Variable with the name `PYSPARK_PYTHON` that points to your Python path (verify with `$ENV:PYSPARK_PYTHON`).
- Install [Anaconda Navigator](https://www.anaconda.com/download/success) by installing Anaconda Distribution.
- From Anaconda Navigator, create a new environment called `spark`, and install `Jupyter Notebook` in this environment.
- Open an `Anaconda Prompt` and navigate to this folder. From there, type `conda activate spark`, and then `jupyter notebook`, to open the project in Jupyter.
- 