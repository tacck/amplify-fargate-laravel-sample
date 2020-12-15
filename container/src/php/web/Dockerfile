FROM public.ecr.aws/nginx/nginx:1.18

ENV PORT=8080
EXPOSE 8080

COPY default.conf /etc/nginx/conf.d/default.conf
COPY laravel /app
