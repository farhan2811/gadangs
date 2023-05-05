<script type="text/javascript">
	import Sidebar from '../../../../components/sidebar.svelte'
	import Navbar from '../../../../components/navbar.svelte'
	import { onMount } from 'svelte';
	import {fly, scale} from 'svelte/transition'
	
</script>

<div id="after-login-layout">
	<Navbar/>
	<div class="flex">
		<Sidebar statusPointer="Nup" pagePointer="admin"/>
		<div class="w-80 content">
			<div class="flex flex-direction-col flex-gap-large" in:fly={{ y: -20, duration: 600 }}>
				<div class="flex flex-between-horizontal flex-center-vertical w-100">
					<div class="flex  flex-direction-col flex-between-horizontal flex-gap-semi-small w-100">
						<div class="title-content">Detail NUP</div>
						<div class="flex flex-gap-regular flex-center-vertical">
							<div class="text-breadcrumb">NUP</div>
							<img src="/images/icons/Arrow_Right.svg">
							<div class="text-breadcrumb-active">Detail NUP</div>
						</div>
					</div>
					<div class="flex flex-gap-regular">
						<a href="/super-admin/nup/edit-nup" class="no-decor"><button class="btn-fill-warning flex flex-center-vertical flex-gap-small"><img src="/images/icons/Edit_White.svg"> <span>Edit</span></button></a>
						<a href="/super-admin/nup/detail-nup" class="no-decor"><button class="btn-fill-danger flex flex-center-vertical flex-gap-small"><img src="/images/icons/Trash_White.svg"> <span>Hapus</span></button></a>
					</div>
				</div>
				<div class="card w-100 flex flex-gap-semi-large">
					<div class="w-40">
						<img class="img-detail w-100 h-100" src="/images/rumah.png">
					</div>
					<div class="w-60 flex flex-direction-col flex-gap-large">
						<div class="flex flex-gap-regular">
							<div class="w-50 flex flex-direction-col flex-gap-small">
								<div class="main-title-card-detail">Gria Esma Cicalengka</div>
								<div class="main-sub-title-card-detail">Nomor Urut Pemesan: 70081</div>
							</div>
							<div class="w-50 flex flex-gap-regular">
								<div class="label-success flex flex-center-horizontal flex-gap-small">
									<span>Approved HO</span>
									<img src="/images/icons/Check_White.svg">
								</div>
								<div class="label-success flex flex-center-horizontal flex-gap-small">
									<span>Approved Finance</span>
									<img src="/images/icons/Check_White.svg">
								</div>
							</div>
						</div>
						<div class="flex flex-gap-regular">
							<div class="w-50 flex flex-direction-col flex-gap-regular">
								<div class="secondary-title-card-detail">Pengajuan Unit</div>
								<div class="flex flex-direction-col">
									<div class="caption-card-detail">Tipe Pengajuan (KPR/KPA)</div>
									<div class="content-card-detail">Subsidi</div>
								</div>
								<div class="flex flex-direction-col">
									<div class="caption-card-detail">Tanggal Submit</div>
									<div class="content-card-detail">25 April 2018</div>
								</div>
								<div class="flex w-100">
									<div class="flex flex-direction-col w-50">
										<div class="caption-card-detail">Harga Unit</div>
										<div class="content-card-detail">Rp. 500.000.000</div>
									</div>
									<div class="flex flex-direction-col">
										<div class="caption-card-detail">Versi Price List</div>
										<div class="content-card-detail">V.2018.04.14</div>
									</div>
								</div>
								<div class="flex flex-direction-col flex-gap-semi-small">
									<div class="caption-card-detail">Pilihan Unit</div>
									<div class="data-perum-detail flex flex-direction-col flex-gap-regular">
										<div class="content-card-detail">Alternatif 1</div>
										<div class="flex flex-direction-col">
											<div class="caption-card-detail">Jenis Bangunan</div>
											<div class="content-card-detail">Perumahan</div>
										</div>
										<div class="flex w-100">
											<div class="flex flex-direction-col w-50">
												<div class="caption-card-detail">Blok</div>
												<div class="content-card-detail">A2</div>
											</div>
											<div class="flex flex-direction-col">
												<div class="caption-card-detail">Nomor</div>
												<div class="content-card-detail">02</div>
											</div>
										</div>
										<div class="flex w-100">
											<div class="flex flex-direction-col w-50">
												<div class="caption-card-detail">Lantai</div>
												<div class="content-card-detail">1 Lantai</div>
											</div>
											<div class="flex flex-direction-col">
												<div class="caption-card-detail">Tipe</div>
												<div class="content-card-detail">35/66 m²</div>
											</div>
										</div>
									</div>
								</div>
							</div>
							<div class="w-50 flex flex-direction-col flex-gap-regular">
								<div class="secondary-title-card-detail">Marketing</div>
								<div class="flex flex-direction-col">
									<div class="caption-card-detail">Lead Marketing</div>
									<div class="content-card-detail">Zaenal Muhtarom</div>
								</div>
								<div class="flex flex-direction-col">
									<div class="caption-card-detail">Marketing</div>
									<div class="content-card-detail">Zaenal Muhtarom</div>
								</div>
								<div class="card-secondary flex flex-direction-col flex-gap-semi-small">
									<div class="caption-card-detail">Dokumen Pendukung</div>
									<div class="flex flex-direction-col">
										<div class="caption-card-detail">Berkas NUP</div>	
										<a href="#" class="no-decor link-detail">lihat</a>
									</div>
								</div>
							</div>
						</div>
					</div>
				</div>
				<div class="flex w-100 flex-gap-large">
					<div class="card w-50 flex flex-gap-semi-large flex-direction-col">
						<div class="w-100 flex flex-direction-col flex-gap-large">
							<div class="flex flex-gap-regular">
								<div class="w-100 flex flex-direction-col flex-gap-regular">
									<div class="secondary-title-card-detail">Pemesan</div>
									<div class="flex w-100">
										<div class="flex flex-direction-col w-50">
											<div class="caption-card-detail">Nama Lengkapi</div>
											<div class="content-card-detail">Suryadi</div>
										</div>
										<div class="flex flex-direction-col w-50">
											<div class="caption-card-detail">Nomor KTP</div>
											<div class="content-card-detail">1234XXXXXXXXXXXX</div>
										</div>
									</div>
									<div class="flex w-100">
										<div class="flex flex-direction-col w-50">
											<div class="caption-card-detail">Jenis Kelamin</div>
											<div class="content-card-detail">Laki-Laki</div>
										</div>
										<div class="flex flex-direction-col w-50">
											<div class="caption-card-detail">Nomor Telepon</div>
											<div class="content-card-detail">1234XXXXXXXXXXXX</div>
										</div>
									</div>
									<div class="flex w-100">
										<div class="flex flex-direction-col w-50">
											<div class="caption-card-detail">Status Nikah</div>
											<div class="content-card-detail">Sudah Menikah</div>
										</div>
										<div class="flex flex-direction-col w-50">
											<div class="caption-card-detail">Alamat Email</div>
											<div class="content-card-detail">suryadi@gmail.com</div>
										</div>
									</div>
									<div class="flex w-100">
										<div class="flex flex-direction-col w-40">
											<div class="caption-card-detail">Alamat Lengkap</div>
											<div class="content-card-detail">Jalan Sudirman No. 32A, RT. 003, RW.012, Kel. Dago, Kec. Coblong, Kota Bandung, Jawa Barat</div>
										</div>
										<div class="w-10"></div>
										<div class="flex flex-direction-col w-50 flex-gap-regular">
											<div class="flex flex-direction-col">
												<div class="caption-card-detail">Nomor NPWP</div>
												<div class="content-card-detail">XX.XXX.XXX.X-XXX.XXX</div>
											</div>
											<div class="flex flex-direction-col">
												<div class="caption-card-detail">Pekerjaan</div>
												<div class="content-card-detail">Karyawan Swasta</div>
											</div>
											<div class="flex flex-direction-col">
												<div class="caption-card-detail">Koordinat Lokasi Usaha</div>
												<div class="content-card-detail">Jawa Barat</div>
											</div>
										</div>
									</div>
								</div>
							</div>
						</div>
						<div class="card-secondary flex flex-direction-col flex-gap-semi-small">
							<div class="caption-card-detail">Dokumen Pendukung</div>
							<div class="flex">
								<div class="w-50">
									<div class="flex flex-direction-col">
										<div class="caption-card-detail">Fotokopi KTP</div>	
										<a href="#" class="no-decor link-detail">lihat</a>
									</div>
								</div>
								<div class="w-50">
									<div class="flex flex-direction-col">
										<div class="caption-card-detail">Fotokopi KK</div>	
										<a href="#" class="no-decor link-detail">lihat</a>
									</div>
								</div>
							</div>
							<div class="flex">
								<div class="w-50">
									<div class="flex flex-direction-col">
										<div class="caption-card-detail">Fotokopi NPWP</div>	
										<a href="#" class="no-decor link-detail">lihat</a>
									</div>
								</div>
								<div class="w-50">
									<div class="flex flex-direction-col">
										<div class="caption-card-detail">Pas Foto</div>	
										<a href="#" class="no-decor link-detail">lihat</a>
									</div>
								</div>
							</div>
						</div>
					</div>
					<div class="w-50 flex flex-direction-col flex-gap-large">
						<div class="card w-100 flex flex-gap-semi-large flex-direction-col">
							<div class="w-100 flex flex-direction-col flex-gap-large">
								<div class="flex flex-gap-regular">
									<div class="w-100 flex flex-direction-col flex-gap-regular">
										<div class="secondary-title-card-detail">Pasangan</div>
										<div class="flex w-100">
											<div class="flex flex-direction-col w-50">
												<div class="caption-card-detail">Nama Lengkapi</div>
												<div class="content-card-detail">Poniyah</div>
											</div>
											<div class="flex flex-direction-col w-50">
												<div class="caption-card-detail">Nomor KTP</div>
												<div class="content-card-detail">1234XXXXXXXXXXXX</div>
											</div>
										</div>
										<div class="flex w-100">
											<div class="flex flex-direction-col w-50">
												<div class="caption-card-detail">Jenis Kelamin</div>
												<div class="content-card-detail">Perempuan</div>
											</div>
											<div class="flex flex-direction-col w-50">
												<div class="caption-card-detail">Nomor Telepon</div>
												<div class="content-card-detail">1234XXXXXXXXXXXX</div>
											</div>
										</div>
									</div>
								</div>
							</div>
							<div class="card-secondary flex flex-direction-col flex-gap-semi-small">
								<div class="caption-card-detail">Dokumen Pendukung</div>
								<div class="flex">
									<div class="w-50">
										<div class="flex flex-direction-col">
											<div class="caption-card-detail">Fotokopi KTP</div>	
											<a href="#" class="no-decor link-detail">lihat</a>
										</div>
									</div>
									<div class="w-50">
										<div class="flex flex-direction-col">
											<div class="caption-card-detail">Pas Foto</div>	
											<a href="#" class="no-decor link-detail">lihat</a>
										</div>
									</div>
								</div>
							</div>
						</div>
						<div class="card w-100 flex flex-gap-semi-large flex-direction-col h-100 flex-center-horizontal">
							<div class="w-100 flex flex-direction-col flex-gap-large">
								<div class="flex flex-gap-regular">
									<div class="w-100 flex flex-direction-col flex-gap-regular">
										<div class="secondary-title-card-detail">BI Checking</div>
										<div class="flex w-100">
											<div class="flex flex-direction-col w-50">
												<div class="caption-card-detail">Status BI Checking</div>
												<div class="content-card-detail">Ya</div>
											</div>
											<div class="flex flex-direction-col w-50">
												<div class="caption-card-detail">Hasil BI Checking</div>
												<div class="content-card-detail">Kolektibilitas 1</div>
											</div>
										</div>
										<div class="flex w-100">
											<div class="flex flex-direction-col w-50">
												<div class="caption-card-detail">Tanggal Pengajuan</div>
												<div class="content-card-detail">27 April 2018</div>
											</div>
											<div class="flex flex-direction-col w-50">
												<div class="caption-card-detail">Hasil BI Checking Pasangan</div>
												<div class="content-card-detail">Kolektibilitas 1</div>
											</div>
										</div>
										<div class="flex w-100">
											<div class="flex flex-direction-col w-50">
												<div class="caption-card-detail">Tanggal Hasil BI Checking</div>
												<div class="content-card-detail">4 Mei 2018</div>
											</div>
											<div class="flex flex-direction-col w-50">
												<div class="caption-card-detail">Nama Referensi</div>
												<div class="content-card-detail">Dani</div>
											</div>
										</div>
									</div>
								</div>
							</div>
						</div>
					</div>
				</div>
				<div class="flex w-100 flex-gap-large">
					<div class="w-50 padding-item-solo">
						<div class="card flex flex-gap-semi-large flex-direction-col">
							<div class="w-100 flex flex-direction-col flex-gap-large">
								<div class="flex flex-gap-regular">
									<div class="w-100 flex flex-direction-col flex-gap-regular">
										<div class="secondary-title-card-detail">Pembayaran Booking Fee</div>
										<div class="flex w-100">
											<div class="flex flex-direction-col w-50">
												<div class="caption-card-detail">Nominal Booking Fee</div>
												<div class="content-card-detail">Rp. 1.000.000</div>
											</div>
											<div class="flex flex-direction-col w-50">
												<div class="caption-card-detail">Metode Pembayaran</div>
												<div class="content-card-detail">Transfer</div>
											</div>
										</div>
										<div class="flex w-100">
											<div class="flex flex-direction-col w-50">
												<div class="caption-card-detail">Nama Bank</div>
												<div class="content-card-detail">Bank Mandiri</div>
											</div>
											<div class="flex flex-direction-col w-50">
												<div class="caption-card-detail">Nomor Rekening</div>
												<div class="content-card-detail">XXXXXXXXXXXX</div>
											</div>
										</div>
										<div class="flex w-100">
											<div class="flex flex-direction-col w-50">
												<div class="caption-card-detail">Tanggal Pembayaran</div>
												<div class="content-card-detail">19 April 2018</div>
											</div>
										</div>
									</div>
								</div>
							</div>
							<div class="card-secondary flex flex-direction-col flex-gap-semi-small">
								<div class="caption-card-detail">Dokumen Pendukung</div>
								<div class="flex">
									<div class="w-50">
										<div class="flex flex-direction-col">
											<div class="caption-card-detail">Bukti Pembayaran</div>	
											<a href="#" class="no-decor link-detail">lihat</a>
										</div>
									</div>
								</div>
							</div>
						</div>
					</div>
				</div>
				<div class="flex w-100 flex-center-horizontal">
					<button class="btn-transparent flex flex-center-vertical flex-gap-small"><span>Lihat Detail Data Unit</span></button>
					<button class="btn-transparent flex flex-center-vertical flex-gap-small"><span>Lihat Detail Data Pemesan</span></button>
				</div>
			</div>
		</div>
	</div>
</div>