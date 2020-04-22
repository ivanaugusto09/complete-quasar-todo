<template>
  <q-card>
    <q-card-section class="row">
      <div class="text-h6">Adicionar Tarefa</div>
      <q-space />
      <q-btn v-close-popup flat round color="primary" icon="close" />
    </q-card-section>

    <q-card-section>
      <div class="row q-mb-sm">
        <q-input outlined v-model="taskToSubmit.name" :rules="[val => !!val || 'Field is required']" label="Nome da Tarefa" class="col" />
      </div>

      <div class="row q-mb-sm">
        <q-input outlined v-model="taskToSubmit.dueDate" label="Data">
          <template v-slot:append>
            <q-icon name="event" class="cursor-pointer">
              <q-popup-proxy>
                <q-date v-model="taskToSubmit.dueDate" />
              </q-popup-proxy>
            </q-icon>
          </template>
        </q-input>
      </div>

      <div class="row q-mb-sm">
        <q-input outlined v-model="taskToSubmit.dueTime" label="Hora">
          <template v-slot:append>
            <q-icon name="access_time" class="cursor-pointer">
              <q-popup-proxy>
                <q-time v-model="taskToSubmit.dueTime" />
              </q-popup-proxy>
            </q-icon>
          </template>
        </q-input>
      </div>
    </q-card-section>

    <q-card-actions align="right">
      <q-btn flat label="Salvar" color="primary" v-close-popup />
    </q-card-actions>
  </q-card>
</template>

<script>
export default {
  data() {
    return {
      taskToSubmit: {
        name: "",
        completed: false,
        dueDate: "",
        dueTime: ""
      }
    };
  }
};
</script>