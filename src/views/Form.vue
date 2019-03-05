<template>
    <div id="form1" class="container p-3">
        <h1 class="text-center">Form Bimbingan Skripsi</h1>
        <br>
        <div class="row">
            <div class="col-sm-8 offset-sm-2 my-2">
                <form action="post" @submit="handleRegister">
                    <div class="form-group row">
                        <label for="inputNIM" class="float-left col-sm-2 col-md-4 col-form-label">NIM :</label>
                        <div  id="nim" class="col-sm-10 col-md-8 validate">
                            <input type="text" v-model="nim" class="form-control" id="inputNIM" @click="validateNim2" @keyup="validateNim" placeholder="Masukkan Nomor Induk Mahasiswa Anda">
                        </div>
                    </div>
                    <div class="form-group row">
                        <label for="inputName" class="float-left col-sm-2 col-md-4 col-form-label">Nama :</label>
                        <div id="name" class="col-sm-10 col-md-8 validate">
                            <input type="text" v-model="name" class="form-control" id="inputName" @keyup="validateName"  placeholder="Masukkan Nama Lengkap Anda" >
                        </div>
                    </div>
                    <div class="form-group row">
                        <label for="inputKelas" class="float-left col-sm-2 col-md-4 col-form-label">Kelas :</label>
                        <div id="kelas" class="col-sm-10 col-md-8 validate">
                            <input type="text" v-model="kelas" class="form-control" id="inputKelas" @keyup="validateKelas" placeholder="Masukkan Kelas Anda" >
                        </div>
                    </div>
                    <div class="form-group row">
                        <label for="inputJurusan" class="float-left col-sm-2 col-md-4 col-form-label">Jurusan :</label>
                        <div id="jurusan" class="col-sm-10 col-md-8 validate">
                            <input type="text" v-model="jurusan" class="form-control" id="inputJurusan" @keyup="validateJurusan" placeholder="Masukkan Jurusan Anda" >
                        </div>
                    </div>
                    <div class="form-group row">
                        <label for="inputJudul" class="float-left col-sm-2 col-md-4 col-form-label">Judul Skripsi :</label>
                        <div id="judul" class="col-sm-10 col-md-8 validate">
                            <input type="text" v-model="judul" class="form-control" id="inputJudul" @keyup="validateJudul" placeholder="Masukkan Judul Skripsi Anda" >
                        </div>
                    </div>
                    <div class="form-group row">
                        <label for="inputTanggal" class="float-left col-sm-2 col-md-4 col-form-label">Tanggal :</label>
                        <div id="tanggal" class="col-sm-10 col-md-8 validate">
                            <input type="date" v-model="tanggal" class="form-control" @keyup="validateTanggal" id="inputTanggal">
                        </div>
                    </div>
                    <div class="form-group row">
                        <label for="inputJam" class="float-left col-sm-2 col-md-4 col-form-label">Waktu :</label>
                        <div id="jam" class="col-sm-10 col-md-8 validate">
                            <input type="time" v-model="jam" class="form-control" @keyup="validateJam" id="inputJam">
                        </div>
                    </div>
                    <div class="form-group row">
                        <label for="inputEmail" class="float-left col-sm-2 col-md-4 col-form-label">Email :</label>
                        <div id="email" class="col-sm-10 col-md-8 validate">
                            <input type="email" v-model="email" class="form-control" @keyup="validateEmail" id="inputEmail" placeholder="Masukkan Email Anda" >
                        </div>
                    </div>
                    <div class="form-group row">
                        <label for="inputText" class="float-left col-sm-2 col-md-4 col-form-label">Deskripsi :</label>
                        <div id="text" class="col-sm-10 col-md-8 validate">
                            <textarea type="text" v-model="text" class="form-control" id="inputText" @keyup="validateText" placeholder="Masukkan Deskripsi Materi Bimbingan Anda" ></textarea>
                        </div>
                    </div>
                    <div id="tombol">
                        <button class="float-right btn btn-dark"  type="submit" @click="send">Kirim</button>
                    </div>
                    
                </form>
            </div>
        </div>
    </div>
</template>

<script>
import {setTimeout} from 'timers';

export default {
    
    data() {
        return {
            nim : '',
            name : '',
            kelas : '',
            jurusan : '',
            judul : '',
            tanggal : '',
            jam: '',
            email : '',
            text : '',
        }
        
    },

    methods: {
        handleRegister(e){
            e.preventDefault();
        },
        // Validasi NIM enter
        validateNim(ev) {
            if (ev.key == "Enter") {
                const colnim = document.getElementById('nim');
                if(this.nim == ''){
                const div = document.createElement('div');
                div.innerHTML = ("Harap di isi jangan ada kosong")
                div.className = `alert alert-danger`;
                colnim.appendChild(div);
                setTimeout(() => document.querySelector(".alert").remove(),500)
                } else {
                    colnim.removeChild(colnim.childNodes[1]);
                }
            }
        },
        //validasi NIM click
        validateNim2(){
            if(this.nim == ''){
                const colnim = document.getElementById('nim');
                const div = document.createElement('div');
                div.innerHTML = ("Isi disini")
                div.className = `alert alert-primary`;
                colnim.appendChild(div);
                setTimeout(() => document.querySelector(".alert").remove(),500)
                }
        },
        // Validasi Nama
        validateName(ev) {
            if (ev.key == "Enter") {
                const colname = document.getElementById('name');
                if(this.name == ''){
                const div = document.createElement('div');
                div.innerHTML = ("Harap di isi jangan ada kosong")
                div.className = `alert alert-danger`;
                colname.appendChild(div);
                setTimeout(() => document.querySelector(".alert").remove(),500)
                } else {
                    colname.removeChild(colname.childNodes[1]);
                }
            }
        },
        // Validasi Kelas
        validateKelas(ev) {
            if (ev.key == "Enter") {
                const colkelas = document.getElementById('kelas');
                if(this.kelas == ''){
                const div = document.createElement('div');
                div.innerHTML = ("Harap di isi jangan ada kosong")
                div.className = `alert alert-danger`;
                colkelas.appendChild(div);
                setTimeout(() => document.querySelector(".alert").remove(),500)
                } else {
                    colkelas.removeChild(colkelas.childNodes[1]);
                }
            }
        },
        // Validasi Jurusan
        validateJurusan(ev) {
            if (ev.key == "Enter") {
                const coljurusan = document.getElementById('jurusan');
                if(this.jurusan == ''){
                const div = document.createElement('div');
                div.innerHTML = ("Harap di isi jangan ada kosong")
                div.className = `alert alert-danger`;
                coljurusan.appendChild(div);
                setTimeout(() => document.querySelector(".alert").remove(),500)
                } else {
                    coljurusan.removeChild(coljurusan.childNodes[1]);
                }
            }
        },
        // Validasi Judul
        validateJudul(ev) {
            if (ev.key == "Enter") {
                const coljudul = document.getElementById('judul');
                if(this.judul == ''){
                const div = document.createElement('div');
                div.innerHTML = ("Harap di isi jangan ada kosong")
                div.className = `alert alert-danger`;
                coljudul.appendChild(div);
                setTimeout(() => document.querySelector(".alert").remove(),500)
                } else {
                    coljudul.removeChild(coljudul.childNodes[1]);
                }
            }
        },
        // Validasi Tanggal
        validateTanggal(ev) {
            if (ev.key == "Enter") {
                const coltanggal = document.getElementById('tanggal');
                if(this.tanggal == ''){
                const div = document.createElement('div');
                div.innerHTML = ("Harap di isi jangan ada kosong")
                div.className = `alert alert-danger`;
                coltanggal.appendChild(div);
                setTimeout(() => document.querySelector(".alert").remove(),500)
                } else {
                    coltanggal.removeChild(coltanggal.childNodes[1]);
                }
            }
        },
        // Validasi Jam
        validateJam(ev) {
            if (ev.key == "Enter") {
                const coljam = document.getElementById('jam');
                if(this.jam == ''){
                const div = document.createElement('div');
                div.innerHTML = ("Harap di isi jangan ada kosong")
                div.className = `alert alert-danger`;
                coljam.appendChild(div);
                setTimeout(() => document.querySelector(".alert").remove(),500)
                } else {
                    coljam.removeChild(coljam.childNodes[1]);
                }
            }
        },
        // Validasi Email
        validateEmail(ev) {
            if (ev.key == "Enter") {
                const colemail = document.getElementById('email');
                if(this.email == ''){
                const div = document.createElement('div');
                div.innerHTML = ("Harap di isi jangan ada kosong")
                div.className = `alert alert-danger`;
                colemail.appendChild(div);
                setTimeout(() => document.querySelector(".alert").remove(),500)
                } else {
                    colemail.removeChild(colemail.childNodes[1]);
                }
            }
        },
        // Validasi Text
        validateText(ev) {
            if (ev.key == "Enter") {
                const coltext = document.getElementById('text');
                if(this.text == ''){
                const div = document.createElement('div');
                div.innerHTML = ("Harap di isi jangan ada kosong")
                div.className = `alert alert-danger`;
                coltext.appendChild(div);
                setTimeout(() => document.querySelector(".alert").remove(),500)
                } else {
                    coltext.removeChild(coltext.childNodes[1]);
                }
            }
        },

        // Validasi Submit
        send() {
            const kirim = document.querySelectorAll('.form-control');
            var x = false;

            for(var i = 0; i < kirim.length; i++){
                if(kirim[i].value == ''){
                    x = true;
                } else if( i == kirim.length-1){
                    for(var j = 0; j < 9; j++){
                        if(kirim[j].value !== ''){
                            kirim[j].value = '';
                        }
                    }
                }
            }
            if(x == true) {
                    const coltombol = document.getElementById('tombol');
                    const div = document.createElement('div');
                    div.innerHTML = ("Harap di isi jangan ada kosong")
                    div.className = `alert alert-danger`;
                    coltombol.append(div);
                    setTimeout(() => document.querySelector(".alert").remove(),500)
            }
            
            
            
            
        }
        
        
        
    }

}
</script>

<style scoped>
    /* form{
        color: #ffffff;
    }

    h1{
        color: #ffffff;
    } */

    .container{
        
	margin-top: 50px;
	left: 0; 
	width: 75%; 
	min-height: 100%;
	max-height: 100%;
	background: rgba(255,255,255,0.7);
    }
    
    .alert{
        border-radius: 1rem;
    }
</style>



