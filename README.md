
# Elastic Meeting - Build Generative AI Apps with A Low Code Local Advanced Open-Source Stack

This repository was created to support a meet up that I was hosting to demonstrate a local AI stack powered by Elastic.
## Authors

- [@michaelcizmar](https://www.github.com/michaelcizmar)


## Tech Stack

**LLMOps:** Dify

**Local LLM Server:** Ollama

**Vector DB:** Elasticsearch


## Documentation

None Yet


## Installation

This project combines various projects so the installation reflects those individual components

### Elastic Stack
I've included a docker compose in the form that we use frequently.  It is based on Elastic's template but it also includes Elastic's Enterprise node which is required for doing web crawls. 

If you do not want that, you can use Elastic's script:
```
$ curl -fsSL https://elastic.co/start-local | sh
```

Otherwise, you can make a copy of .env.example, modify and run:

```
$ docker compose up
```

from the root directory of this project.

### Dify

Dify requires a few services and the project updates frequently so it is recommended to clone that seperately and run it. 
```
$ git clone https://github.com/langgenius/dify.git
$ cd dify
$ cd docker
$ cp .env.example .env
$ docker compose up -d
```

### Ollama

Ollama ideally will be installed locally versus Docker.  Follow the instructions to do so.

Macos  - [download](https://ollama.com/download/Ollama-darwin.zip)
Windows - [download](https://ollama.com/download/OllamaSetup.exe)
Linux - Run this script:
```
curl -fsSL https://ollama.com/install.sh | sh
```


## Appendix / Additional Reading

* [Ollama Models](https://ollama.com/search)
  
* [Dify Project](https://github.com/langgenius/dify)

* [Elastic Search Labs](https://www.elastic.co/search-labs)


## 🚀 About Me
I am a strategic operator who bridges executive leadership with mission-driven execution, specializing in AI, enterprise search, and digital transformation. With deep expertise in professional services, technology strategy, and product innovation, I empower organizations to leverage AI for measurable business impact.

