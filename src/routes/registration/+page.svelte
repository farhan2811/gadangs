<script type="text/javascript">
	import { onMount } from 'svelte';
	import {fly, scale} from 'svelte/transition'
	import ApiController from '../../ApiController'

	let progress_state = 1;
	let jenis_marketing = 'Lead Marketing';

	let provinsi = null
	let kabupaten = null
	let kecamatan = null
	let kelurahan = null
	let posCode = null

	let stepOne = false
	let stepTwo = false

	let informasiPersonal = {
		nama_lengkap: "",
		nomor_ktp: "",
		alamat: "",
		rt: "",
		rw: "",
		kelurahan: "",
		kecamatan: "",
		kode_pos: "",
		kabupaten: "",
		provinsi: "",
	}

	let informasiBank = {

	}

	let getProvinsi = () => {
		ApiController({
			method: 'GET',
			endpoint: 'provinsi',
		}).then(response => {
			provinsi = response.data

			provinsi.forEach((prov, i) => {
				if(stepOne == true && prov.provinsi == informasiPersonal.provinsi){
					document.getElementById('provinsi').selectedIndex = i+1
				}
			});
		})
	}

	let getKabupaten = prov =>{
		ApiController({
			method: 'GET',
			endpoint: `kabupaten/${prov}`,
		}).then(response => {
			kabupaten = response.data

			document.getElementById('kabupaten').options.length = 0

			kabupaten.forEach((kab, i) => {
				if(i == 0){
					let firstOption = document.createElement("option")
					firstOption.text = 'Pilih Kota/Kabupaten'
					firstOption.value = ''
					firstOption.selected = true
					firstOption.hidden = true
					firstOption.disabled = true	
					document.getElementById('kabupaten').appendChild(firstOption)
				}

				let option = document.createElement("option")
				option.text = kab.kabupaten
				option.value = kab.kabupaten

				if(stepOne == true && kab.kabupaten == informasiPersonal.kabupaten){
					option.selected = true
				}

				document.getElementById('kabupaten').appendChild(option)
			});
		})
	}

	let getKecamatan = (kab) =>{
		ApiController({
			method: 'GET',
			endpoint: `kecamatan/${kab}`,
		}).then(response => {
			kecamatan = response.data

			document.getElementById('kecamatan').options.length = 0

			kecamatan.forEach((kec, i) => {
				if(i == 0){
					let firstOption = document.createElement("option")
					firstOption.text = 'Pilih Kecamatan'
					firstOption.value = ''
					firstOption.selected = true
					firstOption.hidden = true
					firstOption.disabled = true	
					document.getElementById('kecamatan').appendChild(firstOption)
				}

				let option = document.createElement("option")
				option.text = kec.kecamatan
				option.value = kec.kecamatan

				if(stepOne == true && kec.kecamatan == informasiPersonal.kecamatan){
					option.selected = true
				}

				document.getElementById('kecamatan').appendChild(option)
			});
		})
	}

	let getKelurahan = kec =>{
		ApiController({
			method: 'GET',
			endpoint: `kelurahan/${kec}`,
		}).then(response => {
			kelurahan = response.data

			document.getElementById('kelurahan').options.length = 0

			kelurahan.forEach((kel, i) => {
				if(i == 0){
					let firstOption = document.createElement("option")
					firstOption.text = 'Pilih Kelurahan'
					firstOption.value = ''
					firstOption.selected = true
					firstOption.hidden = true
					firstOption.disabled = true	
					document.getElementById('kelurahan').appendChild(firstOption)
				}

				let option = document.createElement("option")
				option.text = kel.kelurahan
				option.value = kel.kelurahan
				
				if(stepOne == true && kel.kelurahan == informasiPersonal.kelurahan){
					option.selected = true
				}

				document.getElementById('kelurahan').appendChild(option)
			});
		})
	}

	let getPosCode = kel =>{
		ApiController({
			method: 'GET',
			endpoint: `kodepos/${kel}`,
		}).then(response => {
			posCode = response.data
			informasiPersonal.kode_pos = posCode[0].kodepos
			document.getElementById('post-code').value = posCode[0].kodepos
		})
	}

	let setStepOneData = () => {
		if(stepOne){
			getProvinsi()
			getKabupaten(informasiPersonal.provinsi)
			getKecamatan(informasiPersonal.kabupaten)
			getKelurahan(informasiPersonal.kecamatan)
		}
	}

	onMount(() => {
		getProvinsi()
	})

</script>

<div class="bg-opening {progress_state == 1 || progress_state == 2 || progress_state == 4 ? '' : 'h-100'}" >
	<img src="/images/logo.png" class="opening-brand" alt="">
	<div class="flex h-100">
		<div class="flex flex-direction-col w-50 padding-image-register">
			<div class="flex flex-center-horizontal">
				<img src="/images/signup_vektor.svg" class="w-70" alt="">
			</div>
		</div>
		<div class="flex w-50 padding-register flex-direction-col flex-center-horizontal flex-center-vertical">
			<div class="flex flex-direction-col flex-gap-large w-80">
				<div class="flex flex-direction-col w-100">
					<div class="title-login">Ayo Bergabung dengan Kami</div>
					<div class="sub-title-login">di Internal Marketing Database System</div>
				</div>
				{#if progress_state == 1}
				<div class="w-100 flex flex-direction-col flex-gap-large" in:fly={{ y: -20, duration: 600 }}>
					<div class=" flex flex-direction-col flex-gap-semi-large w-100">
						<div class="flex flex-gap-regular flex-center-vertical">
							<div class="steps-title">Langkah 1</div>
							<div class="steps-sub-title">Informasi Personal</div>
						</div>
						<div class="flex flex-direction-col flex-gap-semi-small">
							<div class="title-input">Nama Lengkap</div>
							<input type="text" id="nama-lengkap" placeholder="masukkan nama lengkap disini.." class="input-col" value="{informasiPersonal.nama_lengkap}">
						</div>
						<div class="flex flex-direction-col flex-gap-semi-small">
							<div class="title-input">Nomor KTP</div>
							<input type="text" id="nomor-ktp" placeholder="1014XXXXXXXXX" class="input-col" value="{informasiPersonal.nomor_ktp}">
						</div>
						<div class="flex flex-direction-col flex-gap-semi-small">
							<div class="title-input">Alamat</div>
							<input type="text" id="alamat" placeholder="Jalan Sudirman" class="input-col" value="{informasiPersonal.alamat}">
						</div>
						<div class="flex flex-gap-regular">
							<div class="flex flex-direction-col flex-gap-semi-small w-20">
								<div class="title-input">RT</div>
								<input type="text" id="rt" placeholder="RT" class="input-col" value="{informasiPersonal.rt}">
							</div>
							<div class="flex flex-direction-col flex-gap-semi-small w-20">
								<div class="title-input">RW</div>
								<input type="text" id="rw" placeholder="RW" class="input-col" value="{informasiPersonal.rw}">
							</div>
							<div class="flex flex-direction-col flex-gap-semi-small w-60">
								<div class="title-input">Kelurahan</div>
								<!-- <input type="text" placeholder="Dago" class="input-col"> -->
								<select name="kelurahan" id="kelurahan" class="select-col" on:change={() => {
									let selectedKel = document.getElementById('kelurahan').value
									informasiPersonal.kelurahan = selectedKel
									
									getPosCode(selectedKel)
								}}>
									<option disabled selected value="">Pilih Kecamatan Terlebih Dahulu</option>
								</select>
							</div>
						</div>
						<div class="flex flex-gap-regular">
							<div class="flex flex-direction-col flex-gap-semi-small w-50">
								<div class="title-input">Kecamatan</div>
								<!-- <input type="text" placeholder="Coblong" class="input-col"> -->
								<select name="kecamatan" id="kecamatan" class="select-col" on:change={() => {
									let selectedKec = document.getElementById('kecamatan').value
									informasiPersonal.kecamatan = selectedKec
									
									getKelurahan(selectedKec)
								}}>
									<option disabled selected value="">Pilih Kota/Kabupaten Terlebih Dahulu</option>
								</select>
							</div>
							<div class="flex flex-direction-col flex-gap-semi-small w-50">
								<div class="title-input">Kode Pos</div>
								<input type="text" placeholder="XXXXX" class="input-col" id="post-code" disabled value="{informasiPersonal.kode_pos}">
							</div>
						</div>
						<div class="flex flex-gap-regular">
							<div class="flex flex-direction-col flex-gap-semi-small w-50">
								<div class="title-input">Kota/Kabupaten</div>
								<!-- <input type="text" placeholder="Kota Bandung" class="input-col"> -->
								<select name="kabupaten" id="kabupaten" class="select-col" on:change={() => {
									let selectedKab = document.getElementById('kabupaten').value
									informasiPersonal.kabupaten = selectedKab
									
									getKecamatan(selectedKab)
								}}>
									<option disabled selected value="">Pilih Provinsi Terlebih Dahulu</option>
								</select>
							</div>
							<div class="flex flex-direction-col flex-gap-semi-small w-50">
								<div class="title-input">Provinsi</div>
								<!-- <input type="text" placeholder="Jawa Barat" class="input-col"> -->
								<select name="provinsi" id="provinsi" class="select-col" on:change={() => {
									let selectedProv = document.getElementById('provinsi').value
									informasiPersonal.provinsi = selectedProv
									
									getKabupaten(selectedProv)
								}}>
									<option disabled selected hidden value="">Pilih Provinsi</option>
									{#if provinsi != null}
										{#each provinsi as prov}
										<option value="{prov.provinsi}">{prov.provinsi}</option>
										{/each}
									{/if}
								</select>
							</div>
						</div>
					</div>
					<div class="flex flex-direction-col flex-gap-regular w-100">
						<div class="flex flex-gap-small">
							<div class="progress-bar-on"></div>
							<div class="progress-bar-off"></div>
							<div class="progress-bar-off"></div>
							<div class="progress-bar-off"></div>
						</div>
						<button class="button-login flex flex-center-horizontal flex-center-vertical flex-gap-regular" on:click={() => {
							if(document.getElementById('nama-lengkap').value != ""){
								informasiPersonal.nama_lengkap = document.getElementById('nama-lengkap').value
							}

							if(document.getElementById('nomor-ktp').value != ""){
								informasiPersonal.nomor_ktp = document.getElementById('nomor-ktp').value
							}

							if(document.getElementById('alamat').value != ""){
								informasiPersonal.alamat = document.getElementById('alamat').value
							}

							if(document.getElementById('rt').value != ""){
								informasiPersonal.rt = document.getElementById('rt').value
							}

							if(document.getElementById('rw').value != ""){
								informasiPersonal.rw = document.getElementById('rw').value
							}

							stepOne = Object.values(informasiPersonal).every(x => x !== '')
							if(stepOne){
								progress_state++
								console.log(informasiPersonal)
							}else{
								alert("Lengkapi semua form!")
							}
						}}>
							<span>Berikutnya</span>
							<i class="fa-solid fa-angle-right"></i>
						</button>
						<div class="flex flex-center-horizontal flex-gap-small w-100">
							<div class="dont-have-acc">Sudah memiliki akun?</div>
							<a class="dont-have-acc-2 no-decor" href="/">Masuk sekarang</a>
						</div>
					</div>
				</div>
				{:else if progress_state == 2}
				<div class="w-100 flex flex-direction-col flex-gap-large" in:fly={{ y: -20, duration: 600 }}>
					<div class=" flex flex-direction-col flex-gap-semi-large w-100">
						<div class="flex flex-gap-regular flex-center-vertical">
							<div class="steps-title">Langkah 2</div>
							<div class="steps-sub-title">Informasi Bank</div>
						</div>
						<div class="flex flex-direction-col flex-gap-semi-small">
							<div class="title-input">Pilih Bank</div>
							<select class="select-col" id="bank">
								<option>Bank Mandiri</option>
								<option>Bank BRI</option>
								<option>Bank BCA</option>
							</select>
						</div>
						<div class="flex flex-direction-col flex-gap-semi-small">
							<div class="title-input">Nomor Rekening Bank</div>
							<input type="text" placeholder="1014XXXXXXXXX" class="input-col" id="nomor-rekening">
						</div>
						<div class="flex flex-direction-col flex-gap-semi-small">
							<div class="title-input">Cabang Bank</div>
							<input type="text" placeholder="Jalan Sudirman" class="input-col" id="cabang-bank">
						</div>
					</div>
					<div class="flex flex-direction-col flex-gap-regular w-100">
						<div class="flex flex-gap-small">
							<div class="progress-bar-on"></div>
							<div class="progress-bar-on"></div>
							<div class="progress-bar-off"></div>
							<div class="progress-bar-off"></div>
						</div>
						<div class="flex flex-gap-regular">
							<button class="button-login-outline flex flex-center-horizontal flex-center-vertical flex-gap-regular" on:click={() => {
								progress_state--
								console.log(informasiPersonal)
								setStepOneData()
						}}>
								<i class="fa-solid fa-angle-left"></i>
								<span>Kembali</span>
							</button>
							<button class="button-login flex flex-center-horizontal flex-center-vertical flex-gap-regular" on:click={() => {
								informasiBank.bank = document.getElementById('bank').value
								informasiBank.nomor_rekening = document.getElementById('nomor-rekening').value
								informasiBank.cabang_bank = document.getElementById('cabang-bank').value

								stepTwo = Object.values(informasiBank).every(x => x !== '')
								if(stepTwo){
									progress_state++
									console.log(informasiBank)
								}else{
									alert("Lengkapi semua form!")
								}
						}}>
								<span>Berikutnya</span>
								<i class="fa-solid fa-angle-right"></i>
							</button>
						</div>
						<div class="flex flex-center-horizontal flex-gap-small w-100">
							<div class="dont-have-acc">Sudah memiliki akun?</div>
							<a class="dont-have-acc-2 no-decor" href="/">Masuk sekarang</a>
						</div>
					</div>
				</div>
				{:else if progress_state == 3}
				<div class="w-100 flex flex-direction-col flex-gap-large" in:fly={{ y: -20, duration: 600 }}>
					<div class=" flex flex-direction-col flex-gap-semi-large w-100">
						<div class="flex flex-gap-regular flex-center-vertical">
							<div class="steps-title">Langkah 3</div>
							<div class="steps-sub-title">Penempatan</div>
						</div>
						<div class="flex flex-direction-col flex-gap-semi-small">
							<div class="title-input">Direkrut Sebagai</div>
							<select class="select-col" bind:value={jenis_marketing}>
								<option value="Lead Marketing">Lead Marketing</option>
								<option value="Marketing">Marketing</option>
							</select>
						</div>
						{#if jenis_marketing == 'Marketing'}
							<div class="flex flex-direction-col flex-gap-semi-small">
								<div class="title-input">Pilih Lead Marketing</div>
								<select class="select-col">
									<option value="Lead Marketing">Risky Setiawan</option>
									<option value="Marketing">Toni Tonaldo</option>
								</select>
							</div>
						{/if}
					</div>
					<div class="flex flex-direction-col flex-gap-regular w-100">
						<div class="flex flex-gap-small">
							<div class="progress-bar-on"></div>
							<div class="progress-bar-on"></div>
							<div class="progress-bar-on"></div>
							<div class="progress-bar-off"></div>
						</div>
						<div class="flex flex-gap-regular">
							<button class="button-login-outline flex flex-center-horizontal flex-center-vertical flex-gap-regular" on:click={() => {
							progress_state--
						}}>
								<i class="fa-solid fa-angle-left"></i>
								<span>Kembali</span>
							</button>
							<button class="button-login flex flex-center-horizontal flex-center-vertical flex-gap-regular" on:click={() => {
							progress_state++
						}}>
								<span>Berikutnya</span>
								<i class="fa-solid fa-angle-right"></i>
							</button>
						</div>
						<div class="flex flex-center-horizontal flex-gap-small w-100">
							<div class="dont-have-acc">Sudah memiliki akun?</div>
							<a class="dont-have-acc-2 no-decor" href="/">Masuk sekarang</a>
						</div>
					</div>
				</div>
				{:else if progress_state == 4}
				<div class="w-100 flex flex-direction-col flex-gap-large" in:fly={{ y: -20, duration: 600 }}>
					<div class=" flex flex-direction-col flex-gap-semi-large w-100">
						<div class="flex flex-gap-regular flex-center-vertical">
							<div class="steps-title">Langkah 4</div>
							<div class="steps-sub-title">Unggah Berkas</div>
						</div>
						<div class="flex flex-direction-col flex-gap-semi-small">
							<div class="title-input">Foto Copy KTP</div>
							<input type="file" class="input-col">
						</div>
						<div class="flex flex-direction-col flex-gap-semi-small">
							<div class="title-input">Foto Copy NPWP</div>
							<input type="file" class="input-col">
						</div>
						<div class="flex flex-direction-col flex-gap-semi-small">
							<div class="title-input">Foto Copy Buku Rekening (Halaman Depan)</div>
							<input type="file" class="input-col">
						</div>
						<div class="flex flex-direction-col flex-gap-semi-small">
							<div class="title-input">Surat Perjanjian Kerja Marketing</div>
							<input type="file" class="input-col">
						</div>
					</div>
					<div class="flex flex-direction-col flex-gap-regular w-100">
						<div class="flex flex-gap-small">
							<div class="progress-bar-on"></div>
							<div class="progress-bar-on"></div>
							<div class="progress-bar-on"></div>
							<div class="progress-bar-on"></div>
						</div>
						<div class="flex flex-gap-regular">
							<button class="button-login-outline flex flex-center-horizontal flex-center-vertical flex-gap-regular" on:click={() => {
							progress_state--
						}}>
								<i class="fa-solid fa-angle-left"></i>
								<span>Kembali</span>
							</button>
							<button class="button-login flex flex-center-horizontal flex-center-vertical flex-gap-regular" on:click={() => {
							// progress_state++
						}}>
								<span>Daftar</span>
								<i class="fa-solid fa-angle-right"></i>
							</button>
						</div>
						<div class="flex flex-center-horizontal flex-gap-small w-100">
							<div class="dont-have-acc">Sudah memiliki akun?</div>
							<a class="dont-have-acc-2 no-decor" href="/">Masuk sekarang</a>
						</div>
					</div>
				</div>
				{/if}
			</div>
		</div>
	</div>
</div>
