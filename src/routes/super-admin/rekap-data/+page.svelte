<script type="text/javascript">
	import Sidebar from '../../../components/sidebar.svelte'
	import Navbar from '../../../components/navbar.svelte'
	import { onMount } from 'svelte';
	import {fly, scale} from 'svelte/transition'
	let tab_state = 1;
</script>

<div id="after-login-layout">
	<Navbar/>
	<div class="flex">
		<Sidebar statusPointer="Rekap" pagePointer="admin"/>
		<div class="w-80 content">
			<div class="flex flex-direction-col flex-gap-large" in:fly={{ y: -20, duration: 600 }}>
				<div class="flex flex-between-horizontal flex-center-vertical w-100">
					<div class="title-content">Rekap Data</div>
					<div class="flex flex-gap-regular">
						<button class="btn-outline flex flex-center-vertical flex-gap-small"><span>Download Rekap Konsumen</span> <img src="/images/icons/File_Download.svg"></button>
					</div>
				</div>
				<div class="flex flex-direction-col flex-gap-regular">
					<div class="flex flex-direction-col flex-gap-small">
						<div class="flex flex-gap-regular">
							<span class="{tab_state == 1 ? 'active-notif-button' : 'unactive-notif-button'}" on:click={() => {tab_state = 1}}>Finansial</span>
							<span class="{tab_state == 2 ? 'active-notif-button' : 'unactive-notif-button'}" on:click={() => {tab_state = 2}}>Konsumen</span>
							<span class="{tab_state == 3 ? 'active-notif-button' : 'unactive-notif-button'}" on:click={() => {tab_state = 3; console.log(tab_state)}}>Head Finance</span>
						</div>
					</div>
				</div>
				{#if tab_state == 1}
				<div class="flex flex-direction-col flex-gap-regular" in:fly={{ y: -20, duration: 600 }}>
					<div class="flex">
						<select class="select-col-2 w-25">
							<option disabled selected>Semua Perum</option>
							<option>Epicentrum Sepatan</option>
							<option>Serpong</option>
						</select>
					</div>
					<div class="flex flex-gap-semi-large w-100">
						<select class="select-col-3 w-15">
							<option>2023</option>
							<option>Serpong</option>
						</select>
						<input type="text" placeholder="Cari NUP" class="input-col-2 w-20">
						<input type="text" placeholder="Cari Head Marketing" class="input-col-2 w-20">
						<input type="text" placeholder="Cari Marketing" class="input-col-2 w-20">
					</div>
					<div class="scroll-x flex flex-direction-col flex-gap-regular">
						<div class="card-head w-content-4 height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-20 border-separate">
									<div class="text-drop-card">NUP</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-30 border-separate">
									<div class="text-drop-card">Perum</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 border-separate">
									<div class="text-drop-card">Blok</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 border-separate">
									<div class="text-drop-card">No</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 border-separate">
									<div class="text-drop-card">Tipe</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Harga Unit</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Pricelist</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Konsumen</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Head Marketing</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Marketing</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-50 border-separate-2">
									<div class="flex w-100 flex-center-horizontal border-bottom-seperate">
										<div class="text-drop-card padding-spec-nup-1">Booking Fee</div>
									</div>
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-60 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Tanggal</div>
										</div>
										<div class="flex flex-center-horizontal w-40">
											<div class="text-drop-card padding-spec-nup-1">Nominal</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-50 border-separate-2">
									<div class="flex w-100 flex-center-horizontal border-bottom-seperate">
										<div class="text-drop-card padding-spec-nup-1">Down Payment</div>
									</div>
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-60 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Tanggal</div>
										</div>
										<div class="flex flex-center-horizontal w-40">
											<div class="text-drop-card padding-spec-nup-1">Nominal</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-80 border-separate-2">
									<div class="flex w-100 flex-center-horizontal border-bottom-seperate">
										<div class="text-drop-card padding-spec-nup-1">Closing Fee</div>
									</div>
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Tanggal</div>
										</div>
										<div class="flex flex-center-horizontal w-31 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1">Voucher</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">Nominal</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-80 border-separate-2">
									<div class="flex w-100 flex-center-horizontal border-bottom-seperate">
										<div class="text-drop-card padding-spec-nup-1">Pengembalian Down Payment</div>
									</div>
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Tanggal</div>
										</div>
										<div class="flex flex-center-horizontal w-31 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1">Nominal</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">Pendapatan</div>
										</div>
									</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 border-separate">
									<div class="text-drop-card">Pendapatan Atas Perubahan</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Plafond BTN</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Tanggal Akad</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 border-separate">
									<div class="text-drop-card">Pencairan Akad dari BTN/Pembayaran Cash</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 border-separate">
									<div class="text-drop-card">Pembayaran DP atas Penjualan</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Sisa/Kekurangan Pembayaran</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Pembayaran Selisih Plafond</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Retensi</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Pencairan Retensi</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Sisa Retensi</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Sisa/Kekurangan Notaris</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Pembayaran Surat dan Notaris</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 border-separate">
									<div class="text-drop-card">Kekurangan Yang Belum Diterima</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Pembayaran Ke Notaris & Bank</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">SBUM</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Pencairan SBUM</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 border-separate">
									<div class="text-drop-card">Hutang/Piutang Konsumen Atas Notaris</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Titipan Akta Hutang</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Kelebihan Pembayaran Tanah</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Penerimaan Atas Subsidi</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Total Pencairan</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 border-non-separate">
									<div class="text-drop-card">Aksi</div>
									<img src="/images/icons/Arrow.svg">
								</div>
							</div>
						</div>
						<div class="card-head w-content-4 height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">3001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-30 no-border-table">
									<div class="text-drop-card">NMG</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">AO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">2</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">36/104</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 5.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">V.2018.04.14</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Aryo Adi Saputra</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-50 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-60">
											<div class="text-drop-card padding-spec-nup-1 ">06 Mar 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-40">
											<div class="text-drop-card padding-spec-nup-1">Rp. 1.000.000</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-50 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-60">
											<div class="text-drop-card padding-spec-nup-1 ">25 Jun 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-40">
											<div class="text-drop-card padding-spec-nup-1"></div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-80 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">15 Mar 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1">OP/2019/III/0260</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">Rp. 600.000</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-80 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 "></div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1"></div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 "></div>
										</div>
									</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 134.900.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">26 Jun 2019</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card">Rp. 116.900.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card">Rp. 3.100.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">0</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 8.550.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 500.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-center-horizontal flex-center-vertical w-10 no-border-table">
									<img src="/images/icons/Edit.svg">
								</div>
							</div>
						</div>
						<div class="card-head w-content-4 height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">3001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-30 no-border-table">
									<div class="text-drop-card">NMG</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">AO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">2</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">36/104</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 5.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">V.2018.04.14</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Aryo Adi Saputra</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-50 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-60">
											<div class="text-drop-card padding-spec-nup-1 ">06 Mar 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-40">
											<div class="text-drop-card padding-spec-nup-1">Rp. 1.000.000</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-50 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-60">
											<div class="text-drop-card padding-spec-nup-1 ">25 Jun 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-40">
											<div class="text-drop-card padding-spec-nup-1"></div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-80 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">15 Mar 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1">OP/2019/III/0260</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">Rp. 600.000</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-80 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 "></div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1"></div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 "></div>
										</div>
									</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 134.900.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">26 Jun 2019</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card">Rp. 116.900.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card">Rp. 3.100.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">0</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 8.550.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 500.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-center-horizontal flex-center-vertical w-10 no-border-table">
									<img src="/images/icons/Edit.svg">
								</div>
							</div>
						</div>
						<div class="card-head w-content-4 height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">3001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-30 no-border-table">
									<div class="text-drop-card">NMG</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">AO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">2</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">36/104</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 5.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">V.2018.04.14</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Aryo Adi Saputra</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-50 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-60">
											<div class="text-drop-card padding-spec-nup-1 ">06 Mar 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-40">
											<div class="text-drop-card padding-spec-nup-1">Rp. 1.000.000</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-50 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-60">
											<div class="text-drop-card padding-spec-nup-1 ">25 Jun 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-40">
											<div class="text-drop-card padding-spec-nup-1"></div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-80 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">15 Mar 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1">OP/2019/III/0260</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">Rp. 600.000</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-80 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 "></div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1"></div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 "></div>
										</div>
									</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 134.900.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">26 Jun 2019</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card">Rp. 116.900.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card">Rp. 3.100.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">0</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 8.550.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 500.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-center-horizontal flex-center-vertical w-10 no-border-table">
									<img src="/images/icons/Edit.svg">
								</div>
							</div>
						</div>
						<div class="card-head w-content-4 height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">3001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-30 no-border-table">
									<div class="text-drop-card">NMG</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">AO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">2</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">36/104</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 5.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">V.2018.04.14</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Aryo Adi Saputra</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-50 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-60">
											<div class="text-drop-card padding-spec-nup-1 ">06 Mar 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-40">
											<div class="text-drop-card padding-spec-nup-1">Rp. 1.000.000</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-50 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-60">
											<div class="text-drop-card padding-spec-nup-1 ">25 Jun 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-40">
											<div class="text-drop-card padding-spec-nup-1"></div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-80 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">15 Mar 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1">OP/2019/III/0260</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">Rp. 600.000</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-80 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 "></div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1"></div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 "></div>
										</div>
									</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 134.900.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">26 Jun 2019</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card">Rp. 116.900.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card">Rp. 3.100.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">0</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 8.550.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 500.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-center-horizontal flex-center-vertical w-10 no-border-table">
									<img src="/images/icons/Edit.svg">
								</div>
							</div>
						</div>
						<div class="card-head w-content-4 height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">3001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-30 no-border-table">
									<div class="text-drop-card">NMG</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">AO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">2</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">36/104</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 5.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">V.2018.04.14</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Aryo Adi Saputra</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-50 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-60">
											<div class="text-drop-card padding-spec-nup-1 ">06 Mar 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-40">
											<div class="text-drop-card padding-spec-nup-1">Rp. 1.000.000</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-50 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-60">
											<div class="text-drop-card padding-spec-nup-1 ">25 Jun 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-40">
											<div class="text-drop-card padding-spec-nup-1"></div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-80 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">15 Mar 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1">OP/2019/III/0260</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">Rp. 600.000</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-80 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 "></div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1"></div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 "></div>
										</div>
									</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 134.900.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">26 Jun 2019</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card">Rp. 116.900.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card">Rp. 3.100.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">0</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 8.550.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 500.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-center-horizontal flex-center-vertical w-10 no-border-table">
									<img src="/images/icons/Edit.svg">
								</div>
							</div>
						</div>
						<div class="card-head w-content-4 height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">3001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-30 no-border-table">
									<div class="text-drop-card">NMG</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">AO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">2</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">36/104</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 5.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">V.2018.04.14</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Aryo Adi Saputra</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-50 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-60">
											<div class="text-drop-card padding-spec-nup-1 ">06 Mar 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-40">
											<div class="text-drop-card padding-spec-nup-1">Rp. 1.000.000</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-50 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-60">
											<div class="text-drop-card padding-spec-nup-1 ">25 Jun 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-40">
											<div class="text-drop-card padding-spec-nup-1"></div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-80 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">15 Mar 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1">OP/2019/III/0260</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">Rp. 600.000</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-80 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 "></div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1"></div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 "></div>
										</div>
									</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 134.900.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">26 Jun 2019</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card">Rp. 116.900.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card">Rp. 3.100.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">0</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 8.550.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 500.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-center-horizontal flex-center-vertical w-10 no-border-table">
									<img src="/images/icons/Edit.svg">
								</div>
							</div>
						</div>
						<div class="card-head w-content-4 height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">3001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-30 no-border-table">
									<div class="text-drop-card">NMG</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">AO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">2</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">36/104</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 5.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">V.2018.04.14</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Aryo Adi Saputra</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-50 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-60">
											<div class="text-drop-card padding-spec-nup-1 ">06 Mar 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-40">
											<div class="text-drop-card padding-spec-nup-1">Rp. 1.000.000</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-50 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-60">
											<div class="text-drop-card padding-spec-nup-1 ">25 Jun 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-40">
											<div class="text-drop-card padding-spec-nup-1"></div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-80 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">15 Mar 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1">OP/2019/III/0260</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">Rp. 600.000</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-80 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 "></div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1"></div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 "></div>
										</div>
									</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 134.900.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">26 Jun 2019</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card">Rp. 116.900.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card">Rp. 3.100.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">0</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 8.550.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 500.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-center-horizontal flex-center-vertical w-10 no-border-table">
									<img src="/images/icons/Edit.svg">
								</div>
							</div>
						</div>
						<div class="card-head w-content-4 height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">3001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-30 no-border-table">
									<div class="text-drop-card">NMG</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">AO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">2</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">36/104</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 5.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">V.2018.04.14</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Aryo Adi Saputra</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-50 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-60">
											<div class="text-drop-card padding-spec-nup-1 ">06 Mar 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-40">
											<div class="text-drop-card padding-spec-nup-1">Rp. 1.000.000</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-50 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-60">
											<div class="text-drop-card padding-spec-nup-1 ">25 Jun 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-40">
											<div class="text-drop-card padding-spec-nup-1"></div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-80 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">15 Mar 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1">OP/2019/III/0260</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">Rp. 600.000</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-80 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 "></div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1"></div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 "></div>
										</div>
									</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 134.900.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">26 Jun 2019</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card">Rp. 116.900.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card">Rp. 3.100.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">0</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 8.550.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 500.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-center-horizontal flex-center-vertical w-10 no-border-table">
									<img src="/images/icons/Edit.svg">
								</div>
							</div>
						</div>
						<div class="card-head w-content-4 height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">3001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-30 no-border-table">
									<div class="text-drop-card">NMG</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">AO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">2</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">36/104</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 5.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">V.2018.04.14</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Aryo Adi Saputra</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-50 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-60">
											<div class="text-drop-card padding-spec-nup-1 ">06 Mar 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-40">
											<div class="text-drop-card padding-spec-nup-1">Rp. 1.000.000</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-50 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-60">
											<div class="text-drop-card padding-spec-nup-1 ">25 Jun 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-40">
											<div class="text-drop-card padding-spec-nup-1"></div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-80 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">15 Mar 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1">OP/2019/III/0260</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">Rp. 600.000</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-80 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 "></div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1"></div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 "></div>
										</div>
									</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 134.900.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">26 Jun 2019</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card">Rp. 116.900.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card">Rp. 3.100.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">0</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 8.550.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 500.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-center-horizontal flex-center-vertical w-10 no-border-table">
									<img src="/images/icons/Edit.svg">
								</div>
							</div>
						</div>
						<div class="card-head w-content-4 height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">3001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-30 no-border-table">
									<div class="text-drop-card">NMG</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">AO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">2</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">36/104</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 5.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">V.2018.04.14</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Aryo Adi Saputra</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-50 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-60">
											<div class="text-drop-card padding-spec-nup-1 ">06 Mar 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-40">
											<div class="text-drop-card padding-spec-nup-1">Rp. 1.000.000</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-50 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-60">
											<div class="text-drop-card padding-spec-nup-1 ">25 Jun 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-40">
											<div class="text-drop-card padding-spec-nup-1"></div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-80 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">15 Mar 2019</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1">OP/2019/III/0260</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">Rp. 600.000</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-80 flex-center-horizontal border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 "></div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1"></div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 "></div>
										</div>
									</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 134.900.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">26 Jun 2019</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card">Rp. 116.900.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card">Rp. 3.100.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">0</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 8.550.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 500.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-50 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card"></div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 18.000.000</div>
								</div>
								<div class="flex flex-center-horizontal flex-center-vertical w-10 no-border-table">
									<img src="/images/icons/Edit.svg">
								</div>
							</div>
						</div>
					</div>
					<div class="card w-100 height-fit">
						<div class="flex flex-between-horizontal">
							<div class="flex flex-gap-regular flex-center-vertical">
								<div class="text-display-sort">Menampilkan</div>
								<select class="select-sort">
									<option>10</option>
								</select>
								<div class="text-display-sort">dari <span class="bold-number">28</span> data Rekap Data</div>
							</div>
							<div class="flex flex-gap-regular flex-center-vertical">
								<div class="flex flex-center-vertical flex-center-horizontal border-pagination"><img src="/images/icons/Arrow_Left.svg"></div>
								<div class="flex flex-center-vertical flex-center-horizontal border-pagination"><div class="text-display-sort bold-number">1</div></div>
								<div class="flex flex-center-vertical flex-center-horizontal border-pagination"><img src="/images/icons/Arrow_Right.svg"></div>
							</div>
						</div>
					</div>
				</div>
				{:else if tab_state == 2}
				<div class="flex flex-direction-col flex-gap-regular" in:fly={{ y: -20, duration: 600 }}>
					<div class="flex">
						<select class="select-col-2 w-25">
							<option disabled selected>Semua Perum</option>
							<option>Epicentrum Sepatan</option>
							<option>Serpong</option>
						</select>
					</div>
					<div class="flex flex-gap-semi-large w-100">
						<select class="select-col-3 w-15">
							<option>2023</option>
							<option>Serpong</option>
						</select>
						<input type="text" placeholder="Cari Pemesan" class="input-col-2 w-20">
						<input type="text" placeholder="Cari Head Marketing" class="input-col-2 w-20">
						<input type="text" placeholder="Cari Marketing" class="input-col-2 w-20">
					</div>
					<div class="scroll-x flex flex-direction-col flex-gap-regular">
						<div class="card-head w-content-5 height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-20 border-separate">
									<div class="text-drop-card">NUP</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-30 border-separate">
									<div class="text-drop-card">Perum</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 border-separate">
									<div class="text-drop-card">Blok</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 border-separate">
									<div class="text-drop-card">No</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 border-separate">
									<div class="text-drop-card">Tipe</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Harga Unit</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Pricelist</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Head Marketing</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Marketing</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Nama Konsumen</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Jenis Kelamin</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-70 border-separate">
									<div class="text-drop-card">Alamat</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Pekerjaan</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 border-separate">
									<div class="text-drop-card">Koordinat Lokasi Usaha</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">No. KTP</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">No. Telepon</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Email</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">No. NPWP</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Nama Pasangan</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">No. KTP Pasangan</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-80 border-separate-2">
									<div class="flex w-100 flex-center-horizontal border-bottom-seperate">
										<div class="text-drop-card padding-spec-nup-1">BI Checking</div>
									</div>
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Status</div>
										</div>
										<div class="flex flex-center-horizontal w-31 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1">Tgl. Pengajuan</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">Tgl. Hasil</div>
										</div>
									</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 border-non-separate">
									<div class="text-drop-card">Aksi</div>
									<img src="/images/icons/Arrow.svg">
								</div>
							</div>
						</div>
						<div class="card-head w-content-5 height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">3001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-30 no-border-table">
									<div class="text-drop-card">NMG</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">AO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">2</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">36/104</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 5.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">V.2018.04.14</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Aryo Adi Saputra</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Laki-Laki</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-70 no-border-table">
									<div class="text-drop-card">Jalan Sudirman No. 32A, RT. 003, RW. 012, Kel. Dago</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Karyawan Swasta</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card">Jawa Barat</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">1471XXXXXXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">0852XXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">aryoadi@gmail.com</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">XX.XXX.XXX.X-XXX.XXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Poniyah</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">1471XXXXXXXXXXXX</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical flex-center-horizontal w-80 border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">Ya</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1">27 Apr 2018</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">04 Mei 2018</div>
										</div>
									</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical flex-center-horizontal w-10 border-non-separate">
									<img src="/images/icons/Edit.svg">
								</div>
							</div>
						</div>
						<div class="card-head w-content-5 height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">3001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-30 no-border-table">
									<div class="text-drop-card">NMG</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">AO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">2</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">36/104</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 5.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">V.2018.04.14</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Aryo Adi Saputra</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Laki-Laki</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-70 no-border-table">
									<div class="text-drop-card">Jalan Sudirman No. 32A, RT. 003, RW. 012, Kel. Dago</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Karyawan Swasta</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card">Jawa Barat</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">1471XXXXXXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">0852XXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">aryoadi@gmail.com</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">XX.XXX.XXX.X-XXX.XXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Poniyah</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">1471XXXXXXXXXXXX</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical flex-center-horizontal w-80 border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">Ya</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1">27 Apr 2018</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">04 Mei 2018</div>
										</div>
									</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical flex-center-horizontal w-10 border-non-separate">
									<img src="/images/icons/Edit.svg">
								</div>
							</div>
						</div>
						<div class="card-head w-content-5 height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">3001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-30 no-border-table">
									<div class="text-drop-card">NMG</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">AO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">2</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">36/104</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 5.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">V.2018.04.14</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Aryo Adi Saputra</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Laki-Laki</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-70 no-border-table">
									<div class="text-drop-card">Jalan Sudirman No. 32A, RT. 003, RW. 012, Kel. Dago</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Karyawan Swasta</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card">Jawa Barat</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">1471XXXXXXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">0852XXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">aryoadi@gmail.com</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">XX.XXX.XXX.X-XXX.XXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Poniyah</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">1471XXXXXXXXXXXX</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical flex-center-horizontal w-80 border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">Ya</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1">27 Apr 2018</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">04 Mei 2018</div>
										</div>
									</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical flex-center-horizontal w-10 border-non-separate">
									<img src="/images/icons/Edit.svg">
								</div>
							</div>
						</div>
						<div class="card-head w-content-5 height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">3001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-30 no-border-table">
									<div class="text-drop-card">NMG</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">AO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">2</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">36/104</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 5.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">V.2018.04.14</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Aryo Adi Saputra</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Laki-Laki</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-70 no-border-table">
									<div class="text-drop-card">Jalan Sudirman No. 32A, RT. 003, RW. 012, Kel. Dago</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Karyawan Swasta</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card">Jawa Barat</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">1471XXXXXXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">0852XXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">aryoadi@gmail.com</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">XX.XXX.XXX.X-XXX.XXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Poniyah</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">1471XXXXXXXXXXXX</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical flex-center-horizontal w-80 border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">Ya</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1">27 Apr 2018</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">04 Mei 2018</div>
										</div>
									</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical flex-center-horizontal w-10 border-non-separate">
									<img src="/images/icons/Edit.svg">
								</div>
							</div>
						</div>
						<div class="card-head w-content-5 height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">3001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-30 no-border-table">
									<div class="text-drop-card">NMG</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">AO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">2</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">36/104</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 5.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">V.2018.04.14</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Aryo Adi Saputra</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Laki-Laki</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-70 no-border-table">
									<div class="text-drop-card">Jalan Sudirman No. 32A, RT. 003, RW. 012, Kel. Dago</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Karyawan Swasta</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card">Jawa Barat</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">1471XXXXXXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">0852XXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">aryoadi@gmail.com</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">XX.XXX.XXX.X-XXX.XXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Poniyah</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">1471XXXXXXXXXXXX</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical flex-center-horizontal w-80 border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">Ya</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1">27 Apr 2018</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">04 Mei 2018</div>
										</div>
									</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical flex-center-horizontal w-10 border-non-separate">
									<img src="/images/icons/Edit.svg">
								</div>
							</div>
						</div>
						<div class="card-head w-content-5 height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">3001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-30 no-border-table">
									<div class="text-drop-card">NMG</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">AO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">2</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">36/104</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 5.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">V.2018.04.14</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Aryo Adi Saputra</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Laki-Laki</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-70 no-border-table">
									<div class="text-drop-card">Jalan Sudirman No. 32A, RT. 003, RW. 012, Kel. Dago</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Karyawan Swasta</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card">Jawa Barat</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">1471XXXXXXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">0852XXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">aryoadi@gmail.com</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">XX.XXX.XXX.X-XXX.XXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Poniyah</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">1471XXXXXXXXXXXX</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical flex-center-horizontal w-80 border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">Ya</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1">27 Apr 2018</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">04 Mei 2018</div>
										</div>
									</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical flex-center-horizontal w-10 border-non-separate">
									<img src="/images/icons/Edit.svg">
								</div>
							</div>
						</div>
						<div class="card-head w-content-5 height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">3001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-30 no-border-table">
									<div class="text-drop-card">NMG</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">AO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">2</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">36/104</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 5.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">V.2018.04.14</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Aryo Adi Saputra</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Laki-Laki</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-70 no-border-table">
									<div class="text-drop-card">Jalan Sudirman No. 32A, RT. 003, RW. 012, Kel. Dago</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Karyawan Swasta</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card">Jawa Barat</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">1471XXXXXXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">0852XXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">aryoadi@gmail.com</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">XX.XXX.XXX.X-XXX.XXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Poniyah</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">1471XXXXXXXXXXXX</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical flex-center-horizontal w-80 border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">Ya</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1">27 Apr 2018</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">04 Mei 2018</div>
										</div>
									</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical flex-center-horizontal w-10 border-non-separate">
									<img src="/images/icons/Edit.svg">
								</div>
							</div>
						</div>
						<div class="card-head w-content-5 height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">3001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-30 no-border-table">
									<div class="text-drop-card">NMG</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">AO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">2</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">36/104</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 5.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">V.2018.04.14</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Aryo Adi Saputra</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Laki-Laki</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-70 no-border-table">
									<div class="text-drop-card">Jalan Sudirman No. 32A, RT. 003, RW. 012, Kel. Dago</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Karyawan Swasta</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card">Jawa Barat</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">1471XXXXXXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">0852XXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">aryoadi@gmail.com</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">XX.XXX.XXX.X-XXX.XXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Poniyah</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">1471XXXXXXXXXXXX</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical flex-center-horizontal w-80 border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">Ya</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1">27 Apr 2018</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">04 Mei 2018</div>
										</div>
									</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical flex-center-horizontal w-10 border-non-separate">
									<img src="/images/icons/Edit.svg">
								</div>
							</div>
						</div>
						<div class="card-head w-content-5 height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">3001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-30 no-border-table">
									<div class="text-drop-card">NMG</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">AO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">2</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">36/104</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 5.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">V.2018.04.14</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Aryo Adi Saputra</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Laki-Laki</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-70 no-border-table">
									<div class="text-drop-card">Jalan Sudirman No. 32A, RT. 003, RW. 012, Kel. Dago</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Karyawan Swasta</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card">Jawa Barat</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">1471XXXXXXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">0852XXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">aryoadi@gmail.com</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">XX.XXX.XXX.X-XXX.XXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Poniyah</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">1471XXXXXXXXXXXX</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical flex-center-horizontal w-80 border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">Ya</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1">27 Apr 2018</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">04 Mei 2018</div>
										</div>
									</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical flex-center-horizontal w-10 border-non-separate">
									<img src="/images/icons/Edit.svg">
								</div>
							</div>
						</div>
						<div class="card-head w-content-5 height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">3001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-30 no-border-table">
									<div class="text-drop-card">NMG</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">AO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">2</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">36/104</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 5.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">V.2018.04.14</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Aryo Adi Saputra</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Laki-Laki</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-70 no-border-table">
									<div class="text-drop-card">Jalan Sudirman No. 32A, RT. 003, RW. 012, Kel. Dago</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Karyawan Swasta</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card">Jawa Barat</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">1471XXXXXXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">0852XXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">aryoadi@gmail.com</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">XX.XXX.XXX.X-XXX.XXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Poniyah</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">1471XXXXXXXXXXXX</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical flex-center-horizontal w-80 border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">Ya</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1">27 Apr 2018</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">04 Mei 2018</div>
										</div>
									</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical flex-center-horizontal w-10 border-non-separate">
									<img src="/images/icons/Edit.svg">
								</div>
							</div>
						</div>
						<div class="card-head w-content-5 height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">3001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-30 no-border-table">
									<div class="text-drop-card">NMG</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">AO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">2</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">36/104</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 5.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">V.2018.04.14</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Tjitojo Charles</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Aryo Adi Saputra</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Laki-Laki</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-70 no-border-table">
									<div class="text-drop-card">Jalan Sudirman No. 32A, RT. 003, RW. 012, Kel. Dago</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Karyawan Swasta</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card">Jawa Barat</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">1471XXXXXXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">0852XXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">aryoadi@gmail.com</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">XX.XXX.XXX.X-XXX.XXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Poniyah</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">1471XXXXXXXXXXXX</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical flex-center-horizontal w-80 border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">Ya</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1">27 Apr 2018</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">04 Mei 2018</div>
										</div>
									</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical flex-center-horizontal w-10 border-non-separate">
									<img src="/images/icons/Edit.svg">
								</div>
							</div>
						</div>
					</div>
					<div class="card w-100 height-fit">
						<div class="flex flex-between-horizontal">
							<div class="flex flex-gap-regular flex-center-vertical">
								<div class="text-display-sort">Menampilkan</div>
								<select class="select-sort">
									<option>10</option>
								</select>
								<div class="text-display-sort">dari <span class="bold-number">28</span> data Rekap Data</div>
							</div>
							<div class="flex flex-gap-regular flex-center-vertical">
								<div class="flex flex-center-vertical flex-center-horizontal border-pagination"><img src="/images/icons/Arrow_Left.svg"></div>
								<div class="flex flex-center-vertical flex-center-horizontal border-pagination"><div class="text-display-sort bold-number">1</div></div>
								<div class="flex flex-center-vertical flex-center-horizontal border-pagination"><img src="/images/icons/Arrow_Right.svg"></div>
							</div>
						</div>
					</div>
				</div>
				{:else if tab_state == 3}
				<div class="flex flex-direction-col flex-gap-regular" in:fly={{ y: -20, duration: 600 }}>
					<div class="flex">
						<select class="select-col-2 w-25">
							<option disabled selected>Semua Perum</option>
							<option>Epicentrum Sepatan</option>
							<option>Serpong</option>
						</select>
					</div>
					<div class="flex flex-gap-semi-large w-100">
						<input type="text" placeholder="Cari NUP" class="input-col-2 w-20">
						<input type="text" placeholder="Cari Pemesan" class="input-col-2 w-20">
						<input type="text" placeholder="Cari Notaris" class="input-col-2 w-20">
					</div>
					<div class="scroll-x flex flex-direction-col flex-gap-regular">
						<div class="card-head w-content-4 height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-10 border-separate">
									<div class="text-drop-card">NUP</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 border-separate">
									<div class="text-drop-card">Perum</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 border-separate">
									<div class="text-drop-card">Blok</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 border-separate">
									<div class="text-drop-card">No</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 border-separate">
									<div class="text-drop-card">Tipe</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-12 border-separate">
									<div class="text-drop-card">Nama Konsumen</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-12 border-separate">
									<div class="text-drop-card">Tanggal Akad</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-12 border-separate">
									<div class="text-drop-card">Nama Notaris</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-12 border-separate">
									<div class="text-drop-card">Plafond</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-12 border-separate">
									<div class="text-drop-card">Besar Plafond</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-12 border-separate">
									<div class="text-drop-card">Pencairan</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-12 border-separate">
									<div class="text-drop-card">Retensi</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-80 border-separate-2">
									<div class="flex w-100 flex-center-horizontal border-bottom-seperate">
										<div class="text-drop-card padding-spec-nup-1">Notaris</div>
									</div>
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-12 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Nominal PPH</div>
										</div>
										<div class="flex flex-center-horizontal w-12 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Tgl Bayar PPH</div>
										</div>
										<div class="flex flex-center-horizontal w-12 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Nominal BPHTB</div>
										</div>
										<div class="flex flex-center-horizontal w-12 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Tgl Bayar BPHTB</div>
										</div>
										<div class="flex flex-center-horizontal w-12 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Nominal ROYA</div>
										</div>
										<div class="flex flex-center-horizontal w-12 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Tgl Bayar ROYA</div>
										</div>
										<div class="flex flex-center-horizontal w-12 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Biaya Notaris</div>
										</div>
										<div class="flex flex-center-horizontal w-12 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Tgl Bayar Notaris</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-40 border-separate-2">
									<div class="flex w-100 flex-center-horizontal border-bottom-seperate">
										<div class="text-drop-card padding-spec-nup-1">PPJB/AJB</div>
									</div>
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-25 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Nilai</div>
										</div>
										<div class="flex flex-center-horizontal w-25 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Diajukan</div>
										</div>
										<div class="flex flex-center-horizontal w-25 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Tanggal Cair</div>
										</div>
										<div class="flex flex-center-horizontal w-25 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Outstanding</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-40 border-separate-2">
									<div class="flex w-100 flex-center-horizontal border-bottom-seperate">
										<div class="text-drop-card padding-spec-nup-1">SPPH</div>
									</div>
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-25 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Tanggal Bayar</div>
										</div>
										<div class="flex flex-center-horizontal w-25 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Selisih Plafond</div>
										</div>
										<div class="flex flex-center-horizontal w-25 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Tanggal Bayar</div>
										</div>
										<div class="flex flex-center-horizontal w-25 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Selisih Notaris</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-20 border-separate-2">
									<div class="flex w-100 flex-center-horizontal border-bottom-seperate">
										<div class="text-drop-card padding-spec-nup-1">SBUM</div>
									</div>
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-50 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Nilai</div>
										</div>
										<div class="flex flex-center-horizontal w-50 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Tanggal Cair</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-50 border-separate-2">
									<div class="flex w-100 flex-center-horizontal border-bottom-seperate">
										<div class="text-drop-card padding-spec-nup-1">Jaminan Kelayakan Konstruksi</div>
									</div>
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-20 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Nilai</div>
										</div>
										<div class="flex flex-center-horizontal w-20 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Diajukan</div>
										</div>
										<div class="flex flex-center-horizontal w-20 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Tanggal Cair</div>
										</div>
										<div class="flex flex-center-horizontal w-20 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Nominal Cair</div>
										</div>
										<div class="flex flex-center-horizontal w-20 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Sisa</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-80 border-separate-2">
									<div class="flex w-100 flex-center-horizontal border-bottom-seperate">
										<div class="text-drop-card padding-spec-nup-1">IMB</div>
									</div>
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-14 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Nilai</div>
										</div>
										<div class="flex flex-center-horizontal w-14 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Pengajuan</div>
										</div>
										<div class="flex flex-center-horizontal w-14 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Tanggal Cair</div>
										</div>
										<div class="flex flex-center-horizontal w-14 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Nilai Cair</div>
										</div>
										<div class="flex flex-center-horizontal w-14 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Cair dari Bank</div>
										</div>
										<div class="flex flex-center-horizontal w-14 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Nilai Outstanding</div>
										</div>
										<div class="flex flex-center-horizontal w-14">
											<div class="text-drop-card padding-spec-nup-1 ">Outstanding dari Bank</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-80 border-separate-2">
									<div class="flex w-100 flex-center-horizontal border-bottom-seperate">
										<div class="text-drop-card padding-spec-nup-1">Listrik</div>
									</div>
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-14 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Nilai</div>
										</div>
										<div class="flex flex-center-horizontal w-14 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Pengajuan</div>
										</div>
										<div class="flex flex-center-horizontal w-14 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Tanggal Cair</div>
										</div>
										<div class="flex flex-center-horizontal w-14 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Nilai Cair</div>
										</div>
										<div class="flex flex-center-horizontal w-14 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Cair dari Bank</div>
										</div>
										<div class="flex flex-center-horizontal w-14 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Nilai Outstanding</div>
										</div>
										<div class="flex flex-center-horizontal w-14">
											<div class="text-drop-card padding-spec-nup-1 ">Outstanding dari Bank</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical w-80 border-separate-2">
									<div class="flex w-100 flex-center-horizontal border-bottom-seperate">
										<div class="text-drop-card padding-spec-nup-1">BESTEK</div>
									</div>
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-14 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Nilai</div>
										</div>
										<div class="flex flex-center-horizontal w-14 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Pengajuan</div>
										</div>
										<div class="flex flex-center-horizontal w-14 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Tanggal Cair</div>
										</div>
										<div class="flex flex-center-horizontal w-14 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Nilai Cair</div>
										</div>
										<div class="flex flex-center-horizontal w-14 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Cair dari Bank</div>
										</div>
										<div class="flex flex-center-horizontal w-14 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Nilai Outstanding</div>
										</div>
										<div class="flex flex-center-horizontal w-14">
											<div class="text-drop-card padding-spec-nup-1 ">Outstanding dari Bank</div>
										</div>
									</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 border-separate">
									<div class="text-drop-card">Retensi Cair</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 border-separate">
									<div class="text-drop-card">Pengajuan</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 border-separate">
									<div class="text-drop-card">Sisa Retensi</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 border-separate">
									<div class="text-drop-card">Rekap</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15 border-separate">
									<div class="text-drop-card">Bukti Pembayaran Notaris</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15 border-separate">
									<div class="text-drop-card">Bukti Pencairan Retensi</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 border-non-separate">
									<div class="text-drop-card">Aksi</div>
									<img src="/images/icons/Arrow.svg">
								</div>
							</div>
						</div>
						<div class="card-head w-content-4 height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<div class="text-drop-card">NUP</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<div class="text-drop-card">Perum</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<div class="text-drop-card">Blok</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<div class="text-drop-card">No</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<div class="text-drop-card">Tipe</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-12 no-border-table">
									<div class="text-drop-card">Nama Konsumen</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-12 no-border-table">
									<div class="text-drop-card">Tanggal Akad</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-12 no-border-table">
									<div class="text-drop-card">Nama Notaris</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-12 no-border-table">
									<div class="text-drop-card">Plafond</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-12 no-border-table">
									<div class="text-drop-card">Besar Plafond</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-12 no-border-table">
									<div class="text-drop-card">Pencairan</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-12 no-border-table">
									<div class="text-drop-card">Retensi</div>
								</div>
								<div class="flex flex-direction-col flex-center-horizontal flex-center-vertical w-80 border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-12">
											<div class="text-drop-card padding-spec-nup-1 ">Nominal PPH</div>
										</div>
										<div class="flex flex-center-horizontal w-12">
											<div class="text-drop-card padding-spec-nup-1 ">Tgl Bayar PPH</div>
										</div>
										<div class="flex flex-center-horizontal w-12">
											<div class="text-drop-card padding-spec-nup-1 ">Nominal BPHTB</div>
										</div>
										<div class="flex flex-center-horizontal w-12">
											<div class="text-drop-card padding-spec-nup-1 ">Tgl Bayar BPHTB</div>
										</div>
										<div class="flex flex-center-horizontal w-12">
											<div class="text-drop-card padding-spec-nup-1 ">Nominal ROYA</div>
										</div>
										<div class="flex flex-center-horizontal w-12">
											<div class="text-drop-card padding-spec-nup-1 ">Tgl Bayar ROYA</div>
										</div>
										<div class="flex flex-center-horizontal w-12">
											<div class="text-drop-card padding-spec-nup-1 ">Biaya Notaris</div>
										</div>
										<div class="flex flex-center-horizontal w-12">
											<div class="text-drop-card padding-spec-nup-1 ">Tgl Bayar Notaris</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-horizontal flex-center-vertical w-40 border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-25">
											<div class="text-drop-card padding-spec-nup-1 ">Nilai</div>
										</div>
										<div class="flex flex-center-horizontal w-25">
											<div class="text-drop-card padding-spec-nup-1 ">Diajukan</div>
										</div>
										<div class="flex flex-center-horizontal w-25">
											<div class="text-drop-card padding-spec-nup-1 ">Tanggal Cair</div>
										</div>
										<div class="flex flex-center-horizontal w-25">
											<div class="text-drop-card padding-spec-nup-1 ">Outstanding</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-horizontal flex-center-vertical w-40 border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-25">
											<div class="text-drop-card padding-spec-nup-1 ">Tanggal Bayar</div>
										</div>
										<div class="flex flex-center-horizontal w-25">
											<div class="text-drop-card padding-spec-nup-1 ">Selisih Plafond</div>
										</div>
										<div class="flex flex-center-horizontal w-25">
											<div class="text-drop-card padding-spec-nup-1 ">Tanggal Bayar</div>
										</div>
										<div class="flex flex-center-horizontal w-25">
											<div class="text-drop-card padding-spec-nup-1 ">Selisih Notaris</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-horizontal flex-center-vertical w-20 border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-50">
											<div class="text-drop-card padding-spec-nup-1 ">Nilai</div>
										</div>
										<div class="flex flex-center-horizontal w-50">
											<div class="text-drop-card padding-spec-nup-1 ">Tanggal Cair</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-vertical flex-center-horizontal w-50 border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-20">
											<div class="text-drop-card padding-spec-nup-1 ">Nilai</div>
										</div>
										<div class="flex flex-center-horizontal w-20">
											<div class="text-drop-card padding-spec-nup-1 ">Diajukan</div>
										</div>
										<div class="flex flex-center-horizontal w-20">
											<div class="text-drop-card padding-spec-nup-1 ">Tanggal Cair</div>
										</div>
										<div class="flex flex-center-horizontal w-20">
											<div class="text-drop-card padding-spec-nup-1 ">Nominal Cair</div>
										</div>
										<div class="flex flex-center-horizontal w-20">
											<div class="text-drop-card padding-spec-nup-1 ">Sisa</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-horizontal flex-center-vertical w-80 border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-14">
											<div class="text-drop-card padding-spec-nup-1 ">Nilai</div>
										</div>
										<div class="flex flex-center-horizontal w-14">
											<div class="text-drop-card padding-spec-nup-1 ">Pengajuan</div>
										</div>
										<div class="flex flex-center-horizontal w-14">
											<div class="text-drop-card padding-spec-nup-1 ">Tanggal Cair</div>
										</div>
										<div class="flex flex-center-horizontal w-14">
											<div class="text-drop-card padding-spec-nup-1 ">Nilai Cair</div>
										</div>
										<div class="flex flex-center-horizontal w-14">
											<div class="text-drop-card padding-spec-nup-1 ">Cair dari Bank</div>
										</div>
										<div class="flex flex-center-horizontal w-14">
											<div class="text-drop-card padding-spec-nup-1 ">Nilai Outstanding</div>
										</div>
										<div class="flex flex-center-horizontal w-14">
											<div class="text-drop-card padding-spec-nup-1 ">Outstanding dari Bank</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-horizontal flex-center-vertical w-80 border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-14">
											<div class="text-drop-card padding-spec-nup-1 ">Nilai</div>
										</div>
										<div class="flex flex-center-horizontal w-14">
											<div class="text-drop-card padding-spec-nup-1 ">Pengajuan</div>
										</div>
										<div class="flex flex-center-horizontal w-14">
											<div class="text-drop-card padding-spec-nup-1 ">Tanggal Cair</div>
										</div>
										<div class="flex flex-center-horizontal w-14">
											<div class="text-drop-card padding-spec-nup-1 ">Nilai Cair</div>
										</div>
										<div class="flex flex-center-horizontal w-14">
											<div class="text-drop-card padding-spec-nup-1 ">Cair dari Bank</div>
										</div>
										<div class="flex flex-center-horizontal w-14">
											<div class="text-drop-card padding-spec-nup-1 ">Nilai Outstanding</div>
										</div>
										<div class="flex flex-center-horizontal w-14">
											<div class="text-drop-card padding-spec-nup-1 ">Outstanding dari Bank</div>
										</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-center-horizontal flex-center-vertical w-80 border-separate-3">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-14">
											<div class="text-drop-card padding-spec-nup-1 ">Nilai</div>
										</div>
										<div class="flex flex-center-horizontal w-14">
											<div class="text-drop-card padding-spec-nup-1 ">Pengajuan</div>
										</div>
										<div class="flex flex-center-horizontal w-14">
											<div class="text-drop-card padding-spec-nup-1 ">Tanggal Cair</div>
										</div>
										<div class="flex flex-center-horizontal w-14">
											<div class="text-drop-card padding-spec-nup-1 ">Nilai Cair</div>
										</div>
										<div class="flex flex-center-horizontal w-14">
											<div class="text-drop-card padding-spec-nup-1 ">Cair dari Bank</div>
										</div>
										<div class="flex flex-center-horizontal w-14">
											<div class="text-drop-card padding-spec-nup-1 ">Nilai Outstanding</div>
										</div>
										<div class="flex flex-center-horizontal w-14">
											<div class="text-drop-card padding-spec-nup-1 ">Outstanding dari Bank</div>
										</div>
									</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<div class="text-drop-card">Retensi Cair</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<div class="text-drop-card">Pengajuan</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<div class="text-drop-card">Sisa Retensi</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<div class="text-drop-card">Rekap</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15 no-border-table">
									<div class="text-drop-card">Bukti Pembayaran Notaris</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15 no-border-table">
									<div class="text-drop-card">Bukti Pencairan Retensi</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 border-non-separate">
									<div class="text-drop-card">Aksi</div>
								</div>
							</div>
						</div>
					</div>
					<div class="card w-100 height-fit">
						<div class="flex flex-between-horizontal">
							<div class="flex flex-gap-regular flex-center-vertical">
								<div class="text-display-sort">Menampilkan</div>
								<select class="select-sort">
									<option>10</option>
								</select>
								<div class="text-display-sort">dari <span class="bold-number">28</span> data Rekap Data</div>
							</div>
							<div class="flex flex-gap-regular flex-center-vertical">
								<div class="flex flex-center-vertical flex-center-horizontal border-pagination"><img src="/images/icons/Arrow_Left.svg"></div>
								<div class="flex flex-center-vertical flex-center-horizontal border-pagination"><div class="text-display-sort bold-number">1</div></div>
								<div class="flex flex-center-vertical flex-center-horizontal border-pagination"><img src="/images/icons/Arrow_Right.svg"></div>
							</div>
						</div>
					</div>
				</div>
				{/if}
			</div>
		</div>
	</div>
</div>