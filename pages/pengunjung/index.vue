<template>
    <div class="container-fluid">
        <div class="row">
            <div class="col-lg-12">
                <h2 class="text-center my-4">RIWAYAT KUNJUNGAN</h2>
                <div class="my-3">
                    <input type="search" class="form-control form-control-lg rounded-5" placeholder="Filter...">
                </div>
                <table class="table">
                    <thead>
                        <tr>
                            <td>#</td>
                            <td>NAMA</td>
                            <td>KEANGGOTAAN</td>
                            <td>WAKTU</td>
                            <td>KEPERLUAN</td>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="(visitor,i) in visitors" :key="i">
                            <td>{{ i+1 }}.</td>
                            <td>{{ visitor.nama }}</td>
                            <td>{{ visitor.keanggotaan.nama }}</td>
                            <td>{{ visitor.created_at }}</td>
                            <td>{{ visitor.keperluan.nama }}</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
        <div class="d-flex justify-content-between">
            <nuxt-link to="/" class="btn btn-light btn-lg rounded-5 px-5 ">
                KEMBALI
            </nuxt-link>
        </div>
    </div>
</template>

<script setup>
const supabase = useSupabaseClient()
const visitors = ref([])
const getPengunjung = async () => {
    const {data, error} = await supabase.from('pengunjung').select('*, keanggotaan(*), keperluan(*)')
    if(data) visitors.value = data
}
onMounted(() => {
    getPengunjung()
})

</script>