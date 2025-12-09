<script lang="ts">

    export let info;
    // Flipping card functions
    let flipped = false;

    const flipCard = () => {
        if (!flipped) {
        flipped = true;
        }
    }
</script>

<div class="card" id="flip-card" on:click={flipCard}>
    <div class="inner" class:flipped={flipped}>
        <div class="front">
            <h2 class="itim" style="font-size: 1rem;">Tap to flip</h2>
        </div>
        <div class="back">
            <p class="itim" style="font-size: 1rem; text-align: center; color: #811331">{info}</p>
        </div>
    </div>
</div>

<style>
    .card {
        background-color: #FFB6C1;
        padding: 1.5rem;
        perspective: 1000px;
        cursor: pointer;
        .inner {
            width: 100%;
            height: 100%;
            position: relative;
            transition: transform 0.6s ease;
            transform-style: preserve-3d;
        }

        .inner.flipped {
            transform: rotateY(180deg);
        }

        .front,
        .back {
            position: absolute;
            width: 100%;
            height: 100%;
            backface-visibility: hidden;
            border-radius: 12px;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .front {
            background: white;
        }

        .back {
            background: #F8C8DC;
            color: white;
            padding: 0 1rem;
            transform: rotateY(180deg);
        }
    }

    @media only screen and (max-width: 1200px) {
        .card {
            width: 269px;
            height: 297px;
        }
    }

                
</style>