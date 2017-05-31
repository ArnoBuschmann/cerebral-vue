<script>

const tmpl = `
  <div>

    <p>Foo is speaking: {{foo}} Local state says: {{ firstName }}</p>
    <p>And he has a last name: {{ lastName }}</p>

    <ul>
      <li v-for="item in mylist">
        {{ item.obst }}
      </li>
    </ul>

  </div>
`

import Vue from 'vue/dist/vue'
import {connect} from 'cerebral/vue'
import {state} from 'cerebral/tags'

export default connect({
  foo: state`foo`,
  mylist: state`mylist`
}, {

  // Local state
  data() {
    return {
      firstName: 'John',
      lastName: 'Smith'
    }
  },

  template: tmpl,

  created: function () {
    // `this` points to the vm instance
    console.log('Lifecycle: foo created')
  },

  // Lifecycle hook
  beforeMount: function() {
    console.log('Lifecycle: foo beforeMount')
  }

})

</script>
