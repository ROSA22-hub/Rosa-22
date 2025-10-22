# Rosa-22
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <h1><!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>คู่มือทักษะการอ่าน</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Sarabun:wght@400;500;600;700&display=swap" rel="stylesheet">
    <!-- Chosen Palette: Calm Harmony Neutrals -->
    <!-- Application Structure Plan: ออกแบบแอปพลิเคชันเป็นแดชบอร์ดเชิงโต้ตอบ แบ่งเนื้อหาตามหัวข้อหลัก (ประเภทการอ่าน, เทคนิค, การอ่านร้อยกรอง, การเลือกสื่อ, มารยาท, แบบฝึกหัด) แทนการนำเสนอแบบเส้นตรงตามเอกสารต้นฉบับ โครงสร้างนี้ช่วยให้ผู้ใช้สามารถเลือกเรียนรู้หัวข้อที่สนใจได้ทันที เพิ่มการมีส่วนร่วมและความเข้าใจได้ดีกว่าการอ่านเอกสารยาวๆ แต่ละส่วนถูกออกแบบเป็นโมดูลย่อยที่เข้าใจง่าย พร้อมองค์ประกอบอินเทอร์แอคทีฟ เช่น แท็บ, การ์ดที่คลิกได้, แบบทดสอบจับเวลา และการฝังแบบฟอร์มภายนอก เพื่อส่งเสริมการเรียนรู้เชิงรุก -->
    <!-- Visualization & Content Choices: 
        - ประเภทการอ่าน -> Goal: Compare -> Viz: แท็บอินเทอร์แอคทีฟ -> Interaction: คลิกเพื่อสลับเนื้อหา -> Justification: ช่วยให้เปรียบเทียบเทคนิคการอ่านแต่ละแบบได้ง่าย -> Library/Method: Vanilla JS
        - การอ่านเร็ว -> Goal: Engage/Test -> Viz: แบบทดสอบจับเวลา -> Interaction: เริ่ม-หยุดเวลา, แสดงคำถาม -> Justification: สร้างประสบการณ์เรียนรู้เชิงปฏิบัติ ทำให้ผู้ใช้ทดลองทักษะได้จริง -> Library/Method: Vanilla JS
        - โวหารและสำนวน -> Goal: Inform/Organize -> Viz: การ์ดที่คลิกเพื่อแสดงข้อมูล -> Interaction: คลิกเพื่อเปิดดูคำอธิบายและตัวอย่าง -> Justification: จัดระเบียบข้อมูลที่ซับซ้อนให้เข้าถึงง่าย -> Library/Method: Vanilla JS
        - การเลือกสื่อ -> Goal: Inform/Visualize Data -> Viz: กราฟแท่งเปรียบเทียบ -> Interaction: แสดงข้อมูลแนวโน้มการใช้สื่อ -> Justification: เปลี่ยนข้อมูลเชิงพรรณนาให้เป็นภาพที่น่าสนใจและเข้าใจง่าย -> Library/Method: Chart.js
        - การอ่านร้อยกรอง -> Goal: Inform/Structure -> Viz: แผนผังโครงสร้างด้วย HTML/CSS -> Interaction: แสดงผังจังหวะการอ่าน -> Justification: ทำให้เข้าใจฉันทลักษณ์ที่ซับซ้อนได้ง่ายขึ้นโดยไม่ต้องใช้กราฟิกภายนอก -> Library/Method: HTML/CSS
    -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body {
            font-family: 'Sarabun', sans-serif;
        }
        .nav-link {
            transition: all 0.3s ease;
        }
        .nav-link.active {
            background-color: #0369a1;
            color: white;
        }
        .tab-btn.active {
            border-bottom-color: #0369a1;
            color: #0369a1;
            font-weight: 600;
        }
        .content-section {
            display: none;
        }
        .content-section.active {
            display: block;
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            height: 300px;
            max-height: 400px;
        }
        @media (min-width: 768px) {
            .chart-container {
                height: 400px;
            }
        }
        .form-container {
            border-radius: 0.5rem;
            overflow: hidden;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -2px rgba(0, 0, 0, 0.1);
        }
    </style>
</head>
<body class="bg-stone-50 text-stone-800">

    <div class="min-h-screen flex flex-col">
        <header class="bg-white shadow-md sticky top-0 z-10">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-4">
                <h1 class="text-3xl font-bold text-sky-800">คู่มือทักษะการอ่าน (บทที่ 3)</h1>
                <p class="text-stone-600 mt-1">สำรวจโลกแห่งการอ่านผ่านเครื่องมืออินเทอร์แอคทีฟ</p>
            </div>
        </header>

        <div class="flex-grow max-w-7xl w-full mx-auto px-4 sm:px-6 lg:px-8 py-8">
            <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
                <nav class="md:col-span-1">
                    <ul class="space-y-2 sticky top-24">
                        <li><a href="#" class="nav-link active block w-full text-left px-4 py-2 rounded-md bg-stone-200 hover:bg-sky-700 hover:text-white" data-target="home">หน้าหลัก</a></li>
                        <li><a href="#" class="nav-link block w-full text-left px-4 py-2 rounded-md bg-stone-200 hover:bg-sky-700 hover:text-white" data-target="types">ประเภทของการอ่าน</a></li>
                        <li><a href="#" class="nav-link block w-full text-left px-4 py-2 rounded-md bg-stone-200 hover:bg-sky-700 hover:text-white" data-target="techniques">เทคนิคและโวหาร</a></li>
                        <li><a href="#" class="nav-link block w-full text-left px-4 py-2 rounded-md bg-stone-200 hover:bg-sky-700 hover:text-white" data-target="poetry">การอ่านร้อยกรอง</a></li>
                        <li><a href="#" class="nav-link block w-full text-left px-4 py-2 rounded-md bg-stone-200 hover:bg-sky-700 hover:text-white" data-target="media">การเลือกสื่อการอ่าน</a></li>
                        <li><a href="#" class="nav-link block w-full text-left px-4 py-2 rounded-md bg-stone-200 hover:bg-sky-700 hover:text-white" data-target="etiquette">มารยาทและนิสัย</a></li>
                        <li><a href="#" class="nav-link block w-full text-left px-4 py-2 rounded-md bg-sky-700 text-white hover:bg-sky-800" data-target="exercises">แบบฝึกหัดวัดความรู้</a></li>
                    </ul>
                </nav>

                <main class="md:col-span-3 bg-white p-6 rounded-lg shadow-lg">
                    <section id="home" class="content-section active">
                        <h2 class="text-2xl font-bold text-sky-700 mb-4">สาระสำคัญของการอ่าน</h2>
                        <p class="mb-4">การอ่านเป็นทักษะทางภาษาที่จำเป็นอย่างยิ่งในสังคมปัจจุบัน ช่วยให้เรารับรู้ข่าวสาร แสวงหาความรู้ใหม่ๆ และปรับตัวให้ทันต่อความก้าวหน้าในทุกสาขา การอ่านที่ประสบผลสำเร็จต้องอาศัยความสามารถในการจับใจความสำคัญ วิเคราะห์ วิจารณ์ และปฏิบัติตนอย่างมีมารยาท</p>
                        <div class="bg-sky-50 border-l-4 border-sky-500 p-4 rounded-r-lg">
                            <h3 class="font-semibold text-lg text-sky-800">ผลการเรียนรู้ที่คาดหวัง</h3>
                            <p class="mt-2">เมื่อศึกษาจบบทนี้ คุณจะสามารถ:</p>
                            <ul class="list-disc list-inside mt-2 space-y-1 text-stone-700">
                                <li>อ่านในใจได้คล่องและเร็ว</li>
                                <li>อ่านออกเสียงและทำนองเสนาะได้ถูกต้อง</li>
                                <li>วิเคราะห์ข้อเท็จจริง ข้อคิดเห็น และจุดมุ่งหมายของเรื่องที่อ่านได้</li>
                                <li>เลือกหนังสือและสื่อสารสนเทศเพื่อพัฒนาตนเองได้</li>
                                <li>มีมารยาทในการอ่านและมีนิสัยรักการอ่าน</li>
                            </ul>
                        </div>
                         <p class="mt-6 text-sm text-stone-500">ใช้เมนูด้านซ้ายเพื่อสำรวจหัวข้อต่างๆ ที่น่าสนใจในบทเรียนนี้</p>
                    </section>

                    <section id="types" class="content-section">
                        <h2 class="text-2xl font-bold text-sky-700 mb-4">ประเภทของการอ่าน</h2>
                        <p class="mb-6">การอ่านมีหลายรูปแบบ แต่ละรูปแบบมีจุดประสงค์และหลักการที่แตกต่างกันไป การทำความเข้าใจประเภทของการอ่านจะช่วยให้เราเลือกใช้วิธีที่เหมาะสมกับสถานการณ์และเป้าหมายของเราได้ดีที่สุด ลองคลิกที่แท็บด้านล่างเพื่อเรียนรู้เพิ่มเติม</p>
                        <div id="types-tabs" class="border-b border-stone-200 mb-4">
                            <button class="tab-btn active py-2 px-4 border-b-2 border-transparent" data-target="silent-reading">การอ่านในใจ</button>
                            <button class="tab-btn py-2 px-4 border-b-2 border-transparent" data-target="aloud-reading">การอ่านออกเสียง</button>
                            <button class="tab-btn py-2 px-4 border-b-2 border-transparent" data-target="speed-reading">การอ่านเร็ว</button>
                        </div>
                        <div id="silent-reading" class="tab-content">
                            <h3 class="font-semibold text-lg mb-2">การอ่านในใจ</h3>
                            <p class="mb-3">คือการแปลตัวอักษรเป็นความรู้ความเข้าใจโดยไม่มีการออกเสียง มีจุดประสงค์เพื่อจับใจความสำคัญให้ได้รวดเร็วและถูกต้อง เพื่อความรู้ และความบันเทิง</p>
                            <strong class="font-semibold">หลักการสำคัญ:</strong>
                            <ul class="list-disc list-inside mt-2 space-y-1">
                                <li>ตั้งจุดมุ่งหมายและสมาธิในการอ่าน</li>
                                <li>ไม่ชี้ตามตัวอักษรและไม่ออกเสียงในใจ</li>
                                <li>กวาดสายตาให้กว้าง ไม่ควรอ่านทีละคำ</li>
                                <li>จับใจความสำคัญให้ได้และบันทึกไว้</li>
                            </ul>
                        </div>
                        <div id="aloud-reading" class="tab-content hidden">
                            <h3 class="font-semibold text-lg mb-2">การอ่านออกเสียง</h3>
                            <p class="mb-3">คือการอ่านที่ผู้อื่นสามารถได้ยินเสียง ส่วนใหญ่มักเป็นการอ่านให้ผู้อื่นฟัง เช่น อ่านข่าว อ่านคำปราศรัย หรืออ่านนิทานให้เด็กฟัง</p>
                            <strong class="font-semibold">หลักการสำคัญ:</strong>
                             <ul class="list-disc list-inside mt-2 space-y-1">
                                <li>อ่านให้ถูกต้องตามอักขรวิธีและชัดเจน</li>
                                <li>ใช้น้ำเสียงและจังหวะให้สอดคล้องกับเนื้อหา</li>
                                <li>เว้นวรรคตอนให้ถูกต้อง</li>
                                <li>อ่านด้วยเสียงดังพอเหมาะและเป็นธรรมชาติ</li>
                            </ul>
                        </div>
                        <div id="speed-reading" class="tab-content hidden">
                            <h3 class="font-semibold text-lg mb-2">ทดสอบทักษะการอ่านเร็ว</h3>
                            <p class="mb-3">การอ่านเร็วไม่ใช่แค่การอ่านให้จบไว แต่ต้องจับใจความสำคัญได้ครบถ้วนด้วย ลองทดสอบตัวเองกับเรื่อง "ลมเหนือ" โดยพยายามอ่านให้จบภายใน 8 นาที</p>
                            <div class="border p-4 rounded-lg bg-stone-50">
                                <h4 class="font-bold text-center">ลมเหนือ</h4>
                                <div id="reading-text" class="my-4 max-h-60 overflow-y-auto text-sm">
                                    ลมทุ่งนาหอมกลิ่นฟางข้าวพัดรวยรินอยู่รอบตัว นุชลูกสาวครูปรีชาวิ่งมาบอกพ่อว่า “พ่อคะ นุชขอไปดูเขาแลกข้าวที่บ้านจำเนียรนะคะ" บ้านจำเนียรไหน “บ้านจำเนียรที่มีต้นมะขามโน่นไงคะ มีคนเขาเอาของเยอะแยะมาแลกข้าว นุชไปนะพ่อ" “เดี๋ยวก่อน" “โธ่ พ่อ นุชช้าไม่ได้นุขจะไปช่วยจำเนียรเขาแลกเสื้อ ประเดี๋ยวจำเนียรก็อดได้เสื้อสวยๆ หรอก" ผมชะเง้อดูที่บ้านหลังหนึ่ง อยู่เกือบกลางทุ่งนา บริเวณบ้านล้อมด้วยกอไผ่ ผมเห็นคนเป็นกลุ่มๆ ยืนอยู่กลางบ้านนั้น นุขเห็นผมมองอย่างอยากรู้อยากเห็น จึงเอ่ยว่า “พี่โชคไปกับหนูไหมล่ะ” “เออ โชคไปเป็นเพื่อนน้องก็ดีนะ แดดร้อนอย่างนี้หาหมวกใส่สักใบเถอะ ประเดี๋ยวจะเป็นไข้” ครูปรีชาพูด “นุชไม่มีหมวก" “เอ้อ...เอาผ้าขาวม้าของพ่อไป” ครูปรีชาส่งผ้าขาวม้าให้ลูกสาว นุชได้ผ้าก็เอามาเคียนหัวแล้ว ออกวิ่งนำหน้าผมไป ผมเห็นคน ๆ หนึ่งแต่งตัวแปลกไปกว่าชาวนา ที่ว่าแปลกก็คือเขาใส่เสื้อนุ่งกางเกงเหมือนคน ในจังหวัด อยู่ตรงกลาง ข้างหน้ามีหาบใส่สิ่งของเครื่องใช้ เช่น เสื้อผ้า หม้ออะลูมิเนียม เป็นต้น วันนี้ผมเห็นพ่อของจำเนียรยอมแลกข้าวเปลือกสองถัง กับเสื้อผ้าดอกสีสดใสให้จำเนียรตัวหนึ่ง ป้าแม้นยอมเสียข้าวเปลือกถังหนึ่งแลกกับแก้วน้ำ 3 ใบ ผมกลับมาเล่าให้ครูปรีชาฟัง ครูปรีชาก็ถอนหายใจยาวพูดว่า “คนพวกนี้แหละเป็นเหลือบคอยดูดเลือดชาวนา" “เขาเห็นจำเนียรอยากได้เสื้อผ้า เลยจะเอาข้าวเปลือกตั้ง 2 ถังแลกกับเสื้อตัวเดียว ผมว่าเสื้อตัวนั้นราคาไม่กี่บาทหรอกครับ” “โธ่ครูถึงว่าพวกนี้เป็นเหลือบไงล่ะ เอาเปรียบกันเกินไป” “แต่พวกนั้นไปยอมแลกกับเขาเอง” ผมพูดเสียงอ่อน “ก็เพราะงั้นนะซิ ครูถึงหนักใจแทน โชคคิดดูสิว่ากว่าจะทำนาได้ข้าวถังหนึ่งน่ะ หมดแรงไป เท่าไรมันคุ้มกันไหมล่ะ” “ทำไมชาวนาถึงโง่..." “ไม่ใช่” ครูปรีชาขัดขึ้น "ไม่ได้โง่ แต่ไม่ทันเล่ห์เหลี่ยมพ่อค้าต่างหากล่ะ” “ครูบอกแล้ว บอกอีก บอกจนไม่รู้จะบอกยังไงแล้ว” “ไม่เชื่อครูหรือครับ” “พูดไม่ถูก อย่างพ่อจำเนียรนั่นแกรู้ดีว่าอะไรเป็นอะไร หากแลกข้าวน่ะยังดีกว่าพวกอื่นนะ นั่นไงล่ะมากันเป็นแถว” ครูปรีชาชี้ให้ผมดู คนขี่จักรยานตามกันเป็นแถว แทบทุกคนสวมหมวกกะโล่ มีไม้กลม ๆ ขนาดแขนผูกติตรถจักรยานมาด้วย “ใครครับ" ผมสงสัย “พวกพ่อค้าคนกลางตัวจริง” ครูปรีชาตอบเสียงต่ำ “เป็นพวกนายหน้ารับซื้อข้าวให้โรงสี อีกที หนึ่ง เธอเห็นไม้ท่อนกลมนั่นไหมล่ะ" "ครับ" “ไม้นั้นแหละเขาเอาไว้รีดข้าวเปลือกดูเมล็ดก่อนตีราคา” “ทำไมต้องตีราคาด้วยเล่า" “เพราะว่าข้าวที่ชาวนาทำได้มีคุณภาพต่าง ๆ กันนะสีโชค นี่แหละเป็นโอกาสให้พ่อค้ามีช่องทาง กดราคาข้าวละ" “เขาท้ายังไงครับ” “เขาจะรีดข้าวดู ถ้าได้ข้าวเมล็ดงามไม่ลีบเล็ก ก็ตีราคาเอาตามใจ ถ้าชาวนาพอใจราคาที่เขาให้ เกิดตกลงขาย เขาก็จะจ่ายเงินให้ล่วงหน้าจำนวนหนึ่ง แล้วก็มาขนข้าวไปโรงสี ส่วนมากคนที่รับซื้อถึงที่ มักจะกดราคาข้าวจนต่ำมาก" “ราคาต่ำ เราก็ไม่ขาย" ผมบอก “แต่ชาวนาต้องการเงิน" “งั้นเอาไปขายเองก็ได้นี่ครับ” “นั้นยิ่งแล้วใหญ่เลย ถ้าหากเธอขนข้าวไปโรงสีจะถูกกดราคามาก เพราะเขาถือว่าเธอไปง้อเขา “อ้าว ทำไมถึงเป็นอย่างนั้นเล่า” ครูปรีชาหัวเราะหึ ๆ แต่แววตาหมอง “ทำไมถึงเป็นเช่นนั้นน่ะหรือ ครูตอบเธอเดี๋ยวนี้ เธอก็คง ไม่เข้าใจหรอก....โชคดี”
                                </div>
                                <div class="flex justify-center items-center space-x-4">
                                    <button id="start-timer" class="bg-sky-600 text-white px-4 py-2 rounded-md hover:bg-sky-700">เริ่มจับเวลา</button>
                                    <button id="stop-timer" class="bg-red-600 text-white px-4 py-2 rounded-md hover:bg-red-700" disabled>หยุดเวลา</button>
                                    <p id="timer-display" class="font-mono text-lg">00:00</p>
                                </div>
                                <div id="timer-result" class="text-center mt-3 font-semibold"></div>
                                <div id="questions" class="mt-4 hidden">
                                    <h4 class="font-semibold">ตอบคำถามเพื่อทดสอบความเข้าใจ:</h4>
                                    <ol class="list-decimal list-inside mt-2 text-sm">
                                        <li>ผู้ที่ใช้สรรพนามว่าผมในเรื่องนี้ชื่ออะไร</li>
                                        <li>พ่อของจำเนียรมีอาชีพอะไร</li>
                                        <li>ทำไมครูปรีชาจึงเรียกพวกที่เอาของมาแลกข้าวว่าตัวเหลือบ</li>
                                        <li>จากเรื่องนี้ ใครเป็นผู้ที่เอาเปรียบชาวนามากที่สุด</li>
                                        <li>ผู้เรียนอ่านเรื่องนี้แล้วได้ข้อคิดอะไรบ้าง</li>
                                    </ol>
                                </div>
                            </div>
                        </div>
                    </section>
                    
                    <section id="techniques" class="content-section">
                        <h2 class="text-2xl font-bold text-sky-700 mb-4">เทคนิคและโวหาร</h2>
                        <p class="mb-6">งานเขียนที่ดีมักมีการใช้โวหารและสำนวนต่างๆ เพื่อสร้างความน่าสนใจและสื่อความหมายได้ลึกซึ้งยิ่งขึ้น การทำความเข้าใจองค์ประกอบเหล่านี้จะช่วยให้เราตีความเรื่องที่อ่านได้อย่างถูกต้อง</p>
                        
                        <div class="mb-8">
                            <h3 class="font-semibold text-xl text-sky-800 mb-3">โวหาร 5 ประเภท</h3>
                            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4">
                                <div class="p-4 bg-stone-100 rounded-lg">
                                    <strong class="font-semibold">บรรยายโวหาร:</strong> การเล่าเรื่องตามลำดับเหตุการณ์อย่างตรงไปตรงมา
                                </div>
                                <div class="p-4 bg-stone-100 rounded-lg">
                                    <strong class="font-semibold">พรรณนาโวหาร:</strong> การให้รายละเอียดอย่างประณีตเพื่อให้ผู้อ่านเห็นภาพและเกิดอารมณ์คล้อยตาม
                                </div>
                                <div class="p-4 bg-stone-100 rounded-lg">
                                    <strong class="font-semibold">เทศนาโวหาร:</strong> การอบรมสั่งสอน ชี้แจงเหตุผล คุณและโทษ
                                </div>
                                <div class="p-4 bg-stone-100 rounded-lg">
                                    <strong class="font-semibold">สาธกโวหาร:</strong> การยกตัวอย่างประกอบเพื่อให้เกิดความชัดเจน
                                </div>
                                <div class="p-4 bg-stone-100 rounded-lg">
                                    <strong class="font-semibold">อุปมาโวหาร:</strong> การเปรียบเทียบเพื่อให้เข้าใจง่ายขึ้น
                                </div>
                            </div>
                        </div>

                        <div>
                            <h3 class="font-semibold text-xl text-sky-800 mb-3">ตัวอย่างสำนวนไทย (คลิกเพื่อดูความหมาย)</h3>
                            <ul id="idiom-list" class="space-y-2">
                                <li class="p-3 bg-sky-50 rounded-md cursor-pointer hover:bg-sky-100" data-meaning="ของตกไปอยู่ในมือผู้อื่นแล้วไม่มีทางได้คืน">อ้อยเข้าปากช้าง</li>
                                <li class="p-3 bg-sky-50 rounded-md cursor-pointer hover:bg-sky-100" data-meaning="ผู้ที่มีความจัดจ้าน เจนสังเวียน">ไก่แก่แม่ปลาช่อน</li>
                                <li class="p-3 bg-sky-50 rounded-md cursor-pointer hover:bg-sky-100" data-meaning="เมื่อเกิดความเสียหายแล้วจึงหาทางป้องกัน">วัวหายล้อมคอก</li>
                                <li class="p-3 bg-sky-50 rounded-md cursor-pointer hover:bg-sky-100" data-meaning="การกระทำที่ไม่รอบคอบ ผลีผลาม">กินข้าวต้มกระโจมกลาง</li>
                            </ul>
                            <div id="idiom-meaning" class="mt-3 p-3 bg-amber-100 border-l-4 border-amber-500 rounded-r-lg text-amber-800 hidden"></div>
                        </div>
                    </section>

                    <section id="poetry" class="content-section">
                        <h2 class="text-2xl font-bold text-sky-700 mb-4">การอ่านร้อยกรอง</h2>
                        <p class="mb-6">การอ่านร้อยกรองให้ไพเราะต้องเข้าใจฉันทลักษณ์ จังหวะ และทำนองของคำประพันธ์แต่ละชนิด ซึ่งเป็นมรดกทางวัฒนธรรมที่ล้ำค่าของไทย</p>
                        <div class="space-y-6">
                            <div>
                                <h3 class="font-semibold text-lg">กลอนสุภาพ (กลอนแปด)</h3>
                                <p class="text-sm text-stone-600 mb-2">จังหวะการอ่านวรรคละ 8-9 คำ: 3-2-3 หรือ 3-3-3</p>
                                <div class="p-3 bg-stone-100 rounded font-mono text-center tracking-wider">เขา-คลอ-ขลุ่ย / ครวญ-เสียง / เพียง-แผ่ว-ผิว<br>ชะ-ลอ-นิ้ว / พลิ้ว-ผ่าน / จน-ม่าน-หมอง</div>
                            </div>
                            <div>
                                <h3 class="font-semibold text-lg">กาพย์ยานี 11</h3>
                                <p class="text-sm text-stone-600 mb-2">จังหวะการอ่าน วรรคหน้า 5 คำ (2-3) วรรคหลัง 6 คำ (3-3)</p>
                                <div class="p-3 bg-stone-100 rounded font-mono text-center tracking-wider">มัส-หมั่น / แกง-แก้ว-ตา<br>หอม-ยี่-หร่า / รส-ร้อน-แรง</div>
                            </div>
                            <div>
                                <h3 class="font-semibold text-lg">โคลงสี่สุภาพ</h3>
                                <p class="text-sm text-stone-600 mb-2">จังหวะการอ่านวรรคหน้า 5 คำ (2-3 หรือ 3-2) วรรคหลัง 2-4 คำ</p>
                                <div class="p-3 bg-stone-100 rounded font-mono text-center tracking-wider">เรื่อง-เรื่อง / ไตรรัตน์-พ้น<br>ริน-รส / พระ-ธรรม-แสดง</div>
                            </div>
                        </div>
                    </section>

                    <section id="media" class="content-section">
                        <h2 class="text-2xl font-bold text-sky-700 mb-4">การเลือกสื่อการอ่าน</h2>
                        <p class="mb-6">ในยุคข้อมูลข่าวสาร การเลือกอ่านหนังสือและสื่อสารสนเทศที่เหมาะสมกับความต้องการ เวลา และโอกาส เป็นสิ่งสำคัญที่จะช่วยให้เราได้รับประโยชน์สูงสุดจากการอ่าน</p>
                        <h3 class="font-semibold text-xl text-sky-800 mb-3">ประเภทของสื่อ</h3>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mb-8">
                            <div class="p-4 border rounded-lg">
                                <strong class="font-semibold">สื่อสิ่งพิมพ์:</strong> หนังสือเรียน ตำรา สารคดี บันเทิงคดี หนังสือพิมพ์ วารสาร ฯลฯ
                                <p class="text-sm mt-1"><strong>หลักการเลือก:</strong> พิจารณาความถูกต้องของเนื้อหา ความน่าเชื่อถือของผู้แต่ง ความเหมาะสมของภาษา และประโยชน์ที่จะได้รับ</p>
                            </div>
                            <div class="p-4 border rounded-lg">
                                <strong class="font-semibold">สื่ออิเล็กทรอนิกส์:</strong> วิทยุ โทรทัศน์ คอมพิวเตอร์ช่วยสอน อินเทอร์เน็ต ฯลฯ
                                <p class="text-sm mt-1"><strong>ประโยชน์:</strong> เข้าถึงข้อมูลได้รวดเร็ว หลากหลาย และส่งเสริมการเรียนรู้ตลอดชีวิต</p>
                            </div>
                        </div>
                        <h3 class="font-semibold text-xl text-sky-800 mb-3 text-center">แนวโน้มการบริโภคสื่อเพื่อการเรียนรู้</h3>
                         <div class="chart-container">
                            <canvas id="mediaChart"></canvas>
                        </div>
                    </section>
                    
                    <section id="etiquette" class="content-section">
                        <h2 class="text-2xl font-bold text-sky-700 mb-4">มารยาทและนิสัยในการอ่าน</h2>
                         <p class="mb-6">การเป็นนักอ่านที่ดีไม่ได้หมายถึงการอ่านเก่งเพียงอย่างเดียว แต่ยังรวมถึงการมีมารยาทที่ดีและการสร้างนิสัยรักการอ่านให้เกิดขึ้นอย่างสม่ำเสมอด้วย</p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                            <div>
                                <h3 class="font-semibold text-xl text-sky-800 mb-3">มารยาทในการอ่าน 📖</h3>
                                <ul class="space-y-2">
                                    <li class="flex items-start"><span class="mr-2 text-green-500">✔</span><span>ไม่ส่งเสียงดังรบกวนผู้อื่น</span></li>
                                    <li class="flex items-start"><span class="mr-2 text-green-500">✔</span><span>ไม่ทำลายหนังสือ เช่น ขีดเขียน หรือฉีก</span></li>
                                    <li class="flex items-start"><span class="mr-2 text-green-500">✔</span><span>อ้างอิงแหล่งที่มาเมื่อคัดลอกเนื้อหา</span></li>
                                    <li class="flex items-start"><span class="mr-2 text-green-500">✔</span><span>เก็บหนังสือเข้าที่เมื่ออ่านเสร็จ</span></li>
                                    <li class="flex items-start"><span class="mr-2 text-red-500">✘</span><span>ไม่ควรอ่านเรื่องส่วนตัวของผู้อื่นโดยไม่ได้รับอนุญาต</span></li>
                                </ul>
                            </div>
                            <div>
                                <h3 class="font-semibold text-xl text-sky-800 mb-3">วิธีสร้างนิสัยรักการอ่าน 💡</h3>
                                <ul class="space-y-2">
                                    <li class="flex items-start"><span class="mr-2 text-sky-500">▶</span><span>เริ่มต้นจากหนังสือที่ตนเองชอบ</span></li>
                                    <li class="flex items-start"><span class="mr-2 text-sky-500">▶</span><span>ทำตนให้เป็นผู้ใฝ่รู้และสงสัยอยู่เสมอ</span></li>
                                    <li class="flex items-start"><span class="mr-2 text-sky-500">▶</span><span>จัดตารางเวลาสำหรับการอ่านเป็นประจำทุกวัน</span></li>
                                    <li class="flex items-start"><span class="mr-2 text-sky-500">▶</span><span>เริ่มจากอ่านช่วงสั้นๆ แล้วค่อยๆ เพิ่มเวลา</span></li>
                                    <li class="flex items-start"><span class="mr-2 text-sky-500">▶</span><span>อ่านอย่างมีสมาธิเพื่อจับใจความสำคัญ</span></li>
                                </ul>
                            </div>
                        </div>
                    </section>
                    
                    <section id="exercises" class="content-section">
                        <h2 class="text-2xl font-bold text-sky-700 mb-4">แบบฝึกหัดวัดความรู้</h2>
                        <p class="mb-6">ทดสอบความเข้าใจในเนื้อหาทักษะการอ่านที่คุณได้เรียนรู้มาทั้งหมด โดยการทำแบบทดสอบวัดความรู้ชุดนี้</p>
                        
                        <div class="form-container">
                            <iframe 
                                src="https://docs.google.com/forms/d/e/1FAIpQLSfLLtZhqcLaoVhCo1oT95QCR7mQQiCcIUgmveo2uWao9IkRxg/viewform?usp=embed_facebook" 
                                width="100%" 
                                height="800" 
                                frameborder="0" 
                                marginheight="0" 
                                marginwidth="0"
                                title="แบบฝึกหัดวัดความรู้ทักษะการอ่าน">
                                กำลังโหลดแบบฟอร์ม...
                            </iframe>
                        </div>
                        <p class="mt-4 text-sm text-stone-500">หากแบบฟอร์มไม่แสดงผล คุณสามารถคลิกที่นี่เพื่อเปิดในแท็บใหม่ได้: <a href="https://docs.google.com/forms/d/e/1FAIpQLSfLLtZhqcLaoVhCo1oT95QCR7mQQiCcIUgmveo2uWao9IkRxg/viewform?usp=publish-editor" target="_blank" class="text-sky-600 hover:text-sky-800 underline">แบบทดสอบวัดความรู้ทักษะการอ่าน</a></p>
                    </section>
                </main>
            </div>
        </div>
        <footer class="text-center py-4 text-stone-500 text-sm bg-white mt-8">
            <p>สร้างสรรค์จากเนื้อหา "บทที่ 3 การอ่าน" เพื่อส่งเสริมทักษะการเรียนรู้</p>
        </footer>
    </div>

<script>
document.addEventListener('DOMContentLoaded', function () {
    const navLinks = document.querySelectorAll('.nav-link');
    const contentSections = document.querySelectorAll('.content-section');

    navLinks.forEach(link => {
        link.addEventListener('click', function (e) {
            e.preventDefault();
            const targetId = this.dataset.target;

            navLinks.forEach(nav => nav.classList.remove('active'));
            this.classList.add('active');

            contentSections.forEach(section => {
                if (section.id === targetId) {
                    section.classList.add('active');
                } else {
                    section.classList.remove('active');
                }
            });
        });
    });

    const typesTabs = document.getElementById('types-tabs');
    if (typesTabs) {
        const tabButtons = typesTabs.querySelectorAll('.tab-btn');
        const tabContents = document.querySelectorAll('#types .tab-content');
        
        tabButtons.forEach(button => {
            button.addEventListener('click', function() {
                const targetId = this.dataset.target;
                tabButtons.forEach(btn => btn.classList.remove('active'));
                this.classList.add('active');

                tabContents.forEach(content => {
                    if (content.id === targetId) {
                        content.classList.remove('hidden');
                    } else {
                        content.classList.add('hidden');
                    }
                });
            });
        });
    }

    const startBtn = document.getElementById('start-timer');
    const stopBtn = document.getElementById('stop-timer');
    const timerDisplay = document.getElementById('timer-display');
    const timerResult = document.getElementById('timer-result');
    const questionsDiv = document.getElementById('questions');
    let timerInterval;
    let startTime;
    
    if (startBtn) {
        startBtn.addEventListener('click', () => {
            startTime = Date.now();
            startBtn.disabled = true;
            stopBtn.disabled = false;
            timerResult.textContent = '';
            questionsDiv.classList.add('hidden');
            timerInterval = setInterval(() => {
                const elapsedTime = Date.now() - startTime;
                const totalSeconds = Math.floor(elapsedTime / 1000);
                const minutes = String(Math.floor(totalSeconds / 60)).padStart(2, '0');
                const seconds = String(totalSeconds % 60).padStart(2, '0');
                timerDisplay.textContent = `${minutes}:${seconds}`;
            }, 1000);
        });
    }

    if (stopBtn) {
        stopBtn.addEventListener('click', () => {
            clearInterval(timerInterval);
            const endTime = Date.now();
            const timeTaken = ((endTime - startTime) / 1000).toFixed(2);
            timerResult.textContent = `คุณใช้เวลาอ่านไป ${timeTaken} วินาที`;
            startBtn.disabled = false;
            stopBtn.disabled = true;
            questionsDiv.classList.remove('hidden');
        });
    }
    
    const idiomList = document.getElementById('idiom-list');
    if (idiomList) {
        const idiomItems = idiomList.querySelectorAll('li');
        const meaningBox = document.getElementById('idiom-meaning');
        
        idiomItems.forEach(item => {
            item.addEventListener('click', () => {
                meaningBox.textContent = `"${item.textContent}" หมายถึง: ${item.dataset.meaning}`;
                meaningBox.classList.remove('hidden');
            });
        });
    }

    const mediaChartCanvas = document.getElementById('mediaChart');
    if (mediaChartCanvas) {
        new Chart(mediaChartCanvas, {
            type: 'bar',
            data: {
                labels: ['หนังสือ/ตำรา', 'ข่าวสารออนไลน์', 'วิดีโอเพื่อการศึกษา', 'หลักสูตรออนไลน์'],
                datasets: [{
                    label: 'ความนิยมในการใช้เพื่อเรียนรู้ (สมมติ)',
                    data: [65, 85, 75, 50],
                    backgroundColor: [
                        'rgba(3, 105, 161, 0.6)',
                        'rgba(14, 165, 233, 0.6)',
                        'rgba(56, 189, 248, 0.6)',
                        'rgba(125, 211, 252, 0.6)'
                    ],
                    borderColor: [
                        '#0369a1',
                        '#0ea5e9',
                        '#38bdf8',
                        '#7dd3fc'
                    ],
                    borderWidth: 1
                }]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                plugins: {
                    legend: {
                        display: false
                    },
                    title: {
                        display: true,
                        text: 'เปรียบเทียบความนิยมของสื่อการเรียนรู้ประเภทต่างๆ'
                    }
                },
                scales: {
                    y: {
                        beginAtZero: true,
                        title: {
                            display: true,
                            text: 'ระดับความนิยม (%)'
                        }
                    }
                }
            }
        });
    }
});
</script>
</body>
</html>
</h1>
</body>
</html>
