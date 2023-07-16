#Create Bucket
resource "aws_s3_bucket" "cloudgen-three-tier-app" {
  bucket = "cloudgen-three-tier-app"

  tags = {
    Name        = "My bucket"
    Environment = "development"
  }
}

#Enable versioning
resource "aws_s3_bucket_versioning" "cloudgen-three-tier-app" {
  bucket = aws_s3_bucket.cloudgen-three-tier-app.id

  versioning_configuration {
    status = "Enabled"
  }
}

#Block public access to the S3 bucket created above
resource "aws_s3_bucket_public_access_block" "cloudgen-three-tier-app-accessblock" {
  bucket = aws_s3_bucket.cloudgen-three-tier-app.id

  block_public_acls       = true
  block_public_policy     = true
  ignore_public_acls      = true
  restrict_public_buckets = true
}
