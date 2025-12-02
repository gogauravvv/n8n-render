services:
  - type: web
    name: n8n
    env: docker
    region: oregon # optional (defaults to oregon)
    plan: standard # optional (defaults to starter)
    branch: main # optional (defaults to master)
    numInstances: 1
    healthCheckPath: /
    envVars:
      - key: DB_TYPE
        value: postgresdb
      - key: DB_POSTGRESDB_HOST
        fromDatabase:
          name: n8n-db
          property: host
      - key: DB_POSTGRESDB_DATABASE
        fromDatabase:
          name: n8n-db
          property: database
      - key: DB_POSTGRESDB_PORT
        fromDatabase:
          name: n8n-db
          property: port
      - key: DB_POSTGRESDB_USER
        fromDatabase:
          name: n8n-db
          property: user
      - key: DB_POSTGRESDB_PASSWORD
        fromDatabase:
          name: n8n-db
          property: password
      - key: DB_POSTGRESDB_SCHEMA
        value: public
      - key: WEBHOOK_URL
        value: https://your-n8n-app.onrender.com/
      - key: N8N_ENCRYPTION_KEY
        value: YOUR_ENCRYPTION_KEY_HERE
      - key: GENERIC_TIMEZONE
        value: America/Sao_Paulo
      - key: TZ
        value: America/Sao_Paulo
      - key: N8N_LOG_LEVEL
        value: info
      - key: EXECUTIONS_DATA_PRUNE
        value: true
      - key: EXECUTIONS_DATA_MAX_AGE
        value: 168
      - key: EXECUTIONS_DATA_SAVE_ON_ERROR
        value: all
      - key: EXECUTIONS_DATA_SAVE_ON_SUCCESS
        value: none
      - key: EXECUTIONS_DATA_SAVE_ON_PROGRESS
        value: false
      - key: EXECUTIONS_DATA_SAVE_MANUAL_EXECUTIONS
        value: false
    disk:
      name: n8n-disk
      mountPath: /home/node/.n8n
      sizeGB: 5

databases:
  - name: n8n-db
    plan: basic-1gb
