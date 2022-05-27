FROM couchbase/server:enterprise-aarch64 AS stage_base
# FROM couchbase:latest AS stage_base 
COPY init-cbserver.sh /opt/couchbase/init/
COPY sample-data.json /opt/couchbase/init/
