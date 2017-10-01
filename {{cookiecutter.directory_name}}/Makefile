mode = draft
engine = {{cookiecutter.engine}}

ifeq ({{cookiecutter.engine}}, lualatex)
	engine = -l
endif

ifeq ({{cookiecutter.engine}}, xelatex)
	engine = -x
endif
	
all: {{cookiecutter.file_name}}.pdf {{cookiecutter.file_name}}.html

{{cookiecutter.file_name}}.pdf: {{cookiecutter.file_name}}.tex
	{{cookiecutter.engine}} {{cookiecutter.file_name}}.tex

{{cookiecutter.file_name}}.html: {{cookiecutter.file_name}}.tex {{cookiecutter.config}}.cfg
	make4ht -um $(mode) -c {{cookiecutter.config}} $(engine)  {{cookiecutter.file_name}}.tex
