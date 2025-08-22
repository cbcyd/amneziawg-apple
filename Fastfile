# fastlane/Fastfile

# IMPORTANT: Change 'com.your-github-username.amneziawg' to a unique prefix.
# Use the same prefix for all three bundle identifiers.
default_platform(:mac)

platform :mac do
  lane :setup_signing do
    app_identifier_base = "com.cbcyd.amneziawg"
    app_identifier_app = "#{app_identifier_base}"
    app_identifier_ext = "#{app_identifier_base}.network-extension"
    app_identifier_helper = "#{app_identifier_base}.login-helper"

    # Register the app identifiers on the developer portal
    produce(
      app_identifier: app_identifier_app,
      app_name: "AmneziaWG (CI)",
      enable_services: {
        app_group: "on"
      }
    )
    produce(
      app_identifier: app_identifier_ext,
      app_name: "AmneziaWG Extension (CI)",
      enable_services: {
        app_group: "on",
        network_extension: "on"
      }
    )
     produce(
      app_identifier: app_identifier_helper,
      app_name: "AmneziaWG Helper (CI)"
    )

    # Generate and download development provisioning profiles
    sigh(
      app_identifier: app_identifier_app,
      development: true,
      force: true
    )
    sigh(
      app_identifier: app_identifier_ext,
      development: true,
      force: true
    )
    sigh(
      app_identifier: app_identifier_helper,
      development: true,
      force: true
    )
  end
end
