# Instanced
代码先行：<br>instance.vert: 

	#version 410 core

	//postition和normal为常规顶点属性
	layout(location=0)in vec4 position;
	layout(location=1)in vec4 normal;
	
	//color是per-instance的属性
	layout(location=2)in vec4 color;
	//model_matrix为per-instance的变换矩阵，注意一个mat4占4个连续的location，因此model_matrix占着3,4,5和6
	layout(location=3)in mat4 model_matrix;

instance.cpp
	
	int position_loc = glGetAttribLocation(prog, "position");
	int normal_loc = glGetAttribLocation(prog, "normal");
	int color_loc = glGetAttribLocation(prog, "color");
	int matrix_loc = glGetAttribLocation(prog, "model_matrix);
