# Quickstart to Building Bots on AWS
I summarized the info provided on <a href="">Create and Deploy a Chat Bot to AWS Lambda in Five Minutes!</a>

## Prerequisites

The Claudia Bot Builder works with the Node.JS 4.3.2 AWS Lambda installation. It requires using the Claudia.JS deployment tool, which you can install using NPM:  
 
```bash
npm install claudia -g
```
The Claudia Bot Builder support requires version 1.4.0 or later.

## Creating a simple text bot

Create a new folder, then, add the claudia-bot-builder library as a project dependency:
```bash
npm init
npm install claudia-bot-builder -S
```