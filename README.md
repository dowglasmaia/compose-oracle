version: '3.8'

services:
  oracle-xe:
    image: container-registry.oracle.com/database/express:21.3.0-xe
    container_name: oracle-xe_container
    ports:
      - "1521:1521"
      - "5500:5500"
    environment:
      - ORACLE_SID=XE
      - ORACLE_PDB=XEPDB1
      - ORACLE_PASSWORD=my_password
    volumes:
      - ./oracle_data:/opt/oracle/oradata

networks:
  db-network:
    driver: bridge
