<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-6 offset-md-3">
        <form class="my-3">
          <div class="mb-3">
            <input type="text" class="form-control" placeholder="Nama">
          </div>
          <div class="mb-3">
            <select class="form-control">
              <option value="">Tugas Piket</option>
              <option value="Menyapu">Menyapu</option>
              <option value="Mengepel">Mengepel</option>
            </select>
          </div>
          <div class="mb-3">
  <input type="email" class="form-control" id="exampleFormControlInput1" placeholder="email ">
</div>
</form>
      </div>
    </div>
    <NuxtLink to="/Riwayat/">
        <button type="button" class="btn btn-success">Kirim</button>
      </NuxtLink>
    <NuxtLink to="/siswa/">
        <button type="button" class="btn btn-success">Kembali</button>
      </NuxtLink>
  </div>
</template>

<script setup>

</script>