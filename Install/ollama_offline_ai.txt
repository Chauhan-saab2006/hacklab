Install and Run Dolphin-Mistral with Ollama on Windows

Step 1: Install Ollama
Download the Windows installer:
OllamaSetup.exe
Then:
Double-click the downloaded .exe file.
Follow the installation wizard prompts.
After installation, close and reopen your terminal (or open a new terminal window) so the ollama command becomes available.

Step 2: Verify Ollama Is Running
On Windows, the Ollama service usually starts automatically.
You can verify this by:
Opening Task Manager
Looking for ollama.exe
Then check the installed version in Command Prompt or PowerShell:
> ollama --version
You should see the installed Ollama version printed in the terminal.

Step 3: Download the Dolphin-Mistral Model
Download the 7B Dolphin-Mistral model:
> ollama pull dolphin-mistral:7b
Notes:
Model size is approximately 4.1 GB
Download time depends on your internet speed
A progress bar will appear during download

Step 4: Start Chatting with the Model
Launch an interactive session:
> ollama run dolphin-mistral:7b
You can now chat directly with the model in your terminal.

Linux Note (Optional)
If you're using Linux and the Ollama service is not running:
> sudo systemctl start ollama
