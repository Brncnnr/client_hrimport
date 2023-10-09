<template>
  <div class="tui-hrimport-user">
    <Collapsible
      :label="$str('hrimport_tabuser_mapping', 'local_hrimport')"
      :initial-state="true"
    >
      <!-- <Uniform
        v-if="initialValuesSet"
        :initial-values="initialValues"
        :errors="errorsForm"
        :validate="validate"
        @change="handleChange"
        @submit="submit"
      >
        <FormRowStack spacing="large">
          <FormRow :label="Idnumber">-->
      <!-- <FormText :name="['formuser_field_idnumber', 'value']" required />
            <FormRowDetails :id="FormRowDetails"> </FormRowDetails> -->
      <!-- </FormRow>
        </FormRowStack>
      </Uniform> -->

      <Form>
        <FormRow label="Firstname">
          <InputText
            :id="firstnameID"
            v-model="users.firstname"
            :disabled="false"
          />
        </FormRow>
        <FormRow v-for="(key, value) in users" :key="key" :label="value">
          <InputText
            :id="firstnameID"
            v-model="test"
            :disabled="false"
          />
        </FormRow>
      </Form>
      <!-- {{ UserData.firstname }} -->
    </Collapsible>
  </div>
</template>

<script>
import Collapsible from 'tui/components/collapsible/Collapsible';
import {
  Uniform,
  FormRow,
  FormRowStack,
  FormText,
} from 'tui/components/uniform';
import FormRowDetails from 'tui/components/form/FormRowDetails';
import InputText from 'tui/components/form/InputText';
import Form from 'tui/components/form/Form';

export default {
  components: {
    Collapsible,
    Uniform,
    FormRow,
    FormRowStack,
    FormText,
    FormRowDetails,
    InputText,
    Form,
  },
  props: {
    firstname: String,
  //   lastname: String,
  //   idnumber: String,
  //   email: String,
  },
  data() {
    return {
      // Userdata: Userdata,
      initialValues: {
        formuser_field_idnumber: {
          value: null,
          type: 'text',
        },
        initialValuesSet: false,
        errorsForm: null,
      },
      users: {
        firstname: 'Alex',
        lastname: 'Suess',
        idnumber: '1234',
      },
    };
  },
  mounted() {
    this.initialValuesSet = true;
  },
  methods: {
    validate() {
      const errors = {};
      return errors;
    },

    handleChange(values) {
      this.valuesForm = values;
      if (this.errorsForm) {
        this.errorsForm = null;
      }
    },
    submit(currentValues) {
      if (this.errorsForm) {
        this.errorsForm = null;
      }
      this.resultForm = currentValues;

      let dataToMutate = this.formatDataForMutation(currentValues);

      this.$emit('submit', dataToMutate);
    },
  },
};
</script>

<lang-strings>
    {
    "local_hrimport": [
        "hrimport_tabuser_mapping"
    ]
    }
</lang-strings>

<style lang="scss">
</style>