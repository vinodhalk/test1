create or replace 
PROCEDURE        "ADS_AP_GET_AWARD_NUMBER" 
 (l_award_id IN VARCHAR2, my_award_number OUT VARCHAR2)
 IS
 BEGIN
 SELECT award_number
    INTO my_award_number
    FROM gms_awards_all gaa
    WHERE gaa.AWARD_ID     = l_award_id;
 EXCEPTION
 WHEN others THEN
   my_award_number := '6001';
 END;
 