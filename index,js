const https = require('https');

const query = "What is the meaning of life?";
const apiKey = "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";

const options = {
  hostname: 'api.openai.com',
  path: '/v1/engines/davinci/completions',
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    'Authorization': `Bearer ${apiKey}`
  }
};

const req = https.request(options, (res) => {
  res.on('data', (d) => {
    const response = JSON.parse(d);
    console.log(response.choices[0].text);
  });
});

req.on('error', (error) => {
  console.error(error);
});

const data = JSON.stringify({
  prompt: query,
  max_tokens:100
});

req.write(data);
req.end();
