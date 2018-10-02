# This makefile is meant to preload KMS configured secrets into kubernetes and then deploy helm
# 2018 Dario Ferrer <dario@mayara.io>
#
# Requirements:
#   * GNU make

CLOUD=gcp
NAME=mayara-loomio

install_secrets: 
	for file in secrets/$(CLOUD)/*.yaml; do sops -d $$file| kubectl apply -f -; done;

install: install_secrets
	helm install --name=$(NAME) .

upgrade: install_secrets
	helm upgrade $(NAME) .
