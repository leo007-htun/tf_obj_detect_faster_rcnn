tf_obj_detect_faster_rcnn
RUN manually ===>
    ~simply create new directory and pull this repo

    ~Note that in saved_model/1/variables/ ==> we need to add the model's appropriate logged variables

    ~To run the TF-SErving, you must have already installed docker and TF-Serving image

    ~ After that bind the ports: and docker run that container by this cmd:

        sudo docker run --gpus all -p 8500:8500 --name od --mount type=bind,source=/home/...USR_DIR.../tf_obj_detect_faster_rcnn/saved_model,target=/models/od -e MODEL_NAME=od -t tensorflow/serving:latest-gpu

    ~ at last simply run 'app.py' and upload the images, TF-serving will inference and give back the results

        python app.py

    ~ saved_model can be replaced with any pre-trained model. try using different models e.g "SSD", "RESNET" but provide according variables

    ~ Download faster-rcnn-resnet101_brid_detection_model here (includes saved_model and variables) ==> https://drive.google.com/drive/folders/1vUvF9jUEtDo8usxaifAxthUMp1mSxLmT?usp=share_link
    -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
 RUN docker compose ===========>
  run --build to build docker compose
    sudo docker compose up --build
    
  run docker compose up to create container images and up-running, if you have already run "  sudo docker compose up --build  ", you can neglect the below cmd:
    sudo docker compose up
   
  stop and remove container images:
    sudo docker compose down
    