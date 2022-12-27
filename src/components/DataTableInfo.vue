<template>
  <v-card>
    <v-card-title>
      <v-text-field
        v-model="search"
        append-icon="mdi-magnify"
        label="Search"
        single-line
        hide-details
      ></v-text-field>
    </v-card-title>        <v-data-table
      :headers="headersTable"
      :items="infoList"
      :search="search"
    ></v-data-table>
  </v-card>
</template>

<script lang="ts">
import Vue from 'vue';
import axios from 'axios';
import Component from 'vue-class-component';

@Component({})
export default class DataTableInfo extends Vue {

public infoList:Array<any> = new Array<any>();

public headersTable:Array<any> = new Array<any>();

public search = '';

public async mounted() {
  const response = await axios.get('assets/data.csv', { responseType: 'blob' });
  console.log('mounted', response.data);

  const file = response.data;

  file.text().then((csvStr: any) => {
    console.log(csvStr);
    const obj = this.csvJSON(csvStr);
    console.log(obj);
    this.infoList = obj;
    console.log('headersTable', this.headersTable);
  });
}

csvJSON(csvStr: any): Array<any> {
  const lines = csvStr.split('\n');
  const result = [];

  const headers = lines[0].split(',');

  for (let a = 1; a < headers.length; a++) {
    let obj: any = { text: '', value: '' };
    obj.text = headers[a];
    obj.value = headers[a];
    this.headersTable.push(obj);
  }

  for (let i = 1; i < lines.length; i++) {
    let obj: any = {};
    const currentline = lines[i].split(',');
    for (let j = 0; j < headers.length; j++) {
      obj[headers[j]] = currentline[j];
    }
    result.push(obj);
  }
  return result;
}
}
  /*
  export default Vue.extend({
  name: 'HelloWorld',

  data: () => ({
    infoList: [],
  }),
  mounted: async () => {
    const response = await axios.get('assets/data.csv', { responseType: 'blob' });
    console.log('mounted', response.data);

    const file = response.data;

    file.text().then((csvStr: any) => {
      console.log(csvStr);
      const obj = csvJSON(csvStr);
      console.log(obj);
      data.infoList = obj;
    });
  },
});
*/
</script>
