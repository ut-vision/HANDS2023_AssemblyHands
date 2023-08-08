# HANDS2023-AssemblyHands

This repository offers a submission guidance for the [ICCV 2023 HANDS challenge - Task 1](https://sites.google.com/view/hands2023/challenges/task1?authuser=0).

## Test image and metadata
You can find test images and files (including image path, bbox): \
[[test images]](https://drive.google.com/drive/folders/1Vsh4V_7JLyycP8c13_RVPpXhmlQaJhdD?usp=sharing) \
[[test files]](https://drive.google.com/drive/folders/1hqqh5ZnbLdDEbXZS_jv4iAVfkQPguLMA?usp=drive_link) \
Please place the `template/` folder under this directory. \
Note: the image size of `nusar-2021_action_both_9061-c13d_9061_user_id_2021-02-09_143830` is realatively smaller than others due to a headset malfunction that stopped the image export midway.

## Evaluation details
We will evaluate two-hand predictions in world coordinates. 
The data file `assemblyhands_test_ego_data_iccv23.json` defines the input images for testing 
and the frame indices used in evaluation are listed in `template/assemblyhands_test_joint_3d_iccv23_pred_template.json`. \
Note: we filtered out samples that are not suitable for evaluation (e.g., the hand is partially out-of-view). This means the frame indices to be evaluated is a bit fewer than the frames in the test image set.

Before submission, please make sure your results have the entries listed in the template json and leave the prediction blank if hand bbox is not provided in the data file.
Since the headset has multiple cameras, you may have muliple predictions in the same scene.
You can postprocess to merge them (e.g., ensemble) and provide a two-hand pose format for every frame.

## Submission intruction
The script `challenge_submit.py` creates your own prediction file in the json format using the template file.
Please custom the `get_pred(.)` function to register in your results.
By default, the script sets the prediction as zero and saves them to `assemblyhands_test_joint_3d_iccv23_pred.json`.


# References
- [AssemblyHands Toolkit](https://github.com/facebookresearch/assemblyhands-toolkit)
- [ICCV 2023 HANDS Workshop](https://sites.google.com/view/hands2023/home)