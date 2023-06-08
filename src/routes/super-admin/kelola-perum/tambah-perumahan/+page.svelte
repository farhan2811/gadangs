<script type="text/javascript">
	import Sidebar from '../../../../components/sidebar.svelte'
	import Navbar from '../../../../components/navbar.svelte'
	import { onMount } from 'svelte';
	import {fly, scale} from 'svelte/transition'
</script>

<div id="after-login-layout">
	<Navbar/>
	<div class="flex">
		<Sidebar statusPointer="KelolaPerum" pagePointer="admin"/>
		<div class="w-80 content">
			<div class="flex flex-direction-col flex-gap-large" in:fly={{ y: -20, duration: 600 }}>
				<div class="flex flex-direction-col flex-gap-semi-large w-100">
					<div class="flex flex-direction-col flex-gap-semi-small w-100">
						<div class="title-content">Tambah Perumahan</div>
						<div class="flex flex-gap-regular flex-center-vertical">
							<div class="text-breadcrumb">Kelola Perum</div>
							<img src="/images/icons/Arrow_Right.svg">
							<div class="text-breadcrumb-active">Tambah</div>
						</div>
					</div>
					<div class="card w-60">
						<div class="flex flex-direction-col flex-gap-semi-large">
							<div class="flex flex-center-vertical">
								<div class="title-card-tambah-nup">Informasi Bank</div>
							</div>
							<div class="flex flex-gap-regular">
								<div class="flex flex-direction-col flex-gap-small w-60">
									<div class="title-input-nup">Nama Perumahan</div>
									<input type="text" name="" class="input-nup" placeholder="nama perumahan..">
								</div>
								<div class="flex flex-direction-col flex-gap-small w-40">
									<div class="title-input-nup">Singkatan Perumahan</div>
									<input type="text" name="" class="input-nup" placeholder="singkatan perumahan..">
								</div>
							</div>
							<div class="flex flex-gap-regular">
								<div class="flex flex-direction-col flex-gap-small w-100">
									<div class="title-input-nup">Alamat Perumahan</div>
									<input type="text" name="" class="input-nup" placeholder="alamat perumahan..">
								</div>
							</div>
							<div class="flex flex-gap-regular">
								<div class="flex flex-direction-col flex-gap-small w-60">
									<div class="title-input-nup">Provinsi</div>
									<select class="select-nup">
										<option>Jawa Timur</option>
									</select>
								</div>
								<div class="flex flex-direction-col flex-gap-small w-40">
									<div class="title-input-nup">Kode Pos</div>
									<input type="text" name="" class="input-nup" placeholder="kode pos..">
								</div>
							</div>
							<div class="flex flex-gap-regular">
								<div class="flex flex-direction-col flex-gap-small w-50">
									<div class="title-input-nup">Telepon</div>
									<input type="text" name="" class="input-nup" placeholder="telepon..">
								</div>
								<div class="flex flex-direction-col flex-gap-small w-50">
									<div class="title-input-nup">Fax</div>
									<input type="text" name="" class="input-nup" placeholder="fax..">
								</div>
							</div>
							<div class="flex flex-gap-regular">
								<div class="flex flex-direction-col flex-gap-small w-48">
									<div class="title-input-nup">Gambar Perumahan</div>
									<input type="file" class="file-nup">
								</div>
								<div class="flex flex-direction-col flex-gap-small w-48">
									<div class="title-input-nup">Site Plan</div>
									<input type="file" class="file-nup">
								</div>
							</div>
						</div>
					</div>
					<div class="flex flex-end-horizontal w-60">
						<div class="w-50 flex flex-gap-regular flex-end-horizontal">
							<button class="btn-outline flex flex-center-vertical flex-gap-small"><span>Batal</span></button>
							<button class="btn-fill flex flex-center-vertical flex-gap-small"><span>Simpan Perumahan</span></button>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</div>