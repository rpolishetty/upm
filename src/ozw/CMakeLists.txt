set (libname "ozw")
set (libdescription "upm module for the OpenZWave library interface")
set (module_src ${libname}.cxx zwNode.cxx ozwinterface.cxx ozwdump.cxx aeotecss6.cxx aeotecsdg2.cxx aeotecdw2e.cxx aeotecdsb09104.cxx tzemt400.cxx)
set (module_hpp ${libname}.hpp ozwinterface.hpp ozwdump.hpp aeotecss6.hpp aeotecsdg2.hpp aeotecdw2e.hpp aeotecdsb09104.hpp tzemt400.hpp)

if (OPENZWAVE_FOUND)
  set (reqlibname "libopenzwave")
  include_directories(${OPENZWAVE_INCLUDE_DIRS})
  upm_module_init()
  upm_target_link_libraries(${libname} ${OPENZWAVE_LIBRARIES})
endif ()
