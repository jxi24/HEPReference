add_library(HEPReference SHARED
    Reference.cc
    Library.cc
)
target_link_libraries(HEPReference PRIVATE project_options project_warnings
                                   PUBLIC fmt::fmt yaml::cpp json::json)

add_library(HEPRequest SHARED
    ArxivRequest.cc
)
target_link_libraries(HEPRequest PRIVATE project_options project_warnings
                                 PUBLIC fmt::fmt yaml::cpp json::json cpr spdlog::spdlog
                                        pugixml)

add_executable(main cpr.cc)
target_link_libraries(main PRIVATE project_options project_warnings
                           PUBLIC fmt::fmt yaml::cpp json::json cpr spdlog::spdlog
                                  range-v3)
