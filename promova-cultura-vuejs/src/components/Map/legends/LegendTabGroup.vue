<template>
<div>
    <ul class="nav nav-tabs legend-tabs" id="myTab" role="tablist">
        <li class="nav-item">
            <a class="nav-link active" id="projeto-tab" data-toggle="tab" href="#projeto" role="tab" aria-controls="projeto" aria-selected="true">Projetos</a>
        </li>
        <li class="nav-item">
            <a class="nav-link" id="proponente-tab" data-toggle="tab" href="#proponente" role="tab" aria-controls="proponente" aria-selected="false">Proponentes</a>
        </li>
        <li class="nav-item">
            <a class="nav-link" id="incentivador-tab" data-toggle="tab" href="#incentivador" role="tab" aria-controls="incentivador" aria-selected="false">Incentivadores</a>
        </li>
    </ul>
    <div class="tab-content legend-content" id="myTabContent">
        <div class="tab-pane fade show active" id="projeto" aria-labelledby="projeto-tab" role="tabpanel"><base-legend :dataLegend="legends.heatMap" :typeOfData="'projetos'" :filtersActivate="filtersActivate" /></div>
        <div class="tab-pane fade" id="proponente" aria-labelledby="proponente-tab" role="tabpanel"><base-legend :dataLegend="legends.proponentes" :typeOfData="'proponentes'" :filtersActivate="filtersActivate"/></div>
        <div class="tab-pane fade" id="incentivador" aria-labelledby="incentivador-tab" role="tabpanel"><base-legend :dataLegend="legends.incentivadores" :typeOfData="'incentivadores'" :filtersActivate="filtersActivate"/></div>
    </div>
</div>
</template>

<script>
import Legend from "@/components/Map/legends/Legend";
export default {
    props: {
        legends: {},
        filtersActivate: Object
    },
    components: {
        "base-legend": Legend,
    },
};
</script>

<style scoped>
.legend-tabs .nav-link {
    padding: 8px;
}
.legend-tabs {
   border-bottom: 0;
   padding-top:5px;
}

.legend-tabs li {
    font-size: 16px;
}

.legend-tabs li a {
    color: #333;
}

.legend-content {
    padding: 20px;
    border: 1px solid #ddd;
}

</style>
