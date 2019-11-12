run:
	docker kill db app check || true
	docker rm db app check || true
	docker network rm fitec || true
	docker network create fitec
	##
	docker run --name db \
		--network fitec \
		-e POSTGRES_PASSWORD=amine \
		-e POSTGRES_USER=amine \
		-e POSTGRES_DB=base_de_test \
		-d -it postgres 
	###
	docker run --name app \
		--network fitec \
		-e POSTGRES_PASSWORD=amine \
		-e POSTGRES_USER=amine \
		-e POSTGRES_DB=base_de_test \
		-e POSTGRES_HOST=db \
		-e NEXTCLOUD_ADMIN_USER=root \
		-e NEXTCLOUD_ADMIN_PASSWORD=admin \
		-p 80:80 -d -it nextcloud
	docker run --name check \
		--network fitec \
		-p 8080:8080 -d -it adminer

