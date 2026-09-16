# Imagen mínima para servir el frontend estático
FROM nginx:alpine

# Reemplaza la configuración por defecto
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Copia los archivos del sitio
COPY index.html /usr/share/nginx/html/
COPY styles.css /usr/share/nginx/html/

EXPOSE 80

HEALTHCHECK --interval=30s --timeout=3s \
  CMD wget -q --spider http://localhost/ || exit 1

CMD ["nginx", "-g", "daemon off;"]
