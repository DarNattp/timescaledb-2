-- Do not forget to create timescaledb extension
CREATE EXTENSION timescaledb;

-- We start by creating a regular SQL table
CREATE TABLE nginx_logs (
    time TIMESTAMP WITH TIME ZONE NOT NULL,
    remote_addr TEXT,
    remote_user TEXT,
    request_method TEXT,
    request_uri TEXT,
    status INTEGER,
    body_bytes_sent INTEGER,
    http_referer TEXT,
    http_user_agent TEXT
);


-- Then we convert it into a hypertable that is partitioned by time
SELECT create_hypertable('nginx_logs', 'time');
