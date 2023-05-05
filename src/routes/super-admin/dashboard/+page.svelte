<script type="text/javascript">
	import Sidebar from '../../../components/sidebar.svelte'
	import Navbar from '../../../components/navbar.svelte'
	import { onMount } from 'svelte';
	import {fly, scale} from 'svelte/transition'
	let active = 0
	onMount(() => {
		var ctx = document.getElementById("myChart").getContext('2d');
		ctx.canvas.width = 300;
		ctx.canvas.height = 200;
        var myChart = new Chart(ctx, {
            type: 'bar',
            data: {
                labels: ["January", "February", "March", "April", "May", "June"],
                datasets: [{
                    label: 'Penjualan dalam 6 bulan terakhir',
                    data: [12, 19, 15, 7, 12, 5],
                    backgroundColor: [
                        'rgba(255, 99, 132, 0.2)',
                        'rgba(54, 162, 235, 0.2)',
                        'rgba(255, 206, 86, 0.2)',
                        'rgba(75, 192, 192, 0.2)',
                        'rgba(153, 102, 255, 0.2)',
                        'rgba(255, 159, 64, 0.2)'
                    ],
                    borderColor: [
                        'rgba(255,99,132,1)',
                        'rgba(54, 162, 235, 1)',
                        'rgba(255, 206, 86, 1)',
                        'rgba(75, 192, 192, 1)',
                        'rgba(153, 102, 255, 1)',
                        'rgba(255, 159, 64, 1)'
                    ],
                    borderWidth: 1
                }]
            },
            options: {
                scales: {
                    yAxes: [{
                        ticks: {
                            beginAtZero:true
                        }
                    }]
                }
            }
        });
	})
</script>

<div id="after-login-layout">
	<Navbar/>
	<div class="flex">
		<Sidebar statusPointer="Dashboard" pagePointer="admin"/>
		<div class="w-100 content">
			<div class="flex flex-direction-col flex-gap-large" in:fly={{ y: -20, duration: 600 }}>
				<div class="title-content">Dashboard</div>
				<div class="flex flex-direction-col flex-gap-semi-large">
					<div class="sub-title-content">Ringkasan</div>
					<div class="flex flex-gap-large">
						<div class="card flex flex-center-horizontal flex-center-vertical flex-gap-semi-small">
							<div class="box-icon flex flex-center-horizontal flex-center-vertical">
								<img src="/images/icons/Building.svg">
							</div>
							<div class="flex flex-direction-col">
								<div class="title-small-card-dashboard">Total NUP</div>
								<div class="flex flex-center-vertical flex-gap-small">
									<div class="value-small-card-dashboard">1000</div>
									<div class="unit-small-card-dashboard">Unit</div>
								</div>
							</div>
						</div>
						<div class="card flex flex-center-horizontal flex-center-vertical flex-gap-semi-small">
							<div class="box-icon flex flex-center-horizontal flex-center-vertical">
								<img src="/images/icons/Book.svg">
							</div>
							<div class="flex flex-direction-col">
								<div class="title-small-card-dashboard">Total Pemberkasan</div>
								<div class="flex flex-center-vertical flex-gap-small">
									<div class="value-small-card-dashboard">62</div>
									<div class="unit-small-card-dashboard">Pengajuan</div>
								</div>
							</div>
						</div>
						<div class="card flex flex-center-horizontal flex-center-vertical flex-gap-semi-small">
							<div class="box-icon flex flex-center-horizontal flex-center-vertical">
								<img src="/images/icons/Check.svg">
							</div>
							<div class="flex flex-direction-col">
								<div class="title-small-card-dashboard">Pengajuan </div>
								<div class="flex flex-center-vertical flex-gap-small">
									<div class="value-small-card-dashboard">1000</div>
									<div class="unit-small-card-dashboard">Pengajuan</div>
								</div>
							</div>
						</div>
						<div class="card flex flex-center-horizontal flex-center-vertical flex-gap-semi-small">
							<div class="box-icon flex flex-center-horizontal flex-center-vertical">
								<img src="/images/icons/Home.svg">
							</div>
							<div class="flex flex-direction-col">
								<div class="title-small-card-dashboard">Total Griya</div>
								<div class="flex flex-center-vertical flex-gap-small">
									<div class="value-small-card-dashboard">10</div>
									<div class="unit-small-card-dashboard">Griya</div>
								</div>
							</div>
						</div>
						<div class="card flex flex-center-horizontal flex-center-vertical flex-gap-semi-small">
							<div class="box-icon flex flex-center-horizontal flex-center-vertical">
								<img src="/images/icons/Home.svg">
							</div>
							<div class="flex flex-direction-col">
								<div class="title-small-card-dashboard">Total Unit</div>
								<div class="flex flex-center-vertical flex-gap-small">
									<div class="value-small-card-dashboard">75</div>
									<div class="unit-small-card-dashboard">Unit</div>
								</div>
							</div>
						</div>
					</div>
					<div class="flex flex-gap-regular">
						<div class="card w-50">
							<div class="title-card-dashboard">Penjualan Tahun Ini</div>
							<div style="width: 100%;"><canvas id="myChart"></canvas></div>
						</div>
						<div class="flex flex-direction-col flex-gap-semi-large w-50">
							<div class="flex flex-direction-col flex-gap-small">
								<div class="title-card-dashboard">Notifikasi</div>
								<div class="flex flex-gap-regular">
									<span class="{active == 0 ? 'active-notif-button' : 'unactive-notif-button'}" on:click={() => {active = 0}}>Belum Dibaca</span>
									<span class="{active == 1 ? 'active-notif-button' : 'unactive-notif-button'}"on:click={() => {active = 1}}>Sudah Dibaca</span>
								</div>
							</div>
							<div class="scroll-notif">
								{#if active == 0}
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
								{:else}
									<div class="flex flex-direction-col flex-gap-regular" in:fly={{ y: -20, duration: 600 }}>
										<div class="card flex flex-direction-col flex-gap-small w-100">
											<div class="flex flex-between-horizontal">
												<span class="text-notif">Dari HO</span>
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
								{/if}
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
<!-- 					<div class="flex flex-direction-col flex-gap-regular">
						<div class="card w-100 height-fit">
							<div class="flex flex-direction-col flex-gap-large">
								<div class="flex flex-between-horizontal flex-center-vertical">
									<div class="title-card-dashboard">Approved NUP</div>
									<button class="btn-outline">Lihat Lebih</button>
								</div>
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
					</div> -->
				</div>
			</div>
		</div>
	</div>
</div>