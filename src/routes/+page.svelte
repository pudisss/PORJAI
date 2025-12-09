<script lang="ts">
    // Import package
    import { fade } from "svelte/transition"
    // Porjai
    import porjai1 from "$lib/assets/images/porjai1.png"

    import p1 from "$lib/assets/images/porjai/1.jpg"
    import p2 from "$lib/assets/images/porjai/2.jpg"
    import p3 from "$lib/assets/images/porjai/3.jpg"
    import p4 from "$lib/assets/images/porjai/4.jpg"
    import p5 from "$lib/assets/images/porjai/5.jpg"
    import p6 from "$lib/assets/images/porjai/6.jpg"
    import p7 from "$lib/assets/images/porjai/7.jpg"
    import p8 from "$lib/assets/images/porjai/8.jpg"

    const porjais = [p1, p2, p3, p4, p5, p6, p7, p8]
    const descriptions = [
        "น่ารักอ่ะ",
        "ยังต้าจัด",
        "อันนี้ก็ยังต้า",
        "แก้มอ้วนเชียวนะ",
        "ละลายเลยครับ",
        "กำลังใจที่ดีเลยครับ",
        "สวยมากอันนี้",
        "แต่งหน้าสวยมากอันนี้"
    ]
    let currentIndex = 0;

    const forward = () => {
        if (currentIndex != 7) {
            currentIndex += 1
        } else {
            currentIndex = 0
        }
    }
    const back = () => {
        if (currentIndex != 0) {
            currentIndex -= 1
        } else {
            currentIndex = 7
        }
    }
    // Heart
    import heart1 from "$lib/assets/images/heart1.png"
    import heart2 from "$lib/assets/images/heart2.png"
    import heart3 from "$lib/assets/images/heart3.png"

    // Text
    const text = [
        "ขอบคุณนะช่วงเวลาที่ผ่านมาสำหรับเรานี้มีค่าสำหรับเรามาก",
        "เราชอบความที่พอใจเป็นผู้หญิงเรียบร้อย มีเยอะแต่ไม่ต้องโชว์อะ มั่นใจในตัวเองเข้าไว้นะะ",
        "พอใจเป็นผู้หญิงที่เรียนเก่งมาก ตรงนี้มีเสน่ห์มาก",
        "เรารู้สึกโชคดีมากเลยที่มีพอใจเข้ามาในชีวิตเหมือนมาเติมเต็มเลยครับบ",
        "พอใจเป็นผู้หญิงที่ทั้งสวยและน่ารักในคนเดียวกัน",
        "คนอื่นอิจฉาเราตาร้อนแล้วเนี่ย เพราะฉะนั้นช่างมัน น่ารักเย้อๆแบบนี้นี้แหละ อิอิ",
        "นอกจากหน้าตาแล้ว เราชอบสไตล์การแต่งหน้าของพอใจมาก",
        "แต่งหน้าเก่งๆแบบนี้ไปนานๆน้าา ถ้าไม่มีใครดู เดี่ยวเรานี้แหละดูเองง",
        "การที่คุณทำตัวอย่างงี้ทำให้หัวใจหวั่นนะครับ อิอิ",
        "ตอนแรกๆ เราก็มีเกร็งบ้าง แต่หลังๆเรารู้สึกสบายทุกครั้งที่ได้คุยหรืออยู่กับพอใจ ถึงแม้จะมี dead air บ้างแต่เราว่าตรงนี้แหละที่เราสบา่ยใจ",
        "เราอยากให้พอใจประสบความสำเร็จในด้านที่ตัวเองอยากทำนะ ขอให้ได้คณะที่หวัง มหาลัยที่ใช่",
        "อย่าหักโห้มอ่านหนังสือเยอะเกินละ พักกินหนมบ้าง หรือทักมาคุยกับเราได้นะ เราพร้อมเป็นที่เติมใจของพอใจเสมออ",
        


    ]

    // Import component
    import FlippingCard from "$lib/Components/FlippingCard.svelte"
</script>

<main class="main-section">
    <section class="first-section">
        <div class="wrapper">
            <div class="text">
                <div class="container" data-aos="fade-up" data-aos-delay="100">
                    <h1 class="header itim">อยากให้รู้ว่า</h1>
                </div>

                <p data-aos="fade-up" data-aos-delay="200" class="paragraph itim">วันเกิดไออ้วนเน่า 100 ตันของเรานั้นเองง<br>12/12/2551</p>
            </div>

            <img data-aos="zoom-in" data-aos-delay="300" src={porjai1} alt="" class="porjai">

            <div class="row">
                <img src={heart2} alt="" class="heart2 one" data-aos="fade-down" data-aos-delay="400">

                <p class="text itim" data-aos="fade-down" data-aos-delay="500">Happy birthday na I auon<br>
I wish you the best in every way possible.</p>
                <img src={heart2} alt="" class="heart2 two" data-aos="fade-down" data-aos-delay="600">
            </div>
        </div>
    </section>
    <section class="second-section">
        <div class="wrapper">
            <div class="text" data-aos="fade-up" data-aos-delay="100">
                <div class="container">
                    <h1 class="header itim">สี่งที่อยากบอก</h1>
                </div>
                
            </div>
            <div class="grid-container" data-aos="fade-up" data-aos-delay="200">
                    {#each text as t}
                        <FlippingCard info={t}></FlippingCard>
                    {/each}
                </div>
                
        </div>
    </section>
    <section class="third-section">
        <div class="wrapper">
            <div class="text">
                <div class="container">
                    <h1 class="header itim">สี่งที่ชอบในตัวพอใจ</h1>
                </div>
                
            </div>

            <div class="switch">
                <button on:click={back} class="before itim">กลับ</button>

                <img src={porjais[currentIndex]} alt="" class="porjai-image">

                <button on:click={forward} class="after itim">ต่อ</button>
            </div>
            <div class="responsive-switch">
                <button on:click={back} class="before itim">กลับ</button>
                <button on:click={forward} class="after itim">ต่อ</button>
            </div>
            <div class="text">
                <div class="container">
                    <h1 class="header itim">{descriptions[currentIndex]}</h1>
                </div>
                
            </div>
        </div>
    </section>
    <section class="fourth-section">
        <div class="wrapper">
            <div class="text" data-aos="fade-down" data-aos-delay="200">
                <div class="container">
                    <h1 class="header itim">คำอวยพร</h1>
                </div>
                
            </div>
            <img src={heart2} alt="" class="heart two" data-aos="fade-down" data-aos-delay="300">
            <div class="luck" data-aos="fade-down" data-aos-delay="400">
                <p class="paragraph itim">
                    ท้ายที่สุดนี้ เราขอให้พอใจความสุขในชีวิต<br>เป็นเด็กดีของพ่อแม่และเป็นพี่สาวที่ดีของน้องชาย<br>เรียนเก่งๆ มีเงินใช้ไม่ขาดมือ<br>อยู่เป็นไอหมูอ้วนเน่าข้างๆเราไปนานๆนะครับ<br>
แฮปปี้เบิร์ดเดย์
                </p>
            </div>
            <img src={heart3} alt="" class="heart three" data-aos="fade-down" data-aos-delay="300">
        </div>
    </section>
</main>



<style lang="scss">

    
    .main-section {
        width: 100%;

        .fourth-section {
            width: 100%;
            padding: 3rem 0;
            height: 100vh;
            .wrapper {
                position: relative;
                width: 100%;
                height: 100%;
                display: flex;
                flex-flow: column nowrap;
                align-items: center;
                .text {
                    width: 100%;
                    display: flex;
                    flex-flow: column nowrap;
                    align-items: center;
                    .container {
                        width: min(289px, 40%);
                        height: 65px;
                        border-radius: 7px;
                        border: none;
                        background-color: white;
                        display: flex;
                        align-items: center;
                        justify-content: center;
                        padding: 0 1rem;

                        .header {
                            font-size: clamp(20px ,4vw, 32px)
                        }
                    }

                }

                .heart {
                    width: clamp(200px, 20vw, 300px);
                    height: clamp(200px, 20vh, 300px);
                    position: absolute;
                    z-index: 1;
                }

                .two {
                    top: 10%;
                    left: 10%;
                    transform: rotate(-30deg)
                }
                .three {
                    bottom: 10%;
                    right: 10%;
                    transform: rotate(30deg)
                }
                .luck {
                    width: 100%;
                    height: 100%;
                    display: flex;
                    align-items: center;
                    justify-content: center;
                    z-index: 2;
                    .paragraph {
                        font-size: clamp(20px, 4vw, 40px);
                        text-align: center;
                    }
                }

                
            }
        }
        .third-section {
            width: 100%;
            padding: 5rem 0;
            .wrapper {
                display: flex;
                flex-flow: column nowrap;
                align-items: center;

                .text {
                    width: 100%;
                    display: flex;
                    flex-flow: column nowrap;
                    align-items: center;
                    .container {
                        width: min(289px, 40%);
                        height: 65px;
                        border-radius: 7px;
                        border: none;
                        background-color: white;
                        display: flex;
                        align-items: center;
                        justify-content: center;
                        padding: 0 1rem;

                        .header {
                            font-size: clamp(16px ,3vw, 32px);
                            text-align: center;
                        }
                    }

                }
                .switch {
                    display: flex;
                    flex-flow: row nowrap;
                    align-items: center;
                    padding: 4rem 0;
                    column-gap: 63px;

                    button {
                        width: 104px;
                        height: 65px;
                        background-color: white;
                        border: none;
                        border-radius: 7px;
                        font-size: 32px;
                        cursor: pointer;
                        transition: 0.3s ease-in;
                    }

                    .porjai-image {
                        width: clamp(250px, 30vw, 400px);
                        height: 600px;
                        border-radius: 7px;
                        object-fit: cover;
                        transition: 0.3s ease-in;
                        aspect-ratio: 16/4;
                    }
                }

                .responsive-switch {
                    
                    display: none;
                    align-items: center;
                    justify-content: space-evenly;
                    
                    width: 100%;

                    padding: 1rem 0;
                    button {
                        width: 104px;
                        height: 40px;
                        background-color: white;
                        border: none;
                        border-radius: 7px;
                        font-size: 32px;
                        cursor: pointer;
                        transition: 0.3s ease-in;
                    }
                }

                @media only screen and (max-width: 800px) {
                    .switch {
                        padding: 2rem 0;
                        button {
                            display: none;
                        }
                    }

                    .responsive-switch {
                        display: flex;
                    }
                }
            }
        }

        .second-section {
            width: 100%;
            padding: 5rem 0;
            .wrapper {
                display: flex;
                flex-flow: column nowrap;
                align-items: center;

                .text {
                    width: 100%;
                    display: flex;
                    flex-flow: column nowrap;
                    align-items: center;
                    .container {
                        width: min(289px, 40%);
                        height: 65px;
                        border-radius: 7px;
                        border: none;
                        background-color: white;
                        display: flex;
                        align-items: center;
                        justify-content: center;
                        padding: 0 1rem;


                        .header {
                            font-size: clamp(16px ,3vw, 32px);
                            text-align: center;
                        }
                        
                    }
                    

                    


                }

                .grid-container {
                    width: 100%;
                    padding: 33px 0;

                    display: grid;
                    grid-template-columns: repeat(4, 269px);
                    grid-template-rows: repeat(3, 297px);
                    justify-content: center;
                    
                    gap: 20px;
                }

                @media only screen and (max-width: 1200px) {
                    .grid-container {
                        display: flex;
                        flex-flow: row wrap;
                        align-items: center;

                        

                    }
                    
                }
            }
        }
        .first-section {
            padding: 3rem 0;
            width: 100%;
            height: 100vh;
            
            .wrapper {
                display: flex;
                flex-flow: column nowrap;
                align-items: center;

                .text {
                    width: 100%;
                    display: flex;
                    flex-flow: column nowrap;
                    align-items: center;
                    .container {
                        width: min(289px, 40%);
                        height: 65px;
                        border-radius: 7px;
                        border: none;
                        background-color: white;
                        display: flex;
                        align-items: center;
                        justify-content: center;
                        padding: 0 1rem;

                        .header {
                            font-size: clamp(16px ,3vw, 32px);
                            text-align: center;
                        }
                    }

                    .paragraph {
                        font-size: clamp(16px, 2vw, 20px);
                        text-align: center;
                        margin-top: 1rem;
                    }
                }

                
                .porjai {
                    border-radius: 7px;
                    padding: 5rem 0 2rem 0;
                }

                .row {
                    display: flex;
                    align-items: center;
                    
                    .text {
                        text-align: center;
                        color: #FF69B4;
                        font-size: clamp(16px, 3vw, 24px)
                    }
                    .heart2 {
                        width: min(200px, 40%);
                        height: min(200px, 20%);
                    }

                    .one {
                        transform: rotate(-45deg)
                    }
                    .two {
                        transform: rotate(45deg)
                    }
                }
            }
        }
    }
</style>
