FROM haproxy

RUN apt-get update; apt-get install -y procps; apt-get install -y unzip; apt-get install -y vim; apt-get install -y curl

ENV CT_URL https://releases.hashicorp.com/consul-template/0.11.1/consul-template_0.11.1_linux_amd64.zip

RUN curl -L -o /opt/consul-template.zip $CT_URL
RUN unzip /opt/consul-template.zip -d /opt

CMD /opt/consul-template -consul=192.168.231.145:8500 -template "/usr/local/etc/haproxy/haproxy.tmpl:/usr/local/etc/haproxy/haproxy.cfg:haproxy -f /usr/local/etc/haproxy/haproxy.cfg"
