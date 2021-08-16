<template>
  <q-layout view="hHh Lpr fFf"> <!-- Be sure to play with the Layout demo on docs -->

    <!-- (Optional) The Header -->
    <q-header elevated>
      <q-toolbar>

        <q-toolbar-title style="text-align: center">
          Калькулятор самозамеса
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <!-- (Optional) The Footer -->

    <!-- (Optional) A Drawer; you can add one more with side="right" or change this one's side -->
    <q-drawer
      v-model="leftDrawerOpen"
      side="left"
      bordered
      class="bg-grey-2"
    >
      <!-- QScrollArea is optional -->
      <q-scroll-area class="fit q-pa-sm">
        <!-- Content here -->
      </q-scroll-area>
    </q-drawer>

    <q-page-container>
      <q-form
     @submit="onSubmit"
     >
      <div class="q-pa-md">
    <div class="q-gutter-md" style="max-width: 300px">

      <q-input filled v-model="Volume" label="Выходной обьем ml" />
      <q-input filled v-model="aroms" label="Ароматизатор в %" />
      <q-input filled v-model="nic" label="Количество никотина" />
      <q-btn type="submit" style="background: #FF0080; color: white" label="Расчитать" />
        <span id="glic">
        

          </span>
          <span id="aroms">

          </span>
          <span id="nic">


          </span>
          <span id="propen">

          </span>
      


    </div>
  </div>
  </q-form>
    </q-page-container>

  </q-layout>
</template>

<script>
import { useQuasar } from 'quasar'
import { ref } from 'vue'

export default {
  // name: 'LayoutName',
    

  setup () {
       const $q = useQuasar()
    const Volume = ref(null)
    const aroms = ref(null)
    const nic = ref(null)
    const glic = ref(null)
    const leftDrawerOpen = ref(false)

    return {
      Volume,
      aroms,
      nic,
      
            onSubmit () {
        
        
          console.log(Volume.value)
          console.log(aroms.value)
          console.log(nic.value)
          
      },

      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  }
}
</script>
