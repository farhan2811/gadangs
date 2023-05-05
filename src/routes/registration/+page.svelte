<script type="text/javascript">
	import {fly, scale} from 'svelte/transition'

	let progress_state = 1;
	let jenis_marketing = 'Lead Marketing';
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
							<input type="text" placeholder="masukkan nama lengkap disini.." class="input-col">
						</div>
						<div class="flex flex-direction-col flex-gap-semi-small">
							<div class="title-input">Nomor KTP</div>
							<input type="text" placeholder="1014XXXXXXXXX" class="input-col">
						</div>
						<div class="flex flex-direction-col flex-gap-semi-small">
							<div class="title-input">Alamat</div>
							<input type="text" placeholder="Jalan Sudirman" class="input-col">
						</div>
						<div class="flex flex-gap-regular">
							<div class="flex flex-direction-col flex-gap-semi-small w-20">
								<div class="title-input">RT</div>
								<input type="text" placeholder="RT" class="input-col">
							</div>
							<div class="flex flex-direction-col flex-gap-semi-small w-20">
								<div class="title-input">RW</div>
								<input type="text" placeholder="RW" class="input-col">
							</div>
							<div class="flex flex-direction-col flex-gap-semi-small w-60">
								<div class="title-input">Kelurahan</div>
								<input type="text" placeholder="Dago" class="input-col">
							</div>
						</div>
						<div class="flex flex-gap-regular">
							<div class="flex flex-direction-col flex-gap-semi-small w-50">
								<div class="title-input">Kecamatan</div>
								<input type="text" placeholder="Coblong" class="input-col">
							</div>
							<div class="flex flex-direction-col flex-gap-semi-small w-50">
								<div class="title-input">Kode Pos</div>
								<input type="text" placeholder="28282" class="input-col">
							</div>
						</div>
						<div class="flex flex-gap-regular">
							<div class="flex flex-direction-col flex-gap-semi-small w-50">
								<div class="title-input">Kota/Kabupaten</div>
								<input type="text" placeholder="Kota Bandung" class="input-col">
							</div>
							<div class="flex flex-direction-col flex-gap-semi-small w-50">
								<div class="title-input">Provinsi</div>
								<input type="text" placeholder="Jawa Barat" class="input-col">
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
							progress_state++
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
							<select class="select-col">
								<option>Bank Mandiri</option>
								<option>Bank BRI</option>
								<option>Bank BCA</option>
							</select>
						</div>
						<div class="flex flex-direction-col flex-gap-semi-small">
							<div class="title-input">Nomor Rekening Bank</div>
							<input type="text" placeholder="1014XXXXXXXXX" class="input-col">
						</div>
						<div class="flex flex-direction-col flex-gap-semi-small">
							<div class="title-input">Cabang Bank</div>
							<input type="text" placeholder="Jalan Sudirman" class="input-col">
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
