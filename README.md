# tropomi_so2_segmentation
Files here include: 

np_training_files -- 500 numpy files containing raw tropomi so2 data (uncropped, unresampled), without unecessary layers just to spead up i/o times.

final_500_training.csv -- csv with vertices describing polygons of manually labeled SO2 plumes for the 500 training files.

SO2_segmentation_satellite_view.ipynb -- python notebook used to train the final model, as well as many test versions. The saved state of this notebook includes the output of all training, as well as some additional cell blocks testing visualization. The saved model from this notebook was called "unet/satview_7kmVCD_HeavyAug_drop0.2_100eps_state=43_LRdecay0.1startingatepoch60" to differentiate it from other models during training. That model will be renamed and saved to "tropomi_so2_segmentation_model", see below.

tropomi_so2_segmentation_model -- The final saved model. Details on training can be found in the file above. To load the model, simply run `model = tf.keras.models.load_model("tropomi_so2_segmentation_model")` with tensorflow imported and with correct pathing. 
