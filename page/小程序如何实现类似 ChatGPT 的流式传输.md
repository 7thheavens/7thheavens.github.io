> 好久没来热闹了，埋头苦干混工资，结果到头没我事，要问我是哪一个，苦命打工终结者。

最近在指导群里解决技术问题时，遇到了一个让我也感到棘手的难题。于是激发了我的潜能，决定深入研究。由于最近沉浸在 ChatGPT 中，很久没用 Google 和百度搜索东西了，发现这方面的解决方案确实不多。于是记录下探索的过程，与大家分享。

## 小程序如何实现流式传输

模拟 ChatGPT 的效果，通过处理流数据实现打字机的效果。

---

## 什么是流式传输？

在解决问题之前，我们需要了解什么是流式传输。流式传输是将数据分成多个数据流，通过网络传输，以减少网络延迟和提高性能。在某些情况下，流式传输也可以用于将视频流和音频流传输到客户端。它是一种高效的数据传输方式，常用于大文件下载和在线视频播放等场景。

---

## 为什么小程序不支持流式传输？

尽管流式传输在某些情况下非常有用，但小程序目前不支持流式传输，主要原因如下：

1. **架构限制**：小程序的代码和资源被打包在一个文件中，依赖框架环境，无法调用浏览器标准的 API。
2. **网络请求限制**：小程序的网络请求必须使用微信提供的 API，这些 API 通常只支持完整的请求和响应，无法实现流式传输。

---

## 我的解决方案

以下是几种可行的解决方案：

1. **使用 WebSocket 协议**  
   WebSocket 提供了双向通信功能，并支持流式传输。在小程序中，可以使用 WebSocket 来实现流式传输。

2. **调整数据格式**  
   如果需要传输大量数据，可以将数据分成更小的块，以便小程序能够逐步处理，避免一次性传输过多数据。

3. **使用分段下载**  
   分段下载是一种常见的技术，可以将数据分成多个部分，每次下载一个部分，最后合并数据。

尽管这些方案可行，但实现起来较为复杂，可能会增加开发成本。

---

### 常规方案：Axios

以下是使用 Axios 的实现方案：

javascript
.then((res) => {
  const arrayBuffer = res.data;
  const uint8Array = new Uint8Array(arrayBuffer);
  const textDecoder = new TextDecoder('utf-8');
  const text = textDecoder.decode(uint8Array);
  for (let i = 0; i < text.length; i++) {
    setTimeout(() => {
      resultText += text[i];
      console.log(resultText);
    }, i * 100);
  }
});


在浏览器和小程序调试工具中测试通过，但在实际小程序中报错，无法支持 `TextDecoder` 方法。

---

### 另辟蹊径：onChunkReceived 方案

最终采用了 `onChunkReceived` 方法，代码如下：

javascript
let buffer = '';
requestTask.onChunkReceived(function (response) {
  const arrayBuffer = response.data;
  const uint8Array = new Uint8Array(arrayBuffer);
  let text = String.fromCharCode.apply(null, uint8Array);
  buffer += text;
  full_command.value = buffer;
});


通过 `String.fromCharCode` 方法处理流数据，解决了 `TextDecoder` 的兼容性问题。当然，根据业务需求，还可以添加过滤和解码逻辑。

---

## 后端接口配置

后端需要支持分段传输，主要是添加请求头，具体配置教程可以参考相关文档。

---

## 总结

目前，小程序对流式传输的支持仍然有限，但通过 WebSocket 或分段传输等方式，可以实现类似 ChatGPT 的流式传输效果。希望这篇文章能为有类似需求的开发者提供一些参考。

👉 [WildCard | 一分钟注册，轻松订阅海外线上服务](https://bit.ly/bewildcard)