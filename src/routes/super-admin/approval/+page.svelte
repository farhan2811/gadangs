<script type="text/javascript">
	import Sidebar from '../../../components/sidebar.svelte'
	import Navbar from '../../../components/navbar.svelte'
	import { onMount } from 'svelte';
	import {fly, scale} from 'svelte/transition'
	
</script>

<div id="after-login-layout">
	<Navbar/>
	<div class="flex">
		<Sidebar statusPointer="Approval" pagePointer="admin"/>
		<div class="flex flex-direction-col flex-gap-large w-100 content">
			<div class="flex flex-direction-col flex-gap-semi-large w-90">
				<div class="flex flex-direction-col flex-gap-small">
					<div class="title-notif-approval">Approval</div>
				</div>
				<div class="flex flex-direction-col flex-gap-regular">
					<div class="card-head height-fit">
						<div class="flex">
							<div class="flex flex-gap-small flex-center-vertical w-20 border-separate">
								<div class="text-drop-card">Tipe Approval</div>
								<img src="/images/icons/Arrow.svg">
							</div>
							<div class="flex flex-gap-small flex-center-vertical w-20 border-separate">
								<div class="text-drop-card">Tanggal Masuk</div>
								<img src="/images/icons/Arrow.svg">
							</div>
							<div class="flex flex-gap-small flex-center-vertical w-10 border-separate">
								<div class="text-drop-card">Oleh</div>
								<img src="/images/icons/Arrow.svg">
							</div>
							<div class="flex flex-gap-small flex-center-vertical w-20 border-separate">
								<div class="text-drop-card">Lampiran Surat</div>
								<img src="/images/icons/Arrow.svg">
							</div>
							<div class="flex flex-gap-small flex-center-vertical w-15 border-separate">
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
						<div class="card-head height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">SP3UR</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">4 Jan 2023</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<div class="text-drop-card">HO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">Ya</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15 no-border-table">
									<div class="text-approve">Approved</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
									<a href="#" class="link-detail-akun no-decor">Approve</a>
								</div>
							</div>
						</div>
					</a>
					<div class="card-head height-fit">
						<div class="flex">
							<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
								<div class="text-drop-card">SP3UR</div>
							</div>
							<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
								<div class="text-drop-card">4 Jan 2023</div>
							</div>
							<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
								<div class="text-drop-card">HO</div>
							</div>
							<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
								<div class="text-drop-card">Ya</div>
							</div>
							<div class="flex flex-gap-small flex-center-vertical w-15 no-border-table">
								<div class="text-approve">Approved</div>
							</div>
							<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
								<a href="#" class="link-detail-akun no-decor">Approve</a>
							</div>
						</div>
					</div>
					<div class="card-head height-fit">
						<div class="flex">
							<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
								<div class="text-drop-card">SP3UR</div>
							</div>
							<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
								<div class="text-drop-card">4 Jan 2023</div>
							</div>
							<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
								<div class="text-drop-card">HO</div>
							</div>
							<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
								<div class="text-drop-card">Ya</div>
							</div>
							<div class="flex flex-gap-small flex-center-vertical w-15 no-border-table">
								<div class="text-approve">Approved</div>
							</div>
							<div class="flex flex-gap-small flex-center-vertical w-10 no-border-table">
								<a href="#" class="link-detail-akun no-decor">Approve</a>
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
							<div class="text-display-sort">dari <span class="bold-number">3</span> Notifikasi</div>
						</div>
						<div class="flex flex-gap-regular flex-center-vertical">
							<div class="flex flex-center-vertical flex-center-horizontal border-pagination"><img src="/images/icons/Arrow_Left.svg"></div>
							<div class="flex flex-center-vertical flex-center-horizontal border-pagination"><div class="text-display-sort bold-number">1</div></div>
							<div class="flex flex-center-vertical flex-center-horizontal border-pagination"><img src="/images/icons/Arrow_Right.svg"></div>
						</div>
					</div>
				</div>
			</div>
			<div class="flex flex-direction-col flex-gap-semi-large w-90">
				<div class="flex flex-direction-col flex-gap-small">
					<div class="title-notif-approval">Notifikasi Approval</div>
					<div class="flex flex-direction-col flex-gap-small">
						<div class="flex flex-gap-regular">
							<span class="active-notif-button">Belum Dibaca</span>
							<span class="unactive-notif-button">Sudah Dibaca</span>
						</div>
					</div>
				</div>
				<div class="flex flex-direction-col flex-gap-regular" in:fly={{ y: -20, duration: 600 }}>
					<div class="card flex flex-direction-col flex-gap-small w-100">
						<div class="flex flex-between-horizontal">
							<span class="text-notif">Dari Sistem</span>
							<span class="text-notif">08 : 00</span>
						</div>
							<span class="text-notif-bold">NUP telah di approve oleh HO</span>
							<div class="text-notif-desc">NUP 70081 telah di approve oleh HO. Silahkan cek kembali data NUP tersebut sebelum melakukan Approval. </div>
					</div>
					<div class="card flex flex-direction-col flex-gap-small w-100">
						<div class="flex flex-between-horizontal">
							<span class="text-notif">Dari Sistem</span>
							<span class="text-notif">08 : 00</span>
						</div>
							<span class="text-notif-bold">NUP telah di approve oleh HO</span>
							<div class="text-notif-desc">NUP 70081 telah di approve oleh HO. Silahkan cek kembali data NUP tersebut sebelum melakukan Approval. </div>
					</div>
					<div class="card flex flex-direction-col flex-gap-small w-100">
						<div class="flex flex-between-horizontal">
							<span class="text-notif">Dari Sistem</span>
							<span class="text-notif">08 : 00</span>
						</div>
							<span class="text-notif-bold">NUP telah di approve oleh HO</span>
							<div class="text-notif-desc">NUP 70081 telah di approve oleh HO. Silahkan cek kembali data NUP tersebut sebelum melakukan Approval. </div>
					</div>
					<div class="card flex flex-direction-col flex-gap-small w-100">
						<div class="flex flex-between-horizontal">
							<span class="text-notif">Dari Sistem</span>
							<span class="text-notif">08 : 00</span>
						</div>
							<span class="text-notif-bold">NUP telah di approve oleh HO</span>
							<div class="text-notif-desc">NUP 70081 telah di approve oleh HO. Silahkan cek kembali data NUP tersebut sebelum melakukan Approval. </div>
					</div>
					<div class="card flex flex-direction-col flex-gap-small w-100">
						<div class="flex flex-between-horizontal">
							<span class="text-notif">Dari Sistem</span>
							<span class="text-notif">08 : 00</span>
						</div>
							<span class="text-notif-bold">NUP telah di approve oleh HO</span>
							<div class="text-notif-desc">NUP 70081 telah di approve oleh HO. Silahkan cek kembali data NUP tersebut sebelum melakukan Approval. </div>
					</div>
					<div class="card flex flex-direction-col flex-gap-small w-100">
						<div class="flex flex-between-horizontal">
							<span class="text-notif">Dari Sistem</span>
							<span class="text-notif">08 : 00</span>
						</div>
							<span class="text-notif-bold">NUP telah di approve oleh HO</span>
							<div class="text-notif-desc">NUP 70081 telah di approve oleh HO. Silahkan cek kembali data NUP tersebut sebelum melakukan Approval. </div>
					</div>
				</div>
				<div class="card w-100 height-fit">
					<div class="flex flex-between-horizontal">
						<div class="flex flex-gap-regular flex-center-vertical">
							<div class="text-display-sort">Menampilkan</div>
							<select class="select-sort">
								<option>10</option>
							</select>
							<div class="text-display-sort">dari <span class="bold-number">3</span> Notifikasi</div>
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