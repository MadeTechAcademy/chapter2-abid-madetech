# Question sheet

Commit your answers to these questions in your copy

## Part 1
Answer these after a day or two to see how much you remember

1. What principle(s) can we apply to improve the size of images?
- Use smaller base images (e.g., alpine)
- Minimize the number of layers in Dockerfiles
- Remove unnecessary files and dependencies

1. What principle(s) can we apply to speed up rebuilds of images locally?
- order the commands in the dockerfile so that the least changing commands come first. This allows us to leverage the caching mechanism better.
- Reduce layers by combining related commands such as: RUN apt-get update && apt-get install

1. What principles can we apply to speed up builds of an image in a pipeline?
- Multi-stage builds

1. What are examples of artefacts, files or values we would not want to have baked into a shipped image used in production and why?
- Secrets such as API keys, PATs, passwords etc
- Files holding development dependencies

1. What principles can we apply to avoid this?
- Exclude unnecessary files such as dockerfiles, tests (if they are not needed in prod)
- multi-stage builds to separate development and production stages
- environment vairables and secret management tools for secret keys
  
1. Which exercise had the biggest impact on the image quality and why?
- Probably multi stage builds as they allow you to build dependencies in one stage and copy of what is necessary into the final image. This allows it to be leaner and faster.

## Part 2
Answer these after some reflection on your delivery

1. Which is the most important type of problem to fix first and why?
1. What problem have you spotted on your delivery that either needs improving or has been solved by one of these approaches? (or another approach we haven’t discussed)
1. Give an example of a problem you spotted and the proposal you made for it to be fixed
2. Give an example of a problem you were involved in fixing and the impact that the fix brought. How was the impact measured?

