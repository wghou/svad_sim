# edited by wghou

INCLUDE_DIRECTORIES(
		${BULLET_PHYSICS_SOURCE_DIR}
		${svad_sim_SOURCE_DIR}/src
        ${svad_sim_SOURCE_DIR}/examples
		${svad_sim_SOURCE_DIR}/examples/ExampleBrowser
        ${svad_sim_SOURCE_DIR}/examples/ThirdPartyLibs/glad
)


SET(SoftDemoGui_SRCS
		main_opengl_single_example.cpp
		../ExampleBrowser/OpenGLGuiHelper.cpp
		../ExampleBrowser/GL_ShapeDrawer.cpp
		../ExampleBrowser/CollisionShape2TriangleMesh.cpp
		../Utils/b3Clock.cpp
		../Utils/b3ResourcePath.cpp
)

SET(StandaloneMain_SRCS
	../DeformableDemo/VolumetricDeformable.cpp
)


LINK_LIBRARIES(
        BulletDynamics BulletCollision LinearMath OpenGLWindow Bullet3Common BulletSoftBody
)

# opengl
LINK_LIBRARIES( ${OPENGL_gl_LIBRARY} ${OPENGL_glu_LIBRARY} )

ADD_EXECUTABLE(StandaloneMain
                ${SoftDemoGui_SRCS}
				${StandaloneMain_SRCS}
)


