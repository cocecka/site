<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Random No Button</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background: whitesmoke;
            overflow: hidden;
        }

        .btn-group {
            margin-bottom: 20px;
            display: flex;
            gap: 20px;
        }

        button {
            width: 150px;
            height: 40px;
            color: white;
            font-size: 1.2em;
            border-radius: 30px;
            outline: none;
            cursor: pointer;
            box-shadow: 0 2px 4px gray;
            border: 2px solid #e94d58;
        }

        button.yes-btn {
            background: #e94d58;
        }

        button.no-btn {
            background: white;
            color: #e94d58;
        }

        .wrapper {
            position: relative;
            width: 100%;
            max-width: 600px;
            text-align: center;
        }

        h2 {
            font-size: 2em;
            color: #e94d58;
            margin: 15px 0;
        }

        .gif {
            width: 100%;
            max-width: 500px;
        }
    </style>
</head>
<body>
    <div class="btn-group">
        <button class="yes-btn">Yes</button>
        <button class="no-btn">No</button>
    </div>
    <div class="wrapper">
        <h2 class="question">Do you love me?</h2>
        <img class="gif" alt="gif" src="https://media.giphy.com/media/c76IJLufpNwSULPk77/giphy.gif?cid=790b7611axpefibph44gbl1bh4km4pv65emx1b8nruyi6q9r&ep=v1_gifs_search&rid=giphy.gif&ct=g" />
    </div>
    <script>
        const yesBtn = document.querySelector(".yes-btn");
        const noBtn = document.querySelector(".no-btn");
        const question = document.querySelector(".question");
        const gif = document.querySelector(".gif");

        yesBtn.addEventListener("click", () => {
                    question.innerHTML = "I love you too 💋💋💋";
                    gif.src = "https://media.giphy.com/media/108M7gCS1JSoO4/giphy.gif?cid=790b7611e1aaphvqz4fql0dqmlnuq6qic2o67y0fhvkhdvao&ep=v1_gifs_search&rid=giphy.gif&ct=g";
                });

        noBtn.addEventListener("mouseover", () => {
            const wrapper = document.querySelector(".wrapper");
            const wrapperRect = wrapper.getBoundingClientRect();
            const noBtnRect = noBtn.getBoundingClientRect();

            const maxX = wrapperRect.width - noBtnRect.width;
            const maxY = wrapperRect.height - noBtnRect.height;

            const randomX = Math.floor(Math.random() * maxX);
            const randomY = Math.floor(Math.random() * maxY);

            noBtn.style.position = "absolute";
            noBtn.style.left = randomX + "px";
            noBtn.style.top = randomY + "px";
        });
    </script>
</body>
</html>
