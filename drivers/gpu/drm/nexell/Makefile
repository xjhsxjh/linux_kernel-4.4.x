#
# Makefile for the drm device driver.  This driver provides support for the
# Direct Rendering Infrastructure (DRI) in XFree86 4.1.0 and higher.

ccflags-y := -Iinclude/drm -Idrivers/gpu/drm/nexell

nx_drm-y  := nx_drm_drv.o nx_drm_connector.o nx_drm_encoder.o \
	nx_drm_crtc.o nx_drm_plane.o nx_drm_fb.o nx_drm_gem.o

ifeq ($(CONFIG_DRM_NX_S5PXX18), y)
nx_drm-objs 	+= s5pxx18/s5pxx18_drv.o	\
		s5pxx18/s5pxx18_dev.o		\
		s5pxx18/s5pxx18_soc_mlc.o	\
		s5pxx18/s5pxx18_soc_dpc.o	\
		s5pxx18/s5pxx18_soc_disptop.o	\
		s5pxx18/s5pxx18_soc_disptop_clk.o

nx_drm-$(CONFIG_DRM_NX_RGB) 	+= nx_drm_lcd.o	\
				s5pxx18/s5pxx18_rgb.o
nx_drm-$(CONFIG_DRM_NX_LVDS) 		+= nx_drm_lcd.o	\
				s5pxx18/s5pxx18_soc_lvds.o	\
				s5pxx18/s5pxx18_lvds.o
nx_drm-$(CONFIG_DRM_NX_MIPI_DSI)	+= nx_drm_lcd.o	\
				s5pxx18/s5pxx18_soc_mipi.o	\
				s5pxx18/s5pxx18_mipi.o
nx_drm-$(CONFIG_DRM_NX_HDMI) 	+= nx_drm_hdmi.o	\
				s5pxx18/s5pxx18_hdmi_presets.o	\
				s5pxx18/s5pxx18_hdmi.o
nx_drm-$(CONFIG_DRM_NX_TVOUT_S5P4418) 	+= nx_drm_s5p4418_tv.o	\
				s5pxx18/s5p4418_tv.o
nx_drm-$(CONFIG_DRM_NX_TVOUT_S5P6818) 	+= nx_drm_s5p6818_tv.o	\
				s5pxx18/s5p6818_tv.o
nx_drm-$(CONFIG_DRM_NX_CLUSTER_LCD) 	+= nx_drm_cluster_lcd.o

else ifeq ($(CONFIG_DRM_NX_NXP5XXX), y)
nx_drm-objs 	+= nxp5xxx/nxp5xxx_drv.o

obj-$(CONFIG_DRM_NX_HDMI)	+= nx_drm_hdmi.o \
				nxp5xxx/nxp5xxx_hdmi.o

endif

obj-$(CONFIG_DRM_NX)	+= nx_drm.o

