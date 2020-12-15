FROM public.ecr.aws/bitnami/php-fpm:7.4

ENV PORT=9000
EXPOSE 9000

COPY web/laravel /app
RUN chown -R www-data:www-data /app/storage
RUN chmod -R o+w /app/storage
