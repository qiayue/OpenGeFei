# OpenAI 的 GPT4 API 正式全量发布，所有至少成功支付过一次的开发者都可以直接调用

> 发布于 2023-07-07 · [公众号原文](https://mp.weixin.qq.com/s/jo4qZAEwrkYrcUR7IWv7dQ)

激动人心的时刻，GPT4 API 全量开放！

刚刚 OpenAI 官方博客介绍，GPT4 API现已全量开放给开发者了。

只要是绑定了信用卡，并且成功扣款过一次的开发者账号，都有权限调用 GPT4 API。

并且，月底之前，会向更多开发者开放。

不过暂时开放的只是 8K 模型，更高的模型会评估算力之后陆续开放。

价格方面，暂时没有变化。

不管是暂时只开放 8K 模型，还是价格暂时不变，还是只开放给成功付款一次的开发者账户，目的都是在可控的范围内让真正有需要的开发者使用。

而不是被滥用，被过度使用。

另外，/v1/completions 将被弃用，OpenAI 推荐大家都转向 /v1/chat/completions ，并且后者已经有了97%的调用量了，也就是还剩3%的请求在调用前者。

这也是为了收回旧模型，集中算力到更多人需要的模型上。

同样被收回的模型还有老的潜入 embeddings 模型，如以下模型，都被建议替换为 text-embedding-ada-002 模型。

code-search-ada-code-001

code-search-ada-text-001
code-search-babbage-code-001
code-search-babbage-text-001
text-search-ada-doc-001
text-search-ada-query-001
text-search-babbage-doc-001
text-search-babbage-query-001
text-search-curie-doc-001
text-search-curie-query-001
text-search-davinci-doc-001
text-search-davinci-query-001
text-similarity-ada-001
text-similarity-babbage-001
text-similarity-curie-001
text-similarity-davinci-001
