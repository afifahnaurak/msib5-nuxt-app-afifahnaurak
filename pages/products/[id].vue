<template>
  <div class="">
    <ProductDetails :product="product" />
  </div>
</template>

<script setup>
const { id } = useRoute().params;
const uri = "https://dummyjson.com/products/" + id;

const { data: product } = await useFetch(uri, { key: id });

if (!product.value) {
  throw createError({
    statusCode: 404,
    statusMessage: "Product not found",
    fatal: true,
  });
}

definePageMeta({
  layout: "pages",
});
</script>

<style scoped></style>
