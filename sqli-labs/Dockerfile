
FROM docker.io/tutum/lamp:latest

MAINTAINER WaferJay

ENV MYSQL_PASS root

RUN rm -rf /app && git clone --depth=1 https://github.com/Audi-1/sqli-labs.git /app \
    && echo '<?php' > /app/sql-connections/db-creds.inc \
    && echo '$host = "localhost";' >> /app/sql-connections/db-creds.inc \
    && echo '$dbuser = "admin";' >> /app/sql-connections/db-creds.inc \
    && echo '$dbpass = $_ENV["MYSQL_PASS"] ?: "";' >> /app/sql-connections/db-creds.inc \
    && echo '$dbname = "security";' >> /app/sql-connections/db-creds.inc \
    && echo '$dbname1 = "challenges";' >> /app/sql-connections/db-creds.inc \
    && echo '?>' >> /app/sql-connections/db-creds.inc \
    && sed -i 's/^variables_order = "GPCS"/variables_order = "EGPCS"/g' /etc/php5/apache2/php.ini

EXPOSE 80 3306

CMD ["./run.sh"]
