# Running the notebook server

## TODO: add input directory volume and output directory volume
```docker run \
	-p 6789:8888 \
	-v $(pwd)/input:/home/jovyan/input \
	-v $(pwd)/output:/home/jovyan/output \
	-it generate_d2vmodel'''
- Go to http://localhost:6789
- Enter token received from terminal in text field
- Open generate_d2vmodel.ipynb
- Run it

