# Facebook88
Sosial media 
<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Fasebook - Social Network</title>

<style>
*{
    box-sizing:border-box;
    margin:0;
    padding:0;
}

body{
    font-family:Arial, Helvetica, sans-serif;
    background:#f0f2f5;
    color:#1c1e21;
}

/* NAVBAR */
.navbar{
    height:60px;
    background:white;
    display:flex;
    align-items:center;
    justify-content:space-between;
    padding:0 18px;
    box-shadow:0 1px 4px rgba(0,0,0,.15);
    position:sticky;
    top:0;
    z-index:100;
}

.logo{
    font-size:28px;
    font-weight:bold;
    color:#1877f2;
}

.search{
    width:300px;
    background:#f0f2f5;
    border-radius:22px;
    padding:10px 16px;
    border:none;
    outline:none;
}

.nav-icons{
    display:flex;
    gap:10px;
}

.nav-btn{
    width:40px;
    height:40px;
    border-radius:50%;
    border:none;
    background:#e4e6eb;
    font-size:18px;
    cursor:pointer;
}

/* LAYOUT */
.container{
    max-width:1400px;
    margin:auto;
    display:grid;
    grid-template-columns:260px minmax(400px,650px) 260px;
    gap:25px;
    padding:25px 15px;
}

/* SIDEBAR */
.sidebar{
    position:sticky;
    top:85px;
    height:max-content;
}

.menu{
    list-style:none;
}

.menu li{
    padding:12px;
    border-radius:8px;
    cursor:pointer;
    font-weight:600;
}

.menu li:hover{
    background:#e4e6eb;
}

.profile-mini{
    display:flex;
    align-items:center;
    gap:10px;
    margin-bottom:15px;
    padding:10px;
}

.avatar{
    width:42px;
    height:42px;
    border-radius:50%;
    object-fit:cover;
    background:#ddd;
}

.line{
    height:1px;
    background:#ddd;
    margin:10px 0;
}

/* STORIES */
.stories{
    display:flex;
    gap:10px;
    overflow-x:auto;
    margin-bottom:18px;
}

.story{
    min-width:105px;
    height:180px;
    border-radius:12px;
    overflow:hidden;
    position:relative;
    background:#1877f2;
    color:white;
    cursor:pointer;
}

.story img{
    width:100%;
    height:100%;
    object-fit:cover;
}

.story span{
    position:absolute;
    bottom:10px;
    left:8px;
    right:5px;
    font-weight:bold;
    text-shadow:0 1px 4px black;
}

/* CARD */
.card{
    background:white;
    border-radius:10px;
    margin-bottom:18px;
    box-shadow:0 1px 3px rgba(0,0,0,.12);
}

/* CREATE POST */
.create{
    padding:15px;
}

.create-top{
    display:flex;
    gap:10px;
    align-items:center;
}

.post-input{
    flex:1;
    border:none;
    background:#f0f2f5;
    padding:12px 16px;
    border-radius:22px;
    outline:none;
}

.post-actions{
    display:flex;
    justify-content:space-around;
    border-top:1px solid #ddd;
    margin-top:12px;
    padding-top:10px;
}

.post-actions button{
    border:none;
    background:none;
    cursor:pointer;
    padding:8px;
    font-weight:bold;
}

.post-actions button:hover{
    background:#f0f2f5;
    border-radius:8px;
}

/* POST */
.post{
    padding:15px;
}

.post-header{
    display:flex;
    align-items:center;
    gap:10px;
}

.post-name{
    font-weight:bold;
}

.post-time{
    color:#65676b;
    font-size:12px;
}

.post-text{
    margin:15px 0;
    line-height:1.5;
}

.post-image{
    width:100%;
    max-height:500px;
    object-fit:cover;
    border-radius:8px;
}

.post-stats{
    display:flex;
    justify-content:space-between;
    color:#65676b;
    font-size:14px;
    padding:10px 0;
}

.post-buttons{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    border-top:1px solid #ddd;
    border-bottom:1px solid #ddd;
}

.post-buttons button{
    border:none;
    background:none;
    padding:10px;
    cursor:pointer;
    font-weight:bold;
}

.post-buttons button:hover{
    background:#f0f2f5;
}

.comments{
    padding-top:10px;
}

.comment{
    background:#f0f2f5;
    padding:8px 12px;
    border-radius:15px;
    margin-top:7px;
    display:inline-block;
}

/* RIGHT SIDEBAR */
.right-title{
    font-size:18px;
    font-weight:bold;
    margin-bottom:12px;
}

.contact{
    display:flex;
    align-items:center;
    gap:10px;
    padding:9px;
    border-radius:8px;
}

.contact:hover{
    background:#e4e6eb;
}

/* MODAL */
.modal{
    display:none;
    position:fixed;
    inset:0;
    background:rgba(0,0,0,.55);
    z-index:200;
    align-items:center;
    justify-content:center;
    padding:15px;
}

.modal-box{
    background:white;
    width:100%;
    max-width:500px;
    border-radius:12px;
    padding:20px;
}

.modal-header{
    display:flex;
    justify-content:space-between;
    align-items:center;
    margin-bottom:15px;
}

.close{
    border:none;
    background:#e4e6eb;
    width:35px;
    height:35px;
    border-radius:50%;
    cursor:pointer;
}

textarea{
    width:100%;
    height:120px;
    resize:none;
    border:1px solid #ddd;
    border-radius:8px;
    padding:12px;
    font-size:16px;
    outline:none;
}

.preview{
    width:100%;
    max-height:250px;
    object-fit:cover;
    margin-top:10px;
    border-radius:8px;
    display:none;
}

.publish{
    width:100%;
    margin-top:15px;
    padding:12px;
    border:none;
    border-radius:8px;
    background:#1877f2;
    color:white;
    font-size:16px;
    font-weight:bold;
    cursor:pointer;
}

/* MOBILE */
@media(max-width:1000px){
    .container{
        grid-template-columns:200px minmax(400px,1fr);
    }

    .rightbar{
        display:none;
    }
}

@media(max-width:700px){
    .navbar{
        padding:0 10px;
    }

    .logo{
        font-size:24px;
    }

    .search{
        display:none;
    }

    .container{
        display:block;
        padding:10px;
    }

    .sidebar{
        display:none;
    }

    .main{
        width:100%;
    }

    .stories{
        margin-left:-10px;
        margin-right:-10px;
        padding:0 10px;
    }

    .story{
        min-width:95px;
        height:155px;
    }

    .card{
        border-radius:8px;
    }
}
</style>
</head>

<body>

<!-- NAVBAR -->
<header class="navbar">

    <div class="logo">Fasebook</div>

    <input
        id="searchInput"
        class="search"
        type="text"
        placeholder="Cari di Fasebook..."
        oninput="searchPosts()"
    >

    <div class="nav-icons">
        <button class="nav-btn" onclick="toggleDark()">🌙</button>
        <button class="nav-btn">🔔</button>
        <button class="nav-btn">💬</button>
    </div>

</header>


<div class="container">

<!-- LEFT SIDEBAR -->
<aside class="sidebar">

    <div class="profile-mini">
        <img class="avatar"
             src="https://i.pravatar.cc/100?img=12">
        <b>Steven</b>
    </div>

    <ul class="menu">
        <li>🏠 Beranda</li>
        <li>👥 Teman</li>
        <li>👨‍👩‍👧 Grup</li>
        <li>🛒 Marketplace</li>
        <li>🎬 Video</li>
        <li>📅 Acara</li>
        <li>💾 Tersimpan</li>
    </ul>

    <div class="line"></div>

    <p style="padding:10px;color:#65676b;">
        © 2026 Fasebook
    </p>

</aside>


<!-- MAIN -->
<main class="main">

    <!-- STORIES -->
    <div class="stories">

        <div class="story" onclick="openStory()">
            <img src="https://picsum.photos/200/300?random=1">
            <span>➕ Buat Cerita</span>
        </div>

        <div class="story">
            <img src="https://picsum.photos/200/300?random=2">
            <span>Rena</span>
        </div>

        <div class="story">
            <img src="https://picsum.photos/200/300?random=3">
            <span>Andi</span>
        </div>

        <div class="story">
            <img src="https://picsum.photos/200/300?random=4">
            <span>Dina</span>
        </div>

        <div class="story">
            <img src="https://picsum.photos/200/300?random=5">
            <span>Budi</span>
        </div>

    </div>


    <!-- CREATE POST -->
    <div class="card create">

        <div class="create-top">

            <img class="avatar"
                 src="https://i.pravatar.cc/100?img=12">

            <input
                class="post-input"
                placeholder="Apa yang Anda pikirkan?"
                onclick="openModal()"
                readonly
            >

        </div>

        <div class="post-actions">

            <button onclick="openModal()">
                🎥 Video
            </button>

            <button onclick="openModal()">
                🖼️ Foto
            </button>

            <button onclick="openModal()">
                😊 Perasaan
            </button>

        </div>

    </div>


    <!-- POSTS -->
    <div id="posts">

        <!-- POST 1 -->
        <article class="card post">

            <div class="post-header">

                <img class="avatar"
                     src="https://i.pravatar.cc/100?img=5">

                <div>
                    <div class="post-name">Andi Pratama</div>
                    <div class="post-time">2 jam · 🌎</div>
                </div>

            </div>

            <p class="post-text">
                Hari ini cuacanya bagus banget. Semoga harimu juga menyenangkan! 😊
            </p>

            <img
                class="post-image"
                src="https://picsum.photos/800/500?random=20"
            >

            <div class="post-stats">
                <span class="likes">👍 128</span>
                <span>24 komentar · 5 dibagikan</span>
            </div>

            <div class="post-buttons">

                <button onclick="likePost(this)">
                    👍 Suka
                </button>

                <button onclick="commentPost(this)">
                    💬 Komentar
                </button>

                <button onclick="sharePost()">
                    ↗️ Bagikan
                </button>

            </div>

            <div class="comments"></div>

        </article>


        <!-- POST 2 -->
        <article class="card post">

            <div class="post-header">

                <img class="avatar"
                     src="https://i.pravatar.cc/100?img=9">

                <div>
                    <div class="post-name">Dina Putri</div>
                    <div class="post-time">5 jam · 🌎</div>
                </div>

            </div>

            <p class="post-text">
                Weekend paling enak jalan-jalan dan menikmati suasana baru ✨
            </p>

            <img
                class="post-image"
                src="https://picsum.photos/800/500?random=25"
            >

            <div class="post-stats">
                <span class="likes">👍 86</span>
                <span>13 komentar · 2 dibagikan</span>
            </div>

            <div class="post-buttons">

                <button onclick="likePost(this)">
                    👍 Suka
                </button>

                <button onclick="commentPost(this)">
                    💬 Komentar
                </button>

                <button onclick="sharePost()">
                    ↗️ Bagikan
                </button>

            </div>

            <div class="comments"></div>

        </article>

    </div>

</main>


<!-- RIGHT SIDEBAR -->
<aside class="rightbar">

    <div class="card" style="padding:15px;">

        <div class="right-title">
            Kontak
        </div>

        <div class="contact">
            🟢 <b>Rena</b>
        </div>

        <div class="contact">
            🟢 <b>Andi</b>
        </div>

        <div class="contact">
            🟢 <b>Dina</b>
        </div>

        <div class="contact">
            🟢 <b>Budi</b>
        </div>

    </div>

</aside>

</div>


<!-- MODAL CREATE POST -->
<div class="modal" id="postModal">

    <div class="modal-box">

        <div class="modal-header">

            <h2>Buat postingan</h2>

            <button class="close"
                    onclick="closeModal()">
                ✕
            </button>

        </div>

        <textarea
            id="postText"
            placeholder="Apa yang Anda pikirkan?"
        ></textarea>

        <input
            type="file"
            id="imageInput"
            accept="image/*"
            onchange="previewImage(event)"
            style="margin-top:12px;"
        >

        <img
            id="imagePreview"
            class="preview"
        >

        <button
            class="publish"
            onclick="publishPost()">
            Posting
        </button>

    </div>

</div>


<script>

/* MODAL */

function openModal(){
    document.getElementById("postModal").style.display="flex";
}

function closeModal(){
    document.getElementById("postModal").style.display="none";
}


/* IMAGE PREVIEW */

function previewImage(event){

    const file = event.target.files[0];
    const preview = document.getElementById("imagePreview");

    if(file){

        const reader = new FileReader();

        reader.onload=function(e){
            preview.src=e.target.result;
            preview.style.display="block";
        };

        reader.readAsDataURL(file);
    }
}


/* CREATE POST */

function publishPost(){

    const text =
        document.getElementById("postText").value.trim();

    const image =
        document.getElementById("imagePreview").src;

    if(!text && !image){
        alert("Tulis sesuatu atau pilih foto terlebih dahulu.");
        return;
    }

    const article =
        document.createElement("article");

    article.className="card post";

    let imageHTML="";

    if(image){
        imageHTML=
        `<img class="post-image" src="${image}">`;
    }

    article.innerHTML=`

        <div class="post-header">

            <img class="avatar"
                 src="https://i.pravatar.cc/100?img=12">

            <div>

                <div class="post-name">
                    Steven
                </div>

                <div class="post-time">
                    Baru saja · 🌎
                </div>

            </div>

        </div>

        <p class="post-text">
            ${escapeHTML(text)}
        </p>

        ${imageHTML}

        <div class="post-stats">
            <span class="likes">👍 0</span>
            <span>0 komentar</span>
        </div>

        <div class="post-buttons">

            <button onclick="likePost(this)">
                👍 Suka
            </button>

            <button onclick="commentPost(this)">
                💬 Komentar
            </button>

            <button onclick="sharePost()">
                ↗️ Bagikan
            </button>

        </div>

        <div class="comments"></div>
    `;

    document
        .getElementById("posts")
        .prepend(article);

    document.getElementById("postText").value="";
    document.getElementById("imageInput").value="";
    document.getElementById("imagePreview").style.display="none";

    closeModal();
}


/* LIKE */

function likePost(button){

    const post =
        button.closest(".post");

    const likes =
        post.querySelector(".likes");

    let number =
        parseInt(likes.textContent.replace(/\D/g,"")) || 0;

    if(!button.classList.contains("liked")){

        number++;

        button.classList.add("liked");
        button.innerHTML="❤️ Disukai";

    }else{

        number--;

        button.classList.remove("liked");
        button.innerHTML="👍 Suka";

    }

    likes.textContent="👍 "+number;
}


/* COMMENT */

function commentPost(button){

    const post =
        button.closest(".post");

    const comments =
        post.querySelector(".comments");

    const text =
        prompt("Tulis komentar:");

    if(text && text.trim()){

        const div =
            document.createElement("div");

        div.className="comment";

        div.innerHTML=
            "<b>Steven:</b> "+
            escapeHTML(text);

        comments.appendChild(div);
    }
}


/* SHARE */

function sharePost(){

    if(navigator.share){

        navigator.share({
            title:"Fasebook",
            text:"Lihat postingan ini di Fasebook!"
        });

    }else{

        alert("Postingan siap dibagikan!");

    }
}


/* SEARCH */

function searchPosts(){

    const query =
        document
        .getElementById("searchInput")
        .value
        .toLowerCase();

    const posts =
        document.querySelectorAll(".post");

    posts.forEach(post=>{

        const text =
            post.innerText.toLowerCase();

        post.style.display =
            text.includes(query)
            ? ""
            : "none";

    });
}


/* DARK MODE */

function toggleDark(){

    document.body.classList.toggle("dark");

    if(document.body.classList.contains("dark")){

        document.body.style.background="#18191a";
        document.body.style.color="#e4e6eb";

        document
        .querySelectorAll(".card")
        .forEach(card=>{
            card.style.background="#242526";
            card.style.color="#e4e6eb";
        });

        document
        .querySelector(".navbar")
        .style.background="#242526";

    }else{

        location.reload();

    }
}


/* STORY */

function openStory(){

    alert("Fitur cerita siap digunakan.");

}


/* SECURITY */

function escapeHTML(text){

    const div =
        document.createElement("div");

    div.textContent=text;

    return div.innerHTML;

}

</script>

</body>
</html>
