<template>
  <div class="card shadow-sm">
    <div class="card-body">
      <h2 class="card-title h5">
        {{ $t("Choisis un mode d'expédition") }}
      </h2>

      <v-radio-group v-model="store.requestData.delivery">
        <v-radio v-for="delivery in deliveryOptions" :key="delivery.id" v-model="requestData.delivery" :label="delivery.name" :value="delivery.name"></v-radio>
      </v-radio-group>
    </div>

    <navigation-card-footer next-page="shop_shipment" />
  </div>
</template>

<script>
import { useHead } from 'unhead'
import { useCart } from 'src/stores/cart'
import { storeToRefs } from 'pinia'
import { useVueSession } from 'src/plugins/vue-storages'
import { ref } from 'vue'

import NavigationCardFooter from 'src/components/cart/NavigationCardFooter.vue'

export default {
  name: 'PaymentHomePage',
  components: {
    NavigationCardFooter
  },
  setup () {
    useHead({
      title: 'Delivery options'
    })
    
    const store = useCart()
    const { requestData }  = storeToRefs(store)

    const { session } = useVueSession()
    requestData.value.session_id = session.retrieve('session_id')

    const deliveryOptions = ref([])

    return {
      store,
      deliveryOptions,
      requestData
    }
  },
  beforeMount () {
    this.requestDeliveryOptions()
  },
  methods: {
    /**
     * Get the delivery options from which the
     * user can choose from in order to deliver
     * the products 
     */
    async requestDeliveryOptions () {
      try {
        const response = await this.$http.get('orders/delivery-options')
        this.deliveryOptions = response.data
      } catch (e) {
        console.log(e)
      }
    }
  }
}
</script>
