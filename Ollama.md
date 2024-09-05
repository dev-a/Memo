sudo docker run -d -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama

		curl http://serveur:11434/api/pull -d '{    
		    "model": "llama3.1"
		}'


    curl http://serveur:11434/api/generate -d '{
                    "model": "llama3.1",
                    "prompt":"pourquoi le ciel est bleu?"
                  }'
