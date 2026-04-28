# Lab: Understanding Docker Bind Mounts

## Objective

By the end of this lab, you will:

* Understand what **bind mounts** are
* Learn how to link local files to a container
* See how changes on your host machine reflect inside a container

---

## Part 1: Prepare Your Workspace

1. Create a project folder on your system
2. Inside it, create two subfolders:

   * One for **configuration files**
   * One for **web content (HTML files)**

---

## Part 2: Create Sample Files

1. Inside your web content folder:

   * Create a simple `index.html`
   * Add a heading like:

     > "Hello from my local machine!"

2. Inside your configuration folder:

   * Add a basic Apache configuration file
   * Ensure it points to the correct directory for your HTML files

---

## Part 3: Run the Container

1. Run an Apache container using Docker
2. While running it:

   * Map a port from the container to your host
   * Attach both local folders to the correct directories inside the container

* Container name
* Port mapping
* Two bind mounts

---

## Part 4: Verify Output

1. Open your browser
2. Visit `http://localhost:<your-port>`

**Questions:**

* Do you see your HTML content?
* Where is this file actually stored — inside the container or on your machine?

---

## Part 5: Live Editing Test

1. Open your `index.html` file on your host machine
2. Change the text (e.g., update the heading)
3. Refresh your browser

**Questions:**

* Did the changes appear instantly?
* Did you restart the container?

---

## Part 6: Break & Observe

1. Stop and remove the container
2. Modify your HTML file again
3. Start a new container using the same setup

**Questions:**

* Is your updated content still there?
* Why didn’t you lose the data this time?

---

## Bonus Challenge

* Try changing the folder path (e.g., rename your local folder)
* Run the container again

What happens if Docker cannot find the local folder?

---

## Notes

* Focus on understanding how local files connect to the container
* Observe behavior instead of memorizing commands
* Experiment freely — breaking things is part of learning

---