<script type="text/javascript">
	import Sidebar from '../../../../../../components/sidebar.svelte'
	import Navbar from '../../../../../../components/navbar.svelte'
	import { onMount } from 'svelte';
	import {fly, scale} from 'svelte/transition'

	import ApiController from '../../../../../../ApiController'
	let form= {
		no_spk: '',
		target_spk: '',
		mandor: '',
		blok: '',
		no_perumahan: '',
		unit: '',
		lantai: null,
		type: null,
		harga_unit: '',
		pricelist: '',
		mulai_pengerjaan: '',
		target_pengerjaan: '',
		selesai_pengerjaan: '',
		keteragan_pengerjaan: '',
		mulai_kavling: '',
		target_kavling: '',
		selesai_kavling: '',
		keterangan_kavling: '',
		foto_unit: null
	};

	function handleSubmit() {
		const formData = new FormData();
		formData.append('no_spk', form.no_spk);
		formData.append('target_spk', form.target_spk);
		formData.append('mandor', form.mandor);
		formData.append('blok', form.blok);
		formData.append('no_perumahan', form.no_perumahan);
		formData.append('unit', form.unit);
		formData.append('lantai', form.lantai);
		formData.append('type', form.type);
		formData.append('harga_unit', form.harga_unit);
		formData.append('pricelist', form.pricelist);
		formData.append('mulai_pengerjaan', form.mulai_pengerjaan);
		formData.append('target_pengerjaan', form.target_pengerjaan);
		formData.append('selesai_pengerjaan', form.selesai_pengerjaan);
		formData.append('keteragan_pengerjaan', form.keteragan_pengerjaan);
		formData.append('mulai_kavling', form.mulai_kavling);
		formData.append('target_kavling', form.target_kavling);
		formData.append('selesai_kavling', form.selesai_kavling);
		formData.append('keterangan_kavling', form.keterangan_kavling);
		formData.append('foto_unit', form.foto_unit);

		let postUnit = () => {
			ApiController({
				method: "POST",
				endpoint: `unit/add`,
				datas: formData
			}).then(response => {
				console.log(response)
			})
		}
		postUnit()
	}
</script>

<div id="after-login-layout">
	<Navbar/>
	<div class="flex">
		<Sidebar statusPointer="Kompilasi" pagePointer="admin"/>
		<div class="w-80 content">
			<div class="flex flex-direction-col flex-gap-large" in:fly={{ y: -20, duration: 600 }}>
				<div class="flex flex-direction-col flex-gap-semi-large w-100">
					<div class="flex flex-direction-col flex-gap-semi-small w-100">
						<div class="title-content">Tambah Unit</div>
						<div class="flex flex-gap-regular flex-center-vertical">
							<div class="text-breadcrumb">Kelola Perum</div>
							<img src="/images/icons/Arrow_Right.svg">
							<div class="text-breadcrumb">Detail</div>
							<img src="/images/icons/Arrow_Right.svg">
							<div class="text-breadcrumb-active">Tambah Unit</div>
						</div>
					</div>
					<div class="card w-70">
						<div class="flex flex-direction-col flex-gap-semi-large">
							<div class="flex flex-gap-regular">
								<div class="flex flex-direction-col flex-gap-small w-50">
									<div class="title-input-nup">No SPK</div>
									<input type="text" name="" class="input-nup" placeholder="no spk.." bind:value={form.no_spk}>
								</div>
								<div class="flex flex-direction-col flex-gap-small w-50">
									<div class="title-input-nup">Target SPK</div>
									<input type="text" name="" class="input-nup" placeholder="target spk.." bind:value={form.target_spk}>
								</div>
							</div>
							<div class="flex flex-gap-regular">
								<div class="flex flex-direction-col flex-gap-small w-100">
									<div class="title-input-nup">Subkon/Mandor</div>
									<input type="text" name="" class="input-nup" placeholder="subkon/mandor.." bind:value={form.mandor}>
								</div>
							</div>
							<div class="flex flex-gap-regular">
								<div class="flex flex-direction-col flex-gap-small w-25">
									<div class="title-input-nup">Blok</div>
									<select class="select-nup" bind:value={form.blok}>
										<option>AA2</option>
									</select>
								</div>
								<div class="flex flex-direction-col flex-gap-small w-komp">
									<div class="title-input-nup">No. Rumah</div>
									<input type="text" name="" class="input-nup" placeholder="lantai.." bind:value={form.no_perumahan}>
								</div>
								<div class="flex flex-direction-col flex-gap-small w-komp">
									<div class="title-input-nup">Lantai</div>
									<input type="text" name="" class="input-nup" placeholder="lantai.." bind:value={form.lantai}>
								</div>
								<div class="flex flex-direction-col flex-gap-small w-komp">
									<div class="title-input-nup">Unit</div>
									<input type="text" name="" class="input-nup" placeholder="unit.." bind:value={form.unit}>
								</div>
								<div class="flex flex-direction-col flex-gap-small w-komp">
									<div class="title-input-nup">Tipe</div>
									<input type="text" name="" class="input-nup" placeholder="tipe.." bind:value={form.type}>
								</div>
							</div>
							<div class="flex flex-direction-col flex-gap-semi-small">
								<div class="title-input-nup">Atur Tarif Unit</div>
								<div class="card-secondary flex flex-direction-col flex-gap-semi-large">
									<div class="flex flex-gap-regular">
										<div class="flex flex-direction-col flex-gap-small w-50">
											<div class="title-input-nup">Harga Unit</div>
											<input type="text" name="" class="input-nup" placeholder="harga unit.." bind:value={form.harga_unit}>
										</div>
										<div class="flex flex-direction-col flex-gap-small w-50">
											<div class="title-input-nup">Versi Pricelist</div>
											<input type="text" name="" class="input-nup" placeholder="versi pricelist.." bind:value={form.pricelist}>
										</div>
									</div>
								</div>
								<div class="title-input-nup">Waktu Pembangunan</div>
								<div class="card-secondary flex flex-direction-col flex-gap-semi-large">
									<div class="flex flex-gap-regular">
										<div class="flex flex-direction-col flex-gap-small w-31">
											<div class="title-input-nup">Mulai Pembangunan</div>
											<input type="date" name="" class="input-nup" bind:value={form.mulai_pengerjaan}>
										</div>
										<div class="flex flex-direction-col flex-gap-small w-31">
											<div class="title-input-nup">Target Selesai</div>
											<input type="date" name="" class="input-nup" bind:value={form.target_pengerjaan}>
										</div>
										<div class="flex flex-direction-col flex-gap-small w-31">
											<div class="title-input-nup">Selesai Pembangunan</div>
											<input type="date" name="" class="input-nup" bind:value={form.selesai_pengerjaan}>
										</div>
									</div>
									<div class="flex flex-gap-regular">
										<div class="flex flex-direction-col flex-gap-small w-100">
											<div class="title-input-nup">Keterangan</div>
											<textarea class="input-nup textarea-spec" placeholder="keterangan.." bind:value={form.keteragan_pengerjaan}></textarea>
										</div>
									</div>
								</div>
								<div class="title-input-nup">Kavling Siap Bangun</div>
								<div class="card-secondary flex flex-direction-col flex-gap-semi-large">
									<div class="flex flex-gap-regular">
										<div class="flex flex-direction-col flex-gap-small w-31">
											<div class="title-input-nup">Mulai Land Clearing</div>
											<input type="date" name="" class="input-nup" bind:value={form.mulai_kavling}>
										</div>
										<div class="flex flex-direction-col flex-gap-small w-31">
											<div class="title-input-nup">Target Selesai</div>
											<input type="date" name="" class="input-nup" bind:value={form.target_kavling}>
										</div>
										<div class="flex flex-direction-col flex-gap-small w-31">
											<div class="title-input-nup">Tanggal Selesai</div>
											<input type="date" name="" class="input-nup" bind:value={form.selesai_kavling}>
										</div>
									</div>
									<div class="flex flex-gap-regular">
										<div class="flex flex-direction-col flex-gap-small w-100">
											<div class="title-input-nup">Keterangan</div>
											<textarea class="input-nup textarea-spec" placeholder="keterangan.." bind:value={form.keterangan_kavling}></textarea>
										</div>
									</div>
								</div>
								<div class="title-input-nup">Unggah Berkas</div>
								<div class="card-secondary flex flex-direction-col flex-gap-semi-large">
									<div class="flex flex-gap-regular">
										<div class="flex flex-direction-col flex-gap-small w-48">
											<div class="title-input-nup">Foto Unit/Rancangan</div>
											<input type="file" class="file-nup" bind:value={form.foto_unit}>
										</div>
									</div>
								</div>
							</div>
						</div>
					</div>
					<div class="flex flex-end-horizontal w-70">
						<div class="w-40 flex flex-gap-regular flex-end-horizontal">
							<a href="/super-admin/kelola-perum/detail-perumahan" class="no-decor"><button class="btn-outline flex flex-center-vertical flex-gap-small"><span>Batal</span></button></a>
							<button class="btn-fill flex flex-center-vertical flex-gap-small" on:click={handleSubmit}><span>Simpan Unit</span></button>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</div>