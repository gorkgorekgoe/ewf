# ewf

Traceback (most recent call last):
  File "/home/kjhjkh/PycharmProjects/pythonProject/venv/lib/python3.9/site-packages/urllib3/connectionpool.py", line 449, in _make_request
    six.raise_from(e, None)
  File "<string>", line 3, in raise_from
  File "/home/kjhjkh/PycharmProjects/pythonProject/venv/lib/python3.9/site-packages/urllib3/connectionpool.py", line 444, in _make_request
    httplib_response = conn.getresponse()
  File "/usr/lib/python3.9/http/client.py", line 1371, in getresponse
    response.begin()
  File "/usr/lib/python3.9/http/client.py", line 319, in begin
    version, status, reason = self._read_status()
  File "/usr/lib/python3.9/http/client.py", line 280, in _read_status
    line = str(self.fp.readline(_MAXLINE + 1), "iso-8859-1")
  File "/usr/lib/python3.9/socket.py", line 704, in readinto
    return self._sock.recv_into(b)
  File "/usr/lib/python3.9/ssl.py", line 1241, in recv_into
    return self.read(nbytes, buffer)
  File "/usr/lib/python3.9/ssl.py", line 1099, in read
    return self._sslobj.read(len, buffer)
socket.timeout: The read operation timed out

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "/home/kjhjkh/PycharmProjects/pythonProject/venv/lib/python3.9/site-packages/requests/adapters.py", line 440, in send
    resp = conn.urlopen(
  File "/home/kjhjkh/PycharmProjects/pythonProject/venv/lib/python3.9/site-packages/urllib3/connectionpool.py", line 785, in urlopen
    retries = retries.increment(
  File "/home/kjhjkh/PycharmProjects/pythonProject/venv/lib/python3.9/site-packages/urllib3/util/retry.py", line 550, in increment
    raise six.reraise(type(error), error, _stacktrace)
  File "/home/kjhjkh/PycharmProjects/pythonProject/venv/lib/python3.9/site-packages/urllib3/packages/six.py", line 770, in reraise
    raise value
  File "/home/kjhjkh/PycharmProjects/pythonProject/venv/lib/python3.9/site-packages/urllib3/connectionpool.py", line 703, in urlopen
    httplib_response = self._make_request(
  File "/home/kjhjkh/PycharmProjects/pythonProject/venv/lib/python3.9/site-packages/urllib3/connectionpool.py", line 451, in _make_request
    self._raise_timeout(err=e, url=url, timeout_value=read_timeout)
  File "/home/kjhjkh/PycharmProjects/pythonProject/venv/lib/python3.9/site-packages/urllib3/connectionpool.py", line 340, in _raise_timeout
    raise ReadTimeoutError(
urllib3.exceptions.ReadTimeoutError: HTTPSConnectionPool(host='api.binance.com', port=443): Read timed out. (read timeout=10)

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "/home/kjhjkh/PycharmProjects/pythonProject/venv/lib/python3.9/site-packages/ccxt/base/exchange.py", line 622, in fetch
    response = self.session.request(
  File "/home/kjhjkh/PycharmProjects/pythonProject/venv/lib/python3.9/site-packages/requests/sessions.py", line 529, in request
    resp = self.send(prep, **send_kwargs)
  File "/home/kjhjkh/PycharmProjects/pythonProject/venv/lib/python3.9/site-packages/requests/sessions.py", line 645, in send
    r = adapter.send(request, **kwargs)
  File "/home/kjhjkh/PycharmProjects/pythonProject/venv/lib/python3.9/site-packages/requests/adapters.py", line 532, in send
    raise ReadTimeout(e, request=request)
requests.exceptions.ReadTimeout: HTTPSConnectionPool(host='api.binance.com', port=443): Read timed out. (read timeout=10)

The above exception was the direct cause of the following exception:

Traceback (most recent call last):
  File "/home/kjhjkh/PycharmProjects/pythonProject/main.py", line 169, in <module>
    price = (binance.fetch_ticker(symbol=symbol))
  File "/home/kjhjkh/PycharmProjects/pythonProject/venv/lib/python3.9/site-packages/ccxt/binance.py", line 2060, in fetch_ticker
    response = getattr(self, method)(self.extend(request, params))
  File "/home/kjhjkh/PycharmProjects/pythonProject/venv/lib/python3.9/site-packages/ccxt/base/exchange.py", line 490, in inner
    return entry(_self, **inner_kwargs)
  File "/home/kjhjkh/PycharmProjects/pythonProject/venv/lib/python3.9/site-packages/ccxt/binance.py", line 4998, in request
    response = self.fetch2(path, api, method, params, headers, body, config, context)
  File "/home/kjhjkh/PycharmProjects/pythonProject/venv/lib/python3.9/site-packages/ccxt/base/exchange.py", line 537, in fetch2
    return self.fetch(request['url'], request['method'], request['headers'], request['body'])
  File "/home/kjhjkh/PycharmProjects/pythonProject/venv/lib/python3.9/site-packages/ccxt/base/exchange.py", line 652, in fetch
    raise RequestTimeout(details) from e
ccxt.base.errors.RequestTimeout: binance GET https://api.binance.com/api/v3/ticker/24hr?symbol=BTCUSDT
