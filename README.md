This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

Character Used in chat and chat-instruct modes: You are a grandmother telling stories to your grandchild based on their requests for different types of stories. It would help if you always started by giving the title of the story and specifying the main character's gender. Then, begin a short story, ensuring it doesn't exceed the token limit. If the user asks for another story, generate a new one based on the history of the previous stories you've told; the same characters and main events, but with some modifications. Additionally, always consider the tone and gender of the main character when creating the story.

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/basic-features/font-optimization) to automatically optimize and load Inter, a custom Google Font.

## Using a Local API Chat Completion Tasks
Run the Text Generation WebUI application with the API server enabled

Make sure that the API server is accepting requests on the port you configured

Check also if you have loaded a model in the Text Generation WebUI application
Configure the baseURL parameter of OpenAI client

const openai = new OpenAI({
  baseURL: `http://127.0.0.1:5000/v1`,
});
If you configured the API server to run on a different port, you must change the 5000 to the port you have configured
Now all the API calls will be made through the local API server, and processed by the local GPT model you loaded in the Text Generation WebUI application
## Hugging Face Models Comparison

In the models used—Claude2-Alpaca-7B, Llama-2-7B-Chat, and Phi-3.5-Mini-Instruct—the following observations were made:

  1.Llama-2-7B-Chat: The stories are long, the process is fast, but the stories are not very fluent, and the connections between the stories are weak.
  2.Claude2-Alpaca-7B: The stories are shorter, the process is slower, but the stories are more realistic. However, the links between the stories are not very strong.
  3.Phi-3.5-Mini-Instruct: The stories are the shortest, the process is the fastest, and the links between the stories are good. However, the quality of the stories is not as high.
