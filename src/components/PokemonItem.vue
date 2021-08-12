/* eslint-disable prettier/prettier */
<template>
    <div>
        <b-col>
            <b-card
                :title="datos.name.toUpperCase()"
                :img-src="urlImg"
                img-alt="Image"
                img-width="200rem"
                img-height="200rem"
                img-top
                tag="articlef"
                style="max-width: 15rem;"
                class="mb-4"
            ><hr>
                <b-card-text>
                    <b-list-group>
                        <b-list-group-item class="d-flex justify-content-between align-items-center border-0" variant="warning" v-for="info in data.stats" :key="info.stat.name">
                            {{ info.stat.name }}
                            <span class="h4">{{ info.base_stat }}</span>
                        </b-list-group-item>
                    </b-list-group>
                </b-card-text>
                <b-button @click="getDetail()" pill variant="outline-info">     more...    </b-button>
                <template #footer>
                    <small class="text-muted"> Fuente: pokeapi.co </small>
                </template>
            </b-card>
        </b-col>
    </div>
</template>

<script>
    import axios from "axios";
    const URL_API = "https://pokeapi.co/api/v2/pokemon/";

    export default {
        data() {
            return { 
                data: [],
                urlImg: '',
             };
        },
        props: {
            datos: []
        },
        methods: {
            async getInfoPokemon() {
                await axios.get(URL_API + this.datos.name).then((response) => {
                    console.log(response);
                    let data = response.data;
                    this.data = data;
                    this.urlImg = data.sprites.front_default;
                });
            },
            getDetail() {
                this.$router.push({ name: "detail", params: { datos: this.data } });
                //console.log(`test button ${this.data.id}`);
            }
        },
        mounted() {
            this.getInfoPokemon();
        }
     }
</script>

<style lang="scss" scoped>

</style>
