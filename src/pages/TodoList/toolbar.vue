<template>
  <q-toolbar>
    <q-btn
      flat
      dense
      round
      @click="toggleLeftDrawer"
      aria-label="Menu"
    >
      <q-icon name="menu" />
    </q-btn>
    <editor-menu-bar :editor="editor">
      <div class="menubar" slot-scope="{ commands, isActive }">

        <q-btn
          :class="{ 'is-active': isActive.bold() }"
          @click="commands.bold"
        >
          <svgicon name="bold" />
        </q-btn>

        <q-btn
          :class="{ 'is-active': isActive.italic() }"
          @click="commands.italic"
        >
          <svgicon name="italic" />
        </q-btn>

        <q-btn
          :class="{ 'is-active': isActive.code() }"
          @click="commands.code"
        >
          <svgicon name="code" />
        </q-btn>

        <q-btn
          :class="{ 'is-active': isActive.todo_list() }"
          @click="commands.todo_list"
        >
          <svgicon name="checklist" />
        </q-btn>

      </div>
    </editor-menu-bar>

  </q-toolbar>
</template>

<script>
import UiMixin from 'src/mixins/ui'
import { EditorMenuBar } from 'tiptap'
import { mapActions } from 'vuex'
export default {
  name: 'DefaultToolbar',
  mixins: [UiMixin],
  props: [],
  components: {
    EditorMenuBar
  },
  methods: {
    ...mapActions([
      'toggleLeftDrawer'
    ])
  }
}
</script>
