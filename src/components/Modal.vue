<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{ sale: theme === 'sale'}">
            <slot></slot>
            <div class="actions">
                <slot name="links"></slot>
                <slot name="sometext"></slot>
            </div>
            <button @click="closeModal">Close Modal</button>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['theme'],
        methods: {
            closeModal() {
                this.$emit('close')
            }
        }
    }
</script>

<style>
    .modal {
        width: 600px;
        padding: 20px;
        margin: 100px auto;
        background: white;
        border-radius: 10px;
    }
    .backdrop {
        top: 0;
        position: fixed;
        background: rgba(0, 0, 0, 0.5);
        width: 100%;
        height: 100%;
    }
    .modal h1 {
        color: rgb(14, 212, 186);
        border: none;
        padding: 0;
    }
    .modal.sale {
        background: crimson;
        color: white;
    }
    .modal.sale.h1 {
        color: white;
    }
    .actions {
        text-align: center;
        margin: 30px 0 10px 0;
    }
    .actions a {
        color: #333;
        padding: 8px;
        border: 1px solid #eee;
        border-radius: 4px;
        text-decoration: none;
        margin: 10px;
    }
</style>