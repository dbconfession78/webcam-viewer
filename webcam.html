import express from 'express';
import bodyParser from 'body-parser';
import fetch from 'node-fetch';
import { config } from 'dotenv';

config();

const app = express();
const port = process.env.PORT || 3000;

app.use(bodyParser.json());
app.use(express.static('public')); // Serve static files from the 'public' directory

// OpenAI API key
const OPENAI_API_KEY = process.env.OPENAI_API_KEY;

app.post('/chat', async (req, res) => {
    const { message } = req.body;
    try {
        const response = await fetch('https://api.openai.com/v1/chat/completions', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json',
                'Authorization': `Bearer ${OPENAI_API_KEY}`
            },
            body: JSON.stringify({
                model: 'gpt-3.5-turbo',
                messages: [{ role: 'user', content: message }],
                max_tokens: 150
            })
        });

        if (!response.ok) {
            const error = await response.json();
            console.error('Error from OpenAI API:', error);
            return res.status(response.status).json({ error: error.message || 'API Error' });
        }

        const data = await response.json();
        console.log('Response from OpenAI API:', data);

        if (data && data.choices && data.choices.length > 0) {
            const botMessage = data.choices[0].message.content.trim();
            res.json({ message: botMessage });
        } else {
            console.error('Invalid response format:', data);
            res.status(500).json({ error: 'Invalid response format from OpenAI API' });
        }
    } catch (error) {
        console.error('Error accessing OpenAI API:', error);
        res.status(500).json({ error: 'Internal Server Error' });
    }
});

app.listen(port, () => {
    console.log(`Server is running on port ${port}`);
});
