<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TeaProtocol - Share Your Problems</title>
<style>
    body {
        font-family: Arial, sans-serif;
        margin: 0;
        padding: 20px;
    }
    .container {
        max-width: 600px;
        margin: auto;
    }
    h1 {
        text-align: center;
    }
    #commentForm {
        margin-bottom: 20px;
    }
    #commentForm textarea {
        width: 100%;
        height: 100px;
        resize: vertical;
    }
    .comment {
        background-color: #f9f9f9;
        padding: 10px;
        margin-bottom: 10px;
        border-radius: 5px;
    }
</style>
</head>
<body>
<div class="container">
    <h1>Share your problems with TeaProtocol</h1>
    <form id="commentForm">
        <textarea id="comment" placeholder="Write your comment here..." required></textarea>
        <br>
        <button type="submit">Submit</button>
    </form>
    <div id="comments">
        <!-- Comments will be displayed here -->
    </div>
</div>

<script>
    document.getElementById('commentForm').addEventListener('submit', function(event) {
        event.preventDefault(); // Prevent form submission
        var commentText = document.getElementById('comment').value;
        if (commentText.trim() !== '') {
            var commentElement = document.createElement('div');
            commentElement.classList.add('comment');
            commentElement.textContent = commentText;
            document.getElementById('comments').appendChild(commentElement);
            document.getElementById('commentForm').reset();
        } else {
            alert('Please enter your comment!');
        }
    });
</script>

</body>
</html>
