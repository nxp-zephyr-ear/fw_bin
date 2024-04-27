1. FW image names:
	Production FW, for users:
		rw61x_sb_wifi_a1.bin, for CPU1_wifi of redfinch A1 board
		rw61x_sb_ble_a1.bin, for CPU2_ble of redfinch A1 board

		rw61x_sb_wifi_a2.bin, for CPU1_wifi of redfinch A2 board
		rw61x_sb_ble_a2.bin, for CPU2_ble of redfinch A2 board

2. where to get FW image:
	In the directory:  /modules/hal/nxp/mcux/components/fw_bin

3. How to load FW:
	(1) For Wi-Fi and BLE sample application, CPU1 and CPU2 FW are linked together with CPU3 image, don’t need to download CPU1 and CPU2 image separately.
	(2) User needs to make sure FW bin is placed at modules/hal/nxp/mcux/components/fw_bin.
	(3) Default FW bin names are listed in above section 1, don’t change these names, build system depends on these names find FW bin.
	(4) Default selected FW image version is A2, if user wants to use A1 FW, pls refer below to change chip version to link correct FW.
		For example,
		wifi: samples/net/wifi/boards/rd_rw612_bga.conf, define CONFIG_SOC_SERIES_RW6XX_REVISION_A1=y
	(5) Build system will choose to link security FW with CPU3 image based on the configuration above.
	(6) For example, the CMD to write CPU3 image containing CPU1 image to flash in J-link window:
		loadbin C:\xxx\zephyr.bin,0x08000000


