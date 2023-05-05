<script type="text/javascript">
	import Sidebar from '../../../components/sidebar.svelte'
	import Navbar from '../../../components/navbar.svelte'
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
					<div class="title-content">Data Akun</div>
					<div class="flex flex-gap-regular">
						<button class="btn-outline flex flex-center-vertical flex-gap-small"><span>Download Excel</span> <img src="/images/icons/File_Download.svg"></button>
						<a href="/super-admin/nup/tambah-nup" class="no-decor"><button class="btn-fill flex flex-center-vertical flex-gap-small"><img src="/images/icons/Add_Plus.svg"> <span>Buat Akun</span></button></a>
					</div>
				</div>
				<div class="flex flex-direction-col flex-gap-regular">
					<div class="flex flex-direction-col flex-gap-small">
						<div class="flex flex-gap-regular">
							<span class="active-notif-button">Semua</span>
							<span class="unactive-notif-button">Aktif</span>
							<span class="unactive-notif-button">Non-Aktif</span>
							<span class="unactive-notif-button">Pengajuan</span>
						</div>
					</div>
					<div class="flex flex-gap-semi-large w-100">
						<input type="text" placeholder="Cari ID" class="input-col-2 w-15">
						<input type="text" placeholder="Cari Pemegang Akun" class="input-col-2 w-20">
						<select class="select-col-3 w-20">
							<option disabled selected>Pilih Jenis Akun</option>
							<option>Epicentrum Sepatan</option>
							<option>Serpong</option>
						</select>
					</div>
					<div class="scroll-x flex flex-direction-col flex-gap-regular">
						<div class="card-head w-content height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-10 border-separate">
									<div class="text-drop-card">ID</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 border-separate">
									<div class="text-drop-card">Pemegang Akun</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 border-separate">
									<div class="text-drop-card">Jenis Akun</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 border-separate">
									<div class="text-drop-card">Penempatan</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 border-separate">
									<div class="text-drop-card">Email</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 border-separate">
									<div class="text-drop-card">No. HP</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 border-separate">
									<div class="text-drop-card">Tanggal Aktif</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 border-separate">
									<div class="text-drop-card">Status</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 border-non-separate">
									<div class="text-drop-card">Aksi</div>
									<img src="/images/icons/Arrow.svg">
								</div>
							</div>
						</div>
						<a href="/super-admin/akun/detail-akun" class="no-decor">
							<div class="card-head w-content height-fit">
								<div class="flex">
									<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
										<div class="text-drop-card">30001</div>
									</div>
									<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
										<div class="text-drop-card">Suryadi</div>
									</div>
									<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
										<div class="text-drop-card">HO</div>
									</div>
									<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
										<div class="text-drop-card">Head Office</div>
									</div>
									<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
										<div class="text-drop-card">suryadi@gmail.com</div>
									</div>
									<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
										<div class="text-drop-card">0823XXXXXXXX</div>
									</div>
									<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
										<div class="text-drop-card">25 Apr 2018</div>
									</div>
									<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
										<div class="text-approve">Aktif</div>
									</div>
									<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
										<button class="btn-outline flex flex-center-vertical flex-gap-small"><span>Non-Aktifkan</span></button>
									</div>
								</div>
							</div>
						</a>
						<div class="card-head w-content height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<div class="text-drop-card">30001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">Suryadi</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">HO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">Head Office</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">suryadi@gmail.com</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">0823XXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">25 Apr 2018</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-reject">Non-Aktif</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<button class="btn-outline flex flex-center-vertical flex-gap-small"><span>Aktifkan</span></button>
								</div>
							</div>
						</div>
						<div class="card-head w-content height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<div class="text-drop-card">30001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">Suryadi</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">HO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">Head Office</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">suryadi@gmail.com</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">0823XXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">25 Apr 2018</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-pending">Diajukan</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<button class="btn-outline flex flex-center-vertical flex-gap-small"><span>Approve</span></button>
								</div>
							</div>
						</div>
						<div class="card-head w-content height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<div class="text-drop-card">30001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">Suryadi</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">HO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">Head Office</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">suryadi@gmail.com</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">0823XXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">25 Apr 2018</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-reject">Non-Aktif</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<button class="btn-outline flex flex-center-vertical flex-gap-small"><span>Aktifkan</span></button>
								</div>
							</div>
						</div>
						<div class="card-head w-content height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<div class="text-drop-card">30001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">Suryadi</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">HO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">Head Office</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">suryadi@gmail.com</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">0823XXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">25 Apr 2018</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-pending">Diajukan</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<button class="btn-outline flex flex-center-vertical flex-gap-small"><span>Approve</span></button>
								</div>
							</div>
						</div>
						<div class="card-head w-content height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<div class="text-drop-card">30001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">Suryadi</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">HO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">Head Office</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">suryadi@gmail.com</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">0823XXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">25 Apr 2018</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-reject">Non-Aktif</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<button class="btn-outline flex flex-center-vertical flex-gap-small"><span>Aktifkan</span></button>
								</div>
							</div>
						</div>
						<div class="card-head w-content height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<div class="text-drop-card">30001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">Suryadi</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">HO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">Head Office</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">suryadi@gmail.com</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">0823XXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">25 Apr 2018</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-pending">Diajukan</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<button class="btn-outline flex flex-center-vertical flex-gap-small"><span>Approve</span></button>
								</div>
							</div>
						</div>
						<div class="card-head w-content height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<div class="text-drop-card">30001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">Suryadi</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">HO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">Head Office</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">suryadi@gmail.com</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">0823XXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">25 Apr 2018</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-reject">Non-Aktif</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<button class="btn-outline flex flex-center-vertical flex-gap-small"><span>Aktifkan</span></button>
								</div>
							</div>
						</div>
						<div class="card-head w-content height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<div class="text-drop-card">30001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">Suryadi</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">HO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">Head Office</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">suryadi@gmail.com</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">0823XXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">25 Apr 2018</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-pending">Diajukan</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<button class="btn-outline flex flex-center-vertical flex-gap-small"><span>Approve</span></button>
								</div>
							</div>
						</div>
						<div class="card-head w-content height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<div class="text-drop-card">30001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">Suryadi</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">HO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">Head Office</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">suryadi@gmail.com</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">0823XXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">25 Apr 2018</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-reject">Non-Aktif</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<button class="btn-outline flex flex-center-vertical flex-gap-small"><span>Aktifkan</span></button>
								</div>
							</div>
						</div>
						<div class="card-head w-content height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<div class="text-drop-card">30001</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">Suryadi</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">HO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">Head Office</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">suryadi@gmail.com</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">0823XXXXXXXX</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">25 Apr 2018</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-pending">Diajukan</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<button class="btn-outline flex flex-center-vertical flex-gap-small"><span>Approve</span></button>
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
								<div class="text-display-sort">dari <span class="bold-number">28</span> data NUP</div>
							</div>
							<div class="flex flex-gap-regular flex-center-vertical">
								<div class="flex flex-center-vertical flex-center-horizontal border-pagination"><img src="/images/icons/Arrow_Left.svg"></div>
								<div class="flex flex-center-vertical flex-center-horizontal border-pagination"><div class="text-display-sort bold-number">1</div></div>
								<div class="flex flex-center-vertical flex-center-horizontal border-pagination"><img src="/images/icons/Arrow_Right.svg"></div>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</div>