<script>


    import {locale} from "../store/locale";
    import axios from "axios";

    const getContent = `http://localhost:1337/api/about?locale=`

    let mainContent = ""
    const load = async () => {
        const response = await axios.get(getContent + $locale)
        mainContent = response.data.data.attributes.main
    }
    $: if($locale){
        load()
    }
</script>


<p>{mainContent}</p>