# Dacon_LG
#### train_data.csv
* col_errtype_i
  * col_errtype_1, ... : 각 user의 i번째 errtype 개수
* all_error : 각 user의 전체 error 개수
* col_week_cluster_i
  * col_week_cluster_-1, ... : 일주일 단위로 나눈 변수로 각 user가 해당 단위동안 발생한 error 개수
    * ~11월 1일 : -1
    * 11월 2일 ~ 11월 8일 : 0
    * ... 12월 2일 : 4
    * 12월 2일~ : 5
* col_fwver_i (dummy)
  * col_fwver_03.11.1141, ... : 해당 버전인지 여부. 만약 해당 버전이라면 1, 아니면 0 
* col_errcode_i 
  * col_errcode_1, ... : 각 user에서 해당 error code가 나온 개수
    * 전체 train user 중 100명 이상 나온 error code만 대상으로 함
* upgrade, downgrade, change_model, change_version, change_all : version, model 변경 관련 변수
  * upgrade : version이 upgrade 되면 1씩 더함
  * downgrade : version이 downgrade 되면 1씩 더함
  * change_model : model이 바뀌면 1씩 더함
  * change_version : version이 바뀌면 1식 더함
  * change_all : version이나 model이 바뀌면 1씩 더함
* col_model_model_i
  * col_model_model_0_model_2, ... : model_0에서 model_2로 변경된 경우 1, 아니면 0
* ok_err_size : 각 user id의 quality 검사시 quality 검사 동안 발생하는 평균 error 개수
* weeknum_size_i
  * weeknum_size_0, ... : 각 user id의 요일에 발생한 quality 검사 횟수
* quality_0_weeknum_1, ... : user 별 각 요일에 발생한 quality i번의 평균값
  * user_id, date 단위로 sum 한 뒤 평균화 함
* err_i_hour_cluster_j
  * err_1_hour_cluster_0, ... : 각 user id의 errtype 1에 대해 해당 단위(0)동안 발생한 개수
    * hour_cluster : 새벽, 주간, 야간으로 시간대를 나눔
      * 0 : 19,20,21,22,23,0,1시
      * 1 : 2,3,4,5,6시
      * 2 : 7,8,9,10,11,12,13,14,15,16,17,18시
* err_i_weeknum_j
  * err_3_weeknum_2, ... : 각 user id의 errtype 2에 대해 각 요일에 발생한 개수
* err_1_week_cluster_0_x
  * err_1_week_cluster_0 : errcode 또는 errtype 1번에 대해 각 요일에 발생한 개수
    * errtype하고 겹치는 경우 해당 이름으로 생성됨
      * 다음 version에서 수정함
