管理面板路径使用 BULL_AUTH_KEY ： http://localhost:3002/admin/CHANGEME/queues

curl -X POST http://localhost:3002/v2/scrape \
  -H "Content-Type: application/json" \
  -d '{"url":"https://www.qyyjt.cn/visitor/information/riskMonitor/news?id=DD7DC518DC9BEB66AC1FF231688D8BD3&type=riskMonitor_news&lastLevel=27ECAA6B6BBDF93B90971D119C47904EBCD08885EEA2B1B79FD3BCD58D4A13AD","limit":3}'



curl -X POST http://localhost:3002/v2/scrape \
  -H "Content-Type: application/json" \
  -d '{"url":"https://www.qyyjt.cn/visitor/information/riskMonitor/news?id=DD7DC518DC9BEB66AC1FF231688D8BD3&type=riskMonitor_news&lastLevel=27ECAA6B6BBDF93B90971D119C47904EBCD08885EEA2B1B79FD3BCD58D4A13AD"}'


curl -X POST http://localhost:3002/v2/scrape \
    -H "Content-Type: application/json" \
    -d '{
    "url": "https://www.qyyjt.cn/visitor/information/riskMonitor/news?id=DD7DC518DC9BEB66AC1FF231688D8BD3&type=riskMonitor_news&lastLevel=27ECAA6B6BBDF93B90971D119C47904EBCD08885EEA2B1B79FD3BCD58D4A13AD",
    "formats": ["markdown"],
    "waitFor": 5000,
    "timeout": 20000
    }'