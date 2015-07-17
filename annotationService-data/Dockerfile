FROM learninglayers/base
MAINTAINER Sadik Bakiu <bakiu@dbis.rwth-aachen.de>

# add files to data volume 
ADD etc /build/etc

CMD sed -i "s#GENERATE_ID_URL#${GENERATE_ID_URL}#g" /build/etc/i5.las2peer.services.annotations.AnnotationsService.properties && \
	sed -i "s#PASSWORD#${PASSWORD}#g" /build/etc/i5.las2peer.services.annotations.AnnotationsService.properties && \
	sed -i "s#USERNAME#${USERNAME}#g" /build/etc/i5.las2peer.services.annotations.AnnotationsService.properties && \
	sed -i "s#DATABASE#${DATABASE}#g" /build/etc/i5.las2peer.services.annotations.AnnotationsService.properties && \
	sed -i "s#DB_HOST#${HOST}#g" /build/etc/i5.las2peer.services.annotations.AnnotationsService.properties && \
	sed -i "s#DB_PORT#${DB_PORT}#g" /build/etc/i5.las2peer.services.annotations.AnnotationsService.properties && \
	sed -i "s#GRAPHNAME#${GRAPHNAME}#g" /build/etc/i5.las2peer.services.annotations.AnnotationsService.properties && \
	sed -i "s#ANN_CONTEXT#${ANN_CONTEXT}#g" /build/etc/i5.las2peer.services.annotations.AnnotationsService.properties && \
	sed -i "s#PLACETYPE#${PLACETYPE}#g" /build/etc/i5.las2peer.services.annotations.AnnotationsService.properties && \
	sed -i "s#TIMETYPE#${TIMETYPE}#g" /build/etc/i5.las2peer.services.annotations.AnnotationsService.properties && \
	sed -i "s#EPURL#${EPURL}#g" /build/etc/i5.las2peer.services.annotations.AnnotationsService.properties && \
	sed -i "s#PORT#${PORT}#g" /build/etc/i5.las2peer.webConnector.WebConnector.properties

# provide directories etc and log as volumes
VOLUME ["/build/etc/","/build/log/"]