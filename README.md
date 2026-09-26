<!DOCTYPE html>
<html lang="ar" dir="rtl">

<head>

<meta charset="UTF-8">

<meta
    name="viewport"
    content="width=device-width, initial-scale=1.0"
>

<title>
    Lecture AI Studio
</title>

<!-- Puter.js -->
<script src="https://js.puter.com/v2/"></script>

<!-- PDF.js -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/pdf.js/3.11.174/pdf.min.js"></script>

<style>

*{
    box-sizing:border-box;
}

body{

    margin:0;

    font-family:
        -apple-system,
        BlinkMacSystemFont,
        "Segoe UI",
        Tahoma,
        Arial,
        sans-serif;

    min-height:100vh;

    color:white;

    background:
        radial-gradient(
            circle at top,
            #293a68,
            #0b1020 55%,
            #050812
        );

}

.container{

    width:min(1100px,94%);

    margin:auto;

    padding:25px 0 60px;

}

.header{

    text-align:center;

    margin-bottom:25px;

}

.header h1{

    font-size:34px;

    margin:0;

}

.header p{

    color:#b8c3da;

    margin-top:10px;

}


/* =========================
   CARDS
========================= */

.card{

    background:
        rgba(255,255,255,.065);

    border:
        1px solid rgba(255,255,255,.12);

    border-radius:22px;

    padding:22px;

    margin-bottom:20px;

    backdrop-filter:blur(15px);

}


/* =========================
   AUTH
========================= */

.auth-card{

    display:flex;

    align-items:center;

    justify-content:space-between;

    gap:15px;

    flex-wrap:wrap;

}

.auth-info{

    display:flex;

    align-items:center;

    gap:12px;

}

.auth-icon{

    width:48px;

    height:48px;

    border-radius:50%;

    display:flex;

    align-items:center;

    justify-content:center;

    font-size:24px;

    background:#182541;

}

.auth-name{

    font-weight:bold;

}

.auth-status{

    font-size:13px;

    color:#9ca9c2;

    margin-top:3px;

}

.auth-buttons{

    display:flex;

    gap:10px;

    flex-wrap:wrap;

}


/* =========================
   BUTTONS
========================= */

button{

    border:none;

    border-radius:13px;

    padding:12px 18px;

    font-size:15px;

    font-weight:bold;

    cursor:pointer;

    color:white;

    transition:.2s;

}

button:hover{

    transform:translateY(-1px);

}

button:disabled{

    opacity:.45;

    cursor:not-allowed;

    transform:none;

}

.login-btn{

    background:
        linear-gradient(
            135deg,
            #667eea,
            #764ba2
        );

}

.logout-btn{

    background:#45202b;

    color:#ffb6c0;

}

.main-btn{

    width:100%;

    margin-top:20px;

    padding:16px;

    background:
        linear-gradient(
            135deg,
            #667eea,
            #764ba2
        );

    font-size:17px;

}

.secondary-btn{

    background:#1b2845;

}


/* =========================
   UPLOAD
========================= */

.upload{

    border:
        2px dashed rgba(255,255,255,.25);

    border-radius:20px;

    padding:45px 20px;

    text-align:center;

    cursor:pointer;

    transition:.2s;

}

.upload:hover,
.upload.drag{

    border-color:#8da9ff;

    background:
        rgba(100,130,255,.08);

}

.upload-icon{

    font-size:55px;

}

.upload h2{

    margin:10px 0;

}

.upload p{

    color:#9da8bd;

}

input[type=file]{

    display:none;

}

.file-name{

    margin-top:15px;

    color:#9db7ff;

    font-weight:bold;

}


/* =========================
   CONTROLS
========================= */

.controls{

    display:grid;

    grid-template-columns:
        repeat(
            auto-fit,
            minmax(180px,1fr)
        );

    gap:15px;

    margin-top:20px;

}

label{

    display:block;

    color:#c4cde0;

    font-size:14px;

    margin-bottom:7px;

}

select{

    width:100%;

    padding:12px;

    border-radius:12px;

    border:
        1px solid rgba(255,255,255,.15);

    background:#11182c;

    color:white;

    outline:none;

}


/* =========================
   PROGRESS
========================= */

.progress-wrap{

    display:none;

}

.progress-bar{

    width:100%;

    height:12px;

    background:#12192b;

    border-radius:20px;

    overflow:hidden;

}

.progress{

    width:0%;

    height:100%;

    background:
        linear-gradient(
            90deg,
            #667eea,
            #9f7aea
        );

    transition:.3s;

}

.progress-text{

    text-align:center;

    margin-top:10px;

    color:#c0cbe0;

}


/* =========================
   STATUS
========================= */

.status{

    background:#10182b;

    border-radius:14px;

    padding:15px;

    line-height:1.8;

    white-space:pre-wrap;

}

.status.success{

    color:#b8ffd0;

    background:
        rgba(50,255,130,.07);

}

.status.error{

    color:#ffb8b8;

    background:
        rgba(255,60,80,.08);

}


/* =========================
   TEXT
========================= */

.lecture-text{

    max-height:350px;

    overflow:auto;

    background:#080d19;

    padding:15px;

    border-radius:14px;

    line-height:1.9;

    color:#d0d7e8;

    white-space:pre-wrap;

}


/* =========================
   GALLERY
========================= */

.gallery{

    display:grid;

    grid-template-columns:
        repeat(
            auto-fit,
            minmax(280px,1fr)
        );

    gap:20px;

}

.image-card{

    overflow:hidden;

    border-radius:18px;

    background:#0d1425;

    border:
        1px solid rgba(255,255,255,.1);

}

.image-card img{

    width:100%;

    display:block;

    background:white;

}

.image-info{

    padding:15px;

}

.image-title{

    font-weight:bold;

    margin-bottom:8px;

}

.image-concept{

    color:#aeb9d0;

    font-size:13px;

    line-height:1.7;

}

.download-btn{

    width:100%;

    margin-top:12px;

    background:#202e4d;

}


/* =========================
   LOGS
========================= */

.logs{

    max-height:350px;

    overflow:auto;

    background:#050914;

    border-radius:14px;

    padding:15px;

    direction:ltr;

    text-align:left;

    font-family:monospace;

    font-size:13px;

    line-height:1.8;

}

.log-info{

    color:#9db8ff;

}

.log-ok{

    color:#8ff0ad;

}

.log-error{

    color:#ff8585;

}


/* =========================
   HELP
========================= */

.help{

    color:#98a5bc;

    font-size:13px;

    line-height:1.8;

}

.hidden{

    display:none!important;

}

</style>

</head>


<body>


<div class="container">


    <!-- =========================
         HEADER
    ========================== -->

    <div class="header">

        <h1>
            📖 Lecture AI Studio
        </h1>

        <p>
            PDF → تحليل المحاضرة → صور تعليمية بالذكاء الاصطناعي
        </p>

    </div>


    <!-- =========================
         AUTH CARD
    ========================== -->

    <div class="card auth-card">


        <div class="auth-info">

            <div
                id="authIcon"
                class="auth-icon"
            >
                🔒
            </div>

            <div>

                <div
                    id="authName"
                    class="auth-name"
                >
                    غير مسجل الدخول
                </div>

                <div
                    id="authStatus"
                    class="auth-status"
                >
                    سجلي الدخول إلى Puter قبل تشغيل الذكاء الاصطناعي
                </div>

            </div>

        </div>


        <div class="auth-buttons">

            <button
                id="loginBtn"
                class="login-btn"
            >
                🔐 تسجيل الدخول إلى Puter
            </button>


            <button
                id="logoutBtn"
                class="logout-btn hidden"
            >
                🚪 تسجيل الخروج
            </button>

        </div>

    </div>


    <!-- =========================
         UPLOAD
    ========================== -->

    <div class="card">


        <div
            id="dropArea"
            class="upload"
        >

            <div class="upload-icon">
                📄
            </div>

            <h2>
                اختاري محاضرة PDF
            </h2>

            <p>
                اضغطي هنا أو اسحبي ملف PDF
            </p>

            <input
                id="pdfInput"
                type="file"
                accept="application/pdf"
            >

            <div
                id="fileName"
                class="file-name hidden"
            ></div>

        </div>


        <div class="controls">


            <div>

                <label>
                    عدد الصور
                </label>

                <select id="imageCount">

                    <option value="3">
                        3 صور
                    </option>

                    <option
                        value="5"
                        selected
                    >
                        5 صور
                    </option>

                    <option value="8">
                        8 صور
                    </option>

                    <option value="10">
                        10 صور
                    </option>

                </select>

            </div>


            <div>

                <label>
                    شكل الصور
                </label>

                <select id="ratio">

                    <option value="16:9">
                        16:9 — محاضرة
                    </option>

                    <option value="1:1">
                        1:1 — مربع
                    </option>

                    <option value="9:16">
                        9:16 — ستوري
                    </option>

                    <option value="4:3">
                        4:3
                    </option>

                </select>

            </div>


        </div>


        <button
            id="startBtn"
            class="main-btn"
            disabled
        >
            🚀 ابدأ إنشاء الصور
        </button>


        <div class="help">

            يجب تسجيل الدخول أولاً.
            لن يبدأ الموقع بقراءة أو تحليل المحاضرة
            قبل التأكد من تسجيل الدخول.

        </div>


    </div>


    <!-- =========================
         PROGRESS
    ========================== -->

    <div
        id="progressWrap"
        class="card progress-wrap"
    >

        <div class="progress-bar">

            <div
                id="progress"
                class="progress"
            ></div>

        </div>

        <div
            id="progressText"
            class="progress-text"
        >
            0%
        </div>

    </div>


    <!-- =========================
         STATUS
    ========================== -->

    <div class="card">

        <h3>
            📊 حالة المشروع
        </h3>

        <div
            id="status"
            class="status"
        >
            سجلي الدخول ثم اختاري محاضرة PDF.
        </div>

    </div>


    <!-- =========================
         EXTRACTED TEXT
    ========================== -->

    <div
        id="textCard"
        class="card hidden"
    >

        <h3>
            📝 النص المستخرج من المحاضرة
        </h3>

        <div
            id="lectureText"
            class="lecture-text"
        ></div>

    </div>


    <!-- =========================
         GALLERY
    ========================== -->

    <div
        id="galleryCard"
        class="card hidden"
    >

        <h3>
            🎨 الصور الناتجة
        </h3>

        <div
            id="gallery"
            class="gallery"
        ></div>

    </div>


    <!-- =========================
         LOGS
    ========================== -->

    <div class="card">

        <h3>
            🛠️ سجل التشغيل
        </h3>

        <div
            id="logs"
            class="logs"
        ></div>

    </div>


</div>


<script>


/* =========================================================
   PDF.JS
========================================================= */

pdfjsLib.GlobalWorkerOptions.workerSrc =
    "https://cdnjs.cloudflare.com/ajax/libs/pdf.js/3.11.174/pdf.worker.min.js";


/* =========================================================
   VARIABLES
========================================================= */

let selectedFile = null;


/* =========================================================
   ELEMENTS
========================================================= */

const loginBtn =
    document.getElementById("loginBtn");

const logoutBtn =
    document.getElementById("logoutBtn");

const authIcon =
    document.getElementById("authIcon");

const authName =
    document.getElementById("authName");

const authStatus =
    document.getElementById("authStatus");

const pdfInput =
    document.getElementById("pdfInput");

const dropArea =
    document.getElementById("dropArea");

const fileName =
    document.getElementById("fileName");

const startBtn =
    document.getElementById("startBtn");

const statusBox =
    document.getElementById("status");

const progressWrap =
    document.getElementById("progressWrap");

const progress =
    document.getElementById("progress");

const progressText =
    document.getElementById("progressText");

const textCard =
    document.getElementById("textCard");

const lectureText =
    document.getElementById("lectureText");

const galleryCard =
    document.getElementById("galleryCard");

const gallery =
    document.getElementById("gallery");

const logs =
    document.getElementById("logs");


/* =========================================================
   LOG
========================================================= */

function log(message,type="info"){

    const line =
        document.createElement("div");

    if(type === "ok")
        line.className = "log-ok";

    else if(type === "error")
        line.className = "log-error";

    else
        line.className = "log-info";


    const time =
        new Date().toLocaleTimeString();


    line.textContent =
        `[${time}] ${message}`;


    logs.appendChild(line);

    logs.scrollTop =
        logs.scrollHeight;

}


/* =========================================================
   STATUS
========================================================= */

function setStatus(message,type="normal"){

    statusBox.textContent =
        message;

    statusBox.className =
        "status";


    if(type === "success")
        statusBox.classList.add("success");


    if(type === "error")
        statusBox.classList.add("error");

}


/* =========================================================
   PROGRESS
========================================================= */

function setProgress(value,message){

    value =
        Math.max(
            0,
            Math.min(
                100,
                value
            )
        );


    progress.style.width =
        value + "%";


    progressText.textContent =
        `${Math.round(value)}% — ${message}`;

}


/* =========================================================
   AUTH STATE
========================================================= */

async function updateAuthUI(){

    try{

        if(
            typeof puter === "undefined" ||
            !puter.auth
        ){

            authIcon.textContent =
                "❌";

            authName.textContent =
                "Puter غير محمل";

            authStatus.textContent =
                "تأكدي من وجود الإنترنت";

            loginBtn.disabled =
                true;

            startBtn.disabled =
                true;

            return;

        }


        const signedIn =
            puter.auth.isSignedIn();


        if(signedIn){

            authIcon.textContent =
                "🟢";


            loginBtn.classList.add(
                "hidden"
            );


            logoutBtn.classList.remove(
                "hidden"
            );


            startBtn.disabled =
                !selectedFile;


            try{

                const user =
                    await puter.auth.getUser();


                if(user){

                    authName.textContent =
                        user.username ||
                        user.email ||
                        "حساب Puter";

                }else{

                    authName.textContent =
                        "حساب Puter";

                }

            }catch{

                authName.textContent =
                    "حساب Puter";

            }


            authStatus.textContent =
                "تم تسجيل الدخول ويمكن تشغيل الذكاء الاصطناعي";


            log(
                "🟢 المستخدم مسجل الدخول إلى Puter",
                "ok"
            );

        }else{

            authIcon.textContent =
                "🔒";


            authName.textContent =
                "غير مسجل الدخول";


            authStatus.textContent =
                "سجلي الدخول إلى Puter أولاً";


            loginBtn.classList.remove(
                "hidden"
            );


            logoutBtn.classList.add(
                "hidden"
            );


            startBtn.disabled =
                true;

        }


    }catch(error){

        log(
            "خطأ في فحص تسجيل الدخول: " +
            formatError(error),
            "error"
        );

    }

}


/* =========================================================
   LOGIN
========================================================= */

loginBtn.addEventListener(
    "click",
    async function(){

        /*
          مهم جداً:
          signIn() يتم استدعاؤه مباشرة
          من حدث الضغط على الزر.
        */

        loginBtn.disabled =
            true;


        setStatus(
            "🔐 جارٍ فتح تسجيل الدخول إلى Puter..."
        );


        log(
            "🔐 محاولة تسجيل الدخول..."
        );


        try{

            const result =
                await puter.auth.signIn();


            console.log(
                "Puter signIn result:",
                result
            );


            log(
                "✅ اكتمل تسجيل الدخول",
                "ok"
            );


            setStatus(
                "✅ تم تسجيل الدخول بنجاح.",
                "success"
            );


            await updateAuthUI();


        }catch(error){

            console.error(
                "LOGIN ERROR:",
                error
            );


            const message =
                formatError(error);


            log(
                "❌ فشل تسجيل الدخول: " +
                message,
                "error"
            );


            setStatus(
                "❌ لم يكتمل تسجيل الدخول.\n\n" +
                message,
                "error"
            );


        }finally{

            loginBtn.disabled =
                false;

        }

    }
);


/* =========================================================
   LOGOUT
========================================================= */

logoutBtn.addEventListener(
    "click",
    async function(){

        try{

            puter.auth.signOut();


            selectedFile =
                null;


            pdfInput.value =
                "";


            fileName.classList.add(
                "hidden"
            );


            startBtn.disabled =
                true;


            gallery.innerHTML =
                "";


            galleryCard.classList.add(
                "hidden"
            );


            textCard.classList.add(
                "hidden"
            );


            setStatus(
                "🚪 تم تسجيل الخروج من Puter."
            );


            log(
                "🚪 تم تسجيل الخروج",
                "ok"
            );


            await updateAuthUI();


        }catch(error){

            log(
                "❌ فشل تسجيل الخروج: " +
                formatError(error),
                "error"
            );

        }

    }
);


/* =========================================================
   PDF SELECT
========================================================= */

dropArea.addEventListener(
    "click",
    function(){

        pdfInput.click();

    }
);


pdfInput.addEventListener(
    "change",
    function(){

        if(
            pdfInput.files &&
            pdfInput.files.length
        ){

            selectPDF(
                pdfInput.files[0]
            );

        }

    }
);


/* =========================================================
   DRAG DROP
========================================================= */

dropArea.addEventListener(
    "dragover",
    function(event){

        event.preventDefault();

        dropArea.classList.add(
            "drag"
        );

    }
);


dropArea.addEventListener(
    "dragleave",
    function(){

        dropArea.classList.remove(
            "drag"
        );

    }
);


dropArea.addEventListener(
    "drop",
    function(event){

        event.preventDefault();

        dropArea.classList.remove(
            "drag"
        );


        const file =
            event.dataTransfer.files[0];


        if(file){

            selectPDF(file);

        }

    }
);


/* =========================================================
   SELECT PDF
========================================================= */

function selectPDF(file){

    if(
        file.type !== "application/pdf" &&
        !file.name
            .toLowerCase()
            .endsWith(".pdf")
    ){

        setStatus(
            "❌ الملف ليس PDF.",
            "error"
        );

        return;

    }


    selectedFile =
        file;


    fileName.textContent =
        `📄 ${file.name} — ${(file.size / 1024 / 1024).toFixed(2)} MB`;


    fileName.classList.remove(
        "hidden"
    );


    if(
        puter.auth.isSignedIn()
    ){

        startBtn.disabled =
            false;


        setStatus(
            "✅ الملف جاهز. اضغطي بدء إنشاء الصور.",
            "success"
        );

    }else{

        startBtn.disabled =
            true;


        setStatus(
            "🔒 الملف جاهز، لكن يجب تسجيل الدخول إلى Puter أولاً."
        );

    }


    log(
        `📄 تم اختيار: ${file.name}`,
        "ok"
    );

}


/* =========================================================
   EXTRACT PDF TEXT
========================================================= */

async function extractPDFText(file){

    log(
        "📖 استخراج النص من PDF..."
    );


    setStatus(
        "📖 قراءة المحاضرة..."
    );


    const buffer =
        await file.arrayBuffer();


    const pdf =
        await pdfjsLib
            .getDocument({
                data:buffer
            })
            .promise;


    let fullText = "";


    log(
        `📄 عدد صفحات PDF: ${pdf.numPages}`,
        "ok"
    );


    for(
        let pageNumber=1;
        pageNumber<=pdf.numPages;
        pageNumber++
    ){

        const page =
            await pdf.getPage(
                pageNumber
            );


        const content =
            await page.getTextContent();


        const text =
            content.items
                .map(
                    item => item.str
                )
                .join(" ")
                .replace(
                    /\s+/g,
                    " "
                )
                .trim();


        if(text){

            fullText +=
                `\n\n--- الصفحة ${pageNumber} ---\n${text}`;

        }


        const percentage =
            (pageNumber / pdf.numPages) * 25;


        setProgress(
            percentage,
            `قراءة الصفحة ${pageNumber} من ${pdf.numPages}`
        );

    }


    return fullText.trim();

}


/* =========================================================
   CLEAN
========================================================= */

function cleanText(text){

    return text
        .replace(
            /\u0000/g,
            ""
        )
        .replace(
            /[ \t]+/g,
            " "
        )
        .replace(
            /\n{3,}/g,
            "\n\n"
        )
        .trim();

}


/* =========================================================
   CHUNKS
========================================================= */

function createChunks(
    text,
    maxLength=6500
){

    const paragraphs =
        text
            .split(/\n+/)
            .map(
                x => x.trim()
            )
            .filter(Boolean);


    const chunks = [];

    let current = "";


    for(
        const paragraph
        of paragraphs
    ){

        if(
            current.length +
            paragraph.length +
            1
            <= maxLength
        ){

            current +=
                (current ? "\n" : "") +
                paragraph;

        }else{

            if(current)
                chunks.push(current);


            current =
                paragraph;

        }

    }


    if(current)
        chunks.push(current);


    return chunks;

}


/* =========================================================
   AI RESPONSE TEXT
========================================================= */

function getAIText(result){

    if(!result)
        return "";


    if(
        result.message &&
        typeof result.message.content ===
        "string"
    ){

        return result.message.content.trim();

    }


    if(
        typeof result.content ===
        "string"
    ){

        return result.content.trim();

    }


    if(
        typeof result.text ===
        "string"
    ){

        return result.text.trim();

    }


    if(
        result.message &&
        Array.isArray(
            result.message.content
        )
    ){

        return result.message.content
            .map(
                part => {

                    if(
                        typeof part ===
                        "string"
                    )
                        return part;


                    return part?.text || "";

                }
            )
            .join("")
            .trim();

    }


    return "";

}


/* =========================================================
   PARSE JSON
========================================================= */

function parseJSON(text){

    if(!text){

        throw new Error(
            "الذكاء الاصطناعي أعاد استجابة فارغة."
        );

    }


    let cleaned =
        text
            .trim();


    cleaned =
        cleaned
            .replace(
                /^```json/i,
                ""
            )
            .replace(
                /^```/i,
                ""
            )
            .replace(
                /```$/i,
                ""
            )
            .trim();


    const first =
        cleaned.indexOf("{");


    const last =
        cleaned.lastIndexOf("}");


    if(
        first !== -1 &&
        last !== -1
    ){

        cleaned =
            cleaned.substring(
                first,
                last + 1
            );

    }


    try{

        return JSON.parse(
            cleaned
        );

    }catch(error){

        console.error(
            "RAW AI:",
            cleaned
        );


        throw new Error(
            "لم أستطع قراءة نتيجة تحليل المحاضرة."
        );

    }

}


/* =========================================================
   ANALYZE LECTURE
========================================================= */

async function analyzeLecture(text){

    log(
        "🧠 الذكاء الاصطناعي يحلل المحاضرة..."
    );


    setStatus(
        "🧠 تحليل أهم المفاهيم في المحاضرة..."
    );


    const imageCount =
        Number(
            document.getElementById(
                "imageCount"
            ).value
        );


    const chunks =
        createChunks(
            text,
            6000
        );


    log(
        `🧩 تم إنشاء ${chunks.length} جزء`,
        "ok"
    );


    /*
      نأخذ أجزاء موزعة من المحاضرة
      حتى لا نركز على البداية فقط.
    */

    let selected = [];


    if(
        chunks.length <= imageCount
    ){

        selected =
            chunks;

    }else{

        for(
            let i=0;
            i<imageCount;
            i++
        ){

            const index =
                Math.floor(
                    i *
                    (chunks.length - 1) /
                    (imageCount - 1)
                );


            selected.push(
                chunks[index]
            );

        }

    }


    const material =
        selected.join(
            "\n\n====================\n\n"
        );


    const prompt = `

You are an expert university educational designer.

Analyze the following university lecture.

LECTURE:

${material}

Create ${imageCount} different educational visual concepts.

Rules:

1. Only use information supported by the lecture.
2. Do not invent scientific facts.
3. Each image must explain an important concept.
4. Use scientific diagrams, medical illustrations, anatomy, molecular structures, laboratory objects, 3D scientific visualization, or infographics when appropriate.
5. Avoid long paragraphs inside images.
6. Use short English labels only when necessary.
7. Make each image visually different.
8. The images are for a university student studying the lecture.

Return ONLY valid JSON:

{
  "scenes": [
    {
      "title": "Short title",
      "concept": "What this image teaches",
      "prompt": "Detailed English visual prompt"
    }
  ]
}

Return exactly ${imageCount} scenes.

`;


    let result;


    try{

        /*
          بعد تسجيل الدخول،
          Puter لا يحتاج API key هنا.
        */

        result =
            await puter.ai.chat(
                prompt
            );


    }catch(error){

        console.error(
            "CHAT ERROR:",
            error
        );


        throw new Error(
            "فشل تحليل المحاضرة:\n" +
            formatError(error)
        );

    }


    const aiText =
        getAIText(
            result
        );


    if(!aiText){

        console.error(
            "RAW CHAT RESULT:",
            result
        );


        throw new Error(
            "Puter أعاد استجابة بدون نص."
        );

    }


    log(
        "✅ تم تحليل المحاضرة",
        "ok"
    );


    const data =
        parseJSON(
            aiText
        );


    if(
        !data.scenes ||
        !Array.isArray(data.scenes)
    ){

        throw new Error(
            "الاستجابة لا تحتوي على scenes."
        );

    }


    return data.scenes
        .slice(
            0,
            imageCount
        );

}


/* =========================================================
   RATIO
========================================================= */

function ratioObject(ratio){

    const parts =
        ratio.split(":");


    return {

        w:
            Number(parts[0]),

        h:
            Number(parts[1])

    };

}


/* =========================================================
   GENERATE IMAGE
========================================================= */

async function generateImage(
    scene,
    index,
    total
){

    const ratio =
        document.getElementById(
            "ratio"
        ).value;


    const prompt = `

Create a professional university educational scientific illustration.

MAIN TOPIC:
${scene.title}

CONCEPT:
${scene.concept}

VISUAL DESCRIPTION:
${scene.prompt}

STYLE:

Professional educational scientific visualization.
Clean composition.
High visual clarity.
Modern medical/scientific illustration.
Detailed but easy for a university student to understand.
Use realistic 3D elements when appropriate.
Use diagrams when they explain the concept better.
Use short English labels only when absolutely necessary.
Do not create long text.
Do not invent scientific information.
No watermark.

`;


    log(
        `🎨 توليد الصورة ${index+1} من ${total}...`
    );


    setStatus(
        `🎨 توليد الصورة ${index+1} من ${total}...`
    );


    let image;


    try{

        image =
            await puter.ai.txt2img(
                prompt,
                {

                    model:
                        "gemini-3.1-flash-image",

                    ratio:
                        ratioObject(
                            ratio
                        ),

                    quality:
                        "1K"

                }
            );


    }catch(error){

        console.error(
            "IMAGE ERROR:",
            error
        );


        throw new Error(
            `فشل توليد الصورة ${index+1}:\n` +
            formatError(error)
        );

    }


    if(!image){

        throw new Error(
            "Puter لم يرجع صورة."
        );

    }


    const src =
        image.src;


    if(
        !src ||
        typeof src !== "string"
    ){

        throw new Error(
            "رابط الصورة غير صالح."
        );

    }


    return {

        title:
            scene.title,

        concept:
            scene.concept,

        prompt:
            prompt,

        src:
            src

    };

}


/* =========================================================
   DISPLAY IMAGE
========================================================= */

function addImageCard(
    data,
    index
){

    galleryCard.classList.remove(
        "hidden"
    );


    const card =
        document.createElement(
            "div"
        );


    card.className =
        "image-card";


    const image =
        document.createElement(
            "img"
        );


    image.src =
        data.src;


    image.alt =
        data.title;


    const info =
        document.createElement(
            "div"
        );


    info.className =
        "image-info";


    const title =
        document.createElement(
            "div"
        );


    title.className =
        "image-title";


    title.textContent =
        `${index+1}. ${data.title}`;


    const concept =
        document.createElement(
            "div"
        );


    concept.className =
        "image-concept";


    concept.textContent =
        data.concept;


    const download =
        document.createElement(
            "button"
        );


    download.className =
        "download-btn";


    download.textContent =
        "⬇️ حفظ الصورة";


    download.onclick =
        function(){

            saveImage(
                data.src,
                `lecture-image-${index+1}.png`
            );

        };


    info.appendChild(
        title
    );


    info.appendChild(
        concept
    );


    info.appendChild(
        download
    );


    card.appendChild(
        image
    );


    card.appendChild(
        info
    );


    gallery.appendChild(
        card
    );

}


/* =========================================================
   SAVE IMAGE
========================================================= */

function saveImage(
    src,
    filename
){

    try{

        const link =
            document.createElement(
                "a"
            );


        link.href =
            src;


        link.download =
            filename;


        document.body.appendChild(
            link
        );


        link.click();


        link.remove();


    }catch(error){

        log(
            "تعذر التنزيل التلقائي. اضغطي مطولاً على الصورة واحفظيها.",
            "error"
        );

    }

}


/* =========================================================
   FORMAT ERROR
========================================================= */

function formatError(error){

    if(!error)
        return "خطأ غير معروف";


    if(
        typeof error ===
        "string"
    )
        return error;


    /*
      Puter أحياناً يعيد:

      {
        error:{
          code:"",
          message:""
        }
      }

    */

    if(error.error){

        return JSON.stringify(
            error,
            null,
            2
        );

    }


    const result = [];


    if(error.code)
        result.push(
            `code: ${error.code}`
        );


    if(error.errorCode)
        result.push(
            `errorCode: ${error.errorCode}`
        );


    if(error.message)
        result.push(
            error.message
        );


    if(error.status)
        result.push(
            `status: ${error.status}`
        );


    if(result.length)
        return result.join(
            " | "
        );


    try{

        return JSON.stringify(
            error,
            null,
            2
        );

    }catch{

        return String(
            error
        );

    }

}


/* =========================================================
   MAIN
========================================================= */

async function run(){

    logs.innerHTML =
        "";


    /*
      فحص Puter
    */

    if(
        typeof puter ===
        "undefined"
    ){

        setStatus(
            "❌ Puter.js لم يتم تحميله. تأكدي من الإنترنت.",
            "error"
        );

        return;

    }


    /*
      فحص تسجيل الدخول
      قبل قراءة PDF
    */

    if(
        !puter.auth.isSignedIn()
    ){

        setStatus(
            "🔒 يجب تسجيل الدخول إلى Puter أولاً.",
            "error"
        );


        log(
            "❌ التشغيل مرفوض: المستخدم غير مسجل الدخول.",
            "error"
        );


        return;

    }


    if(!selectedFile){

        setStatus(
            "❌ اختاري ملف PDF أولاً.",
            "error"
        );

        return;

    }


    startBtn.disabled =
        true;


    progressWrap.style.display =
        "block";


    gallery.innerHTML =
        "";


    galleryCard.classList.add(
        "hidden"
    );


    textCard.classList.add(
        "hidden"
    );


    try{


        /* =====================
           STEP 1
        ===================== */

        const rawText =
            await extractPDFText(
                selectedFile
            );


        const text =
            cleanText(
                rawText
            );


        log(
            `📄 تم استخراج النص`,
            "ok"
        );


        log(
            `📝 عدد الأحرف: ${text.length}`,
            "ok"
        );


        if(
            text.length < 100
        ){

            throw new Error(
                "هذا الـPDF يبدو مصوراً ولا يحتوي على نص قابل للاستخراج.\n\n" +
                "النسخة الحالية تحتاج PDF يحتوي نصاً حقيقياً."
            );

        }


        lectureText.textContent =
            text;


        textCard.classList.remove(
            "hidden"
        );


        setProgress(
            30,
            "تم استخراج النص"
        );


        /* =====================
           STEP 2
        ===================== */

        const scenes =
            await analyzeLecture(
                text
            );


        log(
            `🎯 تم إنشاء ${scenes.length} أفكار للصور`,
            "ok"
        );


        setProgress(
            40,
            "بدء توليد الصور"
        );


        /* =====================
           STEP 3
        ===================== */

        for(
            let i=0;
            i<scenes.length;
            i++
        ){

            const image =
                await generateImage(
                    scenes[i],
                    i,
                    scenes.length
                );


            addImageCard(
                image,
                i
            );


            const percentage =
                40 +
                (
                    (i+1) /
                    scenes.length
                ) *
                60;


            setProgress(
                percentage,
                `اكتملت الصورة ${i+1} من ${scenes.length}`
            );


            log(
                `✅ اكتملت الصورة ${i+1}`,
                "ok"
            );

        }


        setProgress(
            100,
            "اكتملت العملية"
        );


        setStatus(
            `🎉 تمت العملية بنجاح!\n\nتم إنشاء ${scenes.length} صور تعليمية من المحاضرة.`,
            "success"
        );


        log(
            "🎉 اكتمل المشروع بالكامل.",
            "ok"
        );


    }catch(error){

        console.error(
            "FULL PROJECT ERROR:",
            error
        );


        const message =
            formatError(
                error
            );


        setStatus(
            "❌ حدث خطأ:\n\n" +
            message,
            "error"
        );


        log(
            "❌ " + message,
            "error"
        );


    }finally{

        startBtn.disabled =
            !(
                selectedFile &&
                puter.auth.isSignedIn()
            );

    }

}


/* =========================================================
   START BUTTON
========================================================= */

startBtn.addEventListener(
    "click",
    run
);


/* =========================================================
   INITIALIZATION
========================================================= */

window.addEventListener(
    "load",
    async function(){

        log(
            "🚀 تم تحميل الموقع."
        );


        await new Promise(
            resolve =>
                setTimeout(
                    resolve,
                    500
                )
        );


        await updateAuthUI();


        if(
            puter &&
            puter.auth &&
            puter.auth.isSignedIn()
        ){

            log(
                "🟢 الحساب مسجل الدخول مسبقاً.",
                "ok"
            );

        }else{

            log(
                "🔒 بانتظار تسجيل الدخول."
            );

        }

    }
);

</script>


</body>

</html>
