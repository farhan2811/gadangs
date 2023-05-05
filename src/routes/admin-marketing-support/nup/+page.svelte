<script type="text/javascript">
	import Sidebar from '../../../components/sidebar.svelte'
	import Navbar from '../../../components/navbar.svelte'
	import { onMount } from 'svelte';
	import {fly, scale} from 'svelte/transition'
	
</script>

<div id="after-login-layout">
	<Navbar/>
	<div class="flex">
		<Sidebar statusPointer="Nup" pagePointer="ams"/>
		<div class="w-80 content">
			<div class="flex flex-direction-col flex-gap-large" in:fly={{ y: -20, duration: 600 }}>
				<div class="flex flex-between-horizontal w-100">
					<div class="title-content">Daftar NUP</div>
					<div class="flex flex-gap-regular">
						<button class="btn-outline flex flex-center-vertical flex-gap-small"><span>Download Excel</span> <img src="/images/icons/File_Download.svg"></button>
						<a href="/admin-marketing-support/nup/tambah-nup" class="no-decor"><button class="btn-fill flex flex-center-vertical flex-gap-small"><img src="/images/icons/Add_Plus.svg"> <span>Tambah NUP</span></button></a>
					</div>
				</div>
				<div class="flex flex-direction-col flex-gap-regular">
					<div class="flex flex-gap-semi-large w-100">
						<input type="text" placeholder="Cari Kode" class="input-col-2 w-15">
						<input type="text" placeholder="Cari NUP" class="input-col-2 w-15">
						<input type="text" placeholder="Cari Pemesan" class="input-col-2 w-15">
						<input type="text" placeholder="Cari Marketing" class="input-col-2 w-15">
						<input type="date" class="input-col-2 w-15">
						<input type="date" class="input-col-2 w-15">
					</div>
					<div class="card w-100 height-fit">
						<div class="flex flex-gap-regular">
							<div class="flex flex-gap-small flex-center-vertical w-15">
								<div class="text-drop-card">Kode Pengajuan</div>
								<img src="/images/icons/Arrow.svg">
							</div>
							<div class="flex flex-gap-small flex-center-vertical w-10">
								<div class="text-drop-card">NUP</div>
								<img src="/images/icons/Arrow.svg">
							</div>
							<div class="flex flex-gap-small flex-center-vertical w-15">
								<div class="text-drop-card">Pemesan</div>
								<img src="/images/icons/Arrow.svg">
							</div>
							<div class="flex flex-gap-small flex-center-vertical w-15">
								<div class="text-drop-card">Marketing</div>
								<img src="/images/icons/Arrow.svg">
							</div>
							<div class="flex flex-gap-small flex-center-vertical w-15">
								<div class="text-drop-card">Tanggal</div>
								<img src="/images/icons/Arrow.svg">
							</div>
							<div class="flex flex-gap-small flex-center-vertical w-15">
								<div class="text-drop-card">Status</div>
								<img src="/images/icons/Arrow.svg">
							</div>
							<div class="flex flex-gap-small flex-center-vertical w-10">
								<div class="text-drop-card">Aksi</div>
							</div>
						</div>
					</div>
					<div class="card w-100 height-fit">
						<div class="flex flex-direction-col flex-gap-regular">
							<div class="flex flex-gap-regular">
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-drop-card">P003</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10">
									<div class="text-drop-card">-</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-drop-card">Emma D’Arcy</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-drop-card">Dani Risnandar</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-drop-card">14-01-2023</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-approve">Approve</div>
								</div>
								<div class="flex flex-gap-regular flex-center-vertical w-10">
									<img src="/images/icons/Edit.svg">
									<img src="/images/icons/Delete.svg">
								</div>
							</div>
						</div>
					</div>
					<div class="card w-100 height-fit">
						<div class="flex flex-direction-col flex-gap-regular">
							<div class="flex flex-gap-regular">
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-drop-card">P003</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10">
									<div class="text-drop-card">-</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-drop-card">Emma D’Arcy</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-drop-card">Dani Risnandar</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-drop-card">14-01-2023</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-pending">Pending</div>
								</div>
								<div class="flex flex-gap-regular flex-center-vertical w-10">
									<img src="/images/icons/Edit.svg">
									<img src="/images/icons/Delete.svg">
								</div>
							</div>
						</div>
					</div>
					<div class="card w-100 height-fit">
						<div class="flex flex-direction-col flex-gap-regular">
							<div class="flex flex-gap-regular">
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-drop-card">P003</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10">
									<div class="text-drop-card">-</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-drop-card">Emma D’Arcy</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-drop-card">Dani Risnandar</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-drop-card">14-01-2023</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-pending">Pending</div>
								</div>
								<div class="flex flex-gap-regular flex-center-vertical w-10">
									<img src="/images/icons/Edit.svg">
									<img src="/images/icons/Delete.svg">
								</div>
							</div>
						</div>
					</div>
					<div class="card w-100 height-fit">
						<div class="flex flex-direction-col flex-gap-regular">
							<div class="flex flex-gap-regular">
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-drop-card">P003</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10">
									<div class="text-drop-card">-</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-drop-card">Emma D’Arcy</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-drop-card">Dani Risnandar</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-drop-card">14-01-2023</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-pending">Pending</div>
								</div>
								<div class="flex flex-gap-regular flex-center-vertical w-10">
									<img src="/images/icons/Edit.svg">
									<img src="/images/icons/Delete.svg">
								</div>
							</div>
						</div>
					</div>
					<div class="card w-100 height-fit">
						<div class="flex flex-direction-col flex-gap-regular">
							<div class="flex flex-gap-regular">
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-drop-card">P003</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10">
									<div class="text-drop-card">70081</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-drop-card">Emma D’Arcy</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-drop-card">Dani Risnandar</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-drop-card">14-01-2023</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-approve">Approve</div>
								</div>
								<div class="flex flex-gap-regular flex-center-vertical w-10">
									<img src="/images/icons/Edit.svg">
									<img src="/images/icons/Delete.svg">
								</div>
							</div>
						</div>
					</div>
					<div class="card w-100 height-fit">
						<div class="flex flex-direction-col flex-gap-regular">
							<div class="flex flex-gap-regular">
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-drop-card">P003</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10">
									<div class="text-drop-card">70081</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-drop-card">Emma D’Arcy</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-drop-card">Dani Risnandar</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-drop-card">14-01-2023</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15">
									<div class="text-approve">Approve</div>
								</div>
								<div class="flex flex-gap-regular flex-center-vertical w-10">
									<img src="/images/icons/Edit.svg">
									<img src="/images/icons/Delete.svg">
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
								<div class="text-display-sort">dari <span class="bold-number">28</span> NUP</div>
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