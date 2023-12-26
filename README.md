# 3shake-costchecker-agent
🚀 CostChecker-Agent: An AI-Powered 🤖 Tool for Automated Cloud Cost Analysis, Feedback, Suggestions and More! 💻🔍

# CostChecker-Agentとは？
上記はCostChecker-Agentのコンセプト図です。CostChecker-Agent自体はDocker imageを利用して構築しています。Github Actionを利用する事で、Google Cloudのコストの増減について定期的に監視を行い、LLMがレポートを作成します。Github Actionを利用する事で、レポートが定期的に取得出来ます。更にローカルでの実行もサポートしています。2023年11月7日現在、CostChecker-Agentで使用するLLMに、OpenAI社のChatGPTと、Google CloudのVertex AI(PaLM2)をサポートしています。

# 使い方
1. Google Cloud側での設定が事前に必要です。詳細は以下の記事をご覧ください。
   - [PaLM API for textで作るGoogle Cloudコストチェッカー](https://sreake.com/blog/google-cloud-cost-check-with-palm-api-for-text/)
   - **記事公開後にURL->**[Google Cloudコスト増減の定期監視とアドバイスを行うCostChecker-Agentの紹介]()
2. ```costchecker-agent.yml```と```monthly-timestamp-update.yml```を自身のリポジトリの```.github/workflows```配下に置きます。
3. ```Settings > Actions > General > Workflow permissions```の```Read repository contents permission```を```Read and write permissions```に設定します。
4. 環境変数を設定します。
    ```
    GCP_SA_JSON_KEY=<サービスアカウントのキーファイルの内容を張り付ける>
    GCP_PROJECT_NAME=<YOUR ENV>
    GCP_DATASET=<YOUR ENV>
    GCP_TABLE_NAME=<YOUR ENV>
    OPENAI_API_KEY=<YOUR ENV>
    OPENAI_ORGANIZATION_ID=<YOUR ENV>
    LLM_MODEL=PaLM2
    LANGUAGE=Japanese
    ```
