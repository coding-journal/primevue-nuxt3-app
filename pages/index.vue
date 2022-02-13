<script>
export default {
  setup() {
    onMounted(() => {
      productService.value.getProductsSmall().then(data => products.value = data);
    })

    const products = ref([
      {"code":"st1", "name": "Pencil", "category": "Stationary", "quantity": 5 },
      {"code":"st2", "name": "Pen", "category": "Stationary", "quantity": 5 },
      {"code":"sn1", "name": "Doritos", "category": "Snack", "quantity": 2 },
      {"code":"sn2", "name": "Lays", "category": "Snack", "quantity": 1 },
    ]);
    // const productService = ref(new ProductService());

    return { products }
  }
}
</script>

<template>
  <div class="m-auto w-1/2">
    <h1 class="text-lg bg-red-400 text-white">tes</h1>
    <Button label="Prime Vue" icons="pi pi-check"></Button>

    <DataTable :value="products" responsiveLayout="scroll" :paginator="true" :rows="2">
      <Column field="code" header="Code"></Column>
      <Column field="name" header="Name"></Column>
      <Column field="category" header="Category"></Column>
      <Column field="quantity" header="Quantity"></Column>
    </DataTable>
  </div>
</template>


<style>
</style>