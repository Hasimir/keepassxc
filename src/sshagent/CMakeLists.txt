if(WITH_XC_SSHAGENT)
    include_directories(${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_BINARY_DIR})

    set(sshagent_SOURCES
        bcrypt_pbkdf.cpp
        blowfish.c
        AgentSettingsPage.cpp
        AgentSettingsWidget.cpp
        BinaryStream.cpp
        KeeAgentSettings.cpp
        OpenSSHKey.cpp
        ASN1Key.cpp
        SSHAgent.cpp
    )

    add_library(sshagent STATIC ${sshagent_SOURCES})
    target_link_libraries(sshagent Qt5::Core Qt5::Widgets Qt5::Network ${GCRYPT_LIBRARIES})
endif()
