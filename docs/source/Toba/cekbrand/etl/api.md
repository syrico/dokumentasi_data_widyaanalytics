# API Call

## User

| update_data.py               | api_call.py                    | instagram.py (function) | instagram.py (metrics/fields)   | Schema Instagram                 |
|------------------------------|--------------------------------|-------------------------|---------------------------------|----------------------------------|
| update user static           | user_info_api_call             | get_user_info           | fields = None                   | user                             |
| update user dynamic          | user_info_api_call             | get_user_info           | fields = None                   | user_data                        |
| update user media            | user_medias_api_call           | get_user_medias         | fields = None                   | media                            |
| update user audience city    | user_audience_api_call         | get_user_insights       | metrics = ‘audience_city’       | user_insight_audience_city       |
| update user audience country | user_audience_api_call         | get_user_insights       | metrics = ‘audience_country’    | user_insight_audience_country    |
| update user gender and age   | user_audience_api_call         | get_user_insights       | metrics = ‘audience_gender_age’ | user_insight_audience_gender_age |
| update user audience locale  | user_audience_api_call         | get_user_insights       | metrics = ‘audience_locale’     | user_insight_audience_locale     |
| update user online followers | user_online_followers_api_call | get_user_insights       | metrics = ‘online_followers’    | user_insight_online_follower     |
| update user impression       | user_impression_reach_api_call | get_user_insights       | metrics = ‘impression’          | user_insight_reach               |
| update user reach            | user_impression_reach_api_cal  | get_user_insights       | metrics = ‘reach’               | user_insight_impression          |

## Competitor

| update_data.py      | api_call.py                | update.py (function)  | update.py (metrics/fields) | Schema   Instagram |
|---------------------|----------------------------|-----------------------|----------------------------|--------------------|
| update comp static  | competitor_info_api_call   | discovery_user        | fields = None              | user               |
| update comp dynamic | competitor_info_api_call   | discovery_user        | fields = None              | user_data          |
| update comp media   | competitor_medias_api_call | discovery_user_medias | fields = None              | media              |

## Media Insight


| update_data.py       | api_call.py                  | update.py (function)  | update.py (metrics/fields)                                                                                                                                                                                                                                                                                               | Schema   Instagram |
|----------------------|------------------------------|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|
| update media insight | user_media_insights_api_call | get_media_insights    | image_metric = ['engagement',   'reach', 'impressions', 'saved'] <br />video_metric = ['engagement', 'reach', 'impressions', 'saved',   'video_views'] <br /> album_metric = ['carousel_album_engagement', 'carousel_album_impressions',   'carousel_album_reach',    'carousel_album_saved', 'carousel_album_video_views'] | media_insight      |
| update media comment | user_media_comment_api_call  | get_comments_by_media | fields = None                                                                                                                                                                                                                                                                                                            | media_comments     |
