FILE( GLOB D3XP_HDR *.h )
SET( BUILD_SHARED_LIBS ON )
INCLUDE_DIRECTORIES( )
ADD_DEFINITIONS( -D_D3XP -DCTF -DGAME_DLL -D__WITH_PB__ )

SET( D3XP_CPP
	AF.cpp
	AFEntity.cpp
	Actor.cpp
	BrittleFracture.cpp
	Camera.cpp
	Entity.cpp
	Fx.cpp
	GameEdit.cpp
	Game_local.cpp
	Game_network.cpp
	Grabber.cpp
	IK.cpp
	Item.cpp
	Light.cpp
	Misc.cpp
	Moveable.cpp
	Mover.cpp
	MultiplayerGame.cpp
	Player.cpp
	PlayerIcon.cpp
	PlayerView.cpp
	Projectile.cpp
	Pvs.cpp
	SecurityCamera.cpp
	SmokeParticles.cpp
	Sound.cpp
	Target.cpp
	Trigger.cpp
	Weapon.cpp
	WorldSpawn.cpp
	ai/AAS.cpp
	ai/AAS.h
	ai/AAS_debug.cpp
	ai/AAS_local.h
	ai/AAS_pathing.cpp
	ai/AAS_routing.cpp
	ai/AI.cpp
	ai/AI.h
	ai/AI_Vagary.cpp
	ai/AI_events.cpp
	ai/AI_pathing.cpp
	anim/Anim.cpp
	anim/Anim.h
	anim/Anim_Blend.cpp
	anim/Anim_Import.cpp
	anim/Anim_Testmodel.cpp
	anim/Anim_Testmodel.h
	gamesys/Class.cpp
	gamesys/Class.h
	gamesys/DebugGraph.cpp
	gamesys/DebugGraph.h
	gamesys/Event.cpp
	gamesys/Event.h
	gamesys/NoGameTypeInfo.h
	gamesys/SaveGame.cpp
	gamesys/SaveGame.h
	gamesys/SysCmds.cpp
	gamesys/SysCmds.h
	gamesys/SysCvar.cpp
	gamesys/SysCvar.h
	gamesys/TypeInfo.cpp
	gamesys/TypeInfo.h
	physics/Clip.cpp
	physics/Clip.h
	physics/Force.cpp
	physics/Force.h
	physics/Force_Constant.cpp
	physics/Force_Constant.h
	physics/Force_Drag.cpp
	physics/Force_Drag.h
	physics/Force_Field.cpp
	physics/Force_Field.h
	physics/Force_Grab.cpp
	physics/Force_Grab.h
	physics/Force_Spring.cpp
	physics/Force_Spring.h
	physics/Physics.cpp
	physics/Physics.h
	physics/Physics_AF.cpp
	physics/Physics_AF.h
	physics/Physics_Actor.cpp
	physics/Physics_Actor.h
	physics/Physics_Base.cpp
	physics/Physics_Base.h
	physics/Physics_Monster.cpp
	physics/Physics_Monster.h
	physics/Physics_Parametric.cpp
	physics/Physics_Parametric.h
	physics/Physics_Player.cpp
	physics/Physics_Player.h
	physics/Physics_RigidBody.cpp
	physics/Physics_RigidBody.h
	physics/Physics_Static.cpp
	physics/Physics_Static.h
	physics/Physics_StaticMulti.cpp
	physics/Physics_StaticMulti.h
	physics/Push.cpp
	physics/Push.h
	script/Script_Compiler.cpp
	script/Script_Compiler.h
	script/Script_Interpreter.cpp
	script/Script_Interpreter.h
	script/Script_Program.cpp
	script/Script_Program.h
	script/Script_Thread.cpp
	script/Script_Thread.h
)

SET( SOURCES
	${D3XP_CPP}
	${D3XP_HDR}
)

IF(WIN32)
SET( LIB_OPTIONS
    game.def
)
ENDIF()

ADD_DEFINITIONS( ${CPP_WARNING_OPTIONS} )
ADD_LIBRARY( d3xp ${SOURCES} )
target_link_libraries( d3xp idlib )
set_target_properties( d3xp PROPERTIES PREFIX "")

IF(WIN32)
SET_TARGET_PROPERTIES( d3xp PROPERTIES OUTPUT_NAME "d3xp86" )
ENDIF()

