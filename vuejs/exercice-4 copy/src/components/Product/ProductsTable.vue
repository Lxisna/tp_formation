<script>
import ProductForm from "../Form/ProductForm.vue";

export default {
  name: "ProductsTable",
  emits: ["delete-product"],
  components: {
    ProductForm,
  },
  data() {
    return {
      nothing: null,
    };
  },
  props: {
    products: {
      type: Array,
      default: () => [],
    },
    price: {
      type: Number,
      default: 10,
    },
    vta: {
      type: Number,
      default: 20,
    },
  },
  methods: {
    emitDeleteProduct(product) {
      this.$emit("delete-product", product);
    },
  },
  computed: {
    vtaCalculation: () => (price, vta) => {
      if (typeof price != "number") {
        /* throw new Error('Parameter is not a number!') */
        return "Error price is not a number";
      }
      let tax = (price / 100) * vta;
      return price + tax;
    },
    vtaCalculationLocal() {
      let tax = (this.price / 100) * this.vta;
      return this.price + tax;
    },
  },
};
</script>

<template>
  <section id="products-table" class="container">
    <h2 class="text-center">Products Table</h2>
    <p>Exemple de Computed Local</p>
    <p>{{ vtaCalculationLocal }}</p>
    <table class="table">
      <thead>
        <tr>
          <th scope="col">Name</th>
          <th scope="col">Category</th>
          <th scope="col">Description</th>
          <th scope="col">Price HT</th>
          <th scope="col">TVA</th>
          <th scope="col">Prix TTC</th>
          <th scope="col">Action</th>
        </tr>
      </thead>
      <tbody class="table-group-divider">
        <tr v-for="(item, index) in products" :key="item.id">
          <td>{{ item.name }}</td>
          <td>{{ item.category }}</td>
          <td>
            <p>
              {{ item.description }}
            </p>
          </td>
          <td>{{ item.price }} €</td>
          <td>{{ item.vta }} %</td>
          <!-- Appel à une fonction computed -->
          <td>{{ vtaCalculation(item.price, item.vta) }} €</td>
          <td>
            <button
              type="button"
              class="btn btn-primary"
              data-bs-toggle="modal"
              data-bs-target="#exampleModal"
            >
              Edit
            </button>
            <!-- Ajouter un bouton de suppression d'un produit -->
            <!-- au clic, appel de la fonction emitDeleteProduct(product) -->
            <button
              class="btn btn-secondary"
              style="margin-top: 1rem"
              @click="emitDeleteProduct(item)"
            >
              Delete
            </button>
          </td>
        </tr>
      </tbody>
    </table>

    <!-- Modal -->
    <div
      class="modal fade"
      id="exampleModal"
      tabindex="-1"
      aria-labelledby="exampleModalLabel"
      aria-hidden="true"
    >
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h1 class="modal-title fs-5" id="exampleModalLabel">
              Edit a product
            </h1>
            <button
              type="button"
              class="btn-close"
              data-bs-dismiss="modal"
              aria-label="Close"
            ></button>
          </div>
          <div class="modal-body">
            <product-form
              class="col-6"
              product="{item}"
              @addProduct="addProduct"
            />
          </div>
          <div class="modal-footer">
            <button
              type="button"
              class="btn btn-secondary"
              data-bs-dismiss="modal"
            >
              Close
            </button>
            <button type="button" class="btn btn-primary">Save changes</button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
