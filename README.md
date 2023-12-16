# از یک تصویر پایه استفاده کنید که از systemd پشتیبانی می کند، به عنوان مثال، اوبونتو
FROM ubuntu:20.04

# بسته های لازم را نصب کنید
به‌روزرسانی apt-get && \
apt-get install -y shellinabox && \
apt-get install -y systemd && \
apt-get clean && \
rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
RUN echo 'root: ریشه' | chpasswd
# درگاه ترمینال مبتنی بر وب را در معرض نمایش قرار دهید
EXPOSE 4200

# شروع shellinabox
 CMD ["/usr/bin/shellinaboxd", "-t", "-s", "/:LOGIN"]کپی 🀄
