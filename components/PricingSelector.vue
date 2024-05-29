<template>
    <div :class="{active:type==0}" class="pricing-selector">
        <div class="item active" @click="onClick(0)">
            <img src="@/static/pen.png"/> <strong>Figma</strong>
        </div>
        <div :class="{active:type==1}" class="item" @click="onClick(1)">
            <img src="@/static/pencil.png" /> <strong>FigJam</strong>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return{
            type: 0
        }
    },
    methods: {
        onClick(type) {
            this.type = type;
            this.$emit('selectType', this.type);
        },
    }
}
</script>

<style scoped>
.pricing-selector{
    border-radius: 8px;
    border: 2px solid #FFFFFF;
    background: #FFFFFF;
    display: inline-flex;
    padding: 4px;
    gap: 3px;
}
.item{
    font-size: 22px;
    background: rgb(229, 229, 229);
    color: rgba(0, 0, 0, 0.7);
    padding: 12px 32px;
    text-align: center;
    border-radius: 8px;
    align-items: center;
    gap: 4px;
}
.active {
    background: #5551FF;
    color: #FFFFFF;
}
</style>