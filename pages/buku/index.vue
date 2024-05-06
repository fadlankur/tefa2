<template>
    <div class="container-fluid">
        <div class="row">
            <div class="col-lg-12">
                <h2 class="text-center my-4">BUKU</h2>
                <div class="my-3">
                    <input type="search" class="form-control rounded-5" placeholder="Mau baca apa hari ini">
                </div>
                <div class="my-3 text-muted"> menampilkan 3 dari 3</div>
                <div class="row">
                    <div class="col-lg-2">
                        <div v-for="(book,i) in books" :k="i" class="col-lg-2">
                            <div class="card mb-3">
                                <div class="card-body">
                                    <img :src="book.cover" class="cover" alt="cover">
                                </div>
                            </div>
                        </div>

                    
                        <nuxt-link to="/" class="btn btn-light btn-lg rounded-5 px-5 m">
                            KEMBALI
                        </nuxt-link>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
const supabase = useSupabaseClient()

const books = ref ([])
const getBooks = async () => {
    const { data, error } = await supabase.from('buku').select('*,kategori(*)')
    if(data) books.value = data

onMounted(() => {
    getBooks()
})    
}
</script>


<style scoped>
.card-body {
    width: 100%;
    height: 20em;
    padding: 0;
}
.cover {
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: 0 30;
}
</style>