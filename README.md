# awesome-compute-canada
A collection of awesome things about Compute Canada



## How to Run Docker Image on Compute Canada

This guide explains how to run Docker images on Compute Canada (CC) using Apptainer.

### Load Apptainer

First, you need to load the Apptainer module on your Compute Canada environment. Use the following command to do this:

```bash
module load apptainer
```

### Build a Sandbox Image from a Docker Image

Next, create a sandbox image from your Docker image. Here's the command you'll use:

```bash
apptainer build --fakeroot --sandbox <folder_name>/ docker://<repo>/<image_tag>
```

For instance, if you wanted to create a sandbox from the `nvidia/cuda` Docker image with tag `11.8.0-cudnn8-runtime-ubuntu20.04`, you'd use this command:

```bash
apptainer build --fakeroot --sandbox ubuntu/ docker://nvidia/cuda:11.8.0-cudnn8-runtime-ubuntu20.04
```

This will create a folder named `ubuntu` for the container.

### Access the Sandbox with Shell

To access your newly created sandbox with a shell, use the following command:

```bash
apptainer shell --fakeroot --writable <folder_name>
```

In the case of the `ubuntu` folder we created earlier, the command would be:

```bash
apptainer shell --fakeroot --writable ubuntu/
```

### Execute Commands in the Sandbox

To run a command inside the sandbox, use the `apptainer exec` command. Here's the basic structure:

```bash
apptainer exec --nv <command>
```

Replace `<command>` with the command you wish to run.

---

Make sure to replace `<folder_name>`, `<repo>`, `<image_tag>`, and `<command>` with your specific details.




# CONTRIBUTING.md

```markdown
# Contribution Guide

We welcome and appreciate all contributions. If you're interested in contributing, here are the steps:

1. Fork the repository
2. Create a new branch (`git checkout -b new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin new-feature`)
5. Create a new pull request

Feel free to create an issue to discuss any changes or features.

## Code of Conduct

We expect all our contributors to follow our code of conduct. In short, be respectful of others, be considerate, and be professional. Ensure that your changes are in line with the project's standards and guidelines.

```

