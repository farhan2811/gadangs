<script type="text/javascript">
	import {fly, scale} from 'svelte/transition'

	let settings_drop = 0;

	export let statusPointer;
	export let pagePointer;
</script>
{#if pagePointer == "ams"}
	<div class="sidebar w-20">
		<div class="h-100 flex flex-direction-col flex-between-horizontal">
			<div class="flex flex-direction-col flex-gap-regular">
				<div class="flex flex-gap-semi-small sidebar-content">
					<div class="flex flex-gap-small w-80">
						<img src="/images/avatar.png" class="polished-img">
						<div class="flex flex-direction-col flex-center-horizontal">
							<div class="welcome-sidebar">
								Selamat Datang
							</div>
							<div class="name-sidebar">
								Jane Doe
							</div>
						</div>
					</div>
					<div class="flex flex-end-horizontal w-10">
						<i class="fa-solid fa-angle-up position-angle"></i>
					</div>
				</div>
				<div class="flex flex-direction-col flex-gap-small">
					<div class="flex flex-direction-col">
						<div class="flex flex-gap-semi-small flex-center-vertical sidebar-content pointer" on:click={() => {
								if (settings_drop == 0) {
									settings_drop = 1
								} else {
									settings_drop = 0
								}
							}}>
							<div class="flex flex-gap-semi-small flex-center-vertical w-80">
								<img src="/images/icons/Settings.png" class="icon-sidebar">
								<span class="text-sidebar">Pengaturan</span>
							</div>
							<div class="flex flex-end-horizontal w-10">
								<i class="fa-solid fa-angle-up position-angle"></i>
							</div>
						</div>
						{#if settings_drop == 1}
							<a href="" class="no-decor">
								<div class="flex flex-gap-semi-small sidebar-content" in:fly={{ y: -20, duration: 600 }}>
									<div class="flex flex-gap-semi-small flex-center-vertical w-90">
										<div class="icon-sidebar"></div>
										<span class="text-sidebar">Profile</span>
									</div>
								</div>
							</a>
							<a href="" class="no-decor">
								<div class="flex flex-gap-semi-small sidebar-content" in:fly={{ y: -20, duration: 600 }}>
									<div class="flex flex-gap-semi-small flex-center-vertical w-90">
										<div class="icon-sidebar"></div>
										<span class="text-sidebar">Akun</span>
									</div>
								</div>
							</a>
							<div class="flex flex-gap-semi-small sidebar-content flex-center-vertical" in:fly={{ y: -20, duration: 600 }}>
								<div class="flex flex-gap-semi-small flex-center-vertical w-90">
									<img src="/images/icons/Log_Out.png" class="icon-sidebar">
									<span class="text-sidebar">Keluar</span>
								</div>
							</div>
						{/if}
					</div>
					{#if settings_drop == 1}
						<div class="flex flex-center-horizontal w-100" in:fly={{ y: -20, duration: 600 }}>
							<div class="line-dropdown"></div>
						</div>
					{/if}
					{#if statusPointer == "Dashboard"}
						<div class="flex flex-direction-col flex-gap-semi-large active-sidebar">
							<a href="/admin-marketing-support/dashboard" class="no-decor">
								<div class="flex flex-direction-col flex-gap-regular sidebar-content">
									<div class="flex flex-gap-semi-small flex-center-vertical">
										<div class="flex flex-gap-semi-small flex-center-vertical">
											<img src="/images/icons/Dashboard_Active.png" class="icon-sidebar">
											<span class="text-sidebar-active">Dashboard</span>
										</div>
									</div>
								</div>
							</a>
						</div>
					{:else}
						<div class="flex flex-direction-col flex-gap-semi-large">
							<a href="/admin-marketing-support/dashboard" class="no-decor">
								<div class="flex flex-direction-col flex-gap-regular sidebar-content">
									<div class="flex flex-gap-semi-small flex-center-vertical">
										<div class="flex flex-gap-semi-small flex-center-vertical">
											<img src="/images/icons/Dashboard.png" class="icon-sidebar">
											<span class="text-sidebar">Dashboard</span>
										</div>
									</div>
								</div>
							</a>
						</div>
					{/if}
					{#if statusPointer == "Nup"}
						<div class="flex flex-direction-col flex-gap-semi-large active-sidebar">
							<a href="/admin-marketing-support/nup" class="no-decor">
								<div class="flex flex-direction-col flex-gap-regular sidebar-content">
									<div class="flex flex-gap-semi-small flex-center-vertical">
										<div class="flex flex-gap-semi-small flex-center-vertical">
											<img src="/images/icons/Book_Active.svg" class="icon-sidebar">
											<span class="text-sidebar-active">NUP</span>
										</div>
									</div>
								</div>
							</a>
						</div>
					{:else}
						<div class="flex flex-direction-col flex-gap-semi-large">
							<a href="/admin-marketing-support/nup" class="no-decor">
								<div class="flex flex-direction-col flex-gap-regular sidebar-content">
									<div class="flex flex-gap-semi-small flex-center-vertical">
										<div class="flex flex-gap-semi-small flex-center-vertical">
											<img src="/images/icons/Book.png" class="icon-sidebar">
											<span class="text-sidebar">NUP</span>
										</div>
									</div>
								</div>
							</a>
						</div>
					{/if}
					<div class="flex flex-direction-col flex-gap-semi-large">
						<a href="" class="no-decor">
							<div class="flex flex-direction-col flex-gap-regular sidebar-content">
								<div class="flex flex-gap-semi-small flex-center-vertical">
									<div class="flex flex-gap-semi-small flex-center-vertical">
										<img src="/images/icons/Notebook.svg" class="icon-sidebar">
										<span class="text-sidebar">SKPUR</span>
									</div>
								</div>
							</div>
						</a>
					</div>
					<div class="flex flex-direction-col flex-gap-semi-large">
						<a href="" class="no-decor">
							<div class="flex flex-direction-col flex-gap-regular sidebar-content">
								<div class="flex flex-gap-semi-small flex-center-vertical">
									<div class="flex flex-gap-semi-small flex-center-vertical">
										<img src="/images/icons/Handshake.png" class="icon-sidebar">
										<span class="text-sidebar">Pengajuan Hutang</span>
									</div>
								</div>
							</div>
						</a>
					</div>
					<div class="flex flex-direction-col flex-gap-semi-large">
						<a href="" class="no-decor">
							<div class="flex flex-direction-col flex-gap-regular sidebar-content">
								<div class="flex flex-gap-semi-small flex-center-vertical">
									<div class="flex flex-gap-semi-small flex-center-vertical">
										<img src="/images/icons/List_Checklist.png" class="icon-sidebar">
										<span class="text-sidebar">Data Kredit</span>
									</div>
								</div>
							</div>
						</a>
					</div>
					<div class="flex flex-direction-col flex-gap-semi-large">
						<a href="" class="no-decor">
							<div class="flex flex-direction-col flex-gap-regular sidebar-content">
								<div class="flex flex-gap-semi-small flex-center-vertical">
									<div class="flex flex-gap-semi-small flex-center-vertical">
										<img src="/images/icons/House_03.svg" class="icon-sidebar">
										<span class="text-sidebar">Data Unit</span>
									</div>
								</div>
							</div>
						</a>
					</div>
				</div>
			</div>
			<div class="footer-sidebar">
				<div class="footer-text">AMS - Griya Panorama Cimanggung</div>
			</div>
		</div>
	</div>	
{:else if pagePointer == "admin"}
	<div class="sidebar w-20">
		<div class="h-100 flex flex-direction-col flex-between-horizontal">
			<div class="flex flex-direction-col flex-gap-regular">
				<div class="flex flex-gap-semi-small sidebar-content">
					<div class="flex flex-gap-small w-80">
						<img src="/images/avatar.png" class="polished-img">
						<div class="flex flex-direction-col flex-center-horizontal">
							<div class="welcome-sidebar">
								Selamat Datang
							</div>
							<div class="name-sidebar">
								Jane Doe
							</div>
						</div>
					</div>
					<div class="flex flex-end-horizontal w-10">
						<i class="fa-solid fa-angle-up position-angle"></i>
					</div>
				</div>
				<div class="flex flex-direction-col flex-gap-small">
					{#if statusPointer == "Dashboard"}
						<div class="flex flex-direction-col flex-gap-semi-large active-sidebar">
							<a href="/super-admin/dashboard" class="no-decor">
								<div class="flex flex-direction-col flex-gap-regular sidebar-content">
									<div class="flex flex-gap-semi-small flex-center-vertical">
										<div class="flex flex-gap-semi-small flex-center-vertical">
											<img src="/images/icons/Dashboard_Active.png" class="icon-sidebar">
											<span class="text-sidebar-active">Dashboard</span>
										</div>
									</div>
								</div>
							</a>
						</div>
					{:else}
						<div class="flex flex-direction-col flex-gap-semi-large">
							<a href="/super-admin/dashboard" class="no-decor">
								<div class="flex flex-direction-col flex-gap-regular sidebar-content">
									<div class="flex flex-gap-semi-small flex-center-vertical">
										<div class="flex flex-gap-semi-small flex-center-vertical">
											<img src="/images/icons/Dashboard.png" class="icon-sidebar">
											<span class="text-sidebar">Dashboard</span>
										</div>
									</div>
								</div>
							</a>
						</div>
					{/if}
					{#if statusPointer == "Kompilasi"}
					<div class="flex flex-direction-col flex-gap-semi-large active-sidebar">
						<a href="/super-admin/kompilasi-perumahan" class="no-decor">
							<div class="flex flex-direction-col flex-gap-regular sidebar-content">
								<div class="flex flex-gap-semi-small flex-center-vertical">
									<div class="flex flex-gap-semi-small flex-center-vertical">
										<img src="/images/icons/House_Active_03.svg" class="icon-sidebar">
										<span class="text-sidebar-active">Data Kompilasi Perumahan</span>
									</div>
								</div>
							</div>
						</a>
					</div>
					{:else}
					<div class="flex flex-direction-col flex-gap-semi-large">
						<a href="/super-admin/kompilasi-perumahan" class="no-decor">
							<div class="flex flex-direction-col flex-gap-regular sidebar-content">
								<div class="flex flex-gap-semi-small flex-center-vertical">
									<div class="flex flex-gap-semi-small flex-center-vertical">
										<img src="/images/icons/House_03.svg" class="icon-sidebar">
										<span class="text-sidebar">Data Kompilasi Perumahan</span>
									</div>
								</div>
							</div>
						</a>
					</div>
					{/if}
					{#if statusPointer == "Laporan"}
					<div class="flex flex-direction-col flex-gap-semi-large active-sidebar">
						<a href="/super-admin/laporan" class="no-decor">
							<div class="flex flex-direction-col flex-gap-regular sidebar-content">
								<div class="flex flex-gap-semi-small flex-center-vertical">
									<div class="flex flex-gap-semi-small flex-center-vertical">
										<img src="/images/icons/Calendar_Check_Active.svg" class="icon-sidebar">
										<span class="text-sidebar-active">Laporan Mingguan</span>
									</div>
								</div>
							</div>
						</a>
					</div>
					{:else}
					<div class="flex flex-direction-col flex-gap-semi-large">
						<a href="/super-admin/laporan" class="no-decor">
							<div class="flex flex-direction-col flex-gap-regular sidebar-content">
								<div class="flex flex-gap-semi-small flex-center-vertical">
									<div class="flex flex-gap-semi-small flex-center-vertical">
										<img src="/images/icons/Calendar_Check.svg" class="icon-sidebar">
										<span class="text-sidebar">Laporan Mingguan</span>
									</div>
								</div>
							</div>
						</a>
					</div>
					{/if}
					{#if statusPointer == "Rekap"}
					<div class="flex flex-direction-col flex-gap-semi-large active-sidebar">
						<a href="/super-admin/rekap-data" class="no-decor">
							<div class="flex flex-direction-col flex-gap-regular sidebar-content">
								<div class="flex flex-gap-semi-small flex-center-vertical">
									<div class="flex flex-gap-semi-small flex-center-vertical">
										<img src="/images/icons/List_Checklist_Active.svg" class="icon-sidebar">
										<span class="text-sidebar-active">Rekap Data</span>
									</div>
								</div>
							</div>
						</a>
					</div>
					{:else}
					<div class="flex flex-direction-col flex-gap-semi-large">
						<a href="/super-admin/rekap-data" class="no-decor">
							<div class="flex flex-direction-col flex-gap-regular sidebar-content">
								<div class="flex flex-gap-semi-small flex-center-vertical">
									<div class="flex flex-gap-semi-small flex-center-vertical">
										<img src="/images/icons/List_Checklist.svg" class="icon-sidebar">
										<span class="text-sidebar">Rekap Data</span>
									</div>
								</div>
							</div>
						</a>
					</div>
					{/if}
					{#if statusPointer == "KelolaPerum"}
					<div class="flex flex-direction-col flex-gap-semi-large active-sidebar">
						<a href="/super-admin/kelola-perum" class="no-decor">
							<div class="flex flex-direction-col flex-gap-regular sidebar-content">
								<div class="flex flex-gap-semi-small flex-center-vertical">
									<div class="flex flex-gap-semi-small flex-center-vertical">
										<img src="/images/icons/Building_04_Active.svg" class="icon-sidebar">
										<span class="text-sidebar-active">Kelola Perum</span>
									</div>
								</div>
							</div>
						</a>
					</div>
					{:else}
					<div class="flex flex-direction-col flex-gap-semi-large">
						<a href="/super-admin/kelola-perum" class="no-decor">
							<div class="flex flex-direction-col flex-gap-regular sidebar-content">
								<div class="flex flex-gap-semi-small flex-center-vertical">
									<div class="flex flex-gap-semi-small flex-center-vertical">
										<img src="/images/icons/Building_04.svg" class="icon-sidebar">
										<span class="text-sidebar">Kelola Perum</span>
									</div>
								</div>
							</div>
						</a>
					</div>
					{/if}
					{#if statusPointer == "Nup"}
						<div class="flex flex-direction-col flex-gap-semi-large active-sidebar">
							<a href="/super-admin/nup" class="no-decor">
								<div class="flex flex-direction-col flex-gap-regular sidebar-content">
									<div class="flex flex-gap-semi-small flex-center-vertical">
										<div class="flex flex-gap-semi-small flex-center-vertical">
											<img src="/images/icons/Book_Active.svg" class="icon-sidebar">
											<span class="text-sidebar-active">NUP</span>
										</div>
									</div>
								</div>
							</a>
						</div>
					{:else}
						<div class="flex flex-direction-col flex-gap-semi-large">
							<a href="/super-admin/nup" class="no-decor">
								<div class="flex flex-direction-col flex-gap-regular sidebar-content">
									<div class="flex flex-gap-semi-small flex-center-vertical">
										<div class="flex flex-gap-semi-small flex-center-vertical">
											<img src="/images/icons/Book.png" class="icon-sidebar">
											<span class="text-sidebar">NUP</span>
										</div>
									</div>
								</div>
							</a>
						</div>
					{/if}
					{#if statusPointer == "Pemberkasan"}
						<div class="flex flex-direction-col flex-gap-semi-large active-sidebar">
							<a href="/super-admin/pemberkasan" class="no-decor">
								<div class="flex flex-direction-col flex-gap-regular sidebar-content">
									<div class="flex flex-gap-semi-small flex-center-vertical">
										<div class="flex flex-gap-semi-small flex-center-vertical">
											<img src="/images/icons/Pemberkasan_Active.svg" class="icon-sidebar">
											<span class="text-sidebar-active">Pemberkasan</span>
										</div>
									</div>
								</div>
							</a>
						</div>
					{:else}
					<div class="flex flex-direction-col flex-gap-semi-large">
							<a href="/super-admin/pemberkasan" class="no-decor">
								<div class="flex flex-direction-col flex-gap-regular sidebar-content">
									<div class="flex flex-gap-semi-small flex-center-vertical">
										<div class="flex flex-gap-semi-small flex-center-vertical">
											<img src="/images/icons/Notebook.svg" class="icon-sidebar">
											<span class="text-sidebar">Pemberkasan</span>
										</div>
									</div>
								</div>
							</a>
						</div>
					{/if}
					<div class="flex flex-direction-col flex-gap-semi-large">
						<a href="/super-admin/nup" class="no-decor">
							<div class="flex flex-direction-col flex-gap-regular sidebar-content">
								<div class="flex flex-gap-semi-small flex-center-vertical">
									<div class="flex flex-gap-semi-small flex-center-vertical">
										<img src="/images/icons/List_Ordered.svg" class="icon-sidebar">
										<span class="text-sidebar">Cicilan</span>
									</div>
								</div>
							</div>
						</a>
					</div>
					{#if statusPointer == "Akun"}
					<div class="flex flex-direction-col flex-gap-semi-large active-sidebar">
						<a href="/super-admin/akun" class="no-decor">
							<div class="flex flex-direction-col flex-gap-regular sidebar-content">
								<div class="flex flex-gap-semi-small flex-center-vertical">
									<div class="flex flex-gap-semi-small flex-center-vertical">
										<img src="/images/icons/User_Card_ID.svg" class="icon-sidebar">
										<span class="text-sidebar-active">Akun</span>
									</div>
								</div>
							</div>
						</a>
					</div>
					{:else}
					<div class="flex flex-direction-col flex-gap-semi-large">
						<a href="/super-admin/akun" class="no-decor">
							<div class="flex flex-direction-col flex-gap-regular sidebar-content">
								<div class="flex flex-gap-semi-small flex-center-vertical">
									<div class="flex flex-gap-semi-small flex-center-vertical">
										<img src="/images/icons/User_Card_ID.svg" class="icon-sidebar">
										<span class="text-sidebar">Akun</span>
									</div>
								</div>
							</div>
						</a>
					</div>
					{/if}
					<div class="flex flex-direction-col flex-gap-semi-large">
						<a href="/super-admin/nup" class="no-decor">
							<div class="flex flex-direction-col flex-gap-regular sidebar-content">
								<div class="flex flex-gap-semi-small flex-center-vertical">
									<div class="flex flex-gap-semi-small flex-center-vertical">
										<img src="/images/icons/Users_Group.svg" class="icon-sidebar">
										<span class="text-sidebar">Marketing</span>
									</div>
								</div>
							</div>
						</a>
					</div>
					{#if statusPointer == "Approval"}
					<div class="flex flex-direction-col flex-gap-semi-large active-sidebar">
						<a href="/super-admin/approval" class="no-decor">
							<div class="flex flex-direction-col flex-gap-regular sidebar-content">
								<div class="flex flex-gap-semi-small flex-center-vertical">
									<div class="flex flex-gap-semi-small flex-center-vertical">
										<img src="/images/icons/Mail_Active.svg" class="icon-sidebar">
										<span class="text-sidebar-active">Approval</span>
									</div>
								</div>
							</div>
						</a>
					</div>
					{:else}
					<div class="flex flex-direction-col flex-gap-semi-large">
						<a href="/super-admin/approval" class="no-decor">
							<div class="flex flex-direction-col flex-gap-regular sidebar-content">
								<div class="flex flex-gap-semi-small flex-center-vertical">
									<div class="flex flex-gap-semi-small flex-center-vertical">
										<img src="/images/icons/Mail.svg" class="icon-sidebar">
										<span class="text-sidebar">Approval</span>
									</div>
								</div>
							</div>
						</a>
					</div>
					{/if}
				</div>
			</div>
			<div class="footer-sidebar">
				<div class="footer-text">Super Admin</div>
			</div>
		</div>
	</div>	
{/if}
