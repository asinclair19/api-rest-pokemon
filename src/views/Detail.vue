<template>
  <b-container>
    <b-row>
      <b-card no-body class="overflow-hidden" style="max-width: 100rem;">
        <b-row no-gutters>
          <b-col md="3">
            <img :src="datos.sprites.front_default" width="150rem"
              alt="Image" class="rounded-0"/>
          </b-col>
          <b-col md="9">
            <b-card-body :title="datos.name.toUpperCase()">
              <b-card-text>
                <b-tabs content-class="mt-3">
                  <b-tab title="basic information" active>
                      <b-list-group class="text-left">
                          <b-list-group-item class="border-0">ID: <b>{{ datos.id }}</b></b-list-group-item>
                          <b-list-group-item class="border-0">NAME: <b>{{ datos.name }}</b></b-list-group-item>
                          <b-list-group-item class="border-0">BASE EXPERIENCE: <b>{{ datos.base_experience }}</b></b-list-group-item>
                          <b-list-group-item class="border-0">HEIGHT: <b>{{ datos.height }}</b></b-list-group-item>
                      </b-list-group>
                  </b-tab>
                  <b-tab title= "Abilities">
                      <p>Total: {{ datos.abilities.length }}</p>
                      <b-list-group class="text-left">
                          <b-list-group-item v-for="item in datos.abilities" :key="item.ability.name">
                            {{ item.ability.name }}
                          </b-list-group-item>
                      </b-list-group>
                  </b-tab>
                  <b-tab title="Moves">
                    <p>Total: {{ datos.moves.length }}</p>
                    <b-list-group class="text-left">
                          <b-list-group-item v-for="item in datos.moves" :key="item.move.name">
                            {{ item.move.name }}
                          </b-list-group-item>
                      </b-list-group>
                  </b-tab>
                </b-tabs>
              </b-card-text>
            </b-card-body>
          </b-col>
        </b-row>
      </b-card>
    </b-row>
  </b-container>
</template>

<script>
export default {
  props: ['datos']
}
</script>
