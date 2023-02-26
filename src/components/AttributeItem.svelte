<script>
    export let item;
</script>

<div class="attr-item">
    <div class="title">
        <img src={item.icon} alt="">
        <p>{item.category} </p>
    </div>
    <div class="score">
        <span>{item.score}</span> / 100
    </div>
</div>

<style>
    .title {
        display: flex;
        align-items: center;
        gap: .5rem;       
    }
    .title p {
        font-size: .85rem;
    }
    .score {
        font-size: .85rem;
        color: hsla(224, 30%, 27%, 0.5);
    }
    .score span {
        color: var(--darkGrayBlue);
    }
    .attr-item {
        display: flex;
        justify-content: space-between;
        padding: .85rem .75rem;
        border-radius: 7px;
        font-weight: 600;
    }
    .attr-item:nth-child(4n - 3) {
        background-color: hsla(var(--lightRed), 0.15);
        color: hsla(var(--lightRed), 1);
    }
    .attr-item:nth-child(4n - 2) {
        background-color: hsla(var(--orangeyYellow), 0.15);
        color: hsla(var(--orangeyYellow), 1);
    }
    .attr-item:nth-child(4n - 1) {
        background-color: hsla(var(--greenTeal), 0.15);
        color: hsla(var(--greenTeal), 1);
    }
    .attr-item:nth-child(4n + 0) {
        background-color: hsla(var(--cobaltBlue), 0.15);
        color: hsla(var(--cobaltBlue), 1);
    }
</style>