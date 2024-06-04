<template>
    <h2 class="text-star may-4">{{ buku.judul }}</h2>
    <div class="row">
        <div class="col-md-3">
            <img src="buku.cover" alt="cover buku">
        </div>
        <div class="col-md-4">
            <div class="badge bg-primary p-2">{{ buku.kategori }}</div>
            <ul class="list-group list-group-flush">
                <li class="list-group-itrm">penulis: {{ buku.penulis }}</li>
                <li class="list-group-itrm">penerbit: {{ buku.penerbit }}</li>
                <li class="list-group-itrm">{{ buku.deskripsi }}</li>
            </ul>
        </div>
    </div>
</template>
<script setup>
import { onMounted } from 'vue';

const supabase = useSupabaseClient()
const route = useRoute()
const buku = ref([])
const getbookByid = async () => {
    const { data, error } = await  supabase.from('buku').select('*,kategori(*)')
    .eq('id', route.parrams.id)
    if(data) buku.value = data[0]
    onMounted(() =>{
        getbookByid()
    })
}
</script>

