# Lab: Amazon S3 Versioning and Object Lifecycle Management

Objective

Understand how versioning works in Amazon S3, including file updates, version history, delete markers, and permanent deletion.

# 🔹 Step 1: Create Bucket (Without Versioning)

Go to S3 Console

Click Create bucket

Enter bucket name: my-versioning-lab-bucket-123

Keep everything default (versioning disabled)

Click Create bucket

# 🔹 Step 2: Upload Initial File

Open the bucket

Click Upload → Add file

Upload a text file (example: file.txt)

Click Upload

# 🔹 Step 3: View File Content

Click the uploaded file

Open or download it

👉 You can see the content (Version 1)

# 🔹 Step 4: Modify and Re-upload File

Edit the file locally (change content)

Upload the same file again (same name)

👉 Result:

Old file is overwritten

Previous version is lost (no history)

# 🔹 Step 5: Enable Versioning

Go to Properties tab

Scroll to Bucket Versioning

Click Edit

Select Enable

Save changes

# 🔹 Step 6: Upload Modified File Again

Edit file again (new content)

Upload same file name

👉 Now S3 stores it as a new version, not overwrite

# 🔹 Step 7: View Versions

Go to Objects tab

Enable Show versions

👉 You will see:

Multiple versions of the same file

One marked as Latest

# 🔹 Step 8: Delete Object (Without Version View)

Turn OFF Show versions

Select file

Click Delete

👉 Result:

File is not actually deleted

A Delete Marker is created

File appears gone in normal view

# 🔹 Step 9: Understand Delete Marker

Turn ON Show versions

👉 You will see:

Delete Marker (latest)

Previous versions still موجود (present)

# 🔹 Step 10: Permanently Delete Object

Enable Show versions

Select:

Delete marker

All previous versions

Click Delete

👉 Now object is completely removed

# 🔹 Step 11: Delete Bucket

Go to bucket list

Select bucket

Click Delete bucket

# 👉 If versions still exist → deletion fails

After removing all versions:

Type bucket name

Confirm delete

👉 Bucket deleted permanently ✅

# 💡 What This Really Means


Without versioning → overwrite = data loss

With versioning → every change is stored

Delete ≠ delete (it creates a marker)

Permanent delete requires removing all versions

# 🔥 Interview Tip

If they ask:

“What is a delete marker in S3?”

You say:

It is a placeholder created when deleting an object in a versioned bucket. It hides the object but does not remove previous versions.
