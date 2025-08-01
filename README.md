# N8N Daily News
- Scheduled to send you daily news at 10 AM through Telegram.
- You can check it out by importing `News_Summarizer.json` into n8n.

## Output

![Output](./screenshots/sent.png)

- It has successfully generated a summary of the news and sent it to my Telegram through a Telegram Bot.

## Nodes

![nodes](./screenshots/final.png)

- Trigger
    - Schedule Trigger
- Http Request Nodes
    - Based on the number of sources you want to consume news from.
    - Attach in parallel next to the trigger node to fetch news from each source.
- AI Agent
- Telegram

## Steps
- Create a trigger node.

    ![trigger](./screenshots/trigger.png)

- Attach a number of Http Request nodes in parallel to fetch news from each source.

    ![http](./screenshots/http_nodes.png)

- Go to `GNews Api`, [sign up](https://gnews.io/register), and read the documentation to understand the parameters you want to configure like keywords, language...

    ![doc](./screenshots/documentation.png)

- Use one of the Http Request nodes to fetch news from GNews Api by pasting the Get Request url from GNews Api and adding the parameters like q, apikey...

    ![gnews](./screenshots/gnews.png)

    ![gnews](./screenshots/gnews2.png)

- Test the node

    ![test](./screenshots/gnews_test.png)

- Go to `News Api`, sign up, and read the documentation to understand the parameters you want to configure like keywords, language, sort by, page size...

    ![doc](./screenshots/newsapi_doc.png)

- Use one of the Http Request nodes to fetch news from News Api by pasting the Get Request url from News Api and adding the parameters and `X-Api-Key` header for authentication.

    ![newsapi](./screenshots/newsapi.png)

- Test the node.

    ![test](./screenshots/test_newsapi.png)

- Convert the array output of the API responses into string so that the AI Agent can ingest it.

    ![convert](./screenshots/string.png)

- Combine the string outputs of all your sources with the merge node.

    ![merge](./screenshots/merge.png)

- Attach an AI Agent after the Merge node with a prompt to generate a summary of the news.

    ![prompt](./screenshots/prompt.png)

- Test node

    ![test](./screenshots/output.png)

- Create a telegram bot and type `@get_id_bot` without sending it. When popup appears, choose `Your Chat ID`.

    ![id](./screenshots/get_id.png)

- Copy your `chat id` and use it in a Telegram node after the AI Agent node for Sending messages.

    ![chatid](./screenshots/chatid.png)

    - Choose Markdown as parse mode.

    ![send](./screenshots/send_message.png)

## Contact
 - LinkedIn: [Natan Asrat](https://linkedin.com/in/natan-asrat)
 - Gmail: nathanyilmaasrat@gmail.com
 - Telegram: [Natan Asrat](https://t.me/fail_your_way_to_success)
 - Youtube: [Natville](https://www.youtube.com/@natvilletutor)