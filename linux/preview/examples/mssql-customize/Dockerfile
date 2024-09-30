FROM mcr.microsoft.com/mssql/server:2022-latest

USER root

# Create a config directory
RUN mkdir -p /var/opt/mssql/config
WORKDIR /var/opt/mssql/config/

# Bundle config source
COPY *.sh *.sql /var/opt/mssql/config/

# Grant permissions for to our scripts to be executable
USER root
RUN chmod +x /var/opt/mssql/config/entrypoint.sh
RUN chmod +x /var/opt/mssql/config/configure-db.sh
USER mssql

ENTRYPOINT ["./entrypoint.sh"]
