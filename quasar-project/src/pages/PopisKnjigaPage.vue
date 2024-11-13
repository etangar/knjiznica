<template>
  <q-page padding>
    <q-card>
      <q-card-section>
        <div class="text-h5">Popis svih knjiga</div>
      </q-card-section>
      <q-card-section>
        <q-table
          :rows="allBooks"
          :columns="columns"
          row-key="id"
          flat
        />
      </q-card-section>
    </q-card>
  </q-page>
</template>

<script>
export default {
  setup() {
    const allBooks = [
      { id: 1, title: 'Božanstvena komedija', author: 'Dante Alighieri' },
      { id: 2, title: 'Dekameron', author: 'Giovanni Boccaccio' },
      { id: 3, title: 'Stranac', author: 'Albert Camus' },
      { id: 4, title: 'Don Quijote', author: 'Miguel De Cervantes' },
      { id: 5, title: 'Zločin i kazna', author: 'Fjodor Dostojevski' },
    ];

    const columns = [
      { name: 'id', label: 'ID', field: 'id', align: 'left' },
      { name: 'title', label: 'Naslov', field: 'title', align: 'left' },
      { name: 'author', label: 'Autor', field: 'author', align: 'left' },
    ];

    return {
      allBooks,
      columns,
    };
  },
};
</script>