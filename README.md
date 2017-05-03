# mastodon_with_nginx

```
git clone https://github.com/tootsuite/mastodon
cd mastodon
git clone https://github.com/ymmtmdk/mastodon_with_nginx
mv mastodon_with_nginx with_nginx
ln -s with_nginx/with_nginx-compose.yml ./
sudo openssl dhparam -out /etc/ssl/certs/dhparam.pem 1024
# lets encrypt
sudo ln -s /home/ubuntu/mastodon /home/mastodon
# edit .env.produnction
sudo docker-compose -f with_nginx-compose.yml run build
sudo docker-compose -f with_nginx-compose.yml run --rm web rake db:migrate
sudo docker-compose -f with_nginx-compose.yml run --rm web rake assets:precompile
sudo docker-compose -f with_nginx-compose.yml run up
```
