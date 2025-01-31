# Setting Up Kestra: A Step-by-Step Guide

## What We're Going to Do

We're going to set up Kestra, which is a workflow orchestration tool. Think of it like a control center for automating tasks and processes. Here's what we'll do step by step:

## Prerequisites

1. Make sure Docker Desktop is installed and running on your computer.
    - If you're on Windows, you'll need WSL (Windows Subsystem for Linux) enabled.

## Step 1: Start the Kestra Container

First, we're going to start Kestra using Docker:

```bash
docker run --pull=always --rm -it -p 8080:8080 --user=root -v /var/run/docker.sock:/var/run/docker.sock -v /tmp:/tmp kestra/kestra:latest server local
```

### What this command does:

- `docker run`: Tells Docker to start a new container.
- `--pull=always`: Always gets the latest version of Kestra.
- `--rm`: Automatically cleans up after we're done.
- `-it`: Makes it interactive so we can see what's happening.
- `-p 8080:8080`: Opens up port 8080 so we can access Kestra in our web browser.
- `--user=root`: Runs everything with admin permissions.
- The `-v` parts: Connects our computer's Docker system with Kestra's container.
- `kestra/kestra:latest`: Uses the newest version of Kestra.
- `server local`: Starts Kestra in local mode.

## Step 2: What Happens Next

After running this command, you'll see:

1. A bunch of text scrolling in your terminal - this is Kestra starting up.
2. The terminal will keep running (don't close it!).
3. You can now open your web browser.

## Step 3: Access the Interface

1. Open your web browser.
2. Go to [`http://localhost:8080`](http://localhost:8080).
3. You'll see the Kestra welcome screen with:
    - A dashboard.
    - Options to create workflows ("flows").
    - Various management tools.

## Important Notes

- This setup is temporary - when you stop Docker, everything will be reset.
- The database is not permanent (it's using something called H2).
- Perfect for testing and learning, but for real work, you'll want to set up a permanent database.

## Next Steps

Once everything is running, you can:

1. Click **"Create Flow"** to make your first workflow.
2. Explore the interface.
3. Try creating some basic automations.

### To stop Kestra when you're done:

1. Go back to your terminal.
2. Press `Ctrl+C`.
3. Everything will shut down cleanly thanks to the `--rm` flag we used.
