<template>
    <h1>product form</h1>
    <input v-model="message" placeholder="name" />
    <input v-model="sms" placeholder="price" type="number" />
    <input v-model="count" placeholder="count" type="number" />

    <button @click="getValue">add</button>

    <div id="list">
        <ul>
            <li v-for="(item) in items" :key="item.name">
                {{ item.id }} {{ item.product }} ${{ item.price }}
                <button @click="addCart(item.id)">add to cart</button>
            </li>
        </ul>

    </div>
    <div>
        <p>total = {{ items.reduce((a, c) => {
                return a + c.price * c.count;
            }, 0)
        }}</p>
    </div>


    <!-- <AddCArt :items="items"/> -->
</template>
<script>
// import { count } from 'console';

// import AddCArt from "./AddCArt.vue";
// console.log(this.item.id)
export default {
    data() {
        return {
            items: [

                { id: 0, product: "banan", price: 100, count: 0 },
                { id: 1, product: "apple", price: 200, count: 0 },
                { id: 2, product: "mandarin", price: 300, count: 0 },
                { id: 3, product: "beer", price: 400, count: 0 },
                { id: 4, product: "iphone", price: 500, count: 0 },
            ]
        }
    },
    methods: {
        addCart: function (id) {
            console.log(this.items[id].count++)
            console.log(id)
        },
        getValue() {
            const product = this.message
            const price = this.sms
            const count = this.count

            const id = this.items.length
            console.log(id)

            const newItems = [{ id, product, price, count }]
            this.items.push.apply(this.items, newItems)
            console.log(this.items)
            console.log(newItems)

        }
    }
}

</script>