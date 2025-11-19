FROM nginx:alpine

# Kustutame Nginxi vaikimisi HTML-failid
RUN rm -rf /usr/share/nginx/html/*

# Kopeerime sinu rakenduse
COPY index.html /usr/share/nginx/html/

# Konteiner kuulab pordil 80
EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
