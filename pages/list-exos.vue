<template>
  <div>
    <form>
      <v-row>
        <v-col
          cols="4"
        >
          <v-text-field
            v-model="nouveauMachine"
            :label="$t('machine.create_Machine')"
            :rules="rulesnvM"
            counter="15"
            :hint="$t('machine.counter_prop')"
          />
          <v-text-field
            v-model="nvDescription"
            :label="$t('machine.describe_a_Machine')"
            counter="250"
            :rules="rulesnvD"
            :hint="$t('machine.counter_prop')"
          />
          <v-btn
            color="primary"
            dark
            :disabled="!formIsValid"
            @click="addMachine"
          >
            {{ $t('machine.create_Machine') }}
          </v-btn>
        </v-col>
        <v-col
          cols="4"
        >
          <v-card
            class="mx-auto"
            max-width="300"
            tile
          >
            <v-list dense>
              <v-subheader>{{ $t('machine.list_Machine') }}</v-subheader>
              <v-list-item-group

                color="primary"
              >
                <v-list-item
                  v-for="item in listMachine"
                  :key="item.id"
                  nuxt
                  :to="localePath({ name: 'infomachine', query: { text: item.text, id: item.id, description: item.description, icon: item.icon } })"
                >
                  <v-list-item-icon>
                    <v-tooltip>
                      <template #activator="{ on, attrs }">
                        <v-icon
                          v-bind="attrs"
                          v-on="on"
                          v-text="item.icon"
                        />
                      </template>
                      <span>{{ $t('machine.icon') }}</span>
                    </v-tooltip>
                  </v-list-item-icon>
                  <v-list-item-content>
                    <v-list-item-title v-text="item.text" />
                  </v-list-item-content>
                  <v-list-item-content>
                    <v-list-item-title v-text="item.description" />
                  </v-list-item-content>
                </v-list-item>
              </v-list-item-group>
            </v-list>
          </v-card>
        </v-col>
      </v-row>
    </form>
  </div>
</template>

<script>

export default {
  name: 'TestPage',
  data () {
    return {
      rulesnvM: [v => v.length <= 15 || 'Max 15 characters'],
      rulesnvD: [v => v.length <= 250 || 'Max 250 characters'],
      nouveauMachine: '',
      nvDescription: '',
      nvIcon: 'mdi-alarm-panel',
      id: 1,
      listMachine: []
    }
  },

  computed: {
    formIsValid () {
      return (
        this.nouveauMachine &&
          this.nvDescription &&
        this.nouveauMachine.length <= 15 &&
        this.nvDescription.length <= 250
      )
    }
  },

  beforeMount () {
    this.listMachine.push({
      id: this.id++, text: 'machine 1', description: 'description 1', icon: 'mdi-alarm-panel'
    }, {
      id: this.id++, text: 'machine 2', description: 'description 2', icon: 'mdi-alarm-panel'
    }, {
      id: this.id++, text: 'machine 3', description: 'description 3', icon: 'mdi-alarm-panel'
    }
    )
  },

  methods: {
    addMachine () {
      this.listMachine.push({
        id: this.id++, text: this.nouveauMachine, description: this.nvDescription, icon: this.nvIcon
      })
    }
  }
}

</script>

<style scoped>

</style>
