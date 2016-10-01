bin_PROGRAMS = deepin-terminal

VALAFLAGS = \
            --pkg=gtk+-3.0 \
            --pkg=vte-2.91 \
            --pkg=gee-0.8 \
            --pkg=json-glib-1.0 \
            --pkg=gio-2.0 \
            --pkg=libwnck-3.0 \
            --pkg=posix \
            --pkg=gdk-x11-3.0 \
            --pkg=xcb \
            --pkg=libsecret-1 \
            --pkg=fontconfig \
            --vapidir=./vapi

AM_CFLAGS = -w -DGETTEXT_PACKAGE="deepin-terminal" \
            -DWNCK_I_KNOW_THIS_IS_UNSTABLE \
            $(DEEPIN_TERMINAL_CFLAGS)

AM_LDFLAGS = -lm \
             $(DEEPIN_TERMINAL_LDFLAGS) \
             -Wl,--as-needed

deepin_terminal_SOURCES = lib/animation.vala \
                          lib/config.vala \
                          lib/constant.vala \
                          lib/draw.vala \
                          lib/font.c \
                          lib/keymap.vala \
                          lib/menu.vala \
                          lib/utils.vala \
                          lib/xutils.vala \
                          project_path.c \
                          widget/about_dialog.vala \
                          widget/about_widget.vala \
                          widget/add_server_button.vala \
                          widget/appbar.vala \
                          widget/check_button.vala \
                          widget/config_window.vala \
                          widget/confirm_dialog.vala \
                          widget/cursor_toggle_button.vala \
                          widget/dialog.vala \
                          widget/dialog_button.vala \
                          widget/image_button.vala \
                          widget/password_button.vala \
                          widget/preference.vala \
                          widget/preference_slidebar.vala \
                          widget/progressbar.vala \
                          widget/quake_window.vala \
                          widget/remote_panel.vala \
                          widget/remote_server_dialog.vala \
                          widget/search_panel.vala \
                          widget/search_entry.vala \
                          widget/server_button.vala \
                          widget/server_group_button.vala \
                          widget/switcher.vala \
                          widget/tabbar.vala \
                          widget/terminal.vala \
                          widget/text_button.vala \
                          widget/theme_button.vala \
                          widget/theme_panel.vala \
                          widget/titlebar.vala \
                          widget/window.vala \
                          widget/window_event_area.vala \
                          widget/workspace.vala \
                          widget/workspace_manager.vala \
                          main.vala

hicolordir = $(datadir)/icons/hicolor
png32dir = $(hicolordir)/32x32/apps
png48dir = $(hicolordir)/48x48/apps
png96dir = $(hicolordir)/96x96/apps
png128dir = $(hicolordir)/128x128/apps
svgdir = $(hicolordir)/scalable/apps

png32_DATA = hicolor/32x32/deepin-terminal.png
png48_DATA = hicolor/48x48/deepin-terminal.png
png96_DATA = hicolor/96x96/deepin-terminal.png
png128_DATA = hicolor/128x128/deepin-terminal.png
svg_DATA = hicolor/deepin-terminal.svg

desktopdir = $(datadir)/applications
desktop_DATA = deepin-terminal.desktop

deepinterminaldir = $(datadir)/deepin-terminal
deepinterminal_DATA = style.css ssh_login.sh

dmandir = $(datadir)/dman
deepinterminaldmandir = $(dmandir)/deepin-terminal
deepinterminaldmanzhcndir = $(deepinterminaldmandir)/en_US
deepinterminaldmanenusdir = $(deepinterminaldmandir)/zh_CN
deepinterminaldmanenus_DATA = manual/en_US/index.md
deepinterminaldmanzhcn_DATA = manual/zh_CN/index.md

localedir = $(datadir)/locale
zhcntranslationdir = $(localedir)/zh_CN/LC_MESSAGES
#zhcntranslation_DATA = po/zh_CN/LC_MESSAGES/deepin-terminal.mo

install-data-local:
	msgfmt --output po/zh_CN/LC_MESSAGES/deepin-terminal.mo po/zh_CN/LC_MESSAGES/deepin-terminal.po
	@$(NORMAL_INSTALL)
	$(MKDIR_P) $(DESTDIR)$(deepinterminaldir)/image
	$(INSTALL_DATA) image/* $(DESTDIR)$(deepinterminaldir)/image
	$(MKDIR_P) $(DESTDIR)$(deepinterminaldir)/theme
	$(INSTALL_DATA) theme/* $(DESTDIR)$(deepinterminaldir)/theme
	$(MKDIR_P) $(DESTDIR)$(deepinterminaldmandir)/common
	$(INSTALL_DATA) manual/common/* $(DESTDIR)$(deepinterminaldmandir)/common
	$(MKDIR_P) $(DESTDIR)$(deepinterminaldmandir)/zh_CN/icon
	$(INSTALL_DATA) manual/zh_CN/icon/* $(DESTDIR)$(deepinterminaldmandir)/zh_CN/icon
	$(MKDIR_P) $(DESTDIR)$(deepinterminaldmandir)/zh_CN/png
	$(INSTALL_DATA) manual/zh_CN/png/* $(DESTDIR)$(deepinterminaldmandir)/zh_CN/png
	$(MKDIR_P) $(DESTDIR)$(deepinterminaldmandir)/en_US/icon
	$(INSTALL_DATA) manual/en_US/icon/* $(DESTDIR)$(deepinterminaldmandir)/en_US/icon
	$(MKDIR_P) $(DESTDIR)$(deepinterminaldmandir)/en_US/png
	$(INSTALL_DATA) manual/en_US/png/* $(DESTDIR)$(deepinterminaldmandir)/en_US/png
	$(MKDIR_P) $(DESTDIR)/$(zhcntranslationdir)
	$(INSTALL_DATA) po/zh_CN/LC_MESSAGES/*.mo $(DESTDIR)$(zhcntranslationdir)

uninstall-local:
	@$(NORMAL_UNINSTALL)
	rm -rf $(DESTDIR)$(deepinterminaldir)
	rm -rf $(DESTDIR)$(deepinterminaldmandir)
	rm -rf $(DESTDIR)$(zhcntranslationdir)
