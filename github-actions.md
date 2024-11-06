# Continuous Integration & Continuous Deployment Using GitHub Action

#
### GitHub Actions to Docker Hub Login
~~~
on: push
jobs:
  build-container:
    name: Build container
    runs-on: ubuntu-latest
    steps:
    - name: Checkout code
      uses: actions/checkout@v3
    - name: Login to Docker Hub
      uses: docker/login-action@v1
      with:
        username: ${{ secrets.DOCKER_HUB_USERNAME }}
        password: ${{ secrets.DOCKER_HUB_ACCESS_TOKEN }}
~~~
#

### GitHub Actions to Images push on Docker Hub
~~~
on: push
jobs:
  build-container:
    name: Build container
    runs-on: ubuntu-latest
    steps:
    - name: Checkout code
      uses: actions/checkout@v3
    - name: Login to Docker Hub
      uses: docker/login-action@v1
      with:
        username: ${{ secrets.DOCKER_HUB_USERNAME }}
        password: ${{ secrets.DOCKER_HUB_ACCESS_TOKEN }}
    - name: Build and Push to Docker Hub
      uses: docker/build-push-action@v2
      with:
        context: .
        push: true
        tags: sumonpaul/github-actions:latest
~~~

#

### Github Action Using Deploy a Python Apps in AWS EC2 Instance

#### Requirements:
- EC2 Instance
- Create Github Repository Secret for Access EC2 Instance
- Create Github Action
~~~

name: Deploy to EC2 🚀

on:
  push:
    branches:
      - "16-CICD-PYTHON-WEBAPP" # This triggers the workflow on push to any branch

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout current branch ✅
        uses: actions/checkout@v2

      - name: Set up SSH key and whitelist EC2 IP address 🐻‍❄️
        run: |
          mkdir -p ~/.ssh
          echo "${{ secrets.EC2_SSH_KEY }}" > ~/.ssh/id_rsa
          chmod 600 ~/.ssh/id_rsa
          ssh-keyscan ${{ secrets.EC2_HOST }} >> ~/.ssh/known_hosts

      - name: Create .env file dynamically 🧨
        env:
          ENV: ${{ secrets.ENV }}
          EC2_USERNAME: ${{ secrets.EC2_USERNAME }}
          OPENAI_API_KEY: ${{ secrets.OPENAI_API_KEY }}
        run: |
          echo "ENV=${ENV}" >> env
          echo "EC2_USERNAME=${EC2_USERNAME}" >> env
          echo "OPENAI_API_KEY=${OPENAI_API_KEY}" >> env

      - name: Copy files to remote server 🚙
        env:
          EC2_HOST: ${{ secrets.EC2_HOST }}
          EC2_USERNAME: ${{ secrets.EC2_USERNAME }}
        run: |
          scp -r * $EC2_USERNAME@$EC2_HOST:/home/ubuntu/

      - name: Run Bash Script To Delpoy App 🚀
        env:
          EC2_HOST: ${{ secrets.EC2_HOST }}
          EC2_USERNAME: ${{ secrets.EC2_USERNAME }}
        run: |
          ssh -o StrictHostKeyChecking=no $EC2_USERNAME@$EC2_HOST "chmod +x ./deploy.sh && ./deploy.sh"

      - name: Clean up SSH key 🚀
        if: always()
        run: rm -f ~/.ssh/id_rsa

~~~
Reference:
- https://www.youtube.com/watch?v=W8tONeBuTn0
- https://github.com/TrickSumo/langchain-course-python.git

#
