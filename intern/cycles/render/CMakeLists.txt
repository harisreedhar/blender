
set(INC
  ..
  ../../glew-mx
)

set(INC_SYS
  ${GLEW_INCLUDE_DIR}
)

set(SRC
  attribute.cpp
  background.cpp
  bake.cpp
  buffers.cpp
  camera.cpp
  colorspace.cpp
  constant_fold.cpp
  coverage.cpp
  denoising.cpp
  film.cpp
  geometry.cpp
  graph.cpp
  hair.cpp
  image.cpp
  integrator.cpp
  jitter.cpp
  light.cpp
  merge.cpp
  mesh.cpp
  mesh_displace.cpp
  mesh_subdivision.cpp
  mesh_volume.cpp
  nodes.cpp
  object.cpp
  osl.cpp
  particles.cpp
  curves.cpp
  scene.cpp
  session.cpp
  shader.cpp
  sobol.cpp
  stats.cpp
  svm.cpp
  tables.cpp
  tile.cpp
)

set(SRC_HEADERS
  attribute.h
  bake.h
  background.h
  buffers.h
  camera.h
  colorspace.h
  constant_fold.h
  coverage.h
  denoising.h
  film.h
  geometry.h
  graph.h
  hair.h
  image.h
  integrator.h
  light.h
  jitter.h
  merge.h
  mesh.h
  nodes.h
  object.h
  osl.h
  particles.h
  curves.h
  scene.h
  session.h
  shader.h
  sobol.h
  stats.h
  svm.h
  tables.h
  tile.h
)

set(LIB
  cycles_bvh
  cycles_device
  cycles_subd
  cycles_util
)

if(WITH_CYCLES_OSL)
  list(APPEND LIB
    cycles_kernel_osl
  )
endif()

include_directories(${INC})
include_directories(SYSTEM ${INC_SYS})

add_definitions(${GL_DEFINITIONS})

cycles_add_library(cycles_render "${LIB}" ${SRC} ${SRC_HEADERS})
