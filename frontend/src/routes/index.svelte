<script>

    import axios from "axios";
    import {locale} from "../store/locale";

    const getAllProducts = `http://localhost:1337/api/products?locale=`

    let products = [];

    const loadProducts = async () => {
        const productsResponse = await axios.get(getAllProducts + $locale)
        products = productsResponse.data.data
        console.log("updated products")
    }

    $: {
        if($locale){
            loadProducts()
        }
    }

</script>




<div class="flex space-x-2">
    {#each products as p}
        <div class="border rounded p-4">
            <div>{p.attributes.name}</div>
            <div>{p.attributes.description}</div>
            <div>{p.attributes.price}</div>
        </div>
    {/each}
</div>



