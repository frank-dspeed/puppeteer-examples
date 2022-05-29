const client = await myPage.target().createCDPSession();
await client.send('Network.enable');
// All other devtools events do work also
client.on('Network.webSocketFrameReceived', ({ requestId, timestamp, response }) => {
  console.log(response);
});
