# OSCAR Flows

This project enables the deployment of [Node-RED](https://nodered.org/) inside an [OSCAR](https://oscar.grycap.net/) cluster, allowing users to interact with OSCAR and construct working flows, through defined Node-RED [nodes and examples](https://flows.nodered.org/collection/vAqHyycWgCq_)

## Forms of use

To use this functionality from an OSCAR cluster, you simply need to enter the Dashboard and then go to `Flows` → `Deploy`.

You also can use the `flows.yaml` and `script.sh`, present in this repository and deploy it as an OSCAR service.

>
> **Warning**  
> If you want to deploy the service using `flows.yaml` and `script.sh`, don't forget to change the admin password that is in `flows.yaml`.

## Subflows and examples

The deployed service includes additional subflows for asynchronous services in OSCAR. You can import them by going to:
- `Top right corner menu` → `Import` → `Local` → `oscar-subflows`

Also, in the same location, inside `oscar-examples`, you have a list of example flows that can help you better understand the work of different nodes and subflows.

## OSCAR version considerations

The definitions in `flows.yaml` and `script.sh` are not compatible with OSCAR clusters version 3.5.3 or lower, as these versions do not support secrets.  

To deploy the service on older versions, you need to change the admin password variable definition from `environment secrets` to `environment variables`.  

**Note:** This change will expose the admin password to all users who have access to the service.

## Resources and Documentation

- [Node-RED Documentation](https://nodered.org/docs/)
- [OSCAR Documentation](https://docs.oscar.grycap.net/)
- [OSCAR CLI](https://github.com/grycap/oscar-cli)
- [Node-Red: AI4Compose collection](https://flows.nodered.org/collection/vAqHyycWgCq_)
