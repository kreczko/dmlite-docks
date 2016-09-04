FROM centos:6

MAINTAINER Luke Kreczko <kreczko@cern.ch>

ADD http://repository.egi.eu/sw/production/cas/1/current/repo-files/EGI-trustanchors.repo /etc/yum.repos.d/EGI-trustanchors.repo

#add install certificates ( they will go then in a separate volume)
RUN /usr/bin/yum install -y ca-policy-egi-core fetch-crl epel-release


#install supervisor
RUN yum install -y supervisor

COPY "supervisord.conf" "/etc/supervisor/conf.d/supervisord.conf"

# Start supervisor
CMD ["/usr/bin/supervisord", "-c", "/etc/supervisor/conf.d/supervisord.conf"]