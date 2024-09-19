<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-12"> 
        <h2 class="text-center my-4">RIWAYAT Piket Kelas</h2>
        <div class="my-3">
          <form @sumbit.prevent="">
            <input v-model="keyword"  class="form-control form-control-lg rounded-3" placeholder="Filter...">
          </form>
          </div>
        <div class="my-3 text-muted"> menampilkan  {{ visitors.length }} dari {{ jumlah }}  </div>
        <table class="table">
          <thead>
            <tr>
              <td>Hari/tgl</td>
              <td>NAMA</td>
              <td>Tugas Piket</td>
              <td>Email</td>
              <td>Jenis kelamin</td>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>{{ i + 1 }}</td>
              <td>{{ visitors.hari }}, {{ visitors.tanggal }}</td>
              <td>{{ visitors.nama }}</td>
              <td>{{ visitors.tugaspiket }}</td>
              <td>{{ visitors.email }}</td>
              <td>{{ visitors.Jeniskelamin }}</td>
            </tr>
          </tbody>
          </table>

      </div>
      <NuxtLink to="/siswa/">
      <button type="button" class="btn btn-success">Kembali</button>
    </NuxtLink>
    </div>
  
  </div>
</template>
<style scoped>
table, th, td {
  border: 1px solid black;
  border-collapse: collapse;
}
</style>

<script setup>
const supabase= useSupabseCLient()

const visitors = ref([])
const jumlah = ref(0)
const keyword = ref('')

const getpiketkelas = async () => {
  const { data, error } = await supabase.from('').select(`*, tugaspiket(*), email(*)`);
  // ilike('nama', `%${keyword.value}%`)
  if (data) visitors.value = data
}

const totalpiketkelas = async () => {
  const { data, count } = await supabase.from('').select("*", { count: 'exact' })
  if (data) jumlah.value = count
}
onMounted(() => {
  getpiketkelas()
  totalpiketkelas()
})
</script>

