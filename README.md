# moneymaker
money money money
app.post('/webhook', async (req, res) => {
  const { type, data } = req.body;
  if (type === 'message.created') {
    const reply = await openai.chat.completions.create({
      model: 'gpt-4',
      messages: [{ role: 'user', content: data.text }]
    });
    await fanvue.messages.send({
      chatId: data.chatId,
      text: reply.choices[0].message.content
    });
  }
  res.status(200).send('OK');
});

app.post('/webhook', async (req, res) => {
  const { type, data } = req.body;

  if (type === 'message.created') {
    const reply = await openai.chat.completions.create({
      model: 'gpt-4',
      messages: [{ role: 'user', content: data.text }]
    });

    await fanvue.messages.send({
      chatId: data.chatId,
      text: reply.choices[0].message.content
    });
  }

  res.status(200).send('OK');
});
[
  { "id": "c_12345", "name": "Creator A", "earnings_24h": 1500.00 },
  { "id": "c_67890", "name": "Creator B", "earnings_24h": 3200.50 }
]
Webhook Latency
~45ms
Reliability
99.99%
Supported: n8n, Zapier, Make
    
