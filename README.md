```yml
# .circleci/config.yml

version: 2.1

orbs:
  codeclimate-velocity-deploys: hmelenok/codeclimate-velocity-deploys@1.0.0

jobs:
  deploy:
    docker:
      - image: cimg/python:3.8
    steps:
      - checkout
      # Your deployment steps go here...
      - codeclimate-velocity-deploys:register_deploy:
          branch: "main"
          environment: "production"
          version: "1.0.1"
          revision: "a43599a46ed5dd23295b2ff3824eba8e1cff61d6"
          token: "149fe2f744d274f27d5b2d523accea8f97ba6a50f956d0d17682aa257d3b"
          repository_url: "https://github.com/user/project"
          deployed_at: "2023-01-01T12:00:00.000Z"

workflows:
  version: 2
  build_and_deploy:
    jobs:
      - deploy

```
