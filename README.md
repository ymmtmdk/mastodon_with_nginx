# mastodon_with_nginx

git clone https://github.com/tootsuite/mastodon
cd mastodon
git clone https://github.com/ymmtmdk/mastodon_with_nginx
mv mastodon_with_nginx with_nginx
ln -s with_nginx/with_nginx-compose.yml ./
sudo openssl dhparam -out /etc/ssl/certs/dhparam.pem 1024
# lets encrypt
sudo /home/ubuntu/mastodon /home/mastodon
sudo docker-compose -f with_nginx.yml run build
sudo docker-compose -f with_nginx.yml run --rm web rake db:migrate
sudo docker-compose -f with_nginx.yml run --rm web rake assets:precompile
sudo docker-compose -f with_nginx.yml run up
