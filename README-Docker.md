docker build -t esrgan .

docker tag esrgan bmaltais/esrgan

docker push bmaltais/esrgan

docker run --rm -it -v ~/images:/code/esrgan/images esrgan /bin/bash
