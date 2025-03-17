# sdk-auto

## Build
### Local Build
```bash
make build-sdk
```

### Docker Build
```bash
docker build -t sdk-auto:latest .
```

## Run
### Configuration Parameters
* `trace_api` - Specifies the OTEL backend endpoint address (e.g., jaegerip:4318)
* `scan_interval` - Defines the interval (in seconds) for scanning new processes. Currently supports auto-instrumentation for Go applications only (Java not supported)
* `black_list` - Process blacklist using fuzzy matching. For Go applications, matches against the Comm file content; for Java applications, matches against the CmdLine file content. Any application not in the blacklist will be automatically instrumented

### Local Execution
```bash
./originx-sdk-auto
```

### Kubernetes Deployment
```bash
kubectl apply -f sdk-auto-deploy.yml
```