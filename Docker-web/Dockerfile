FROM nginx
LABEL "Project"="Vprofile"
# Remove the original nginx configuration file
RUN rm -rf /etc/nginx/conf.d/default.conf
# Copy our configuration file into the nginx config directory
COPY nginvproapp.conf /etc/nginx/conf.d/vproapp.conf
