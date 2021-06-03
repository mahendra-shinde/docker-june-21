# Simple Plain Text file 
# Filename must be "Dockerfile" with no extension
# Comments begins with "#"
# Step1 : Choose BASE image
FROM nginx:alpine
RUN apk del curl
# Step2: Copy the files
COPY *.html /usr/share/nginx/html/
