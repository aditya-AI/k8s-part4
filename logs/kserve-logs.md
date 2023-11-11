```bash
WARNING: sun.reflect.Reflection.getCallerClass is not supported. This will impact performance.
2023-11-11T19:39:43,390 [WARN ] main org.pytorch.serve.util.ConfigManager - Your torchserve instance can access any URL to load models. When deploying to production, make sure to limit the set of allowed_urls in config.properties
2023-11-11T19:39:43,393 [INFO ] main org.pytorch.serve.servingsdk.impl.PluginsManager - Initializing plugins manager...
2023-11-11T19:39:43,586 [INFO ] main org.pytorch.serve.metrics.configuration.MetricConfiguration - Successfully loaded metrics configuration from /home/venv/lib/python3.9/site-packages/ts/configs/metrics.yaml
2023-11-11T19:39:43,791 [INFO ] main org.pytorch.serve.ModelServer - 
Torchserve version: 0.8.2
TS Home: /home/venv/lib/python3.9/site-packages
Current directory: /home/model-server
Temp directory: /home/model-server/tmp
Metrics config path: /home/venv/lib/python3.9/site-packages/ts/configs/metrics.yaml
Number of GPUs: 1
Number of CPUs: 1
Max heap size: 989 M
Python executable: /home/venv/bin/python
Config file: /mnt/models/config/config.properties
Inference address: http://0.0.0.0:8085
Management address: http://0.0.0.0:8085
Metrics address: http://0.0.0.0:8082
Model Store: /mnt/models/model-store
Initial Models: all
Log dir: /home/model-server/logs
Metrics dir: /home/model-server/logs
Netty threads: 4
Netty client threads: 0
Default workers per model: 1
Blacklist Regex: N/A
Maximum Response Size: 655350000
Maximum Request Size: 6553500
Limit Maximum Image Pixels: true
Prefer direct buffer: false
Allowed Urls: [file://.*|http(s)?://.*]
Custom python dependency for model allowed: true
Enable metrics API: true
Metrics mode: log
Disable system metrics: false
Workflow Store: /mnt/models/model-store
Model config: N/A
2023-11-11T19:39:43,796 [INFO ] main org.pytorch.serve.servingsdk.impl.PluginsManager -  Loading snapshot serializer plugin...
2023-11-11T19:39:43,874 [INFO ] main org.pytorch.serve.snapshot.SnapshotManager - Started restoring models from snapshot {"name":"startup.cfg","modelCount":1,"models":{"sdxl":{"1.0":{"defaultVersion":true,"marName":"sdxl.mar","minWorkers":1,"maxWorkers":1,"batchSize":1,"maxBatchDelay":10,"responseTimeout":600}}}}
2023-11-11T19:39:43,881 [INFO ] main org.pytorch.serve.snapshot.SnapshotManager - Validating snapshot startup.cfg
2023-11-11T19:39:43,882 [INFO ] main org.pytorch.serve.snapshot.SnapshotManager - Snapshot startup.cfg validated successfully
INFO:root:Wrapper : Model names ['sdxl'], inference address http://0.0.0.0:8085, management address http://0.0.0.0:8085, grpc_inference_address, 0.0.0.0:7070, model store /mnt/models/model-store
INFO:root:Predict URL set to 0.0.0.0:8085
INFO:root:Explain URL set to 0.0.0.0:8085
INFO:root:Protocol version is v1
INFO:root:Copying contents of /mnt/models/model-store to local
INFO:root:TSModelRepo is initialized
INFO:kserve:Registering model: sdxl
INFO:kserve:Setting max asyncio worker threads as 5
INFO:kserve:Starting uvicorn with 1 workers
2023-11-11 19:39:46.481 uvicorn.error INFO:     Started server process [9]
2023-11-11 19:39:46.481 uvicorn.error INFO:     Waiting for application startup.
2023-11-11 19:39:46.483 9 kserve INFO [start():62] Starting gRPC server on [::]:8081
2023-11-11 19:39:46.484 uvicorn.error INFO:     Application startup complete.
2023-11-11 19:39:46.484 uvicorn.error INFO:     Uvicorn running on http://0.0.0.0:8080 (Press CTRL+C to quit)
2023-11-11T19:41:49,348 [DEBUG] main org.pytorch.serve.wlm.ModelVersionedRefs - Adding new version 1.0 for model sdxl
2023-11-11T19:41:49,349 [DEBUG] main org.pytorch.serve.wlm.ModelVersionedRefs - Setting default version to 1.0 for model sdxl
2023-11-11 19:43:40.424 kserve.trace kserve.io.kserve.protocol.rest.v1_endpoints.predict: 0.020880460739135742
2023-11-11 19:43:40.425 kserve.trace kserve.io.kserve.protocol.rest.v1_endpoints.predict: 0.02087699999999959
2023-11-11 19:43:40.425 9 kserve ERROR [generic_exception_handler():94] Exception:
Traceback (most recent call last):
  File "/home/venv/lib/python3.9/site-packages/anyio/_core/_sockets.py", line 167, in try_connect
    stream = await asynclib.connect_tcp(remote_host, remote_port, local_address)
  File "/home/venv/lib/python3.9/site-packages/anyio/_backends/_asyncio.py", line 1627, in connect_tcp
    await get_running_loop().create_connection(
  File "/usr/lib/python3.9/asyncio/base_events.py", line 1065, in create_connection
    raise exceptions[0]
  File "/usr/lib/python3.9/asyncio/base_events.py", line 1050, in create_connection
    sock = await self._connect_sock(
  File "/usr/lib/python3.9/asyncio/base_events.py", line 961, in _connect_sock
    await self.sock_connect(sock, address)
  File "/usr/lib/python3.9/asyncio/selector_events.py", line 500, in sock_connect
    return await fut
  File "/usr/lib/python3.9/asyncio/selector_events.py", line 535, in _sock_connect_cb
    raise OSError(err, f'Connect call failed {address}')
ConnectionRefusedError: [Errno 111] Connect call failed ('0.0.0.0', 8085)

The above exception was the direct cause of the following exception:

Traceback (most recent call last):
  File "/home/venv/lib/python3.9/site-packages/httpcore/_exceptions.py", line 10, in map_exceptions
    yield
  File "/home/venv/lib/python3.9/site-packages/httpcore/backends/asyncio.py", line 111, in connect_tcp
    stream: anyio.abc.ByteStream = await anyio.connect_tcp(
  File "/home/venv/lib/python3.9/site-packages/anyio/_core/_sockets.py", line 225, in connect_tcp
    raise OSError("All connection attempts failed") from cause
OSError: All connection attempts failed

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "/home/venv/lib/python3.9/site-packages/httpx/_transports/default.py", line 60, in map_httpcore_exceptions
    yield
  File "/home/venv/lib/python3.9/site-packages/httpx/_transports/default.py", line 353, in handle_async_request
    resp = await self._pool.handle_async_request(req)
  File "/home/venv/lib/python3.9/site-packages/httpcore/_async/connection_pool.py", line 253, in handle_async_request
    raise exc
  File "/home/venv/lib/python3.9/site-packages/httpcore/_async/connection_pool.py", line 237, in handle_async_request
    response = await connection.handle_async_request(request)
  File "/home/venv/lib/python3.9/site-packages/httpcore/_async/connection.py", line 86, in handle_async_request
    raise exc
  File "/home/venv/lib/python3.9/site-packages/httpcore/_async/connection.py", line 63, in handle_async_request
    stream = await self._connect(request)
  File "/home/venv/lib/python3.9/site-packages/httpcore/_async/connection.py", line 111, in _connect
    stream = await self._network_backend.connect_tcp(**kwargs)
  File "/home/venv/lib/python3.9/site-packages/httpcore/backends/auto.py", line 29, in connect_tcp
    return await self._backend.connect_tcp(
  File "/home/venv/lib/python3.9/site-packages/httpcore/backends/asyncio.py", line 111, in connect_tcp
    stream: anyio.abc.ByteStream = await anyio.connect_tcp(
  File "/usr/lib/python3.9/contextlib.py", line 137, in __exit__
    self.gen.throw(typ, value, traceback)
  File "/home/venv/lib/python3.9/site-packages/httpcore/_exceptions.py", line 14, in map_exceptions
    raise to_exc(exc)
httpcore.ConnectError: All connection attempts failed

The above exception was the direct cause of the following exception:

Traceback (most recent call last):
  File "/home/venv/lib/python3.9/site-packages/starlette/middleware/errors.py", line 162, in __call__
    await self.app(scope, receive, _send)
  File "/home/venv/lib/python3.9/site-packages/timing_asgi/middleware.py", line 70, in __call__
    await self.app(scope, receive, send_wrapper)
  File "/home/venv/lib/python3.9/site-packages/starlette/middleware/exceptions.py", line 79, in __call__
    raise exc
  File "/home/venv/lib/python3.9/site-packages/starlette/middleware/exceptions.py", line 68, in __call__
    await self.app(scope, receive, sender)
  File "/home/venv/lib/python3.9/site-packages/fastapi/middleware/asyncexitstack.py", line 21, in __call__
    raise e
  File "/home/venv/lib/python3.9/site-packages/fastapi/middleware/asyncexitstack.py", line 18, in __call__
    await self.app(scope, receive, send)
  File "/home/venv/lib/python3.9/site-packages/starlette/routing.py", line 718, in __call__
    await route.handle(scope, receive, send)
  File "/home/venv/lib/python3.9/site-packages/starlette/routing.py", line 276, in handle
    await self.app(scope, receive, send)
  File "/home/venv/lib/python3.9/site-packages/starlette/routing.py", line 66, in app
    response = await func(request)
  File "/home/venv/lib/python3.9/site-packages/fastapi/routing.py", line 237, in app
    raw_response = await run_endpoint_function(
  File "/home/venv/lib/python3.9/site-packages/fastapi/routing.py", line 163, in run_endpoint_function
    return await dependant.call(**values)
  File "/home/venv/lib/python3.9/site-packages/kserve/protocol/rest/v1_endpoints.py", line 76, in predict
    response, response_headers = await self.dataplane.infer(model_name=model_name,
  File "/home/venv/lib/python3.9/site-packages/kserve/protocol/dataplane.py", line 311, in infer
    response = await model(request, headers=headers)
  File "/home/venv/lib/python3.9/site-packages/kserve/model.py", line 121, in __call__
    response = (await self.predict(payload, headers)) if inspect.iscoroutinefunction(self.predict) \
  File "/home/venv/lib/python3.9/site-packages/kserve/model.py", line 295, in predict
    res = await self._http_predict(payload, headers)
  File "/home/venv/lib/python3.9/site-packages/kserve/model.py", line 245, in _http_predict
    response = await self._http_client.post(
  File "/home/venv/lib/python3.9/site-packages/httpx/_client.py", line 1848, in post
    return await self.request(
  File "/home/venv/lib/python3.9/site-packages/httpx/_client.py", line 1533, in request
    return await self.send(request, auth=auth, follow_redirects=follow_redirects)
  File "/home/venv/lib/python3.9/site-packages/httpx/_client.py", line 1620, in send
    response = await self._send_handling_auth(
  File "/home/venv/lib/python3.9/site-packages/httpx/_client.py", line 1648, in _send_handling_auth
    response = await self._send_handling_redirects(
  File "/home/venv/lib/python3.9/site-packages/httpx/_client.py", line 1685, in _send_handling_redirects
    response = await self._send_single_request(request)
  File "/home/venv/lib/python3.9/site-packages/httpx/_client.py", line 1722, in _send_single_request
    response = await transport.handle_async_request(request)
  File "/home/venv/lib/python3.9/site-packages/httpx/_transports/default.py", line 353, in handle_async_request
    resp = await self._pool.handle_async_request(req)
  File "/usr/lib/python3.9/contextlib.py", line 137, in __exit__
    self.gen.throw(typ, value, traceback)
  File "/home/venv/lib/python3.9/site-packages/httpx/_transports/default.py", line 77, in map_httpcore_exceptions
    raise mapped_exc(message) from exc
httpx.ConnectError: All connection attempts failed
2023-11-11 19:43:40.429 uvicorn.access INFO:     127.0.0.6:49033 9 - "POST /v1/models/sdxl%3Apredict HTTP/1.1" 500 Internal Server Error
2023-11-11 19:43:40.429 uvicorn.error ERROR:    Exception in ASGI application
Traceback (most recent call last):
  File "/home/venv/lib/python3.9/site-packages/anyio/_core/_sockets.py", line 167, in try_connect
    stream = await asynclib.connect_tcp(remote_host, remote_port, local_address)
  File "/home/venv/lib/python3.9/site-packages/anyio/_backends/_asyncio.py", line 1627, in connect_tcp
    await get_running_loop().create_connection(
  File "/usr/lib/python3.9/asyncio/base_events.py", line 1065, in create_connection
    raise exceptions[0]
  File "/usr/lib/python3.9/asyncio/base_events.py", line 1050, in create_connection
    sock = await self._connect_sock(
  File "/usr/lib/python3.9/asyncio/base_events.py", line 961, in _connect_sock
    await self.sock_connect(sock, address)
  File "/usr/lib/python3.9/asyncio/selector_events.py", line 500, in sock_connect
    return await fut
  File "/usr/lib/python3.9/asyncio/selector_events.py", line 535, in _sock_connect_cb
    raise OSError(err, f'Connect call failed {address}')
ConnectionRefusedError: [Errno 111] Connect call failed ('0.0.0.0', 8085)

The above exception was the direct cause of the following exception:

Traceback (most recent call last):
  File "/home/venv/lib/python3.9/site-packages/httpcore/_exceptions.py", line 10, in map_exceptions
    yield
  File "/home/venv/lib/python3.9/site-packages/httpcore/backends/asyncio.py", line 111, in connect_tcp
    stream: anyio.abc.ByteStream = await anyio.connect_tcp(
  File "/home/venv/lib/python3.9/site-packages/anyio/_core/_sockets.py", line 225, in connect_tcp
    raise OSError("All connection attempts failed") from cause
OSError: All connection attempts failed

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "/home/venv/lib/python3.9/site-packages/httpx/_transports/default.py", line 60, in map_httpcore_exceptions
    yield
  File "/home/venv/lib/python3.9/site-packages/httpx/_transports/default.py", line 353, in handle_async_request
    resp = await self._pool.handle_async_request(req)
  File "/home/venv/lib/python3.9/site-packages/httpcore/_async/connection_pool.py", line 253, in handle_async_request
    raise exc
  File "/home/venv/lib/python3.9/site-packages/httpcore/_async/connection_pool.py", line 237, in handle_async_request
    response = await connection.handle_async_request(request)
  File "/home/venv/lib/python3.9/site-packages/httpcore/_async/connection.py", line 86, in handle_async_request
    raise exc
  File "/home/venv/lib/python3.9/site-packages/httpcore/_async/connection.py", line 63, in handle_async_request
    stream = await self._connect(request)
  File "/home/venv/lib/python3.9/site-packages/httpcore/_async/connection.py", line 111, in _connect
    stream = await self._network_backend.connect_tcp(**kwargs)
  File "/home/venv/lib/python3.9/site-packages/httpcore/backends/auto.py", line 29, in connect_tcp
    return await self._backend.connect_tcp(
  File "/home/venv/lib/python3.9/site-packages/httpcore/backends/asyncio.py", line 111, in connect_tcp
    stream: anyio.abc.ByteStream = await anyio.connect_tcp(
  File "/usr/lib/python3.9/contextlib.py", line 137, in __exit__
    self.gen.throw(typ, value, traceback)
  File "/home/venv/lib/python3.9/site-packages/httpcore/_exceptions.py", line 14, in map_exceptions
    raise to_exc(exc)
httpcore.ConnectError: All connection attempts failed

The above exception was the direct cause of the following exception:

Traceback (most recent call last):
  File "/home/venv/lib/python3.9/site-packages/uvicorn/protocols/http/httptools_impl.py", line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File "/home/venv/lib/python3.9/site-packages/uvicorn/middleware/proxy_headers.py", line 78, in __call__
    return await self.app(scope, receive, send)
  File "/home/venv/lib/python3.9/site-packages/fastapi/applications.py", line 276, in __call__
    await super().__call__(scope, receive, send)
  File "/home/venv/lib/python3.9/site-packages/starlette/applications.py", line 122, in __call__
    await self.middleware_stack(scope, receive, send)
  File "/home/venv/lib/python3.9/site-packages/starlette/middleware/errors.py", line 184, in __call__
    raise exc
  File "/home/venv/lib/python3.9/site-packages/starlette/middleware/errors.py", line 162, in __call__
    await self.app(scope, receive, _send)
  File "/home/venv/lib/python3.9/site-packages/timing_asgi/middleware.py", line 70, in __call__
    await self.app(scope, receive, send_wrapper)
  File "/home/venv/lib/python3.9/site-packages/starlette/middleware/exceptions.py", line 79, in __call__
    raise exc
  File "/home/venv/lib/python3.9/site-packages/starlette/middleware/exceptions.py", line 68, in __call__
    await self.app(scope, receive, sender)
  File "/home/venv/lib/python3.9/site-packages/fastapi/middleware/asyncexitstack.py", line 21, in __call__
    raise e
  File "/home/venv/lib/python3.9/site-packages/fastapi/middleware/asyncexitstack.py", line 18, in __call__
    await self.app(scope, receive, send)
  File "/home/venv/lib/python3.9/site-packages/starlette/routing.py", line 718, in __call__
    await route.handle(scope, receive, send)
  File "/home/venv/lib/python3.9/site-packages/starlette/routing.py", line 276, in handle
    await self.app(scope, receive, send)
  File "/home/venv/lib/python3.9/site-packages/starlette/routing.py", line 66, in app
    response = await func(request)
  File "/home/venv/lib/python3.9/site-packages/fastapi/routing.py", line 237, in app
    raw_response = await run_endpoint_function(
  File "/home/venv/lib/python3.9/site-packages/fastapi/routing.py", line 163, in run_endpoint_function
    return await dependant.call(**values)
  File "/home/venv/lib/python3.9/site-packages/kserve/protocol/rest/v1_endpoints.py", line 76, in predict
    response, response_headers = await self.dataplane.infer(model_name=model_name,
  File "/home/venv/lib/python3.9/site-packages/kserve/protocol/dataplane.py", line 311, in infer
    response = await model(request, headers=headers)
  File "/home/venv/lib/python3.9/site-packages/kserve/model.py", line 121, in __call__
    response = (await self.predict(payload, headers)) if inspect.iscoroutinefunction(self.predict) \
  File "/home/venv/lib/python3.9/site-packages/kserve/model.py", line 295, in predict
    res = await self._http_predict(payload, headers)
  File "/home/venv/lib/python3.9/site-packages/kserve/model.py", line 245, in _http_predict
    response = await self._http_client.post(
  File "/home/venv/lib/python3.9/site-packages/httpx/_client.py", line 1848, in post
    return await self.request(
  File "/home/venv/lib/python3.9/site-packages/httpx/_client.py", line 1533, in request
    return await self.send(request, auth=auth, follow_redirects=follow_redirects)
  File "/home/venv/lib/python3.9/site-packages/httpx/_client.py", line 1620, in send
    response = await self._send_handling_auth(
  File "/home/venv/lib/python3.9/site-packages/httpx/_client.py", line 1648, in _send_handling_auth
    response = await self._send_handling_redirects(
  File "/home/venv/lib/python3.9/site-packages/httpx/_client.py", line 1685, in _send_handling_redirects
    response = await self._send_single_request(request)
  File "/home/venv/lib/python3.9/site-packages/httpx/_client.py", line 1722, in _send_single_request
    response = await transport.handle_async_request(request)
  File "/home/venv/lib/python3.9/site-packages/httpx/_transports/default.py", line 353, in handle_async_request
    resp = await self._pool.handle_async_request(req)
  File "/usr/lib/python3.9/contextlib.py", line 137, in __exit__
    self.gen.throw(typ, value, traceback)
  File "/home/venv/lib/python3.9/site-packages/httpx/_transports/default.py", line 77, in map_httpcore_exceptions
    raise mapped_exc(message) from exc
httpx.ConnectError: All connection attempts failed
2023-11-11T19:44:51,588 [DEBUG] main org.pytorch.serve.wlm.ModelVersionedRefs - Setting default version to 1.0 for model sdxl
2023-11-11T19:44:51,593 [INFO ] main org.pytorch.serve.wlm.ModelManager - Model sdxl loaded.
2023-11-11T19:44:51,594 [DEBUG] main org.pytorch.serve.wlm.ModelManager - updateModel: sdxl, count: 1
2023-11-11T19:44:51,611 [DEBUG] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerLifeCycle - Worker cmdline: [/home/venv/bin/python, /home/venv/lib/python3.9/site-packages/ts/model_service_worker.py, --sock-type, unix, --sock-name, /home/model-server/tmp/.ts.sock.9000, --metrics-config, /home/venv/lib/python3.9/site-packages/ts/configs/metrics.yaml]
2023-11-11T19:44:51,614 [INFO ] main org.pytorch.serve.ModelServer - Initialize Inference server with: EpollServerSocketChannel.
2023-11-11T19:44:51,899 [INFO ] main org.pytorch.serve.ModelServer - Inference API bind to: http://0.0.0.0:8085
2023-11-11T19:44:51,968 [INFO ] main org.pytorch.serve.ModelServer - Initialize Metrics server with: EpollServerSocketChannel.
2023-11-11T19:44:51,969 [INFO ] main org.pytorch.serve.ModelServer - Metrics API bind to: http://0.0.0.0:8082
Model server started.
2023-11-11T19:44:52,469 [WARN ] pool-3-thread-1 org.pytorch.serve.metrics.MetricCollector - worker pid is not available yet.
2023-11-11T19:44:53,151 [INFO ] pool-3-thread-1 TS_METRICS - CPUUtilization.Percent:50.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699731893
2023-11-11T19:44:53,152 [INFO ] pool-3-thread-1 TS_METRICS - DiskAvailable.Gigabytes:32.942230224609375|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699731893
2023-11-11T19:44:53,152 [INFO ] pool-3-thread-1 TS_METRICS - DiskUsage.Gigabytes:47.0460319519043|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699731893
2023-11-11T19:44:53,153 [INFO ] pool-3-thread-1 TS_METRICS - DiskUtilization.Percent:58.8|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699731893
2023-11-11T19:44:53,153 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699731893
2023-11-11T19:44:53,153 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUsed.Megabytes:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699731893
2023-11-11T19:44:53,153 [INFO ] pool-3-thread-1 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699731893
2023-11-11T19:44:53,154 [INFO ] pool-3-thread-1 TS_METRICS - MemoryAvailable.Megabytes:14004.12890625|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699731893
2023-11-11T19:44:53,154 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUsed.Megabytes:1364.15625|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699731893
2023-11-11T19:44:53,154 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUtilization.Percent:10.8|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699731893
2023-11-11T19:44:56,723 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - s_name_part0=/home/model-server/tmp/.ts.sock, s_name_part1=9000, pid=128
2023-11-11T19:44:56,724 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - Listening on port: /home/model-server/tmp/.ts.sock.9000
2023-11-11T19:44:56,731 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - Successfully loaded /home/venv/lib/python3.9/site-packages/ts/configs/metrics.yaml.
2023-11-11T19:44:56,732 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - [PID]128
2023-11-11T19:44:56,732 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - Torch worker started.
2023-11-11T19:44:56,732 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - Python runtime: 3.9.18
2023-11-11T19:44:56,733 [DEBUG] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - W-9000-sdxl_1.0 State change null -> WORKER_STARTED
2023-11-11T19:44:56,770 [INFO ] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - Connecting to: /home/model-server/tmp/.ts.sock.9000
2023-11-11T19:44:56,777 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - Connection accepted: /home/model-server/tmp/.ts.sock.9000.
2023-11-11T19:44:56,779 [INFO ] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - Flushing req.cmd LOAD to backend at: 1699731896779
2023-11-11T19:44:56,804 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - model_name: sdxl, batchSize: 1
2023-11-11T19:44:57,119 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - The cache for model files in Transformers v4.22.0 has been updated. Migrating your old cache. This is a one-time only operation. You can interrupt this and resume the migration later on by calling `transformers.utils.move_cache()`.
2023-11-11T19:44:57,121 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 
2023-11-11T19:44:57,122 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 0it [00:00, ?it/s]
2023-11-11T19:44:57,122 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 0it [00:00, ?it/s]
2023-11-11T19:44:57,310 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - Created a temporary directory at /home/model-server/tmp/tmpzqke16iy
2023-11-11T19:44:57,310 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - Writing /home/model-server/tmp/tmpzqke16iy/_remote_module_non_scriptable.py
2023-11-11T19:44:57,795 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - proceeding without onnxruntime
2023-11-11T19:44:57,795 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - Torch TensorRT not enabled
2023-11-11T19:44:57,795 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - Loading sdxl_handler...
2023-11-11T19:44:57,796 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - torch.cuda.is_available() = True
2023-11-11T19:44:57,796 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - gpu_id = 0
2023-11-11T19:45:53,170 [INFO ] pool-3-thread-1 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699731953
2023-11-11T19:45:53,186 [INFO ] pool-3-thread-1 TS_METRICS - DiskAvailable.Gigabytes:29.450218200683594|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699731953
2023-11-11T19:45:53,186 [INFO ] pool-3-thread-1 TS_METRICS - DiskUsage.Gigabytes:50.53804397583008|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699731953
2023-11-11T19:45:53,187 [INFO ] pool-3-thread-1 TS_METRICS - DiskUtilization.Percent:63.2|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699731953
2023-11-11T19:45:53,187 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUtilization.Percent:0.019855715136673505|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699731953
2023-11-11T19:45:53,187 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUsed.Megabytes:3.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699731953
2023-11-11T19:45:53,187 [INFO ] pool-3-thread-1 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699731953
2023-11-11T19:45:53,188 [INFO ] pool-3-thread-1 TS_METRICS - MemoryAvailable.Megabytes:13797.1171875|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699731953
2023-11-11T19:45:53,188 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUsed.Megabytes:1571.21875|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699731953
2023-11-11T19:45:53,188 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUtilization.Percent:12.1|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699731953
2023-11-11T19:46:43,157 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 
2023-11-11T19:46:43,258 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - Loading pipeline components...:   0%|          | 0/7 [00:00<?, ?it/s]Special tokens have been added in the vocabulary, make sure the associated word embeddings are fine-tuned or trained.
2023-11-11T19:46:43,258 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 
2023-11-11T19:46:43,603 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - Loading pipeline components...:  14%|█▍        | 1/7 [00:00<00:00,  9.95it/s]
2023-11-11T19:46:43,676 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - Loading pipeline components...:  29%|██▊       | 2/7 [00:00<00:01,  4.10it/s]Special tokens have been added in the vocabulary, make sure the associated word embeddings are fine-tuned or trained.
2023-11-11T19:46:43,759 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 
2023-11-11T19:46:44,250 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - Loading pipeline components...:  57%|█████▋    | 4/7 [00:00<00:00,  7.13it/s]
2023-11-11T19:46:45,396 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - Loading pipeline components...:  71%|███████▏  | 5/7 [00:01<00:00,  4.02it/s]
2023-11-11T19:46:45,396 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - Loading pipeline components...: 100%|██████████| 7/7 [00:02<00:00,  2.50it/s]
2023-11-11T19:46:45,396 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - Loading pipeline components...: 100%|██████████| 7/7 [00:02<00:00,  3.13it/s]
2023-11-11T19:46:53,141 [INFO ] pool-3-thread-1 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732013
2023-11-11T19:46:53,147 [INFO ] pool-3-thread-1 TS_METRICS - DiskAvailable.Gigabytes:26.5107421875|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732013
2023-11-11T19:46:53,147 [INFO ] pool-3-thread-1 TS_METRICS - DiskUsage.Gigabytes:53.47751998901367|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732013
2023-11-11T19:46:53,147 [INFO ] pool-3-thread-1 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732013
2023-11-11T19:46:53,148 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUtilization.Percent:4.3219273280826|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732013
2023-11-11T19:46:53,148 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUsed.Megabytes:653.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732013
2023-11-11T19:46:53,148 [INFO ] pool-3-thread-1 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732013
2023-11-11T19:46:53,149 [INFO ] pool-3-thread-1 TS_METRICS - MemoryAvailable.Megabytes:12790.703125|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732013
2023-11-11T19:46:53,149 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUsed.Megabytes:2557.56640625|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732013
2023-11-11T19:46:53,149 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUtilization.Percent:18.5|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732013
2023-11-11T19:47:10,634 [INFO ] epollEventLoopGroup-3-1 TS_METRICS - ts_inference_requests_total.Count:1.0|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732030
2023-11-11T19:47:49,130 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - loaded StableDiffusionXL model from /home/model-server/tmp/models/e1ac93deb1434335ba74236ded8af456/sdxl-1.0-model.zip
2023-11-11T19:47:49,131 [DEBUG] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - sent a reply, jobdone: true
2023-11-11T19:47:49,131 [INFO ] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - Backend response time: 172327
2023-11-11T19:47:49,132 [DEBUG] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - W-9000-sdxl_1.0 State change WORKER_STARTED -> WORKER_MODEL_LOADED
2023-11-11T19:47:49,132 [INFO ] W-9000-sdxl_1.0 TS_METRICS - WorkerLoadTime.Milliseconds:177524.0|#WorkerName:W-9000-sdxl_1.0,Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732069
2023-11-11T19:47:49,133 [INFO ] W-9000-sdxl_1.0 TS_METRICS - WorkerThreadTime.Milliseconds:27.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732069
2023-11-11T19:47:49,134 [INFO ] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - Flushing req.cmd PREDICT to backend at: 1699732069134
2023-11-11T19:47:49,135 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - Backend received inference at: 1699732069
2023-11-11T19:47:49,136 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - received text: 'a cat staring at a chicken'
2023-11-11T19:47:51,344 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 
2023-11-11T19:47:53,043 [INFO ] pool-3-thread-2 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732073
2023-11-11T19:47:53,045 [INFO ] pool-3-thread-2 TS_METRICS - DiskAvailable.Gigabytes:26.513870239257812|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732073
2023-11-11T19:47:53,045 [INFO ] pool-3-thread-2 TS_METRICS - DiskUsage.Gigabytes:53.47439193725586|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732073
2023-11-11T19:47:53,045 [INFO ] pool-3-thread-2 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732073
2023-11-11T19:47:53,046 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUtilization.Percent:52.00211794294791|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732073
2023-11-11T19:47:53,046 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUsed.Megabytes:7857.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732073
2023-11-11T19:47:53,046 [INFO ] pool-3-thread-2 TS_METRICS - GPUUtilization.Percent:1.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732073
2023-11-11T19:47:53,046 [INFO ] pool-3-thread-2 TS_METRICS - MemoryAvailable.Megabytes:11972.47265625|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732073
2023-11-11T19:47:53,047 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUsed.Megabytes:3373.88671875|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732073
2023-11-11T19:47:53,047 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUtilization.Percent:23.7|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732073
2023-11-11T19:47:54,495 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   0%|          | 0/50 [00:00<?, ?it/s]
2023-11-11T19:47:55,235 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   2%|▏         | 1/50 [00:03<02:34,  3.15s/it]
2023-11-11T19:47:55,974 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   4%|▍         | 2/50 [00:03<01:23,  1.73s/it]
2023-11-11T19:47:56,695 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   6%|▌         | 3/50 [00:04<01:00,  1.28s/it]
2023-11-11T19:47:57,423 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   8%|▊         | 4/50 [00:05<00:48,  1.06s/it]
2023-11-11T19:47:58,153 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  10%|█         | 5/50 [00:06<00:42,  1.06it/s]
2023-11-11T19:47:58,887 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  12%|█▏        | 6/50 [00:06<00:38,  1.15it/s]
2023-11-11T19:47:59,627 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  14%|█▍        | 7/50 [00:07<00:35,  1.21it/s]
2023-11-11T19:48:00,359 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  16%|█▌        | 8/50 [00:08<00:33,  1.25it/s]
2023-11-11T19:48:01,088 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  18%|█▊        | 9/50 [00:09<00:31,  1.29it/s]
2023-11-11T19:48:01,817 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  20%|██        | 10/50 [00:09<00:30,  1.31it/s]
2023-11-11T19:48:02,545 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  22%|██▏       | 11/50 [00:10<00:29,  1.33it/s]
2023-11-11T19:48:03,275 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  24%|██▍       | 12/50 [00:11<00:28,  1.34it/s]
2023-11-11T19:48:04,013 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  26%|██▌       | 13/50 [00:11<00:27,  1.35it/s]
2023-11-11T19:48:04,751 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  28%|██▊       | 14/50 [00:12<00:26,  1.35it/s]
2023-11-11T19:48:05,487 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  30%|███       | 15/50 [00:13<00:25,  1.35it/s]
2023-11-11T19:48:06,227 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  32%|███▏      | 16/50 [00:14<00:25,  1.35it/s]
2023-11-11T19:48:06,957 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  34%|███▍      | 17/50 [00:14<00:24,  1.35it/s]
2023-11-11T19:48:07,696 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  36%|███▌      | 18/50 [00:15<00:23,  1.36it/s]
2023-11-11T19:48:08,434 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  38%|███▊      | 19/50 [00:16<00:22,  1.36it/s]
2023-11-11T19:48:09,168 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  40%|████      | 20/50 [00:17<00:22,  1.36it/s]
2023-11-11T19:48:09,903 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  42%|████▏     | 21/50 [00:17<00:21,  1.36it/s]
2023-11-11T19:48:10,646 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  44%|████▍     | 22/50 [00:18<00:20,  1.36it/s]
2023-11-11T19:48:11,389 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  46%|████▌     | 23/50 [00:19<00:19,  1.35it/s]
2023-11-11T19:48:12,130 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  48%|████▊     | 24/50 [00:20<00:19,  1.35it/s]
2023-11-11T19:48:12,874 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  50%|█████     | 25/50 [00:20<00:18,  1.35it/s]
2023-11-11T19:48:13,614 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  52%|█████▏    | 26/50 [00:21<00:17,  1.35it/s]
2023-11-11T19:48:14,354 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  54%|█████▍    | 27/50 [00:22<00:17,  1.35it/s]
2023-11-11T19:48:15,102 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  56%|█████▌    | 28/50 [00:23<00:16,  1.35it/s]
2023-11-11T19:48:15,844 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  58%|█████▊    | 29/50 [00:23<00:15,  1.35it/s]
2023-11-11T19:48:16,584 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  60%|██████    | 30/50 [00:24<00:14,  1.35it/s]
2023-11-11T19:48:17,331 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  62%|██████▏   | 31/50 [00:25<00:14,  1.35it/s]
2023-11-11T19:48:18,075 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  64%|██████▍   | 32/50 [00:25<00:13,  1.35it/s]
2023-11-11T19:48:18,816 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  66%|██████▌   | 33/50 [00:26<00:12,  1.35it/s]
2023-11-11T19:48:19,562 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  68%|██████▊   | 34/50 [00:27<00:11,  1.35it/s]
2023-11-11T19:48:20,308 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  70%|███████   | 35/50 [00:28<00:11,  1.34it/s]
2023-11-11T19:48:21,053 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  72%|███████▏  | 36/50 [00:28<00:10,  1.34it/s]
2023-11-11T19:48:21,795 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  74%|███████▍  | 37/50 [00:29<00:09,  1.34it/s]
2023-11-11T19:48:22,541 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  76%|███████▌  | 38/50 [00:30<00:08,  1.34it/s]
2023-11-11T19:48:23,282 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  78%|███████▊  | 39/50 [00:31<00:08,  1.34it/s]
2023-11-11T19:48:24,022 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  80%|████████  | 40/50 [00:31<00:07,  1.34it/s]
2023-11-11T19:48:24,769 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  82%|████████▏ | 41/50 [00:32<00:06,  1.35it/s]
2023-11-11T19:48:25,518 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  84%|████████▍ | 42/50 [00:33<00:05,  1.34it/s]
2023-11-11T19:48:26,265 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  86%|████████▌ | 43/50 [00:34<00:05,  1.34it/s]
2023-11-11T19:48:27,010 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  88%|████████▊ | 44/50 [00:34<00:04,  1.34it/s]
2023-11-11T19:48:27,754 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  90%|█████████ | 45/50 [00:35<00:03,  1.34it/s]
2023-11-11T19:48:28,497 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  92%|█████████▏| 46/50 [00:36<00:02,  1.34it/s]
2023-11-11T19:48:29,244 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  94%|█████████▍| 47/50 [00:37<00:02,  1.34it/s]
2023-11-11T19:48:29,993 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  96%|█████████▌| 48/50 [00:37<00:01,  1.34it/s]
2023-11-11T19:48:30,744 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  98%|█████████▊| 49/50 [00:38<00:00,  1.34it/s]
2023-11-11T19:48:30,745 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 100%|██████████| 50/50 [00:39<00:00,  1.34it/s]
2023-11-11T19:48:30,745 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 100%|██████████| 50/50 [00:39<00:00,  1.27it/s]
2023-11-11T19:48:32,507 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - generated images: [<PIL.Image.Image image mode=RGB size=1024x1024 at 0x7F7A9E4CF2B0>]
2023-11-11T19:48:33,359 [INFO ] W-9000-sdxl_1.0-stdout org.pytorch.serve.wlm.WorkerLifeCycle - result=[METRICS]HandlerTime.Milliseconds:44223.3|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,1699732113,a3cc2983-996b-45ea-8324-e5f07b6e2a2a, pattern=[METRICS]
2023-11-11T19:48:33,368 [INFO ] W-9000-sdxl_1.0-stdout MODEL_METRICS - HandlerTime.ms:44223.3|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,requestID:a3cc2983-996b-45ea-8324-e5f07b6e2a2a,timestamp:1699732113
2023-11-11T19:48:33,368 [INFO ] W-9000-sdxl_1.0-stdout org.pytorch.serve.wlm.WorkerLifeCycle - result=[METRICS]PredictionTime.Milliseconds:44223.53|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,1699732113,a3cc2983-996b-45ea-8324-e5f07b6e2a2a, pattern=[METRICS]
2023-11-11T19:48:33,368 [INFO ] W-9000-sdxl_1.0-stdout MODEL_METRICS - PredictionTime.ms:44223.53|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,requestID:a3cc2983-996b-45ea-8324-e5f07b6e2a2a,timestamp:1699732113
2023-11-11T19:48:37,462 [INFO ] W-9000-sdxl_1.0 ACCESS_LOG - /127.0.0.1:53046 "POST /v1/models/sdxl:predict HTTP/1.1" 200 86831
2023-11-11T19:48:37,462 [INFO ] W-9000-sdxl_1.0 TS_METRICS - Requests2XX.Count:1.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732117
2023-11-11T19:48:37,463 [INFO ] W-9000-sdxl_1.0 TS_METRICS - ts_inference_latency_microseconds.Microseconds:8.6755408452E7|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732117
2023-11-11T19:48:37,463 [INFO ] W-9000-sdxl_1.0 TS_METRICS - ts_queue_latency_microseconds.Microseconds:3.8498903182E7|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732117
2023-11-11T19:48:37,463 [DEBUG] W-9000-sdxl_1.0 org.pytorch.serve.job.Job - Waiting time ns: 38498903182, Backend time ns: 48329567923
2023-11-11T19:48:37,463 [INFO ] W-9000-sdxl_1.0 TS_METRICS - QueueTime.Milliseconds:38498.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732117
2023-11-11T19:48:37,464 [DEBUG] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - sent a reply, jobdone: true
2023-11-11T19:48:37,464 [INFO ] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - Backend response time: 48255
2023-11-11T19:48:37,464 [INFO ] W-9000-sdxl_1.0 TS_METRICS - WorkerThreadTime.Milliseconds:75.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732117
2023-11-11 19:48:38.692 kserve.trace requestId: e5308443-e4ca-4adf-971e-30bacffde0fb, preprocess_ms: 0.011920929, explain_ms: 0, predict_ms: 88128.706932068, postprocess_ms: 0.003814697
2023-11-11 19:48:45.217 kserve.trace kserve.io.kserve.protocol.rest.v1_endpoints.predict: 94.653484582901
2023-11-11 19:48:45.217 kserve.trace kserve.io.kserve.protocol.rest.v1_endpoints.predict: 7.7585049999999995
2023-11-11T19:48:52,888 [INFO ] pool-3-thread-2 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732132
2023-11-11T19:48:52,888 [INFO ] pool-3-thread-2 TS_METRICS - DiskAvailable.Gigabytes:26.513748168945312|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732132
2023-11-11T19:48:52,889 [INFO ] pool-3-thread-2 TS_METRICS - DiskUsage.Gigabytes:53.47451400756836|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732132
2023-11-11T19:48:52,889 [INFO ] pool-3-thread-2 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732132
2023-11-11T19:48:52,889 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUtilization.Percent:91.36938248725924|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732132
2023-11-11T19:48:52,890 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUsed.Megabytes:13805.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732132
2023-11-11T19:48:52,890 [INFO ] pool-3-thread-2 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732132
2023-11-11T19:48:52,890 [INFO ] pool-3-thread-2 TS_METRICS - MemoryAvailable.Megabytes:11406.51953125|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732132
2023-11-11T19:48:52,890 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUsed.Megabytes:3915.87109375|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732132
2023-11-11T19:48:52,890 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUtilization.Percent:27.4|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732132
2023-11-11T19:49:02,044 [INFO ] epollEventLoopGroup-3-2 TS_METRICS - ts_inference_requests_total.Count:1.0|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732142
2023-11-11T19:49:02,045 [INFO ] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - Flushing req.cmd PREDICT to backend at: 1699732142045
2023-11-11T19:49:02,046 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - Backend received inference at: 1699732142
2023-11-11T19:49:02,046 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - received text: 'a cat staring at a chicken'
2023-11-11T19:49:02,077 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 
2023-11-11T19:49:02,792 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   0%|          | 0/50 [00:00<?, ?it/s]
2023-11-11T19:49:03,547 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   2%|▏         | 1/50 [00:00<00:34,  1.40it/s]
2023-11-11T19:49:04,290 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   4%|▍         | 2/50 [00:01<00:35,  1.35it/s]
2023-11-11T19:49:05,022 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   6%|▌         | 3/50 [00:02<00:34,  1.35it/s]
2023-11-11T19:49:05,760 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   8%|▊         | 4/50 [00:02<00:33,  1.36it/s]
2023-11-11T19:49:06,508 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  10%|█         | 5/50 [00:03<00:33,  1.36it/s]
2023-11-11T19:49:07,253 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  12%|█▏        | 6/50 [00:04<00:32,  1.35it/s]
2023-11-11T19:49:07,990 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  14%|█▍        | 7/50 [00:05<00:31,  1.35it/s]
2023-11-11T19:49:08,737 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  16%|█▌        | 8/50 [00:05<00:31,  1.35it/s]
2023-11-11T19:49:09,482 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  18%|█▊        | 9/50 [00:06<00:30,  1.35it/s]
2023-11-11T19:49:10,221 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  20%|██        | 10/50 [00:07<00:29,  1.35it/s]
2023-11-11T19:49:10,964 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  22%|██▏       | 11/50 [00:08<00:28,  1.35it/s]
2023-11-11T19:49:11,713 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  24%|██▍       | 12/50 [00:08<00:28,  1.35it/s]
2023-11-11T19:49:12,458 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  26%|██▌       | 13/50 [00:09<00:27,  1.34it/s]
2023-11-11T19:49:13,206 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  28%|██▊       | 14/50 [00:10<00:26,  1.34it/s]
2023-11-11T19:49:13,953 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  30%|███       | 15/50 [00:11<00:26,  1.34it/s]
2023-11-11T19:49:14,704 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  32%|███▏      | 16/50 [00:11<00:25,  1.34it/s]
2023-11-11T19:49:15,451 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  34%|███▍      | 17/50 [00:12<00:24,  1.34it/s]
2023-11-11T19:49:16,192 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  36%|███▌      | 18/50 [00:13<00:23,  1.34it/s]
2023-11-11T19:49:16,938 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  38%|███▊      | 19/50 [00:14<00:23,  1.34it/s]
2023-11-11T19:49:17,688 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  40%|████      | 20/50 [00:14<00:22,  1.34it/s]
2023-11-11T19:49:18,435 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  42%|████▏     | 21/50 [00:15<00:21,  1.34it/s]
2023-11-11T19:49:19,187 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  44%|████▍     | 22/50 [00:16<00:20,  1.34it/s]
2023-11-11T19:49:19,936 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  46%|████▌     | 23/50 [00:17<00:20,  1.34it/s]
2023-11-11T19:49:20,686 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  48%|████▊     | 24/50 [00:17<00:19,  1.34it/s]
2023-11-11T19:49:21,434 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  50%|█████     | 25/50 [00:18<00:18,  1.34it/s]
2023-11-11T19:49:22,184 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  52%|█████▏    | 26/50 [00:19<00:17,  1.34it/s]
2023-11-11T19:49:22,934 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  54%|█████▍    | 27/50 [00:20<00:17,  1.33it/s]
2023-11-11T19:49:23,682 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  56%|█████▌    | 28/50 [00:20<00:16,  1.33it/s]
2023-11-11T19:49:24,431 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  58%|█████▊    | 29/50 [00:21<00:15,  1.33it/s]
2023-11-11T19:49:25,181 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  60%|██████    | 30/50 [00:22<00:14,  1.34it/s]
2023-11-11T19:49:25,932 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  62%|██████▏   | 31/50 [00:23<00:14,  1.33it/s]
2023-11-11T19:49:26,679 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  64%|██████▍   | 32/50 [00:23<00:13,  1.33it/s]
2023-11-11T19:49:27,428 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  66%|██████▌   | 33/50 [00:24<00:12,  1.34it/s]
2023-11-11T19:49:28,179 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  68%|██████▊   | 34/50 [00:25<00:11,  1.34it/s]
2023-11-11T19:49:28,927 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  70%|███████   | 35/50 [00:26<00:11,  1.33it/s]
2023-11-11T19:49:29,676 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  72%|███████▏  | 36/50 [00:26<00:10,  1.33it/s]
2023-11-11T19:49:30,424 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  74%|███████▍  | 37/50 [00:27<00:09,  1.34it/s]
2023-11-11T19:49:31,176 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  76%|███████▌  | 38/50 [00:28<00:08,  1.34it/s]
2023-11-11T19:49:31,927 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  78%|███████▊  | 39/50 [00:29<00:08,  1.33it/s]
2023-11-11T19:49:32,681 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  80%|████████  | 40/50 [00:29<00:07,  1.33it/s]
2023-11-11T19:49:33,432 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  82%|████████▏ | 41/50 [00:30<00:06,  1.33it/s]
2023-11-11T19:49:34,187 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  84%|████████▍ | 42/50 [00:31<00:06,  1.33it/s]
2023-11-11T19:49:34,939 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  86%|████████▌ | 43/50 [00:32<00:05,  1.33it/s]
2023-11-11T19:49:35,690 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  88%|████████▊ | 44/50 [00:32<00:04,  1.33it/s]
2023-11-11T19:49:36,441 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  90%|█████████ | 45/50 [00:33<00:03,  1.33it/s]
2023-11-11T19:49:37,193 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  92%|█████████▏| 46/50 [00:34<00:03,  1.33it/s]
2023-11-11T19:49:37,949 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  94%|█████████▍| 47/50 [00:35<00:02,  1.33it/s]
2023-11-11T19:49:38,702 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  96%|█████████▌| 48/50 [00:35<00:01,  1.33it/s]
2023-11-11T19:49:39,455 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  98%|█████████▊| 49/50 [00:36<00:00,  1.33it/s]
2023-11-11T19:49:39,455 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 100%|██████████| 50/50 [00:37<00:00,  1.33it/s]
2023-11-11T19:49:39,455 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 100%|██████████| 50/50 [00:37<00:00,  1.34it/s]
2023-11-11T19:49:41,199 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - generated images: [<PIL.Image.Image image mode=RGB size=1024x1024 at 0x7F7A974DC160>]
2023-11-11T19:49:41,904 [INFO ] W-9000-sdxl_1.0-stdout org.pytorch.serve.wlm.WorkerLifeCycle - result=[METRICS]HandlerTime.Milliseconds:39857.46|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,1699732181,b2de6868-7d79-4d1a-917b-24da33499a3e, pattern=[METRICS]
2023-11-11T19:49:41,904 [INFO ] W-9000-sdxl_1.0-stdout MODEL_METRICS - HandlerTime.ms:39857.46|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,requestID:b2de6868-7d79-4d1a-917b-24da33499a3e,timestamp:1699732181
2023-11-11T19:49:41,905 [INFO ] W-9000-sdxl_1.0-stdout org.pytorch.serve.wlm.WorkerLifeCycle - result=[METRICS]PredictionTime.Milliseconds:39857.67|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,1699732181,b2de6868-7d79-4d1a-917b-24da33499a3e, pattern=[METRICS]
2023-11-11T19:49:41,905 [INFO ] W-9000-sdxl_1.0-stdout MODEL_METRICS - PredictionTime.ms:39857.67|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,requestID:b2de6868-7d79-4d1a-917b-24da33499a3e,timestamp:1699732181
2023-11-11T19:49:45,890 [INFO ] W-9000-sdxl_1.0 ACCESS_LOG - /127.0.0.1:39332 "POST /v1/models/sdxl:predict HTTP/1.1" 200 43846
2023-11-11T19:49:45,891 [INFO ] W-9000-sdxl_1.0 TS_METRICS - Requests2XX.Count:1.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732185
2023-11-11T19:49:45,891 [INFO ] W-9000-sdxl_1.0 TS_METRICS - ts_inference_latency_microseconds.Microseconds:4.3743867521E7|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732185
2023-11-11T19:49:45,891 [INFO ] W-9000-sdxl_1.0 TS_METRICS - ts_queue_latency_microseconds.Microseconds:98.513|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732185
2023-11-11T19:49:45,891 [DEBUG] W-9000-sdxl_1.0 org.pytorch.serve.job.Job - Waiting time ns: 98513, Backend time ns: 43845900163
2023-11-11T19:49:45,891 [INFO ] W-9000-sdxl_1.0 TS_METRICS - QueueTime.Milliseconds:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732185
2023-11-11T19:49:45,891 [DEBUG] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - sent a reply, jobdone: true
2023-11-11T19:49:45,891 [INFO ] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - Backend response time: 43743
2023-11-11T19:49:45,892 [INFO ] W-9000-sdxl_1.0 TS_METRICS - WorkerThreadTime.Milliseconds:104.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732185
2023-11-11 19:49:47.040 kserve.trace requestId: bdb22522-7ff5-418c-97c8-0fdd26cb1a95, preprocess_ms: 0.012159348, explain_ms: 0, predict_ms: 44998.877048492, postprocess_ms: 0.003576279
2023-11-11T19:49:53,180 [INFO ] pool-3-thread-2 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732193
2023-11-11T19:49:53,180 [INFO ] pool-3-thread-2 TS_METRICS - DiskAvailable.Gigabytes:26.513710021972656|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732193
2023-11-11T19:49:53,180 [INFO ] pool-3-thread-2 TS_METRICS - DiskUsage.Gigabytes:53.474552154541016|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732193
2023-11-11T19:49:53,181 [INFO ] pool-3-thread-2 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732193
2023-11-11T19:49:53,181 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732193
2023-11-11T19:49:53,181 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732193
2023-11-11T19:49:53,181 [INFO ] pool-3-thread-2 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732193
2023-11-11T19:49:53,182 [INFO ] pool-3-thread-2 TS_METRICS - MemoryAvailable.Megabytes:11152.69921875|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732193
2023-11-11T19:49:53,182 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUsed.Megabytes:4169.69140625|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732193
2023-11-11T19:49:53,182 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUtilization.Percent:29.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732193
2023-11-11 19:49:54.378 uvicorn.access INFO:     127.0.0.6:40959 9 - "POST /v1/models/sdxl%3Apredict HTTP/1.1" 200 OK
2023-11-11 19:49:54.386 kserve.trace kserve.io.kserve.protocol.rest.v1_endpoints.predict: 52.34605860710144
2023-11-11 19:49:54.387 kserve.trace kserve.io.kserve.protocol.rest.v1_endpoints.predict: 7.945345
2023-11-11T19:50:52,896 [INFO ] pool-3-thread-2 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732252
2023-11-11T19:50:52,896 [INFO ] pool-3-thread-2 TS_METRICS - DiskAvailable.Gigabytes:26.513748168945312|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732252
2023-11-11T19:50:52,896 [INFO ] pool-3-thread-2 TS_METRICS - DiskUsage.Gigabytes:53.47451400756836|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732252
2023-11-11T19:50:52,897 [INFO ] pool-3-thread-2 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732252
2023-11-11T19:50:52,897 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732252
2023-11-11T19:50:52,897 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732252
2023-11-11T19:50:52,897 [INFO ] pool-3-thread-2 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732252
2023-11-11T19:50:52,897 [INFO ] pool-3-thread-2 TS_METRICS - MemoryAvailable.Megabytes:11331.81640625|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732252
2023-11-11T19:50:52,897 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUsed.Megabytes:3990.57421875|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732252
2023-11-11T19:50:52,897 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUtilization.Percent:27.8|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732252
2023-11-11T19:51:01,164 [INFO ] epollEventLoopGroup-3-3 TS_METRICS - ts_inference_requests_total.Count:1.0|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732261
2023-11-11T19:51:01,165 [INFO ] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - Flushing req.cmd PREDICT to backend at: 1699732261165
2023-11-11T19:51:01,166 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - Backend received inference at: 1699732261
2023-11-11T19:51:01,166 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - received text: 'a cat playing football'
2023-11-11T19:51:01,195 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 
2023-11-11T19:51:01,916 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   0%|          | 0/50 [00:00<?, ?it/s]
2023-11-11T19:51:02,662 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   2%|▏         | 1/50 [00:00<00:35,  1.39it/s]
2023-11-11T19:51:03,403 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   4%|▍         | 2/50 [00:01<00:35,  1.36it/s]
2023-11-11T19:51:04,135 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   6%|▌         | 3/50 [00:02<00:34,  1.35it/s]
2023-11-11T19:51:04,866 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   8%|▊         | 4/50 [00:02<00:33,  1.36it/s]
2023-11-11T19:51:05,611 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  10%|█         | 5/50 [00:03<00:33,  1.36it/s]
2023-11-11T19:51:06,354 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  12%|█▏        | 6/50 [00:04<00:32,  1.36it/s]
2023-11-11T19:51:07,090 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  14%|█▍        | 7/50 [00:05<00:31,  1.35it/s]
2023-11-11T19:51:07,828 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  16%|█▌        | 8/50 [00:05<00:31,  1.35it/s]
2023-11-11T19:51:08,571 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  18%|█▊        | 9/50 [00:06<00:30,  1.35it/s]
2023-11-11T19:51:09,315 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  20%|██        | 10/50 [00:07<00:29,  1.35it/s]
2023-11-11T19:51:10,052 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  22%|██▏       | 11/50 [00:08<00:28,  1.35it/s]
2023-11-11T19:51:10,798 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  24%|██▍       | 12/50 [00:08<00:28,  1.35it/s]
2023-11-11T19:51:11,544 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  26%|██▌       | 13/50 [00:09<00:27,  1.35it/s]
2023-11-11T19:51:12,283 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  28%|██▊       | 14/50 [00:10<00:26,  1.35it/s]
2023-11-11T19:51:13,025 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  30%|███       | 15/50 [00:11<00:25,  1.35it/s]
2023-11-11T19:51:13,772 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  32%|███▏      | 16/50 [00:11<00:25,  1.35it/s]
2023-11-11T19:51:14,519 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  34%|███▍      | 17/50 [00:12<00:24,  1.34it/s]
2023-11-11T19:51:15,261 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  36%|███▌      | 18/50 [00:13<00:23,  1.34it/s]
2023-11-11T19:51:16,005 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  38%|███▊      | 19/50 [00:14<00:23,  1.34it/s]
2023-11-11T19:51:16,750 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  40%|████      | 20/50 [00:14<00:22,  1.34it/s]
2023-11-11T19:51:17,491 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  42%|████▏     | 21/50 [00:15<00:21,  1.34it/s]
2023-11-11T19:51:18,237 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  44%|████▍     | 22/50 [00:16<00:20,  1.35it/s]
2023-11-11T19:51:18,984 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  46%|████▌     | 23/50 [00:17<00:20,  1.34it/s]
2023-11-11T19:51:19,732 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  48%|████▊     | 24/50 [00:17<00:19,  1.34it/s]
2023-11-11T19:51:20,479 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  50%|█████     | 25/50 [00:18<00:18,  1.34it/s]
2023-11-11T19:51:21,229 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  52%|█████▏    | 26/50 [00:19<00:17,  1.34it/s]
2023-11-11T19:51:21,978 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  54%|█████▍    | 27/50 [00:20<00:17,  1.34it/s]
2023-11-11T19:51:22,728 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  56%|█████▌    | 28/50 [00:20<00:16,  1.34it/s]
2023-11-11T19:51:23,477 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  58%|█████▊    | 29/50 [00:21<00:15,  1.34it/s]
2023-11-11T19:51:24,226 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  60%|██████    | 30/50 [00:22<00:14,  1.34it/s]
2023-11-11T19:51:24,976 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  62%|██████▏   | 31/50 [00:23<00:14,  1.34it/s]
2023-11-11T19:51:25,726 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  64%|██████▍   | 32/50 [00:23<00:13,  1.33it/s]
2023-11-11T19:51:26,476 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  66%|██████▌   | 33/50 [00:24<00:12,  1.33it/s]
2023-11-11T19:51:27,225 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  68%|██████▊   | 34/50 [00:25<00:11,  1.33it/s]
2023-11-11T19:51:27,976 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  70%|███████   | 35/50 [00:26<00:11,  1.33it/s]
2023-11-11T19:51:28,725 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  72%|███████▏  | 36/50 [00:26<00:10,  1.33it/s]
2023-11-11T19:51:29,475 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  74%|███████▍  | 37/50 [00:27<00:09,  1.33it/s]
2023-11-11T19:51:30,223 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  76%|███████▌  | 38/50 [00:28<00:08,  1.33it/s]
2023-11-11T19:51:30,971 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  78%|███████▊  | 39/50 [00:29<00:08,  1.33it/s]
2023-11-11T19:51:31,720 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  80%|████████  | 40/50 [00:29<00:07,  1.34it/s]
2023-11-11T19:51:32,470 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  82%|████████▏ | 41/50 [00:30<00:06,  1.34it/s]
2023-11-11T19:51:33,219 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  84%|████████▍ | 42/50 [00:31<00:05,  1.33it/s]
2023-11-11T19:51:33,969 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  86%|████████▌ | 43/50 [00:32<00:05,  1.33it/s]
2023-11-11T19:51:34,721 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  88%|████████▊ | 44/50 [00:32<00:04,  1.33it/s]
2023-11-11T19:51:35,473 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  90%|█████████ | 45/50 [00:33<00:03,  1.33it/s]
2023-11-11T19:51:36,223 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  92%|█████████▏| 46/50 [00:34<00:03,  1.33it/s]
2023-11-11T19:51:36,971 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  94%|█████████▍| 47/50 [00:35<00:02,  1.33it/s]
2023-11-11T19:51:37,718 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  96%|█████████▌| 48/50 [00:35<00:01,  1.33it/s]
2023-11-11T19:51:38,470 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  98%|█████████▊| 49/50 [00:36<00:00,  1.34it/s]
2023-11-11T19:51:38,470 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 100%|██████████| 50/50 [00:37<00:00,  1.33it/s]
2023-11-11T19:51:38,470 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 100%|██████████| 50/50 [00:37<00:00,  1.34it/s]
2023-11-11T19:51:40,208 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - generated images: [<PIL.Image.Image image mode=RGB size=1024x1024 at 0x7F7A974DC070>]
2023-11-11T19:51:40,939 [INFO ] W-9000-sdxl_1.0-stdout org.pytorch.serve.wlm.WorkerLifeCycle - result=[METRICS]HandlerTime.Milliseconds:39772.62|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,1699732300,2436a314-411b-491c-9a90-ac7782239287, pattern=[METRICS]
2023-11-11T19:51:40,939 [INFO ] W-9000-sdxl_1.0-stdout MODEL_METRICS - HandlerTime.ms:39772.62|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,requestID:2436a314-411b-491c-9a90-ac7782239287,timestamp:1699732300
2023-11-11T19:51:40,939 [INFO ] W-9000-sdxl_1.0-stdout org.pytorch.serve.wlm.WorkerLifeCycle - result=[METRICS]PredictionTime.Milliseconds:39772.89|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,1699732300,2436a314-411b-491c-9a90-ac7782239287, pattern=[METRICS]
2023-11-11T19:51:40,939 [INFO ] W-9000-sdxl_1.0-stdout MODEL_METRICS - PredictionTime.ms:39772.89|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,requestID:2436a314-411b-491c-9a90-ac7782239287,timestamp:1699732300
2023-11-11T19:51:45,028 [INFO ] W-9000-sdxl_1.0 ACCESS_LOG - /127.0.0.1:53494 "POST /v1/models/sdxl:predict HTTP/1.1" 200 43864
2023-11-11T19:51:45,029 [INFO ] W-9000-sdxl_1.0 TS_METRICS - Requests2XX.Count:1.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732305
2023-11-11T19:51:45,029 [INFO ] W-9000-sdxl_1.0 TS_METRICS - ts_inference_latency_microseconds.Microseconds:4.3792266144E7|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732305
2023-11-11T19:51:45,029 [INFO ] W-9000-sdxl_1.0 TS_METRICS - ts_queue_latency_microseconds.Microseconds:101.378|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732305
2023-11-11T19:51:45,029 [DEBUG] W-9000-sdxl_1.0 org.pytorch.serve.job.Job - Waiting time ns: 101378, Backend time ns: 43864313816
2023-11-11T19:51:45,030 [INFO ] W-9000-sdxl_1.0 TS_METRICS - QueueTime.Milliseconds:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732305
2023-11-11T19:51:45,030 [DEBUG] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - sent a reply, jobdone: true
2023-11-11T19:51:45,031 [INFO ] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - Backend response time: 43791
2023-11-11T19:51:45,031 [INFO ] W-9000-sdxl_1.0 TS_METRICS - WorkerThreadTime.Milliseconds:75.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732305
2023-11-11 19:51:45.935 kserve.trace requestId: 2dae0a84-06ea-4093-8108-278b4b66abda, preprocess_ms: 0.011444092, explain_ms: 0, predict_ms: 44774.075746536, postprocess_ms: 0.003576279
2023-11-11 19:51:53.098 uvicorn.access INFO:     127.0.0.6:51177 9 - "POST /v1/models/sdxl%3Apredict HTTP/1.1" 200 OK
2023-11-11 19:51:53.108 kserve.trace kserve.io.kserve.protocol.rest.v1_endpoints.predict: 51.94715929031372
2023-11-11 19:51:53.108 kserve.trace kserve.io.kserve.protocol.rest.v1_endpoints.predict: 7.673258999999998
2023-11-11T19:51:53,180 [INFO ] pool-3-thread-2 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732313
2023-11-11T19:51:53,181 [INFO ] pool-3-thread-2 TS_METRICS - DiskAvailable.Gigabytes:26.51372528076172|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732313
2023-11-11T19:51:53,181 [INFO ] pool-3-thread-2 TS_METRICS - DiskUsage.Gigabytes:53.47453689575195|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732313
2023-11-11T19:51:53,181 [INFO ] pool-3-thread-2 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732313
2023-11-11T19:51:53,181 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732313
2023-11-11T19:51:53,181 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732313
2023-11-11T19:51:53,181 [INFO ] pool-3-thread-2 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732313
2023-11-11T19:51:53,182 [INFO ] pool-3-thread-2 TS_METRICS - MemoryAvailable.Megabytes:11327.953125|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732313
2023-11-11T19:51:53,182 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUsed.Megabytes:3994.43359375|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732313
2023-11-11T19:51:53,182 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUtilization.Percent:27.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732313
2023-11-11T19:52:52,911 [INFO ] pool-3-thread-2 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732372
2023-11-11T19:52:52,911 [INFO ] pool-3-thread-2 TS_METRICS - DiskAvailable.Gigabytes:26.513545989990234|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732372
2023-11-11T19:52:52,911 [INFO ] pool-3-thread-2 TS_METRICS - DiskUsage.Gigabytes:53.47471618652344|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732372
2023-11-11T19:52:52,912 [INFO ] pool-3-thread-2 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732372
2023-11-11T19:52:52,912 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732372
2023-11-11T19:52:52,912 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732372
2023-11-11T19:52:52,912 [INFO ] pool-3-thread-2 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732372
2023-11-11T19:52:52,912 [INFO ] pool-3-thread-2 TS_METRICS - MemoryAvailable.Megabytes:11325.07421875|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732372
2023-11-11T19:52:52,912 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUsed.Megabytes:3997.31640625|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732372
2023-11-11T19:52:52,912 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUtilization.Percent:27.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732372
2023-11-11T19:53:52,900 [INFO ] pool-3-thread-2 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732432
2023-11-11T19:53:52,900 [INFO ] pool-3-thread-2 TS_METRICS - DiskAvailable.Gigabytes:26.51357650756836|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732432
2023-11-11T19:53:52,900 [INFO ] pool-3-thread-2 TS_METRICS - DiskUsage.Gigabytes:53.47468566894531|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732432
2023-11-11T19:53:52,900 [INFO ] pool-3-thread-2 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732432
2023-11-11T19:53:52,900 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732432
2023-11-11T19:53:52,901 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732432
2023-11-11T19:53:52,901 [INFO ] pool-3-thread-2 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732432
2023-11-11T19:53:52,901 [INFO ] pool-3-thread-2 TS_METRICS - MemoryAvailable.Megabytes:11325.94140625|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732432
2023-11-11T19:53:52,901 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUsed.Megabytes:3996.44921875|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732432
2023-11-11T19:53:52,901 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUtilization.Percent:27.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732432
2023-11-11T19:54:48,671 [INFO ] epollEventLoopGroup-3-4 TS_METRICS - ts_inference_requests_total.Count:1.0|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732488
2023-11-11T19:54:48,672 [INFO ] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - Flushing req.cmd PREDICT to backend at: 1699732488672
2023-11-11T19:54:48,673 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - Backend received inference at: 1699732488
2023-11-11T19:54:48,673 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - received text: 'a cat playing football'
2023-11-11T19:54:48,703 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 
2023-11-11T19:54:49,414 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   0%|          | 0/50 [00:00<?, ?it/s]
2023-11-11T19:54:50,159 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   2%|▏         | 1/50 [00:00<00:34,  1.41it/s]
2023-11-11T19:54:50,900 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   4%|▍         | 2/50 [00:01<00:35,  1.37it/s]
2023-11-11T19:54:51,624 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   6%|▌         | 3/50 [00:02<00:34,  1.36it/s]
2023-11-11T19:54:52,354 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   8%|▊         | 4/50 [00:02<00:33,  1.37it/s]
2023-11-11T19:54:53,096 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  10%|█         | 5/50 [00:03<00:32,  1.37it/s]
2023-11-11T19:54:53,180 [INFO ] pool-3-thread-2 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732493
2023-11-11T19:54:53,181 [INFO ] pool-3-thread-2 TS_METRICS - DiskAvailable.Gigabytes:26.51348876953125|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732493
2023-11-11T19:54:53,181 [INFO ] pool-3-thread-2 TS_METRICS - DiskUsage.Gigabytes:53.47477340698242|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732493
2023-11-11T19:54:53,181 [INFO ] pool-3-thread-2 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732493
2023-11-11T19:54:53,182 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732493
2023-11-11T19:54:53,182 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732493
2023-11-11T19:54:53,182 [INFO ] pool-3-thread-2 TS_METRICS - GPUUtilization.Percent:100.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732493
2023-11-11T19:54:53,182 [INFO ] pool-3-thread-2 TS_METRICS - MemoryAvailable.Megabytes:11325.6796875|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732493
2023-11-11T19:54:53,183 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUsed.Megabytes:3996.7109375|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732493
2023-11-11T19:54:53,183 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUtilization.Percent:27.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732493
2023-11-11T19:54:53,834 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  12%|█▏        | 6/50 [00:04<00:32,  1.36it/s]
2023-11-11T19:54:54,568 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  14%|█▍        | 7/50 [00:05<00:31,  1.36it/s]
2023-11-11T19:54:55,308 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  16%|█▌        | 8/50 [00:05<00:30,  1.36it/s]
2023-11-11T19:54:56,049 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  18%|█▊        | 9/50 [00:06<00:30,  1.36it/s]
2023-11-11T19:54:56,788 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  20%|██        | 10/50 [00:07<00:29,  1.35it/s]
2023-11-11T19:54:57,529 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  22%|██▏       | 11/50 [00:08<00:28,  1.35it/s]
2023-11-11T19:54:58,268 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  24%|██▍       | 12/50 [00:08<00:28,  1.35it/s]
2023-11-11T19:54:59,005 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  26%|██▌       | 13/50 [00:09<00:27,  1.35it/s]
2023-11-11T19:54:59,744 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  28%|██▊       | 14/50 [00:10<00:26,  1.35it/s]
2023-11-11T19:55:00,484 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  30%|███       | 15/50 [00:11<00:25,  1.35it/s]
2023-11-11T19:55:01,224 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  32%|███▏      | 16/50 [00:11<00:25,  1.35it/s]
2023-11-11T19:55:01,969 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  34%|███▍      | 17/50 [00:12<00:24,  1.35it/s]
2023-11-11T19:55:02,710 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  36%|███▌      | 18/50 [00:13<00:23,  1.35it/s]
2023-11-11T19:55:03,451 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  38%|███▊      | 19/50 [00:14<00:22,  1.35it/s]
2023-11-11T19:55:04,199 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  40%|████      | 20/50 [00:14<00:22,  1.35it/s]
2023-11-11T19:55:04,946 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  42%|████▏     | 21/50 [00:15<00:21,  1.35it/s]
2023-11-11T19:55:05,686 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  44%|████▍     | 22/50 [00:16<00:20,  1.34it/s]
2023-11-11T19:55:06,428 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  46%|████▌     | 23/50 [00:16<00:20,  1.35it/s]
2023-11-11T19:55:07,175 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  48%|████▊     | 24/50 [00:17<00:19,  1.35it/s]
2023-11-11T19:55:07,923 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  50%|█████     | 25/50 [00:18<00:18,  1.34it/s]
2023-11-11T19:55:08,667 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  52%|█████▏    | 26/50 [00:19<00:17,  1.34it/s]
2023-11-11T19:55:09,405 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  54%|█████▍    | 27/50 [00:19<00:17,  1.34it/s]
2023-11-11T19:55:10,151 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  56%|█████▌    | 28/50 [00:20<00:16,  1.35it/s]
2023-11-11T19:55:10,897 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  58%|█████▊    | 29/50 [00:21<00:15,  1.34it/s]
2023-11-11T19:55:11,643 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  60%|██████    | 30/50 [00:22<00:14,  1.34it/s]
2023-11-11T19:55:12,389 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  62%|██████▏   | 31/50 [00:22<00:14,  1.34it/s]
2023-11-11T19:55:13,135 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  64%|██████▍   | 32/50 [00:23<00:13,  1.34it/s]
2023-11-11T19:55:13,877 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  66%|██████▌   | 33/50 [00:24<00:12,  1.34it/s]
2023-11-11T19:55:14,625 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  68%|██████▊   | 34/50 [00:25<00:11,  1.34it/s]
2023-11-11T19:55:15,379 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  70%|███████   | 35/50 [00:25<00:11,  1.34it/s]
2023-11-11T19:55:16,127 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  72%|███████▏  | 36/50 [00:26<00:10,  1.34it/s]
2023-11-11T19:55:16,874 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  74%|███████▍  | 37/50 [00:27<00:09,  1.34it/s]
2023-11-11T19:55:17,623 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  76%|███████▌  | 38/50 [00:28<00:08,  1.34it/s]
2023-11-11T19:55:18,374 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  78%|███████▊  | 39/50 [00:28<00:08,  1.34it/s]
2023-11-11T19:55:19,126 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  80%|████████  | 40/50 [00:29<00:07,  1.34it/s]
2023-11-11T19:55:19,875 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  82%|████████▏ | 41/50 [00:30<00:06,  1.33it/s]
2023-11-11T19:55:20,621 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  84%|████████▍ | 42/50 [00:31<00:05,  1.33it/s]
2023-11-11T19:55:21,372 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  86%|████████▌ | 43/50 [00:31<00:05,  1.34it/s]
2023-11-11T19:55:22,124 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  88%|████████▊ | 44/50 [00:32<00:04,  1.33it/s]
2023-11-11T19:55:22,875 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  90%|█████████ | 45/50 [00:33<00:03,  1.33it/s]
2023-11-11T19:55:23,620 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  92%|█████████▏| 46/50 [00:34<00:03,  1.33it/s]
2023-11-11T19:55:24,373 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  94%|█████████▍| 47/50 [00:34<00:02,  1.34it/s]
2023-11-11T19:55:25,124 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  96%|█████████▌| 48/50 [00:35<00:01,  1.33it/s]
2023-11-11T19:55:25,873 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  98%|█████████▊| 49/50 [00:36<00:00,  1.33it/s]
2023-11-11T19:55:25,873 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 100%|██████████| 50/50 [00:37<00:00,  1.33it/s]
2023-11-11T19:55:25,874 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 100%|██████████| 50/50 [00:37<00:00,  1.35it/s]
2023-11-11T19:55:27,610 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - generated images: [<PIL.Image.Image image mode=RGB size=1024x1024 at 0x7F7A974DC1F0>]
2023-11-11T19:55:28,218 [INFO ] W-9000-sdxl_1.0-stdout org.pytorch.serve.wlm.WorkerLifeCycle - result=[METRICS]HandlerTime.Milliseconds:39544.45|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,1699732528,faa05f2c-9c6c-453d-80e1-ff929e50c979, pattern=[METRICS]
2023-11-11T19:55:28,218 [INFO ] W-9000-sdxl_1.0-stdout MODEL_METRICS - HandlerTime.ms:39544.45|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,requestID:faa05f2c-9c6c-453d-80e1-ff929e50c979,timestamp:1699732528
2023-11-11T19:55:28,218 [INFO ] W-9000-sdxl_1.0-stdout org.pytorch.serve.wlm.WorkerLifeCycle - result=[METRICS]PredictionTime.Milliseconds:39544.66|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,1699732528,faa05f2c-9c6c-453d-80e1-ff929e50c979, pattern=[METRICS]
2023-11-11T19:55:28,218 [INFO ] W-9000-sdxl_1.0-stdout MODEL_METRICS - PredictionTime.ms:39544.66|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,requestID:faa05f2c-9c6c-453d-80e1-ff929e50c979,timestamp:1699732528
2023-11-11T19:55:32,124 [INFO ] W-9000-sdxl_1.0 ACCESS_LOG - /127.0.0.1:36928 "POST /v1/models/sdxl:predict HTTP/1.1" 200 43453
2023-11-11T19:55:32,124 [INFO ] W-9000-sdxl_1.0 TS_METRICS - Requests2XX.Count:1.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732532
2023-11-11T19:55:32,125 [INFO ] W-9000-sdxl_1.0 TS_METRICS - ts_inference_latency_microseconds.Microseconds:4.3378152679E7|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732532
2023-11-11T19:55:32,125 [INFO ] W-9000-sdxl_1.0 TS_METRICS - ts_queue_latency_microseconds.Microseconds:104.671|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732532
2023-11-11T19:55:32,125 [DEBUG] W-9000-sdxl_1.0 org.pytorch.serve.job.Job - Waiting time ns: 104671, Backend time ns: 43452726802
2023-11-11T19:55:32,125 [INFO ] W-9000-sdxl_1.0 TS_METRICS - QueueTime.Milliseconds:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732532
2023-11-11T19:55:32,125 [DEBUG] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - sent a reply, jobdone: true
2023-11-11T19:55:32,125 [INFO ] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - Backend response time: 43377
2023-11-11T19:55:32,125 [INFO ] W-9000-sdxl_1.0 TS_METRICS - WorkerThreadTime.Milliseconds:76.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732532
2023-11-11 19:55:33.016 kserve.trace requestId: 4ce7e67e-14a5-422d-907b-e7c59a208080, preprocess_ms: 0.011920929, explain_ms: 0, predict_ms: 44347.072839737, postprocess_ms: 0.003814697
2023-11-11 19:55:39.591 uvicorn.access INFO:     127.0.0.6:52053 9 - "POST /v1/models/sdxl%3Apredict HTTP/1.1" 200 OK
2023-11-11 19:55:39.598 kserve.trace kserve.io.kserve.protocol.rest.v1_endpoints.predict: 50.929931640625
2023-11-11 19:55:39.598 kserve.trace kserve.io.kserve.protocol.rest.v1_endpoints.predict: 7.438020999999999
2023-11-11T19:55:52,898 [INFO ] pool-3-thread-2 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732552
2023-11-11T19:55:52,899 [INFO ] pool-3-thread-2 TS_METRICS - DiskAvailable.Gigabytes:26.513458251953125|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732552
2023-11-11T19:55:52,899 [INFO ] pool-3-thread-2 TS_METRICS - DiskUsage.Gigabytes:53.47480392456055|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732552
2023-11-11T19:55:52,899 [INFO ] pool-3-thread-2 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732552
2023-11-11T19:55:52,899 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732552
2023-11-11T19:55:52,899 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732552
2023-11-11T19:55:52,899 [INFO ] pool-3-thread-2 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732552
2023-11-11T19:55:52,899 [INFO ] pool-3-thread-2 TS_METRICS - MemoryAvailable.Megabytes:11344.8515625|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732552
2023-11-11T19:55:52,899 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUsed.Megabytes:3977.5390625|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732552
2023-11-11T19:55:52,900 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUtilization.Percent:27.7|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732552
2023-11-11T19:56:52,896 [INFO ] pool-3-thread-2 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732612
2023-11-11T19:56:52,896 [INFO ] pool-3-thread-2 TS_METRICS - DiskAvailable.Gigabytes:26.513530731201172|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732612
2023-11-11T19:56:52,896 [INFO ] pool-3-thread-2 TS_METRICS - DiskUsage.Gigabytes:53.4747314453125|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732612
2023-11-11T19:56:52,896 [INFO ] pool-3-thread-2 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732612
2023-11-11T19:56:52,896 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732612
2023-11-11T19:56:52,897 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732612
2023-11-11T19:56:52,897 [INFO ] pool-3-thread-2 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732612
2023-11-11T19:56:52,897 [INFO ] pool-3-thread-2 TS_METRICS - MemoryAvailable.Megabytes:11342.8671875|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732612
2023-11-11T19:56:52,897 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUsed.Megabytes:3979.5234375|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732612
2023-11-11T19:56:52,897 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUtilization.Percent:27.8|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732612
2023-11-11T19:56:59,099 [INFO ] epollEventLoopGroup-3-1 TS_METRICS - ts_inference_requests_total.Count:1.0|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732619
2023-11-11T19:56:59,100 [INFO ] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - Flushing req.cmd PREDICT to backend at: 1699732619100
2023-11-11T19:56:59,101 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - Backend received inference at: 1699732619
2023-11-11T19:56:59,101 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - received text: 'a dog playing cricket'
2023-11-11T19:56:59,130 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 
2023-11-11T19:56:59,845 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   0%|          | 0/50 [00:00<?, ?it/s]
2023-11-11T19:57:00,593 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   2%|▏         | 1/50 [00:00<00:35,  1.40it/s]
2023-11-11T19:57:01,331 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   4%|▍         | 2/50 [00:01<00:35,  1.36it/s]
2023-11-11T19:57:02,066 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   6%|▌         | 3/50 [00:02<00:34,  1.36it/s]
2023-11-11T19:57:02,800 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   8%|▊         | 4/50 [00:02<00:33,  1.36it/s]
2023-11-11T19:57:03,535 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  10%|█         | 5/50 [00:03<00:33,  1.36it/s]
2023-11-11T19:57:04,279 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  12%|█▏        | 6/50 [00:04<00:32,  1.36it/s]
2023-11-11T19:57:05,012 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  14%|█▍        | 7/50 [00:05<00:31,  1.35it/s]
2023-11-11T19:57:05,755 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  16%|█▌        | 8/50 [00:05<00:30,  1.36it/s]
2023-11-11T19:57:06,489 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  18%|█▊        | 9/50 [00:06<00:30,  1.35it/s]
2023-11-11T19:57:07,228 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  20%|██        | 10/50 [00:07<00:29,  1.36it/s]
2023-11-11T19:57:07,970 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  22%|██▏       | 11/50 [00:08<00:28,  1.36it/s]
2023-11-11T19:57:08,708 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  24%|██▍       | 12/50 [00:08<00:28,  1.35it/s]
2023-11-11T19:57:09,449 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  26%|██▌       | 13/50 [00:09<00:27,  1.35it/s]
2023-11-11T19:57:10,187 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  28%|██▊       | 14/50 [00:10<00:26,  1.35it/s]
2023-11-11T19:57:10,925 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  30%|███       | 15/50 [00:11<00:25,  1.35it/s]
2023-11-11T19:57:11,671 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  32%|███▏      | 16/50 [00:11<00:25,  1.35it/s]
2023-11-11T19:57:12,415 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  34%|███▍      | 17/50 [00:12<00:24,  1.35it/s]
2023-11-11T19:57:13,156 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  36%|███▌      | 18/50 [00:13<00:23,  1.35it/s]
2023-11-11T19:57:13,905 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  38%|███▊      | 19/50 [00:14<00:22,  1.35it/s]
2023-11-11T19:57:14,644 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  40%|████      | 20/50 [00:14<00:22,  1.34it/s]
2023-11-11T19:57:15,385 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  42%|████▏     | 21/50 [00:15<00:21,  1.35it/s]
2023-11-11T19:57:16,132 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  44%|████▍     | 22/50 [00:16<00:20,  1.35it/s]
2023-11-11T19:57:16,874 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  46%|████▌     | 23/50 [00:17<00:20,  1.35it/s]
2023-11-11T19:57:17,620 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  48%|████▊     | 24/50 [00:17<00:19,  1.35it/s]
2023-11-11T19:57:18,362 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  50%|█████     | 25/50 [00:18<00:18,  1.34it/s]
2023-11-11T19:57:19,110 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  52%|█████▏    | 26/50 [00:19<00:17,  1.35it/s]
2023-11-11T19:57:19,859 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  54%|█████▍    | 27/50 [00:19<00:17,  1.34it/s]
2023-11-11T19:57:20,609 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  56%|█████▌    | 28/50 [00:20<00:16,  1.34it/s]
2023-11-11T19:57:21,356 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  58%|█████▊    | 29/50 [00:21<00:15,  1.34it/s]
2023-11-11T19:57:22,096 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  60%|██████    | 30/50 [00:22<00:14,  1.34it/s]
2023-11-11T19:57:22,837 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  62%|██████▏   | 31/50 [00:22<00:14,  1.34it/s]
2023-11-11T19:57:23,581 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  64%|██████▍   | 32/50 [00:23<00:13,  1.34it/s]
2023-11-11T19:57:24,326 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  66%|██████▌   | 33/50 [00:24<00:12,  1.34it/s]
2023-11-11T19:57:25,075 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  68%|██████▊   | 34/50 [00:25<00:11,  1.34it/s]
2023-11-11T19:57:25,826 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  70%|███████   | 35/50 [00:25<00:11,  1.34it/s]
2023-11-11T19:57:26,576 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  72%|███████▏  | 36/50 [00:26<00:10,  1.34it/s]
2023-11-11T19:57:27,324 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  74%|███████▍  | 37/50 [00:27<00:09,  1.34it/s]
2023-11-11T19:57:28,074 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  76%|███████▌  | 38/50 [00:28<00:08,  1.34it/s]
2023-11-11T19:57:28,826 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  78%|███████▊  | 39/50 [00:28<00:08,  1.34it/s]
2023-11-11T19:57:29,574 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  80%|████████  | 40/50 [00:29<00:07,  1.33it/s]
2023-11-11T19:57:30,327 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  82%|████████▏ | 41/50 [00:30<00:06,  1.33it/s]
2023-11-11T19:57:31,077 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  84%|████████▍ | 42/50 [00:31<00:06,  1.33it/s]
2023-11-11T19:57:31,828 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  86%|████████▌ | 43/50 [00:31<00:05,  1.33it/s]
2023-11-11T19:57:32,580 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  88%|████████▊ | 44/50 [00:32<00:04,  1.33it/s]
2023-11-11T19:57:33,330 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  90%|█████████ | 45/50 [00:33<00:03,  1.33it/s]
2023-11-11T19:57:34,081 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  92%|█████████▏| 46/50 [00:34<00:03,  1.33it/s]
2023-11-11T19:57:34,833 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  94%|█████████▍| 47/50 [00:34<00:02,  1.33it/s]
2023-11-11T19:57:35,581 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  96%|█████████▌| 48/50 [00:35<00:01,  1.33it/s]
2023-11-11T19:57:36,330 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  98%|█████████▊| 49/50 [00:36<00:00,  1.33it/s]
2023-11-11T19:57:36,330 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 100%|██████████| 50/50 [00:37<00:00,  1.33it/s]
2023-11-11T19:57:36,330 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 100%|██████████| 50/50 [00:37<00:00,  1.34it/s]
2023-11-11T19:57:38,070 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - generated images: [<PIL.Image.Image image mode=RGB size=1024x1024 at 0x7F7A974DC0A0>]
2023-11-11T19:57:38,829 [INFO ] W-9000-sdxl_1.0-stdout org.pytorch.serve.wlm.WorkerLifeCycle - result=[METRICS]HandlerTime.Milliseconds:39727.75|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,1699732658,47e0c03f-3f94-4903-8fb1-16954228e9cd, pattern=[METRICS]
2023-11-11T19:57:38,829 [INFO ] W-9000-sdxl_1.0-stdout MODEL_METRICS - HandlerTime.ms:39727.75|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,requestID:47e0c03f-3f94-4903-8fb1-16954228e9cd,timestamp:1699732658
2023-11-11T19:57:38,829 [INFO ] W-9000-sdxl_1.0-stdout org.pytorch.serve.wlm.WorkerLifeCycle - result=[METRICS]PredictionTime.Milliseconds:39727.97|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,1699732658,47e0c03f-3f94-4903-8fb1-16954228e9cd, pattern=[METRICS]
2023-11-11T19:57:38,829 [INFO ] W-9000-sdxl_1.0-stdout MODEL_METRICS - PredictionTime.ms:39727.97|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,requestID:47e0c03f-3f94-4903-8fb1-16954228e9cd,timestamp:1699732658
2023-11-11T19:57:42,677 [INFO ] W-9000-sdxl_1.0 ACCESS_LOG - /127.0.0.1:37958 "POST /v1/models/sdxl:predict HTTP/1.1" 200 43578
2023-11-11T19:57:42,677 [INFO ] W-9000-sdxl_1.0 TS_METRICS - Requests2XX.Count:1.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732662
2023-11-11T19:57:42,677 [INFO ] W-9000-sdxl_1.0 TS_METRICS - ts_inference_latency_microseconds.Microseconds:4.3502698731E7|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732662
2023-11-11T19:57:42,677 [INFO ] W-9000-sdxl_1.0 TS_METRICS - ts_queue_latency_microseconds.Microseconds:155.685|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732662
2023-11-11T19:57:42,677 [DEBUG] W-9000-sdxl_1.0 org.pytorch.serve.job.Job - Waiting time ns: 155685, Backend time ns: 43577573453
2023-11-11T19:57:42,677 [INFO ] W-9000-sdxl_1.0 TS_METRICS - QueueTime.Milliseconds:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732662
2023-11-11T19:57:42,677 [DEBUG] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - sent a reply, jobdone: true
2023-11-11T19:57:42,677 [INFO ] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - Backend response time: 43502
2023-11-11T19:57:42,677 [INFO ] W-9000-sdxl_1.0 TS_METRICS - WorkerThreadTime.Milliseconds:75.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732662
2023-11-11 19:57:43.799 kserve.trace requestId: 8d00fdfc-70a9-4f5e-afe2-f65ebcd72cf0, preprocess_ms: 0.012636185, explain_ms: 0, predict_ms: 44702.37493515, postprocess_ms: 0.004053116
2023-11-11 19:57:50.533 uvicorn.access INFO:     127.0.0.6:53765 9 - "POST /v1/models/sdxl%3Apredict HTTP/1.1" 200 OK
2023-11-11 19:57:50.538 kserve.trace kserve.io.kserve.protocol.rest.v1_endpoints.predict: 51.44173336029053
2023-11-11 19:57:50.538 kserve.trace kserve.io.kserve.protocol.rest.v1_endpoints.predict: 7.817875000000001
2023-11-11T19:57:52,903 [INFO ] pool-3-thread-2 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732672
2023-11-11T19:57:52,903 [INFO ] pool-3-thread-2 TS_METRICS - DiskAvailable.Gigabytes:26.51342010498047|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732672
2023-11-11T19:57:52,903 [INFO ] pool-3-thread-2 TS_METRICS - DiskUsage.Gigabytes:53.4748420715332|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732672
2023-11-11T19:57:52,903 [INFO ] pool-3-thread-2 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732672
2023-11-11T19:57:52,903 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732672
2023-11-11T19:57:52,903 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732672
2023-11-11T19:57:52,903 [INFO ] pool-3-thread-2 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732672
2023-11-11T19:57:52,904 [INFO ] pool-3-thread-2 TS_METRICS - MemoryAvailable.Megabytes:11341.0625|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732672
2023-11-11T19:57:52,904 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUsed.Megabytes:3981.328125|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732672
2023-11-11T19:57:52,904 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUtilization.Percent:27.8|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732672
2023-11-11T19:58:41,549 [INFO ] epollEventLoopGroup-3-2 TS_METRICS - ts_inference_requests_total.Count:1.0|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732721
2023-11-11T19:58:41,549 [INFO ] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - Flushing req.cmd PREDICT to backend at: 1699732721549
2023-11-11T19:58:41,550 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - Backend received inference at: 1699732721
2023-11-11T19:58:41,550 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - received text: 'a dog playing cricket'
2023-11-11T19:58:41,580 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 
2023-11-11T19:58:42,292 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   0%|          | 0/50 [00:00<?, ?it/s]
2023-11-11T19:58:43,042 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   2%|▏         | 1/50 [00:00<00:34,  1.40it/s]
2023-11-11T19:58:43,786 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   4%|▍         | 2/50 [00:01<00:35,  1.36it/s]
2023-11-11T19:58:44,521 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   6%|▌         | 3/50 [00:02<00:34,  1.35it/s]
2023-11-11T19:58:45,254 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   8%|▊         | 4/50 [00:02<00:33,  1.36it/s]
2023-11-11T19:58:45,998 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  10%|█         | 5/50 [00:03<00:33,  1.36it/s]
2023-11-11T19:58:46,735 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  12%|█▏        | 6/50 [00:04<00:32,  1.35it/s]
2023-11-11T19:58:47,465 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  14%|█▍        | 7/50 [00:05<00:31,  1.36it/s]
2023-11-11T19:58:48,201 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  16%|█▌        | 8/50 [00:05<00:30,  1.36it/s]
2023-11-11T19:58:48,942 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  18%|█▊        | 9/50 [00:06<00:30,  1.36it/s]
2023-11-11T19:58:49,681 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  20%|██        | 10/50 [00:07<00:29,  1.36it/s]
2023-11-11T19:58:50,422 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  22%|██▏       | 11/50 [00:08<00:28,  1.36it/s]
2023-11-11T19:58:51,171 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  24%|██▍       | 12/50 [00:08<00:28,  1.35it/s]
2023-11-11T19:58:51,915 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  26%|██▌       | 13/50 [00:09<00:27,  1.35it/s]
2023-11-11T19:58:52,668 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  28%|██▊       | 14/50 [00:10<00:26,  1.35it/s]
2023-11-11T19:58:53,179 [INFO ] pool-3-thread-2 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732733
2023-11-11T19:58:53,179 [INFO ] pool-3-thread-2 TS_METRICS - DiskAvailable.Gigabytes:26.513431549072266|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732733
2023-11-11T19:58:53,179 [INFO ] pool-3-thread-2 TS_METRICS - DiskUsage.Gigabytes:53.474830627441406|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732733
2023-11-11T19:58:53,179 [INFO ] pool-3-thread-2 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732733
2023-11-11T19:58:53,179 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732733
2023-11-11T19:58:53,179 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732733
2023-11-11T19:58:53,179 [INFO ] pool-3-thread-2 TS_METRICS - GPUUtilization.Percent:100.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732733
2023-11-11T19:58:53,180 [INFO ] pool-3-thread-2 TS_METRICS - MemoryAvailable.Megabytes:11346.07421875|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732733
2023-11-11T19:58:53,180 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUsed.Megabytes:3976.31640625|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732733
2023-11-11T19:58:53,180 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUtilization.Percent:27.7|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732733
2023-11-11T19:58:53,406 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  30%|███       | 15/50 [00:11<00:26,  1.34it/s]
2023-11-11T19:58:54,150 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  32%|███▏      | 16/50 [00:11<00:25,  1.35it/s]
2023-11-11T19:58:54,895 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  34%|███▍      | 17/50 [00:12<00:24,  1.35it/s]
2023-11-11T19:58:55,640 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  36%|███▌      | 18/50 [00:13<00:23,  1.34it/s]
2023-11-11T19:58:56,382 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  38%|███▊      | 19/50 [00:14<00:23,  1.34it/s]
2023-11-11T19:58:57,124 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  40%|████      | 20/50 [00:14<00:22,  1.34it/s]
2023-11-11T19:58:57,870 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  42%|████▏     | 21/50 [00:15<00:21,  1.35it/s]
2023-11-11T19:58:58,617 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  44%|████▍     | 22/50 [00:16<00:20,  1.34it/s]
2023-11-11T19:58:59,353 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  46%|████▌     | 23/50 [00:17<00:20,  1.34it/s]
2023-11-11T19:59:00,099 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  48%|████▊     | 24/50 [00:17<00:19,  1.35it/s]
2023-11-11T19:59:00,846 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  50%|█████     | 25/50 [00:18<00:18,  1.35it/s]
2023-11-11T19:59:01,596 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  52%|█████▏    | 26/50 [00:19<00:17,  1.34it/s]
2023-11-11T19:59:02,337 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  54%|█████▍    | 27/50 [00:20<00:17,  1.34it/s]
2023-11-11T19:59:03,084 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  56%|█████▌    | 28/50 [00:20<00:16,  1.34it/s]
2023-11-11T19:59:03,835 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  58%|█████▊    | 29/50 [00:21<00:15,  1.34it/s]
2023-11-11T19:59:04,580 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  60%|██████    | 30/50 [00:22<00:14,  1.34it/s]
2023-11-11T19:59:05,325 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  62%|██████▏   | 31/50 [00:22<00:14,  1.34it/s]
2023-11-11T19:59:06,074 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  64%|██████▍   | 32/50 [00:23<00:13,  1.34it/s]
2023-11-11T19:59:06,824 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  66%|██████▌   | 33/50 [00:24<00:12,  1.34it/s]
2023-11-11T19:59:07,570 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  68%|██████▊   | 34/50 [00:25<00:11,  1.34it/s]
2023-11-11T19:59:08,319 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  70%|███████   | 35/50 [00:25<00:11,  1.34it/s]
2023-11-11T19:59:09,067 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  72%|███████▏  | 36/50 [00:26<00:10,  1.34it/s]
2023-11-11T19:59:09,817 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  74%|███████▍  | 37/50 [00:27<00:09,  1.34it/s]
2023-11-11T19:59:10,568 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  76%|███████▌  | 38/50 [00:28<00:08,  1.34it/s]
2023-11-11T19:59:11,315 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  78%|███████▊  | 39/50 [00:28<00:08,  1.33it/s]
2023-11-11T19:59:12,065 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  80%|████████  | 40/50 [00:29<00:07,  1.34it/s]
2023-11-11T19:59:12,814 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  82%|████████▏ | 41/50 [00:30<00:06,  1.34it/s]
2023-11-11T19:59:13,563 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  84%|████████▍ | 42/50 [00:31<00:05,  1.34it/s]
2023-11-11T19:59:14,313 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  86%|████████▌ | 43/50 [00:31<00:05,  1.34it/s]
2023-11-11T19:59:15,063 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  88%|████████▊ | 44/50 [00:32<00:04,  1.33it/s]
2023-11-11T19:59:15,812 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  90%|█████████ | 45/50 [00:33<00:03,  1.33it/s]
2023-11-11T19:59:16,560 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  92%|█████████▏| 46/50 [00:34<00:02,  1.33it/s]
2023-11-11T19:59:17,312 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  94%|█████████▍| 47/50 [00:34<00:02,  1.34it/s]
2023-11-11T19:59:18,064 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  96%|█████████▌| 48/50 [00:35<00:01,  1.33it/s]
2023-11-11T19:59:18,815 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  98%|█████████▊| 49/50 [00:36<00:00,  1.33it/s]
2023-11-11T19:59:18,816 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 100%|██████████| 50/50 [00:37<00:00,  1.33it/s]
2023-11-11T19:59:18,816 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 100%|██████████| 50/50 [00:37<00:00,  1.34it/s]
2023-11-11T19:59:20,552 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - generated images: [<PIL.Image.Image image mode=RGB size=1024x1024 at 0x7F7A974DC160>]
2023-11-11T19:59:21,340 [INFO ] W-9000-sdxl_1.0-stdout org.pytorch.serve.wlm.WorkerLifeCycle - result=[METRICS]HandlerTime.Milliseconds:39790.05|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,1699732761,51f4566d-be14-42c6-995b-151a54c68506, pattern=[METRICS]
2023-11-11T19:59:21,341 [INFO ] W-9000-sdxl_1.0-stdout MODEL_METRICS - HandlerTime.ms:39790.05|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,requestID:51f4566d-be14-42c6-995b-151a54c68506,timestamp:1699732761
2023-11-11T19:59:21,341 [INFO ] W-9000-sdxl_1.0-stdout org.pytorch.serve.wlm.WorkerLifeCycle - result=[METRICS]PredictionTime.Milliseconds:39790.26|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,1699732761,51f4566d-be14-42c6-995b-151a54c68506, pattern=[METRICS]
2023-11-11T19:59:21,341 [INFO ] W-9000-sdxl_1.0-stdout MODEL_METRICS - PredictionTime.ms:39790.26|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,requestID:51f4566d-be14-42c6-995b-151a54c68506,timestamp:1699732761
2023-11-11T19:59:25,228 [INFO ] W-9000-sdxl_1.0 ACCESS_LOG - /127.0.0.1:37422 "POST /v1/models/sdxl:predict HTTP/1.1" 200 43679
2023-11-11T19:59:25,228 [INFO ] W-9000-sdxl_1.0 TS_METRICS - Requests2XX.Count:1.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732765
2023-11-11T19:59:25,228 [INFO ] W-9000-sdxl_1.0 TS_METRICS - ts_inference_latency_microseconds.Microseconds:4.3611416314E7|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732765
2023-11-11T19:59:25,228 [INFO ] W-9000-sdxl_1.0 TS_METRICS - ts_queue_latency_microseconds.Microseconds:105.693|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732765
2023-11-11T19:59:25,228 [DEBUG] W-9000-sdxl_1.0 org.pytorch.serve.job.Job - Waiting time ns: 105693, Backend time ns: 43678930730
2023-11-11T19:59:25,229 [INFO ] W-9000-sdxl_1.0 TS_METRICS - QueueTime.Milliseconds:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732765
2023-11-11T19:59:25,229 [DEBUG] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - sent a reply, jobdone: true
2023-11-11T19:59:25,229 [INFO ] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - Backend response time: 43611
2023-11-11T19:59:25,229 [INFO ] W-9000-sdxl_1.0 TS_METRICS - WorkerThreadTime.Milliseconds:69.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732765
2023-11-11 19:59:26.252 kserve.trace requestId: 4e232d9f-92e0-4c72-84c5-0c6dcaae69aa, preprocess_ms: 0.014066696, explain_ms: 0, predict_ms: 44705.497741699, postprocess_ms: 0.003576279
2023-11-11 19:59:32.795 uvicorn.access INFO:     127.0.0.6:54249 9 - "POST /v1/models/sdxl%3Apredict HTTP/1.1" 200 OK
2023-11-11 19:59:32.799 kserve.trace kserve.io.kserve.protocol.rest.v1_endpoints.predict: 51.25305533409119
2023-11-11 19:59:32.799 kserve.trace kserve.io.kserve.protocol.rest.v1_endpoints.predict: 7.510127000000004
2023-11-11T19:59:52,897 [INFO ] pool-3-thread-2 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732792
2023-11-11T19:59:52,897 [INFO ] pool-3-thread-2 TS_METRICS - DiskAvailable.Gigabytes:26.51340103149414|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732792
2023-11-11T19:59:52,897 [INFO ] pool-3-thread-2 TS_METRICS - DiskUsage.Gigabytes:53.47486114501953|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732792
2023-11-11T19:59:52,897 [INFO ] pool-3-thread-2 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732792
2023-11-11T19:59:52,897 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732792
2023-11-11T19:59:52,897 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732792
2023-11-11T19:59:52,898 [INFO ] pool-3-thread-2 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732792
2023-11-11T19:59:52,898 [INFO ] pool-3-thread-2 TS_METRICS - MemoryAvailable.Megabytes:11343.6796875|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732792
2023-11-11T19:59:52,898 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUsed.Megabytes:3978.7109375|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732792
2023-11-11T19:59:52,898 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUtilization.Percent:27.8|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732792
2023-11-11T20:00:18,002 [INFO ] epollEventLoopGroup-3-3 TS_METRICS - ts_inference_requests_total.Count:1.0|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732818
2023-11-11T20:00:18,002 [INFO ] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - Flushing req.cmd PREDICT to backend at: 1699732818002
2023-11-11T20:00:18,003 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - Backend received inference at: 1699732818
2023-11-11T20:00:18,003 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - received text: 'a human playing with a dog'
2023-11-11T20:00:18,033 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 
2023-11-11T20:00:18,748 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   0%|          | 0/50 [00:00<?, ?it/s]
2023-11-11T20:00:19,498 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   2%|▏         | 1/50 [00:00<00:34,  1.40it/s]
2023-11-11T20:00:20,242 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   4%|▍         | 2/50 [00:01<00:35,  1.36it/s]
2023-11-11T20:00:20,982 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   6%|▌         | 3/50 [00:02<00:34,  1.35it/s]
2023-11-11T20:00:21,713 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   8%|▊         | 4/50 [00:02<00:34,  1.35it/s]
2023-11-11T20:00:22,462 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  10%|█         | 5/50 [00:03<00:33,  1.36it/s]
2023-11-11T20:00:23,198 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  12%|█▏        | 6/50 [00:04<00:32,  1.35it/s]
2023-11-11T20:00:23,940 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  14%|█▍        | 7/50 [00:05<00:31,  1.35it/s]
2023-11-11T20:00:24,688 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  16%|█▌        | 8/50 [00:05<00:31,  1.35it/s]
2023-11-11T20:00:25,429 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  18%|█▊        | 9/50 [00:06<00:30,  1.35it/s]
2023-11-11T20:00:26,172 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  20%|██        | 10/50 [00:07<00:29,  1.35it/s]
2023-11-11T20:00:26,917 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  22%|██▏       | 11/50 [00:08<00:28,  1.35it/s]
2023-11-11T20:00:27,665 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  24%|██▍       | 12/50 [00:08<00:28,  1.35it/s]
2023-11-11T20:00:28,410 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  26%|██▌       | 13/50 [00:09<00:27,  1.34it/s]
2023-11-11T20:00:29,156 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  28%|██▊       | 14/50 [00:10<00:26,  1.34it/s]
2023-11-11T20:00:29,898 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  30%|███       | 15/50 [00:11<00:26,  1.34it/s]
2023-11-11T20:00:30,641 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  32%|███▏      | 16/50 [00:11<00:25,  1.34it/s]
2023-11-11T20:00:31,390 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  34%|███▍      | 17/50 [00:12<00:24,  1.34it/s]
2023-11-11T20:00:32,134 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  36%|███▌      | 18/50 [00:13<00:23,  1.34it/s]
2023-11-11T20:00:32,879 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  38%|███▊      | 19/50 [00:14<00:23,  1.34it/s]
2023-11-11T20:00:33,623 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  40%|████      | 20/50 [00:14<00:22,  1.34it/s]
2023-11-11T20:00:34,368 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  42%|████▏     | 21/50 [00:15<00:21,  1.34it/s]
2023-11-11T20:00:35,117 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  44%|████▍     | 22/50 [00:16<00:20,  1.34it/s]
2023-11-11T20:00:35,866 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  46%|████▌     | 23/50 [00:17<00:20,  1.34it/s]
2023-11-11T20:00:36,616 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  48%|████▊     | 24/50 [00:17<00:19,  1.34it/s]
2023-11-11T20:00:37,365 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  50%|█████     | 25/50 [00:18<00:18,  1.34it/s]
2023-11-11T20:00:38,114 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  52%|█████▏    | 26/50 [00:19<00:17,  1.34it/s]
2023-11-11T20:00:38,863 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  54%|█████▍    | 27/50 [00:20<00:17,  1.34it/s]
2023-11-11T20:00:39,611 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  56%|█████▌    | 28/50 [00:20<00:16,  1.34it/s]
2023-11-11T20:00:40,361 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  58%|█████▊    | 29/50 [00:21<00:15,  1.34it/s]
2023-11-11T20:00:41,110 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  60%|██████    | 30/50 [00:22<00:14,  1.34it/s]
2023-11-11T20:00:41,859 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  62%|██████▏   | 31/50 [00:23<00:14,  1.34it/s]
2023-11-11T20:00:42,609 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  64%|██████▍   | 32/50 [00:23<00:13,  1.34it/s]
2023-11-11T20:00:43,361 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  66%|██████▌   | 33/50 [00:24<00:12,  1.33it/s]
2023-11-11T20:00:44,109 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  68%|██████▊   | 34/50 [00:25<00:12,  1.33it/s]
2023-11-11T20:00:44,858 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  70%|███████   | 35/50 [00:26<00:11,  1.33it/s]
2023-11-11T20:00:45,608 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  72%|███████▏  | 36/50 [00:26<00:10,  1.33it/s]
2023-11-11T20:00:46,357 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  74%|███████▍  | 37/50 [00:27<00:09,  1.33it/s]
2023-11-11T20:00:47,107 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  76%|███████▌  | 38/50 [00:28<00:08,  1.33it/s]
2023-11-11T20:00:47,856 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  78%|███████▊  | 39/50 [00:29<00:08,  1.33it/s]
2023-11-11T20:00:48,607 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  80%|████████  | 40/50 [00:29<00:07,  1.33it/s]
2023-11-11T20:00:49,358 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  82%|████████▏ | 41/50 [00:30<00:06,  1.33it/s]
2023-11-11T20:00:50,108 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  84%|████████▍ | 42/50 [00:31<00:06,  1.33it/s]
2023-11-11T20:00:50,858 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  86%|████████▌ | 43/50 [00:32<00:05,  1.33it/s]
2023-11-11T20:00:51,609 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  88%|████████▊ | 44/50 [00:32<00:04,  1.33it/s]
2023-11-11T20:00:52,361 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  90%|█████████ | 45/50 [00:33<00:03,  1.33it/s]
2023-11-11T20:00:53,113 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  92%|█████████▏| 46/50 [00:34<00:03,  1.33it/s]
2023-11-11T20:00:53,180 [INFO ] pool-3-thread-2 TS_METRICS - CPUUtilization.Percent:100.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732853
2023-11-11T20:00:53,181 [INFO ] pool-3-thread-2 TS_METRICS - DiskAvailable.Gigabytes:26.513294219970703|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732853
2023-11-11T20:00:53,181 [INFO ] pool-3-thread-2 TS_METRICS - DiskUsage.Gigabytes:53.47496795654297|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732853
2023-11-11T20:00:53,181 [INFO ] pool-3-thread-2 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732853
2023-11-11T20:00:53,181 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732853
2023-11-11T20:00:53,181 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732853
2023-11-11T20:00:53,181 [INFO ] pool-3-thread-2 TS_METRICS - GPUUtilization.Percent:100.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732853
2023-11-11T20:00:53,181 [INFO ] pool-3-thread-2 TS_METRICS - MemoryAvailable.Megabytes:11342.9453125|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732853
2023-11-11T20:00:53,182 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUsed.Megabytes:3979.4453125|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732853
2023-11-11T20:00:53,182 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUtilization.Percent:27.8|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732853
2023-11-11T20:00:53,864 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  94%|█████████▍| 47/50 [00:35<00:02,  1.33it/s]
2023-11-11T20:00:54,616 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  96%|█████████▌| 48/50 [00:35<00:01,  1.33it/s]
2023-11-11T20:00:55,367 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  98%|█████████▊| 49/50 [00:36<00:00,  1.33it/s]
2023-11-11T20:00:55,368 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 100%|██████████| 50/50 [00:37<00:00,  1.33it/s]
2023-11-11T20:00:55,368 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 100%|██████████| 50/50 [00:37<00:00,  1.34it/s]
2023-11-11T20:00:57,101 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - generated images: [<PIL.Image.Image image mode=RGB size=1024x1024 at 0x7F7A974DC070>]
2023-11-11T20:00:57,880 [INFO ] W-9000-sdxl_1.0-stdout org.pytorch.serve.wlm.WorkerLifeCycle - result=[METRICS]HandlerTime.Milliseconds:39877.03|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,1699732857,f40f5a66-976a-489b-8198-8779b94e133b, pattern=[METRICS]
2023-11-11T20:00:57,880 [INFO ] W-9000-sdxl_1.0-stdout MODEL_METRICS - HandlerTime.ms:39877.03|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,requestID:f40f5a66-976a-489b-8198-8779b94e133b,timestamp:1699732857
2023-11-11T20:00:57,881 [INFO ] W-9000-sdxl_1.0-stdout org.pytorch.serve.wlm.WorkerLifeCycle - result=[METRICS]PredictionTime.Milliseconds:39877.23|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,1699732857,f40f5a66-976a-489b-8198-8779b94e133b, pattern=[METRICS]
2023-11-11T20:00:57,881 [INFO ] W-9000-sdxl_1.0-stdout MODEL_METRICS - PredictionTime.ms:39877.23|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,requestID:f40f5a66-976a-489b-8198-8779b94e133b,timestamp:1699732857
2023-11-11T20:01:01,787 [INFO ] W-9000-sdxl_1.0 ACCESS_LOG - /127.0.0.1:58232 "POST /v1/models/sdxl:predict HTTP/1.1" 200 43786
2023-11-11T20:01:01,787 [INFO ] W-9000-sdxl_1.0 TS_METRICS - Requests2XX.Count:1.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732861
2023-11-11T20:01:01,787 [INFO ] W-9000-sdxl_1.0 TS_METRICS - ts_inference_latency_microseconds.Microseconds:4.3717036259E7|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732861
2023-11-11T20:01:01,787 [INFO ] W-9000-sdxl_1.0 TS_METRICS - ts_queue_latency_microseconds.Microseconds:117.908|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732861
2023-11-11T20:01:01,788 [DEBUG] W-9000-sdxl_1.0 org.pytorch.serve.job.Job - Waiting time ns: 117908, Backend time ns: 43785534337
2023-11-11T20:01:01,788 [INFO ] W-9000-sdxl_1.0 TS_METRICS - QueueTime.Milliseconds:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732861
2023-11-11T20:01:01,788 [DEBUG] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - sent a reply, jobdone: true
2023-11-11T20:01:01,788 [INFO ] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - Backend response time: 43717
2023-11-11T20:01:01,788 [INFO ] W-9000-sdxl_1.0 TS_METRICS - WorkerThreadTime.Milliseconds:69.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732861
2023-11-11 20:01:02.975 kserve.trace requestId: 9be4a38c-0ba4-423a-955f-c26e75760e85, preprocess_ms: 0.011920929, explain_ms: 0, predict_ms: 44975.811243057, postprocess_ms: 0.00333786
2023-11-11 20:01:09.602 kserve.trace kserve.io.kserve.protocol.rest.v1_endpoints.predict: 51.603137731552124
2023-11-11 20:01:09.602 kserve.trace kserve.io.kserve.protocol.rest.v1_endpoints.predict: 7.785711999999997
2023-11-11T20:01:52,911 [INFO ] pool-3-thread-2 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732912
2023-11-11T20:01:52,911 [INFO ] pool-3-thread-2 TS_METRICS - DiskAvailable.Gigabytes:26.513351440429688|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732912
2023-11-11T20:01:52,911 [INFO ] pool-3-thread-2 TS_METRICS - DiskUsage.Gigabytes:53.474910736083984|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732912
2023-11-11T20:01:52,911 [INFO ] pool-3-thread-2 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732912
2023-11-11T20:01:52,912 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732912
2023-11-11T20:01:52,912 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732912
2023-11-11T20:01:52,912 [INFO ] pool-3-thread-2 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732912
2023-11-11T20:01:52,912 [INFO ] pool-3-thread-2 TS_METRICS - MemoryAvailable.Megabytes:11345.8125|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732912
2023-11-11T20:01:52,912 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUsed.Megabytes:3976.578125|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732912
2023-11-11T20:01:52,912 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUtilization.Percent:27.7|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732912
2023-11-11T20:02:52,903 [INFO ] pool-3-thread-2 TS_METRICS - CPUUtilization.Percent:100.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732972
2023-11-11T20:02:52,903 [INFO ] pool-3-thread-2 TS_METRICS - DiskAvailable.Gigabytes:26.513145446777344|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732972
2023-11-11T20:02:52,903 [INFO ] pool-3-thread-2 TS_METRICS - DiskUsage.Gigabytes:53.47511672973633|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732972
2023-11-11T20:02:52,903 [INFO ] pool-3-thread-2 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732972
2023-11-11T20:02:52,903 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732972
2023-11-11T20:02:52,903 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732972
2023-11-11T20:02:52,903 [INFO ] pool-3-thread-2 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732972
2023-11-11T20:02:52,904 [INFO ] pool-3-thread-2 TS_METRICS - MemoryAvailable.Megabytes:11341.92578125|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732972
2023-11-11T20:02:52,904 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUsed.Megabytes:3980.46484375|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732972
2023-11-11T20:02:52,904 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUtilization.Percent:27.8|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699732972
2023-11-11T20:03:36,510 [INFO ] epollEventLoopGroup-3-4 TS_METRICS - ts_inference_requests_total.Count:1.0|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733016
2023-11-11T20:03:36,511 [INFO ] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - Flushing req.cmd PREDICT to backend at: 1699733016511
2023-11-11T20:03:36,511 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - Backend received inference at: 1699733016
2023-11-11T20:03:36,511 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - received text: 'a human playing cricket'
2023-11-11T20:03:36,541 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 
2023-11-11T20:03:37,255 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   0%|          | 0/50 [00:00<?, ?it/s]
2023-11-11T20:03:37,998 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   2%|▏         | 1/50 [00:00<00:34,  1.40it/s]
2023-11-11T20:03:38,742 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   4%|▍         | 2/50 [00:01<00:35,  1.37it/s]
2023-11-11T20:03:39,473 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   6%|▌         | 3/50 [00:02<00:34,  1.36it/s]
2023-11-11T20:03:40,208 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   8%|▊         | 4/50 [00:02<00:33,  1.36it/s]
2023-11-11T20:03:40,950 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  10%|█         | 5/50 [00:03<00:33,  1.36it/s]
2023-11-11T20:03:41,691 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  12%|█▏        | 6/50 [00:04<00:32,  1.36it/s]
2023-11-11T20:03:42,422 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  14%|█▍        | 7/50 [00:05<00:31,  1.35it/s]
2023-11-11T20:03:43,159 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  16%|█▌        | 8/50 [00:05<00:30,  1.36it/s]
2023-11-11T20:03:43,901 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  18%|█▊        | 9/50 [00:06<00:30,  1.36it/s]
2023-11-11T20:03:44,640 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  20%|██        | 10/50 [00:07<00:29,  1.36it/s]
2023-11-11T20:03:45,377 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  22%|██▏       | 11/50 [00:08<00:28,  1.35it/s]
2023-11-11T20:03:46,122 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  24%|██▍       | 12/50 [00:08<00:28,  1.36it/s]
2023-11-11T20:03:46,858 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  26%|██▌       | 13/50 [00:09<00:27,  1.35it/s]
2023-11-11T20:03:47,595 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  28%|██▊       | 14/50 [00:10<00:26,  1.35it/s]
2023-11-11T20:03:48,335 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  30%|███       | 15/50 [00:11<00:25,  1.35it/s]
2023-11-11T20:03:49,081 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  32%|███▏      | 16/50 [00:11<00:25,  1.35it/s]
2023-11-11T20:03:49,825 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  34%|███▍      | 17/50 [00:12<00:24,  1.35it/s]
2023-11-11T20:03:50,572 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  36%|███▌      | 18/50 [00:13<00:23,  1.35it/s]
2023-11-11T20:03:51,315 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  38%|███▊      | 19/50 [00:14<00:23,  1.35it/s]
2023-11-11T20:03:52,060 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  40%|████      | 20/50 [00:14<00:22,  1.35it/s]
2023-11-11T20:03:52,806 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  42%|████▏     | 21/50 [00:15<00:21,  1.34it/s]
2023-11-11T20:03:53,276 [INFO ] pool-3-thread-2 TS_METRICS - CPUUtilization.Percent:100.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733033
2023-11-11T20:03:53,277 [INFO ] pool-3-thread-2 TS_METRICS - DiskAvailable.Gigabytes:26.512847900390625|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733033
2023-11-11T20:03:53,277 [INFO ] pool-3-thread-2 TS_METRICS - DiskUsage.Gigabytes:53.47541427612305|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733033
2023-11-11T20:03:53,277 [INFO ] pool-3-thread-2 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733033
2023-11-11T20:03:53,277 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733033
2023-11-11T20:03:53,277 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733033
2023-11-11T20:03:53,277 [INFO ] pool-3-thread-2 TS_METRICS - GPUUtilization.Percent:100.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733033
2023-11-11T20:03:53,278 [INFO ] pool-3-thread-2 TS_METRICS - MemoryAvailable.Megabytes:11339.40234375|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733033
2023-11-11T20:03:53,278 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUsed.Megabytes:3982.98828125|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733033
2023-11-11T20:03:53,278 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUtilization.Percent:27.8|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733033
2023-11-11T20:03:53,554 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  44%|████▍     | 22/50 [00:16<00:20,  1.34it/s]
2023-11-11T20:03:54,299 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  46%|████▌     | 23/50 [00:17<00:20,  1.34it/s]
2023-11-11T20:03:55,042 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  48%|████▊     | 24/50 [00:17<00:19,  1.34it/s]
2023-11-11T20:03:55,789 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  50%|█████     | 25/50 [00:18<00:18,  1.34it/s]
2023-11-11T20:03:56,538 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  52%|█████▏    | 26/50 [00:19<00:17,  1.34it/s]
2023-11-11T20:03:57,280 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  54%|█████▍    | 27/50 [00:19<00:17,  1.34it/s]
2023-11-11T20:03:58,034 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  56%|█████▌    | 28/50 [00:20<00:16,  1.34it/s]
2023-11-11T20:03:58,783 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  58%|█████▊    | 29/50 [00:21<00:15,  1.34it/s]
2023-11-11T20:03:59,531 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  60%|██████    | 30/50 [00:22<00:14,  1.34it/s]
2023-11-11T20:04:00,281 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  62%|██████▏   | 31/50 [00:22<00:14,  1.34it/s]
2023-11-11T20:04:01,033 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  64%|██████▍   | 32/50 [00:23<00:13,  1.34it/s]
2023-11-11T20:04:01,780 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  66%|██████▌   | 33/50 [00:24<00:12,  1.33it/s]
2023-11-11T20:04:02,528 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  68%|██████▊   | 34/50 [00:25<00:11,  1.34it/s]
2023-11-11T20:04:03,282 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  70%|███████   | 35/50 [00:25<00:11,  1.34it/s]
2023-11-11T20:04:04,030 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  72%|███████▏  | 36/50 [00:26<00:10,  1.33it/s]
2023-11-11T20:04:04,782 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  74%|███████▍  | 37/50 [00:27<00:09,  1.33it/s]
2023-11-11T20:04:05,532 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  76%|███████▌  | 38/50 [00:28<00:09,  1.33it/s]
2023-11-11T20:04:06,282 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  78%|███████▊  | 39/50 [00:28<00:08,  1.33it/s]
2023-11-11T20:04:07,031 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  80%|████████  | 40/50 [00:29<00:07,  1.33it/s]
2023-11-11T20:04:07,781 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  82%|████████▏ | 41/50 [00:30<00:06,  1.33it/s]
2023-11-11T20:04:08,530 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  84%|████████▍ | 42/50 [00:31<00:05,  1.33it/s]
2023-11-11T20:04:09,280 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  86%|████████▌ | 43/50 [00:31<00:05,  1.33it/s]
2023-11-11T20:04:10,029 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  88%|████████▊ | 44/50 [00:32<00:04,  1.33it/s]
2023-11-11T20:04:10,781 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  90%|█████████ | 45/50 [00:33<00:03,  1.33it/s]
2023-11-11T20:04:11,531 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  92%|█████████▏| 46/50 [00:34<00:03,  1.33it/s]
2023-11-11T20:04:12,282 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  94%|█████████▍| 47/50 [00:34<00:02,  1.33it/s]
2023-11-11T20:04:13,033 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  96%|█████████▌| 48/50 [00:35<00:01,  1.33it/s]
2023-11-11T20:04:13,783 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  98%|█████████▊| 49/50 [00:36<00:00,  1.33it/s]
2023-11-11T20:04:13,783 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 100%|██████████| 50/50 [00:37<00:00,  1.33it/s]
2023-11-11T20:04:13,783 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 100%|██████████| 50/50 [00:37<00:00,  1.34it/s]
2023-11-11T20:04:15,521 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - generated images: [<PIL.Image.Image image mode=RGB size=1024x1024 at 0x7F7A974DC130>]
2023-11-11T20:04:16,260 [INFO ] W-9000-sdxl_1.0-stdout org.pytorch.serve.wlm.WorkerLifeCycle - result=[METRICS]HandlerTime.Milliseconds:39748.56|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,1699733056,7048741b-b13b-4a7d-9639-bdf595a979b1, pattern=[METRICS]
2023-11-11T20:04:16,260 [INFO ] W-9000-sdxl_1.0-stdout MODEL_METRICS - HandlerTime.ms:39748.56|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,requestID:7048741b-b13b-4a7d-9639-bdf595a979b1,timestamp:1699733056
2023-11-11T20:04:16,260 [INFO ] W-9000-sdxl_1.0-stdout org.pytorch.serve.wlm.WorkerLifeCycle - result=[METRICS]PredictionTime.Milliseconds:39748.76|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,1699733056,7048741b-b13b-4a7d-9639-bdf595a979b1, pattern=[METRICS]
2023-11-11T20:04:16,261 [INFO ] W-9000-sdxl_1.0-stdout MODEL_METRICS - PredictionTime.ms:39748.76|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,requestID:7048741b-b13b-4a7d-9639-bdf595a979b1,timestamp:1699733056
2023-11-11T20:04:20,122 [INFO ] W-9000-sdxl_1.0 ACCESS_LOG - /127.0.0.1:58896 "POST /v1/models/sdxl:predict HTTP/1.1" 200 43612
2023-11-11T20:04:20,122 [INFO ] W-9000-sdxl_1.0 TS_METRICS - Requests2XX.Count:1.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733060
2023-11-11T20:04:20,122 [INFO ] W-9000-sdxl_1.0 TS_METRICS - ts_inference_latency_microseconds.Microseconds:4.3540184993E7|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733060
2023-11-11T20:04:20,122 [INFO ] W-9000-sdxl_1.0 TS_METRICS - ts_queue_latency_microseconds.Microseconds:106.749|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733060
2023-11-11T20:04:20,122 [DEBUG] W-9000-sdxl_1.0 org.pytorch.serve.job.Job - Waiting time ns: 106749, Backend time ns: 43611524661
2023-11-11T20:04:20,122 [INFO ] W-9000-sdxl_1.0 TS_METRICS - QueueTime.Milliseconds:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733060
2023-11-11T20:04:20,122 [DEBUG] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - sent a reply, jobdone: true
2023-11-11T20:04:20,122 [INFO ] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - Backend response time: 43540
2023-11-11T20:04:20,123 [INFO ] W-9000-sdxl_1.0 TS_METRICS - WorkerThreadTime.Milliseconds:71.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733060
2023-11-11 20:04:21.253 kserve.trace requestId: 5b733832-123b-40fa-9745-2ee9abd2277b, preprocess_ms: 0.012397766, explain_ms: 0, predict_ms: 44744.829893112, postprocess_ms: 0.003814697
2023-11-11 20:04:28.014 uvicorn.access INFO:     127.0.0.6:48435 9 - "POST /v1/models/sdxl%3Apredict HTTP/1.1" 200 OK
2023-11-11 20:04:28.023 kserve.trace kserve.io.kserve.protocol.rest.v1_endpoints.predict: 51.51529002189636
2023-11-11 20:04:28.023 kserve.trace kserve.io.kserve.protocol.rest.v1_endpoints.predict: 7.862312999999993
2023-11-11T20:04:52,899 [INFO ] pool-3-thread-2 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733092
2023-11-11T20:04:52,900 [INFO ] pool-3-thread-2 TS_METRICS - DiskAvailable.Gigabytes:26.512760162353516|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733092
2023-11-11T20:04:52,900 [INFO ] pool-3-thread-2 TS_METRICS - DiskUsage.Gigabytes:53.475502014160156|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733092
2023-11-11T20:04:52,900 [INFO ] pool-3-thread-2 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733092
2023-11-11T20:04:52,900 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733092
2023-11-11T20:04:52,900 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733092
2023-11-11T20:04:52,900 [INFO ] pool-3-thread-2 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733092
2023-11-11T20:04:52,900 [INFO ] pool-3-thread-2 TS_METRICS - MemoryAvailable.Megabytes:11341.7890625|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733092
2023-11-11T20:04:52,900 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUsed.Megabytes:3980.6015625|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733092
2023-11-11T20:04:52,900 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUtilization.Percent:27.8|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733092
2023-11-11T20:05:52,869 [INFO ] pool-3-thread-1 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733152
2023-11-11T20:05:52,870 [INFO ] pool-3-thread-1 TS_METRICS - DiskAvailable.Gigabytes:26.51268768310547|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733152
2023-11-11T20:05:52,870 [INFO ] pool-3-thread-1 TS_METRICS - DiskUsage.Gigabytes:53.4755744934082|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733152
2023-11-11T20:05:52,870 [INFO ] pool-3-thread-1 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733152
2023-11-11T20:05:52,870 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733152
2023-11-11T20:05:52,870 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733152
2023-11-11T20:05:52,870 [INFO ] pool-3-thread-1 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733152
2023-11-11T20:05:52,870 [INFO ] pool-3-thread-1 TS_METRICS - MemoryAvailable.Megabytes:11341.8828125|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733152
2023-11-11T20:05:52,870 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUsed.Megabytes:3980.5078125|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733152
2023-11-11T20:05:52,870 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUtilization.Percent:27.8|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733152
2023-11-11T20:06:52,893 [INFO ] pool-3-thread-1 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733212
2023-11-11T20:06:52,893 [INFO ] pool-3-thread-1 TS_METRICS - DiskAvailable.Gigabytes:26.512920379638672|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733212
2023-11-11T20:06:52,893 [INFO ] pool-3-thread-1 TS_METRICS - DiskUsage.Gigabytes:53.475341796875|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733212
2023-11-11T20:06:52,893 [INFO ] pool-3-thread-1 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733212
2023-11-11T20:06:52,893 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733212
2023-11-11T20:06:52,893 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733212
2023-11-11T20:06:52,893 [INFO ] pool-3-thread-1 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733212
2023-11-11T20:06:52,893 [INFO ] pool-3-thread-1 TS_METRICS - MemoryAvailable.Megabytes:11340.703125|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733212
2023-11-11T20:06:52,894 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUsed.Megabytes:3981.6875|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733212
2023-11-11T20:06:52,894 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUtilization.Percent:27.8|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733212
2023-11-11T20:07:52,905 [INFO ] pool-3-thread-1 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733272
2023-11-11T20:07:52,905 [INFO ] pool-3-thread-1 TS_METRICS - DiskAvailable.Gigabytes:26.512462615966797|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733272
2023-11-11T20:07:52,905 [INFO ] pool-3-thread-1 TS_METRICS - DiskUsage.Gigabytes:53.475799560546875|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733272
2023-11-11T20:07:52,905 [INFO ] pool-3-thread-1 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733272
2023-11-11T20:07:52,905 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733272
2023-11-11T20:07:52,905 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733272
2023-11-11T20:07:52,906 [INFO ] pool-3-thread-1 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733272
2023-11-11T20:07:52,906 [INFO ] pool-3-thread-1 TS_METRICS - MemoryAvailable.Megabytes:11338.671875|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733272
2023-11-11T20:07:52,906 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUsed.Megabytes:3983.71875|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733272
2023-11-11T20:07:52,906 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUtilization.Percent:27.8|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733272
2023-11-11T20:08:52,897 [INFO ] pool-3-thread-1 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733332
2023-11-11T20:08:52,897 [INFO ] pool-3-thread-1 TS_METRICS - DiskAvailable.Gigabytes:26.51220703125|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733332
2023-11-11T20:08:52,897 [INFO ] pool-3-thread-1 TS_METRICS - DiskUsage.Gigabytes:53.47605514526367|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733332
2023-11-11T20:08:52,898 [INFO ] pool-3-thread-1 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733332
2023-11-11T20:08:52,898 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733332
2023-11-11T20:08:52,898 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733332
2023-11-11T20:08:52,898 [INFO ] pool-3-thread-1 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733332
2023-11-11T20:08:52,898 [INFO ] pool-3-thread-1 TS_METRICS - MemoryAvailable.Megabytes:11338.37109375|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733332
2023-11-11T20:08:52,898 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUsed.Megabytes:3984.01953125|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733332
2023-11-11T20:08:52,898 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUtilization.Percent:27.8|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733332
2023-11-11T20:09:52,902 [INFO ] pool-3-thread-1 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733392
2023-11-11T20:09:52,903 [INFO ] pool-3-thread-1 TS_METRICS - DiskAvailable.Gigabytes:26.51218032836914|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733392
2023-11-11T20:09:52,903 [INFO ] pool-3-thread-1 TS_METRICS - DiskUsage.Gigabytes:53.47608184814453|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733392
2023-11-11T20:09:52,903 [INFO ] pool-3-thread-1 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733392
2023-11-11T20:09:52,903 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733392
2023-11-11T20:09:52,903 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733392
2023-11-11T20:09:52,903 [INFO ] pool-3-thread-1 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733392
2023-11-11T20:09:52,903 [INFO ] pool-3-thread-1 TS_METRICS - MemoryAvailable.Megabytes:11336.02734375|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733392
2023-11-11T20:09:52,903 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUsed.Megabytes:3986.36328125|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733392
2023-11-11T20:09:52,903 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUtilization.Percent:27.8|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733392
2023-11-11T20:10:52,899 [INFO ] pool-3-thread-1 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733452
2023-11-11T20:10:52,899 [INFO ] pool-3-thread-1 TS_METRICS - DiskAvailable.Gigabytes:26.5120849609375|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733452
2023-11-11T20:10:52,899 [INFO ] pool-3-thread-1 TS_METRICS - DiskUsage.Gigabytes:53.47617721557617|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733452
2023-11-11T20:10:52,899 [INFO ] pool-3-thread-1 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733452
2023-11-11T20:10:52,899 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733452
2023-11-11T20:10:52,899 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733452
2023-11-11T20:10:52,899 [INFO ] pool-3-thread-1 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733452
2023-11-11T20:10:52,899 [INFO ] pool-3-thread-1 TS_METRICS - MemoryAvailable.Megabytes:11334.73046875|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733452
2023-11-11T20:10:52,900 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUsed.Megabytes:3987.66015625|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733452
2023-11-11T20:10:52,900 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUtilization.Percent:27.8|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733452
2023-11-11T20:11:52,900 [INFO ] pool-3-thread-1 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733512
2023-11-11T20:11:52,900 [INFO ] pool-3-thread-1 TS_METRICS - DiskAvailable.Gigabytes:26.51211929321289|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733512
2023-11-11T20:11:52,900 [INFO ] pool-3-thread-1 TS_METRICS - DiskUsage.Gigabytes:53.47614288330078|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733512
2023-11-11T20:11:52,900 [INFO ] pool-3-thread-1 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733512
2023-11-11T20:11:52,900 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733512
2023-11-11T20:11:52,901 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733512
2023-11-11T20:11:52,901 [INFO ] pool-3-thread-1 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733512
2023-11-11T20:11:52,901 [INFO ] pool-3-thread-1 TS_METRICS - MemoryAvailable.Megabytes:11337.26953125|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733512
2023-11-11T20:11:52,901 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUsed.Megabytes:3985.12109375|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733512
2023-11-11T20:11:52,901 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUtilization.Percent:27.8|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733512
2023-11-11T20:12:52,905 [INFO ] pool-3-thread-1 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733572
2023-11-11T20:12:52,905 [INFO ] pool-3-thread-1 TS_METRICS - DiskAvailable.Gigabytes:26.512451171875|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733572
2023-11-11T20:12:52,905 [INFO ] pool-3-thread-1 TS_METRICS - DiskUsage.Gigabytes:53.47581100463867|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733572
2023-11-11T20:12:52,906 [INFO ] pool-3-thread-1 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733572
2023-11-11T20:12:52,906 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733572
2023-11-11T20:12:52,906 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733572
2023-11-11T20:12:52,906 [INFO ] pool-3-thread-1 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733572
2023-11-11T20:12:52,906 [INFO ] pool-3-thread-1 TS_METRICS - MemoryAvailable.Megabytes:11337.8125|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733572
2023-11-11T20:12:52,906 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUsed.Megabytes:3984.578125|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733572
2023-11-11T20:12:52,906 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUtilization.Percent:27.8|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733572
2023-11-11T20:13:52,892 [INFO ] pool-3-thread-1 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733632
2023-11-11T20:13:52,892 [INFO ] pool-3-thread-1 TS_METRICS - DiskAvailable.Gigabytes:26.51211166381836|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733632
2023-11-11T20:13:52,893 [INFO ] pool-3-thread-1 TS_METRICS - DiskUsage.Gigabytes:53.47615051269531|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733632
2023-11-11T20:13:52,893 [INFO ] pool-3-thread-1 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733632
2023-11-11T20:13:52,893 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733632
2023-11-11T20:13:52,893 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733632
2023-11-11T20:13:52,893 [INFO ] pool-3-thread-1 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733632
2023-11-11T20:13:52,893 [INFO ] pool-3-thread-1 TS_METRICS - MemoryAvailable.Megabytes:11339.21484375|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733632
2023-11-11T20:13:52,893 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUsed.Megabytes:3983.171875|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733632
2023-11-11T20:13:52,893 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUtilization.Percent:27.8|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733632
2023-11-11T20:14:52,913 [INFO ] pool-3-thread-1 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733692
2023-11-11T20:14:52,914 [INFO ] pool-3-thread-1 TS_METRICS - DiskAvailable.Gigabytes:26.512115478515625|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733692
2023-11-11T20:14:52,914 [INFO ] pool-3-thread-1 TS_METRICS - DiskUsage.Gigabytes:53.47614669799805|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733692
2023-11-11T20:14:52,914 [INFO ] pool-3-thread-1 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733692
2023-11-11T20:14:52,914 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733692
2023-11-11T20:14:52,914 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733692
2023-11-11T20:14:52,914 [INFO ] pool-3-thread-1 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733692
2023-11-11T20:14:52,914 [INFO ] pool-3-thread-1 TS_METRICS - MemoryAvailable.Megabytes:11336.82421875|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733692
2023-11-11T20:14:52,914 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUsed.Megabytes:3985.56640625|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733692
2023-11-11T20:14:52,914 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUtilization.Percent:27.8|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733692
2023-11-11T20:15:39,447 [INFO ] epollEventLoopGroup-3-1 TS_METRICS - ts_inference_requests_total.Count:1.0|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733739
2023-11-11T20:15:39,448 [INFO ] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - Flushing req.cmd PREDICT to backend at: 1699733739448
2023-11-11T20:15:39,449 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - Backend received inference at: 1699733739
2023-11-11T20:15:39,449 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - received text: 'a human playing cricket'
2023-11-11T20:15:39,478 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 
2023-11-11T20:15:40,186 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   0%|          | 0/50 [00:00<?, ?it/s]
2023-11-11T20:15:40,929 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   2%|▏         | 1/50 [00:00<00:34,  1.41it/s]
2023-11-11T20:15:41,666 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   4%|▍         | 2/50 [00:01<00:34,  1.37it/s]
2023-11-11T20:15:42,396 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   6%|▌         | 3/50 [00:02<00:34,  1.37it/s]
2023-11-11T20:15:43,131 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   8%|▊         | 4/50 [00:02<00:33,  1.37it/s]
2023-11-11T20:15:43,866 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  10%|█         | 5/50 [00:03<00:32,  1.36it/s]
2023-11-11T20:15:44,605 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  12%|█▏        | 6/50 [00:04<00:32,  1.36it/s]
2023-11-11T20:15:45,345 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  14%|█▍        | 7/50 [00:05<00:31,  1.36it/s]
2023-11-11T20:15:46,081 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  16%|█▌        | 8/50 [00:05<00:30,  1.36it/s]
2023-11-11T20:15:46,824 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  18%|█▊        | 9/50 [00:06<00:30,  1.36it/s]
2023-11-11T20:15:47,559 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  20%|██        | 10/50 [00:07<00:29,  1.35it/s]
2023-11-11T20:15:48,302 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  22%|██▏       | 11/50 [00:08<00:28,  1.36it/s]
2023-11-11T20:15:49,033 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  24%|██▍       | 12/50 [00:08<00:28,  1.35it/s]
2023-11-11T20:15:49,781 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  26%|██▌       | 13/50 [00:09<00:27,  1.36it/s]
2023-11-11T20:15:50,520 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  28%|██▊       | 14/50 [00:10<00:26,  1.35it/s]
2023-11-11T20:15:51,261 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  30%|███       | 15/50 [00:11<00:25,  1.35it/s]
2023-11-11T20:15:52,005 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  32%|███▏      | 16/50 [00:11<00:25,  1.35it/s]
2023-11-11T20:15:52,768 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  34%|███▍      | 17/50 [00:12<00:24,  1.35it/s]
2023-11-11T20:15:53,179 [INFO ] pool-3-thread-1 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733753
2023-11-11T20:15:53,179 [INFO ] pool-3-thread-1 TS_METRICS - DiskAvailable.Gigabytes:26.5120849609375|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733753
2023-11-11T20:15:53,179 [INFO ] pool-3-thread-1 TS_METRICS - DiskUsage.Gigabytes:53.47617721557617|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733753
2023-11-11T20:15:53,179 [INFO ] pool-3-thread-1 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733753
2023-11-11T20:15:53,179 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733753
2023-11-11T20:15:53,179 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733753
2023-11-11T20:15:53,179 [INFO ] pool-3-thread-1 TS_METRICS - GPUUtilization.Percent:100.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733753
2023-11-11T20:15:53,179 [INFO ] pool-3-thread-1 TS_METRICS - MemoryAvailable.Megabytes:11332.87109375|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733753
2023-11-11T20:15:53,180 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUsed.Megabytes:3989.51953125|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733753
2023-11-11T20:15:53,182 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUtilization.Percent:27.8|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733753
2023-11-11T20:15:53,505 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  36%|███▌      | 18/50 [00:13<00:23,  1.34it/s]
2023-11-11T20:15:54,245 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  38%|███▊      | 19/50 [00:14<00:23,  1.34it/s]
2023-11-11T20:15:54,990 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  40%|████      | 20/50 [00:14<00:22,  1.35it/s]
2023-11-11T20:15:55,734 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  42%|████▏     | 21/50 [00:15<00:21,  1.34it/s]
2023-11-11T20:15:56,473 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  44%|████▍     | 22/50 [00:16<00:20,  1.34it/s]
2023-11-11T20:15:57,219 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  46%|████▌     | 23/50 [00:16<00:20,  1.35it/s]
2023-11-11T20:15:57,965 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  48%|████▊     | 24/50 [00:17<00:19,  1.35it/s]
2023-11-11T20:15:58,713 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  50%|█████     | 25/50 [00:18<00:18,  1.34it/s]
2023-11-11T20:15:59,456 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  52%|█████▏    | 26/50 [00:19<00:17,  1.34it/s]
2023-11-11T20:16:00,198 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  54%|█████▍    | 27/50 [00:19<00:17,  1.34it/s]
2023-11-11T20:16:00,946 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  56%|█████▌    | 28/50 [00:20<00:16,  1.34it/s]
2023-11-11T20:16:01,692 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  58%|█████▊    | 29/50 [00:21<00:15,  1.34it/s]
2023-11-11T20:16:02,439 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  60%|██████    | 30/50 [00:22<00:14,  1.34it/s]
2023-11-11T20:16:03,187 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  62%|██████▏   | 31/50 [00:22<00:14,  1.34it/s]
2023-11-11T20:16:03,934 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  64%|██████▍   | 32/50 [00:23<00:13,  1.34it/s]
2023-11-11T20:16:04,683 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  66%|██████▌   | 33/50 [00:24<00:12,  1.34it/s]
2023-11-11T20:16:05,429 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  68%|██████▊   | 34/50 [00:25<00:11,  1.34it/s]
2023-11-11T20:16:06,179 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  70%|███████   | 35/50 [00:25<00:11,  1.34it/s]
2023-11-11T20:16:06,929 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  72%|███████▏  | 36/50 [00:26<00:10,  1.34it/s]
2023-11-11T20:16:07,677 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  74%|███████▍  | 37/50 [00:27<00:09,  1.34it/s]
2023-11-11T20:16:08,425 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  76%|███████▌  | 38/50 [00:28<00:08,  1.34it/s]
2023-11-11T20:16:09,177 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  78%|███████▊  | 39/50 [00:28<00:08,  1.34it/s]
2023-11-11T20:16:09,928 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  80%|████████  | 40/50 [00:29<00:07,  1.33it/s]
2023-11-11T20:16:10,680 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  82%|████████▏ | 41/50 [00:30<00:06,  1.33it/s]
2023-11-11T20:16:11,428 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  84%|████████▍ | 42/50 [00:31<00:06,  1.33it/s]
2023-11-11T20:16:12,174 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  86%|████████▌ | 43/50 [00:31<00:05,  1.33it/s]
2023-11-11T20:16:12,927 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  88%|████████▊ | 44/50 [00:32<00:04,  1.34it/s]
2023-11-11T20:16:13,675 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  90%|█████████ | 45/50 [00:33<00:03,  1.33it/s]
2023-11-11T20:16:14,425 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  92%|█████████▏| 46/50 [00:34<00:02,  1.33it/s]
2023-11-11T20:16:15,174 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  94%|█████████▍| 47/50 [00:34<00:02,  1.33it/s]
2023-11-11T20:16:15,926 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  96%|█████████▌| 48/50 [00:35<00:01,  1.33it/s]
2023-11-11T20:16:16,675 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  98%|█████████▊| 49/50 [00:36<00:00,  1.33it/s]
2023-11-11T20:16:16,675 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 100%|██████████| 50/50 [00:37<00:00,  1.33it/s]
2023-11-11T20:16:16,675 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 100%|██████████| 50/50 [00:37<00:00,  1.34it/s]
2023-11-11T20:16:18,419 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - generated images: [<PIL.Image.Image image mode=RGB size=1024x1024 at 0x7F7A974DC160>]
2023-11-11T20:16:19,026 [INFO ] W-9000-sdxl_1.0-stdout org.pytorch.serve.wlm.WorkerLifeCycle - result=[METRICS]HandlerTime.Milliseconds:39577.38|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,1699733779,c5b24dcd-911a-4db0-be1e-2a7c4eedbab7, pattern=[METRICS]
2023-11-11T20:16:19,026 [INFO ] W-9000-sdxl_1.0-stdout MODEL_METRICS - HandlerTime.ms:39577.38|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,requestID:c5b24dcd-911a-4db0-be1e-2a7c4eedbab7,timestamp:1699733779
2023-11-11T20:16:19,027 [INFO ] W-9000-sdxl_1.0-stdout org.pytorch.serve.wlm.WorkerLifeCycle - result=[METRICS]PredictionTime.Milliseconds:39577.59|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,1699733779,c5b24dcd-911a-4db0-be1e-2a7c4eedbab7, pattern=[METRICS]
2023-11-11T20:16:19,031 [INFO ] W-9000-sdxl_1.0-stdout MODEL_METRICS - PredictionTime.ms:39577.59|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,requestID:c5b24dcd-911a-4db0-be1e-2a7c4eedbab7,timestamp:1699733779
2023-11-11T20:16:22,943 [INFO ] W-9000-sdxl_1.0 ACCESS_LOG - /127.0.0.1:44986 "POST /v1/models/sdxl:predict HTTP/1.1" 200 43496
2023-11-11T20:16:22,943 [INFO ] W-9000-sdxl_1.0 TS_METRICS - Requests2XX.Count:1.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733782
2023-11-11T20:16:22,943 [INFO ] W-9000-sdxl_1.0 TS_METRICS - ts_inference_latency_microseconds.Microseconds:4.3425045488E7|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733782
2023-11-11T20:16:22,943 [INFO ] W-9000-sdxl_1.0 TS_METRICS - ts_queue_latency_microseconds.Microseconds:114.073|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733782
2023-11-11T20:16:22,944 [DEBUG] W-9000-sdxl_1.0 org.pytorch.serve.job.Job - Waiting time ns: 114073, Backend time ns: 43495863456
2023-11-11T20:16:22,944 [INFO ] W-9000-sdxl_1.0 TS_METRICS - QueueTime.Milliseconds:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733782
2023-11-11T20:16:22,944 [DEBUG] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - sent a reply, jobdone: true
2023-11-11T20:16:22,944 [INFO ] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - Backend response time: 43425
2023-11-11T20:16:22,944 [INFO ] W-9000-sdxl_1.0 TS_METRICS - WorkerThreadTime.Milliseconds:71.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733782
2023-11-11 20:16:23.798 kserve.trace requestId: d18233f7-8f8f-4aa9-85ca-9fd4e2df6aaa, preprocess_ms: 0.011920929, explain_ms: 0, predict_ms: 44353.208065033, postprocess_ms: 0.00333786
2023-11-11 20:16:30.545 uvicorn.access INFO:     127.0.0.6:34761 9 - "POST /v1/models/sdxl%3Apredict HTTP/1.1" 200 OK
2023-11-11 20:16:30.549 kserve.trace kserve.io.kserve.protocol.rest.v1_endpoints.predict: 51.10473871231079
2023-11-11 20:16:30.549 kserve.trace kserve.io.kserve.protocol.rest.v1_endpoints.predict: 7.572485999999998
2023-11-11T20:16:52,904 [INFO ] pool-3-thread-1 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733812
2023-11-11T20:16:52,905 [INFO ] pool-3-thread-1 TS_METRICS - DiskAvailable.Gigabytes:26.511981964111328|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733812
2023-11-11T20:16:52,905 [INFO ] pool-3-thread-1 TS_METRICS - DiskUsage.Gigabytes:53.476280212402344|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733812
2023-11-11T20:16:52,905 [INFO ] pool-3-thread-1 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733812
2023-11-11T20:16:52,905 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733812
2023-11-11T20:16:52,905 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733812
2023-11-11T20:16:52,905 [INFO ] pool-3-thread-1 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733812
2023-11-11T20:16:52,905 [INFO ] pool-3-thread-1 TS_METRICS - MemoryAvailable.Megabytes:11334.15234375|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733812
2023-11-11T20:16:52,905 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUsed.Megabytes:3988.23828125|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733812
2023-11-11T20:16:52,905 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUtilization.Percent:27.8|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733812
2023-11-11T20:17:52,893 [INFO ] pool-3-thread-2 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733872
2023-11-11T20:17:52,894 [INFO ] pool-3-thread-2 TS_METRICS - DiskAvailable.Gigabytes:26.511974334716797|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733872
2023-11-11T20:17:52,894 [INFO ] pool-3-thread-2 TS_METRICS - DiskUsage.Gigabytes:53.476287841796875|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733872
2023-11-11T20:17:52,894 [INFO ] pool-3-thread-2 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733872
2023-11-11T20:17:52,894 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733872
2023-11-11T20:17:52,894 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733872
2023-11-11T20:17:52,894 [INFO ] pool-3-thread-2 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733872
2023-11-11T20:17:52,894 [INFO ] pool-3-thread-2 TS_METRICS - MemoryAvailable.Megabytes:11334.1484375|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733872
2023-11-11T20:17:52,894 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUsed.Megabytes:3988.2421875|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733872
2023-11-11T20:17:52,894 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUtilization.Percent:27.8|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733872
2023-11-11T20:18:48,167 [INFO ] epollEventLoopGroup-3-2 TS_METRICS - ts_inference_requests_total.Count:1.0|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733928
2023-11-11T20:18:48,167 [INFO ] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - Flushing req.cmd PREDICT to backend at: 1699733928167
2023-11-11T20:18:48,168 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - Backend received inference at: 1699733928
2023-11-11T20:18:48,168 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - received text: 'a human playing with a dog'
2023-11-11T20:18:48,197 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 
2023-11-11T20:18:48,907 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   0%|          | 0/50 [00:00<?, ?it/s]
2023-11-11T20:18:49,653 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   2%|▏         | 1/50 [00:00<00:34,  1.41it/s]
2023-11-11T20:18:50,397 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   4%|▍         | 2/50 [00:01<00:35,  1.37it/s]
2023-11-11T20:18:51,130 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   6%|▌         | 3/50 [00:02<00:34,  1.36it/s]
2023-11-11T20:18:51,862 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -   8%|▊         | 4/50 [00:02<00:33,  1.36it/s]
2023-11-11T20:18:52,668 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  10%|█         | 5/50 [00:03<00:33,  1.36it/s]
2023-11-11T20:18:53,179 [INFO ] pool-3-thread-2 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733933
2023-11-11T20:18:53,179 [INFO ] pool-3-thread-2 TS_METRICS - DiskAvailable.Gigabytes:26.511985778808594|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733933
2023-11-11T20:18:53,179 [INFO ] pool-3-thread-2 TS_METRICS - DiskUsage.Gigabytes:53.47627639770508|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733933
2023-11-11T20:18:53,179 [INFO ] pool-3-thread-2 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733933
2023-11-11T20:18:53,179 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733933
2023-11-11T20:18:53,179 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733933
2023-11-11T20:18:53,179 [INFO ] pool-3-thread-2 TS_METRICS - GPUUtilization.Percent:100.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733933
2023-11-11T20:18:53,179 [INFO ] pool-3-thread-2 TS_METRICS - MemoryAvailable.Megabytes:11334.1171875|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733933
2023-11-11T20:18:53,180 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUsed.Megabytes:3988.2734375|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733933
2023-11-11T20:18:53,180 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUtilization.Percent:27.8|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733933
2023-11-11T20:18:53,385 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  12%|█▏        | 6/50 [00:04<00:33,  1.32it/s]
2023-11-11T20:18:54,133 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  14%|█▍        | 7/50 [00:05<00:32,  1.34it/s]
2023-11-11T20:18:54,881 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  16%|█▌        | 8/50 [00:05<00:31,  1.34it/s]
2023-11-11T20:18:55,616 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  18%|█▊        | 9/50 [00:06<00:30,  1.34it/s]
2023-11-11T20:18:56,353 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  20%|██        | 10/50 [00:07<00:29,  1.35it/s]
2023-11-11T20:18:57,094 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  22%|██▏       | 11/50 [00:08<00:28,  1.35it/s]
2023-11-11T20:18:57,829 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  24%|██▍       | 12/50 [00:08<00:28,  1.35it/s]
2023-11-11T20:18:58,572 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  26%|██▌       | 13/50 [00:09<00:27,  1.35it/s]
2023-11-11T20:18:59,313 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  28%|██▊       | 14/50 [00:10<00:26,  1.35it/s]
2023-11-11T20:19:00,054 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  30%|███       | 15/50 [00:11<00:25,  1.35it/s]
2023-11-11T20:19:00,800 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  32%|███▏      | 16/50 [00:11<00:25,  1.35it/s]
2023-11-11T20:19:01,545 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  34%|███▍      | 17/50 [00:12<00:24,  1.35it/s]
2023-11-11T20:19:02,288 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  36%|███▌      | 18/50 [00:13<00:23,  1.35it/s]
2023-11-11T20:19:03,029 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  38%|███▊      | 19/50 [00:14<00:23,  1.35it/s]
2023-11-11T20:19:03,768 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  40%|████      | 20/50 [00:14<00:22,  1.35it/s]
2023-11-11T20:19:04,511 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  42%|████▏     | 21/50 [00:15<00:21,  1.35it/s]
2023-11-11T20:19:05,256 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  44%|████▍     | 22/50 [00:16<00:20,  1.35it/s]
2023-11-11T20:19:06,003 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  46%|████▌     | 23/50 [00:17<00:20,  1.35it/s]
2023-11-11T20:19:06,752 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  48%|████▊     | 24/50 [00:17<00:19,  1.34it/s]
2023-11-11T20:19:07,495 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  50%|█████     | 25/50 [00:18<00:18,  1.34it/s]
2023-11-11T20:19:08,244 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  52%|█████▏    | 26/50 [00:19<00:17,  1.34it/s]
2023-11-11T20:19:08,990 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  54%|█████▍    | 27/50 [00:20<00:17,  1.34it/s]
2023-11-11T20:19:09,733 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  56%|█████▌    | 28/50 [00:20<00:16,  1.34it/s]
2023-11-11T20:19:10,479 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  58%|█████▊    | 29/50 [00:21<00:15,  1.34it/s]
2023-11-11T20:19:11,226 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  60%|██████    | 30/50 [00:22<00:14,  1.34it/s]
2023-11-11T20:19:11,974 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  62%|██████▏   | 31/50 [00:23<00:14,  1.34it/s]
2023-11-11T20:19:12,723 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  64%|██████▍   | 32/50 [00:23<00:13,  1.34it/s]
2023-11-11T20:19:13,473 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  66%|██████▌   | 33/50 [00:24<00:12,  1.34it/s]
2023-11-11T20:19:14,223 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  68%|██████▊   | 34/50 [00:25<00:11,  1.34it/s]
2023-11-11T20:19:14,975 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  70%|███████   | 35/50 [00:26<00:11,  1.34it/s]
2023-11-11T20:19:15,723 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  72%|███████▏  | 36/50 [00:26<00:10,  1.33it/s]
2023-11-11T20:19:16,473 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  74%|███████▍  | 37/50 [00:27<00:09,  1.33it/s]
2023-11-11T20:19:17,222 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  76%|███████▌  | 38/50 [00:28<00:08,  1.33it/s]
2023-11-11T20:19:17,973 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  78%|███████▊  | 39/50 [00:29<00:08,  1.33it/s]
2023-11-11T20:19:18,723 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  80%|████████  | 40/50 [00:29<00:07,  1.33it/s]
2023-11-11T20:19:19,472 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  82%|████████▏ | 41/50 [00:30<00:06,  1.33it/s]
2023-11-11T20:19:20,222 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  84%|████████▍ | 42/50 [00:31<00:05,  1.33it/s]
2023-11-11T20:19:20,971 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  86%|████████▌ | 43/50 [00:32<00:05,  1.33it/s]
2023-11-11T20:19:21,721 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  88%|████████▊ | 44/50 [00:32<00:04,  1.33it/s]
2023-11-11T20:19:22,468 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  90%|█████████ | 45/50 [00:33<00:03,  1.33it/s]
2023-11-11T20:19:23,221 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  92%|█████████▏| 46/50 [00:34<00:02,  1.34it/s]
2023-11-11T20:19:23,971 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  94%|█████████▍| 47/50 [00:35<00:02,  1.33it/s]
2023-11-11T20:19:24,718 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  96%|█████████▌| 48/50 [00:35<00:01,  1.33it/s]
2023-11-11T20:19:25,466 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG -  98%|█████████▊| 49/50 [00:36<00:00,  1.34it/s]
2023-11-11T20:19:25,466 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 100%|██████████| 50/50 [00:37<00:00,  1.34it/s]
2023-11-11T20:19:25,466 [WARN ] W-9000-sdxl_1.0-stderr MODEL_LOG - 100%|██████████| 50/50 [00:37<00:00,  1.34it/s]
2023-11-11T20:19:27,207 [INFO ] W-9000-sdxl_1.0-stdout MODEL_LOG - generated images: [<PIL.Image.Image image mode=RGB size=1024x1024 at 0x7F7A974DC100>]
2023-11-11T20:19:27,970 [INFO ] W-9000-sdxl_1.0-stdout org.pytorch.serve.wlm.WorkerLifeCycle - result=[METRICS]HandlerTime.Milliseconds:39801.98|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,1699733967,ebca8b19-b5d1-4731-96f9-d69b0e1f0faf, pattern=[METRICS]
2023-11-11T20:19:27,970 [INFO ] W-9000-sdxl_1.0-stdout MODEL_METRICS - HandlerTime.ms:39801.98|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,requestID:ebca8b19-b5d1-4731-96f9-d69b0e1f0faf,timestamp:1699733967
2023-11-11T20:19:27,970 [INFO ] W-9000-sdxl_1.0-stdout org.pytorch.serve.wlm.WorkerLifeCycle - result=[METRICS]PredictionTime.Milliseconds:39802.19|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,1699733967,ebca8b19-b5d1-4731-96f9-d69b0e1f0faf, pattern=[METRICS]
2023-11-11T20:19:27,971 [INFO ] W-9000-sdxl_1.0-stdout MODEL_METRICS - PredictionTime.ms:39802.19|#ModelName:sdxl,Level:Model|#hostname:torchserve-predictor-556dc4dd84-8bhnq,requestID:ebca8b19-b5d1-4731-96f9-d69b0e1f0faf,timestamp:1699733967
2023-11-11T20:19:31,860 [INFO ] W-9000-sdxl_1.0 ACCESS_LOG - /127.0.0.1:38302 "POST /v1/models/sdxl:predict HTTP/1.1" 200 43694
2023-11-11T20:19:31,860 [INFO ] W-9000-sdxl_1.0 TS_METRICS - Requests2XX.Count:1.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733971
2023-11-11T20:19:31,860 [INFO ] W-9000-sdxl_1.0 TS_METRICS - ts_inference_latency_microseconds.Microseconds:4.3624112455E7|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733971
2023-11-11T20:19:31,860 [INFO ] W-9000-sdxl_1.0 TS_METRICS - ts_queue_latency_microseconds.Microseconds:137.459|#model_name:sdxl,model_version:default|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733971
2023-11-11T20:19:31,860 [DEBUG] W-9000-sdxl_1.0 org.pytorch.serve.job.Job - Waiting time ns: 137459, Backend time ns: 43693254911
2023-11-11T20:19:31,860 [INFO ] W-9000-sdxl_1.0 TS_METRICS - QueueTime.Milliseconds:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733971
2023-11-11T20:19:31,860 [DEBUG] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - sent a reply, jobdone: true
2023-11-11T20:19:31,860 [INFO ] W-9000-sdxl_1.0 org.pytorch.serve.wlm.WorkerThread - Backend response time: 43624
2023-11-11T20:19:31,860 [INFO ] W-9000-sdxl_1.0 TS_METRICS - WorkerThreadTime.Milliseconds:69.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733971
2023-11-11 20:19:32.957 kserve.trace requestId: fda1f762-b1d8-46dc-a011-a15eb00d8dea, preprocess_ms: 0.012397766, explain_ms: 0, predict_ms: 44792.607307434, postprocess_ms: 0.00333786
2023-11-11 20:19:39.697 uvicorn.access INFO:     127.0.0.6:54731 9 - "POST /v1/models/sdxl%3Apredict HTTP/1.1" 200 OK
2023-11-11 20:19:39.706 kserve.trace kserve.io.kserve.protocol.rest.v1_endpoints.predict: 51.542301654815674
2023-11-11 20:19:39.706 kserve.trace kserve.io.kserve.protocol.rest.v1_endpoints.predict: 7.810098000000011
2023-11-11T20:19:52,917 [INFO ] pool-3-thread-2 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733992
2023-11-11T20:19:52,917 [INFO ] pool-3-thread-2 TS_METRICS - DiskAvailable.Gigabytes:26.51193618774414|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733992
2023-11-11T20:19:52,917 [INFO ] pool-3-thread-2 TS_METRICS - DiskUsage.Gigabytes:53.47632598876953|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733992
2023-11-11T20:19:52,917 [INFO ] pool-3-thread-2 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733992
2023-11-11T20:19:52,917 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733992
2023-11-11T20:19:52,917 [INFO ] pool-3-thread-2 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733992
2023-11-11T20:19:52,917 [INFO ] pool-3-thread-2 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733992
2023-11-11T20:19:52,918 [INFO ] pool-3-thread-2 TS_METRICS - MemoryAvailable.Megabytes:11334.2578125|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733992
2023-11-11T20:19:52,918 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUsed.Megabytes:3988.1328125|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733992
2023-11-11T20:19:52,918 [INFO ] pool-3-thread-2 TS_METRICS - MemoryUtilization.Percent:27.8|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699733992
2023-11-11T20:20:52,894 [INFO ] pool-3-thread-1 TS_METRICS - CPUUtilization.Percent:0.0|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699734052
2023-11-11T20:20:52,895 [INFO ] pool-3-thread-1 TS_METRICS - DiskAvailable.Gigabytes:26.51193618774414|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699734052
2023-11-11T20:20:52,895 [INFO ] pool-3-thread-1 TS_METRICS - DiskUsage.Gigabytes:53.47632598876953|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699734052
2023-11-11T20:20:52,895 [INFO ] pool-3-thread-1 TS_METRICS - DiskUtilization.Percent:66.9|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699734052
2023-11-11T20:20:52,895 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUtilization.Percent:91.38261963068369|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699734052
2023-11-11T20:20:52,895 [INFO ] pool-3-thread-1 TS_METRICS - GPUMemoryUsed.Megabytes:13807.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699734052
2023-11-11T20:20:52,895 [INFO ] pool-3-thread-1 TS_METRICS - GPUUtilization.Percent:0.0|#Level:Host,DeviceId:0|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699734052
2023-11-11T20:20:52,895 [INFO ] pool-3-thread-1 TS_METRICS - MemoryAvailable.Megabytes:11334.44921875|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699734052
2023-11-11T20:20:52,895 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUsed.Megabytes:3987.94140625|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699734052
2023-11-11T20:20:52,895 [INFO ] pool-3-thread-1 TS_METRICS - MemoryUtilization.Percent:27.8|#Level:Host|#hostname:torchserve-predictor-556dc4dd84-8bhnq,timestamp:1699734052
```