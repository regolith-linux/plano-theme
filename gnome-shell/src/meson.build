# destination directory
install_dir = join_paths(gnomeshell_theme_dir, 'gnome-shell')

# generate .css files
theme_sources = files([
  'gnome-shell-high-contrast.scss',
  'gnome-shell.scss',
  'gnome-shell-sass/_colors.scss',
  'gnome-shell-sass/_common.scss',
  'gnome-shell-sass/_drawing.scss',
  'gnome-shell-sass/_high-contrast-colors.scss',
  'gnome-shell-sass/_widgets.scss',
  'gnome-shell-sass/widgets/_a11y.scss',
  'gnome-shell-sass/widgets/_app-grid.scss',
  'gnome-shell-sass/widgets/_base.scss',
  'gnome-shell-sass/widgets/_buttons.scss',
  'gnome-shell-sass/widgets/_calendar.scss',
  'gnome-shell-sass/widgets/_check-box.scss',
  'gnome-shell-sass/widgets/_corner-ripple.scss',
  'gnome-shell-sass/widgets/_dash.scss',
  'gnome-shell-sass/widgets/_dialogs.scss',
  'gnome-shell-sass/widgets/_entries.scss',
  'gnome-shell-sass/widgets/_hotplug.scss',
  'gnome-shell-sass/widgets/_ibus-popup.scss',
  'gnome-shell-sass/widgets/_keyboard.scss',
  'gnome-shell-sass/widgets/_login-dialog.scss',
  'gnome-shell-sass/widgets/_looking-glass.scss',
  'gnome-shell-sass/widgets/_message-list.scss',
  'gnome-shell-sass/widgets/_misc.scss',
  'gnome-shell-sass/widgets/_network-dialog.scss',
  'gnome-shell-sass/widgets/_notifications.scss',
  'gnome-shell-sass/widgets/_osd.scss',
  'gnome-shell-sass/widgets/_overview.scss',
  'gnome-shell-sass/widgets/_panel.scss',
  'gnome-shell-sass/widgets/_popovers.scss',
  'gnome-shell-sass/widgets/_screen-shield.scss',
  'gnome-shell-sass/widgets/_scrollbars.scss',
  'gnome-shell-sass/widgets/_search-entry.scss',
  'gnome-shell-sass/widgets/_search-results.scss',
  'gnome-shell-sass/widgets/_slider.scss',
  'gnome-shell-sass/widgets/_switcher-popup.scss',
  'gnome-shell-sass/widgets/_switches.scss',
  'gnome-shell-sass/widgets/_tiled-previews.scss',
  'gnome-shell-sass/widgets/_window-picker.scss',
  'gnome-shell-sass/widgets/_workspace-switcher.scss',
  'gnome-shell-sass/widgets/_workspace-thumbnails.scss',
  'gnome-shell-sass/widgets/_third-party.scss'
])

styles = [
  'gnome-shell-high-contrast',
  'gnome-shell'
]

theme_deps = []

sassc = find_program('sassc')
foreach style: styles
  theme_deps += custom_target('style-' + style,
                              input: '@0@.scss'.format(style),
                              output: '@0@.css'.format(style),
                              command: [
                                sassc, '-M', '-t', 'compact', '@INPUT@', '@OUTPUT@'
                              ],
                              install: true,
                              install_dir: install_dir,
                              depend_files: theme_sources)
endforeach

# static files to copy
data_sources = [
  'activities.svg',
  'activities-active.svg',
  'calendar-today.svg',
  'checkbox-focused.svg',
  'checkbox-off-focused.svg',
  'checkbox-off.svg',
  'checkbox.svg',
  'd2p-activities-active.svg',
  'd2p-activities.svg',
  'dash-placeholder.svg',
  'eye-not-looking-symbolic.svg',
  'eye-open-negative-filled-symbolic.svg',
  'keyboard-caps-lock-filled-symbolic.svg',
  'keyboard-enter-symbolic.svg',
  'keyboard-hide-symbolic.svg',
  'keyboard-layout-filled-symbolic.svg',
  'keyboard-shift-filled-symbolic.svg',
  'message-indicator-symbolic.svg',
  'no-events.svg',
  'no-notifications.svg',
  'pointer-double-click-symbolic.svg',
  'pointer-drag-symbolic.svg',
  'pointer-primary-click-symbolic.svg',
  'pointer-secondary-click-symbolic.svg',
  'process-working.svg',
  'running-indicator.svg',
  'toggle-off-dark.svg',
  'toggle-off-hc.svg',
  'toggle-off.svg',
  'toggle-on-dark.svg',
  'toggle-on-hc.svg',
  'toggle-on.svg',
  'transparent.png'
]

# install static data files
install_data(data_sources, install_dir: install_dir)
