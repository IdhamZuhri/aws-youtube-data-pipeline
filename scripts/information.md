Bronze Bucket Name - yt-data-pipeline-bronze-ap-southeast-1-idham
Silver Bucket Name - yt-data-pipeline-silver-ap-southeast-1-idham
Gold Bucket Name -  yt-data-pipeline-gold-ap-southeast-1-idham

Script Bucket - yt-data-pipeline-script-ap-southeast-1-idham

SNS ARN - arn:aws:sns:us-east-1:413545130322:yt-data-pipeline-alerts-dev:fd89ff58-ed34-4419-8d43-806a59321e4f

Glue Bronze - yt_pipeline_bronze_dev
Glue Silver - yt_pipeline_silver_dev
Glue Gold -  yt_pipeline_gold_dev


--bronze_database yt_pipeline_bronze_dev
--bronze_table raw_statistics
--silver_bucket yt-data-pipeline-silver-ap-southeast-1-idham
--silver_database yt_pipeline_silver_dev
--silver_table clean_statistics

--silver_database yt_pipeline_silver_dev
--gold_bucket yt-data-pipeline-gold-ap-southeast-1-idham
--gold_database yt_pipeline_gold_dev
