<script type="text/javascript">
	import Sidebar from '../../../../components/sidebar.svelte'
	import Navbar from '../../../../components/navbar.svelte'
	import { onMount } from 'svelte';
	import {fly, scale} from 'svelte/transition'
	
</script>

<div id="after-login-layout">
	<Navbar/>
	<div class="flex">
		<Sidebar statusPointer="Akun" pagePointer="admin"/>
		<div class="w-80 content">
			<div class="flex flex-direction-col flex-gap-large" in:fly={{ y: -20, duration: 600 }}>
				<div class="flex flex-between-horizontal flex-center-vertical w-100">
					<div class="flex  flex-direction-col flex-between-horizontal flex-gap-semi-small w-50">
						<div class="title-content">Detail Akun</div>
						<div class="flex flex-gap-regular flex-center-vertical">
							<div class="text-breadcrumb">Akun</div>
							<img src="/images/icons/Arrow_Right.svg">
							<div class="text-breadcrumb-active">Detail</div>
						</div>
					</div>
					<div class="flex flex-gap-regular">
						<a href="/super-admin/kompilasi-perumahan/edit-kompilasi-perumahan" class="no-decor"><button class="btn-fill-warning flex flex-center-vertical flex-gap-small"><img src="/images/icons/Edit_White.svg"> <span>Edit</span></button></a>
						<a href="/super-admin/nup/detail-nup" class="no-decor"><button class="btn-fill-danger flex flex-center-vertical flex-gap-small"> <span>Non-Aktifkan</span></button></a>
					</div>
				</div>
				<div class="flex flex-gap-large w-100">
					<div class="card w-30 flex flex-direction-col flex-gap-regular">
						<img src="/images/avatar.svg" class="w-100 img-detail-akun">
						<div class="label-success flex flex-center-horizontal flex-gap-small w-100">
							<span>Lead Marketing</span>
							<img src="/images/icons/Check_White.svg">
						</div>
						<div class="kode-akun text-center">Kode: 8000001</div>
					</div>
					<div class="card w-70 flex flex-direction-col flex-gap-large">
						<div class="flex flex-direction-col ">
							<div class="flex flex-between-horizontal flex-center-vertical">
								<div class="w-100 flex flex-direction-col flex-gap-semi-large">
									<div class="main-title-card-detail">Informasi Personal</div>
									<div class="flex w-100">
										<div class="flex flex-direction-col w-50">
											<div class="caption-card-detail">Nama Lengkap</div>
											<div class="content-card-detail">Zaenal Muhtarom</div>
										</div>
										<div class="flex flex-direction-col w-50">
											<div class="caption-card-detail">Nomor KTP</div>
											<div class="content-card-detail">1234XXXXXXXXXXXX</div>
										</div>
									</div>
									<div class="flex w-100">
										<div class="flex flex-direction-col w-50">
											<div class="caption-card-detail">Alamat Email</div>
											<div class="content-card-detail">1234XXXXXXXXXXXX</div>
										</div>
										<div class="flex flex-direction-col w-50">
											<div class="caption-card-detail">Nomor HP</div>
											<div class="content-card-detail">1234XXXXXXXXXXXX</div>
										</div>
									</div>
									<div class="flex w-100">
										<div class="flex flex-direction-col w-100">
											<div class="caption-card-detail">Alamat Lengkap</div>
											<div class="content-card-detail">PERUM BSR BLOK F 12 NO. 3 RT 005/004 KEL. RAHARJA KEC. TANJUNGSARI, KAB. SUMEDANG</div>
										</div>
									</div>
									<div class="flex w-100">
										<div class="flex flex-direction-col w-50">
											<div class="caption-card-detail">Penempatan</div>
											<div class="content-card-detail">Griya</div>
										</div>
										<div class="flex flex-direction-col w-50">
											<div class="caption-card-detail">Griya</div>
											<div class="content-card-detail">Bukit Esma Cicalengka (BEC)</div>
										</div>
									</div>
								</div>
							</div>
						</div>
					</div>
				</div>
				<div class="flex flex-gap-large w-100">
					<div class="card w-30 flex flex-direction-col flex-gap-semi-large">
						<div class="main-title-card-detail">Informasi Bank</div>
						<div class="flex w-100">
							<div class="flex flex-direction-col w-100">
								<div class="caption-card-detail">Nama Bank</div>
								<div class="content-card-detail">Mandiri</div>
							</div>
						</div>
						<div class="flex w-100">
							<div class="flex flex-direction-col w-100">
								<div class="caption-card-detail">No. Rekening</div>
								<div class="content-card-detail">131-XX-XXXXXXX-X</div>
							</div>
						</div>
						<div class="flex w-100">
							<div class="flex flex-direction-col w-100">
								<div class="caption-card-detail">Nama di Rekening Bank</div>
								<div class="content-card-detail">ZAENAL MUHTAROM</div>
							</div>
						</div>
						<div class="flex w-100">
							<div class="flex flex-direction-col w-100">
								<div class="caption-card-detail">Cabang Bank</div>
								<div class="content-card-detail">Bandung Rancaekek</div>
							</div>
						</div>
					</div>
					<div class="card w-70 flex flex-direction-col flex-gap-large">
						<div class="flex flex-direction-col ">
							<div class="flex flex-between-horizontal flex-center-vertical">
								<div class="w-100 flex flex-direction-col flex-gap-semi-large">
									<div class="main-title-card-detail">Berkas</div>
									<div class="flex w-100">
										<div class="flex flex-direction-col w-50">
											<div class="caption-card-detail">Pas Foto 3x4</div>	
											<div class="flex flex-center-vertical flex-gap-semi-small">
												<a href="#" class="no-decor link-detail-akun">Lihat Berkas</a>
												<img src="/images/icons/External_Link.svg">
											</div>
										</div>
										<div class="flex flex-direction-col w-50">
											<div class="caption-card-detail">NPWP</div>
											<div class="flex flex-center-vertical flex-gap-semi-small">
												<a href="#" class="no-decor link-detail-akun">Lihat Berkas</a>
												<img src="/images/icons/External_Link.svg">
											</div>
										</div>
									</div>
									<div class="flex w-100">
										<div class="flex flex-direction-col w-50">
											<div class="caption-card-detail">KTP</div>
											<div class="flex flex-center-vertical flex-gap-semi-small">
												<a href="#" class="no-decor link-detail-akun">Lihat Berkas</a>
												<img src="/images/icons/External_Link.svg">
											</div>
										</div>
										<div class="flex flex-direction-col w-50">
											<div class="caption-card-detail">Surat Perjanjian Kerja</div>
											<div class="flex flex-center-vertical flex-gap-semi-small">
												<a href="#" class="no-decor link-detail-akun">Lihat Berkas</a>
												<img src="/images/icons/External_Link.svg">
											</div>
										</div>
									</div>
									<div class="flex w-100">
										<div class="flex flex-direction-col w-100">
											<div class="caption-card-detail">Buku Rekening (Halaman Depan)</div>
											<div class="flex flex-center-vertical flex-gap-semi-small">
												<a href="#" class="no-decor link-detail-akun">Lihat Berkas</a>
												<img src="/images/icons/External_Link.svg">
											</div>
										</div>
									</div>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</div>